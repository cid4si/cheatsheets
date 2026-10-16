# ffmpeg

## Extrair o primeiro quadro do vídeo

```bash
ffmpeg -i input.mp4 -frames:v 1 output.jpg

# comando em .zshrc (ex: extract_1st_frame video_name.mp4)
extract_1st_frame() { ffmpeg -i "$1" -frames:v 1 "${1%.*}.jpg"; }
```

## Remover som do vídeo

```bash
ffmpeg -i input.mp4 -c:v copy -an output.mp4
```

Remova o som de todos os vídeos `.mp4` em uma pasta e sobrescreva os arquivos (cuidado):

```bash
for f in *.mp4; do ffmpeg -i "$f" -c:v copy -an "temp_$f" && mv "temp_$f" "$f"; done
```

## Adicionar automaticamente um quadro preto no início de cada vídeo mp4 em uma pasta

**Nota:** Certifique-se de fazer backup da sua pasta primeiro.

```bash
for f in *.mp4; do 
  ffmpeg -i "$f" -filter_complex "[0:v]tpad=start_duration=0.033:color=black" -map "0:a?" -c:a copy -y "temp.mp4" && mv "temp.mp4" "$f"
done
```

## Comprimir imagens

Comprima todas as imagens na pasta atual:

```bash
for file in *.jpg *.jpeg *.png; do ffmpeg -i "$file" -q:v 10 -y "${file%.*}_temp.${file##*.}" && mv "${file%.*}_temp.${file##*.}" "$file"; done
```

## Comprimir e reduzir o tamanho do vídeo

### Comprimir e redimensionar vídeo para 480p

```bash
ffmpeg -i file_name.mp4 -vf scale=-2:480 -c:v libx264 -preset medium -crf 23 -c:a aac -b:a 128k -movflags +faststart file_name_compressed.mp4
```

### Comprimir e redimensionar todos os vídeos da pasta atual para 480p

```bash
for file in *.{mp4,mov,avi,mkv,m4v}; do
  [ -f "$file" ] || continue
  ffmpeg -i "$file" -vf "scale=-2:480" -c:v libx264 -crf 28 -preset slow -c:a aac -b:a 96k "480p_${file%.*}.mp4"
done
```

### Criar um comando útil para comprimir vídeos

Adicione ao `.zshrc` ou `.bashrc`:

```bash
fix_video() {
    local replace=false
    local input=""
    local threads="6"

    # Parse arguments
    while [[ $# -gt 0 ]]; do
        case $1 in
            --replace)
                replace=true
                shift
                ;;
            --threads)
                if [[ -n "$2" && "$2" =~ ^[0-9]+$ ]]; then
                    threads="$2"
                    shift 2
                else
                    echo "Error: --threads requires a numeric value"
                    return 1
                fi
                ;;
            *)
                if [[ -z "$input" ]]; then
                    input="$1"
                else
                    echo "Error: Multiple input files specified"
                    return 1
                fi
                shift
                ;;
        esac
    done

    if [[ -z "$input" ]]; then
        echo "Usage: fix_video [--replace] [--threads N] <filename.ext>"
        return 1
    fi

    local basename="${input%.*}"
    local output_file
    local ffmpeg_cmd="ffmpeg -i \"$input\" -threads $threads -c:v libx264 -c:a aac -map_metadata 0"

    if [[ "$replace" == true ]]; then
        # Create temporary file first, then replace original
        output_file="${basename}_temp.mp4"
        eval "$ffmpeg_cmd \"$output_file\""

        if [[ $? -eq 0 ]]; then
            # Preserve original file's creation date
            touch -r "$input" "$output_file"
            mv "$output_file" "$input"
            echo "Video fixed and replaced: $input"
        else
            rm -f "$output_file"
            echo "Error: Failed to process video"
            return 1
        fi
    else
        # Create new file with fixed_ prefix
        output_file="fixed_${basename}.mp4"
        eval "$ffmpeg_cmd \"$output_file\""

        if [[ $? -eq 0 ]]; then
            # Preserve original file's creation date
            touch -r "$input" "$output_file"
            echo "Video fixed: $output_file"
        else
            echo "Error: Failed to process video"
            return 1
        fi
    fi
}
```

**Uso:** `fix_video [--replace] [--threads N] <filename.ext>`

### Processar todos os vídeos em uma pasta

```bash
fix_all_videos() {
    local replace=false
    local target_folder="."
    local threads="6"
    local processed_count=0
    local error_count=0

    # Parse arguments
    while [[ $# -gt 0 ]]; do
        case $1 in
            --replace)
                replace=true
                shift
                ;;
            --threads)
                if [[ -n "$2" && "$2" =~ ^[0-9]+$ ]]; then
                    threads="$2"
                    shift 2
                else
                    echo "Error: --threads requires a numeric value"
                    return 1
                fi
                ;;
            *)
                if [[ -z "$target_folder" || "$target_folder" == "." ]]; then
                    target_folder="$1"
                else
                    echo "Error: Multiple target folders specified"
                    return 1
                fi
                shift
                ;;
        esac
    done

    # Check if target folder exists
    if [[ ! -d "$target_folder" ]]; then
        echo "Error: Folder '$target_folder' does not exist"
        return 1
    fi

    # Define common video extensions
    local extensions=("mp4" "MP4" "mov" "MOV" "avi" "AVI" "mkv" "MKV" "webm" "WEBM" "flv" "FLV" "wmv" "WMV" "m4v" "M4V")

    echo "Searching for videos in: $target_folder"
    echo "Mode: $([ "$replace" == true ] && echo "Replace original files" || echo "Create new files with 'fixed_' prefix")"
    echo "Threads: $threads"
    echo "----------------------------------------"

    # Find and process all video files
    for ext in "${extensions[@]}"; do
        while IFS= read -r -d '' file; do
            echo "Processing: $(basename "$file")"

            # Call fix_video function for each file
            if [[ "$replace" == true ]]; then
                fix_video --replace --threads "$threads" "$file"
            else
                fix_video --threads "$threads" "$file"
            fi

            if [[ $? -eq 0 ]]; then
                ((processed_count++))
                echo "Success: $(basename "$file")"
            else
                ((error_count++))
                echo "Failed: $(basename "$file")"
            fi
            echo ""
        done < <(find "$target_folder" -maxdepth 1 -name "*.${ext}" -type f -print0 2>/dev/null)
    done

    echo "----------------------------------------"
    echo "Processing complete!"
    echo "Successfully processed: $processed_count videos"
    if [[ $error_count -gt 0 ]]; then
        echo "Failed: $error_count videos"
    fi
}
```

**Uso:** `fix_all_videos [--replace] [--threads N] [folder]` — Use `.` para a pasta atual.

## Mesclar vídeos

Junte todos os arquivos de vídeo nomeados `a_1.mp4`, `a_2.mp4`, etc. em um único arquivo em ordem:

```bash
ffmpeg -f concat -safe 0 -i <(for i in {1..2}; do echo "file '$(pwd)/a_$i.mp4'"; done) -c:v libx264 -preset fast -crf 23 -c:a aac a.mp4
```

### Alias para mesclar e silenciar vídeos

Adicione ao `.zshrc` ou `.bashrc`:

```bash
alias merge_video='_merge_video() { 
  local prefix=$1
  local last=$2
  local concat_file=$(mktemp)
  
  for i in {1..$last}; do
    echo "file '\''$(pwd)/${prefix}_${i}.mp4'\''" >> $concat_file
  done
  
  ffmpeg -f concat -safe 0 -i $concat_file -an -c copy "${prefix}_merged.mp4"
  rm $concat_file
}; _merge_video'
```

**Uso:** `merge_video a 5`

## Dividir vídeos

Divida um vídeo em segmentos de 200 ms cada:

```bash
ffmpeg -i input.mp4 -c copy -map 0 -segment_time 200 -f segment output_%03d.mp4
```

## Conversor

Converter `.m3u8` (vídeo em streaming) para `.mp4`:

```bash
ffmpeg -i "$1" -c copy -bsf:a aac_adtstoasc "${1%.m3u8}.mp4"
```