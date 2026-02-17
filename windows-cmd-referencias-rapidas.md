# Comandos CMD para consulta rápida

## Básico
- `command1 | command2` — Encadeia a saída de um comando na entrada de outro.  
- `comando /?` — Mostra ajuda sobre o comando.  
- `clip` — Copia a saída para a área de transferência.  
- `exit` — Encerra o prompt de comando.  
- `cls` — Limpa a tela.  
- `hostname` — Exibe o nome do computador.  
- `@echo off` — Oculta a exibição dos comandos na execução de scripts.  
- `echo` — Exibe uma mensagem ou variável.  
- `help` — Lista comandos disponíveis.  

### Outros úteis
- `pause` — Pausa a execução, aguardando o usuário pressionar uma tecla.  
- `set` — Exibe e define variáveis de ambiente.  

---

## Teclas de atalho
- ↑ e ↓ — Percorrem comandos já utilizados.  
- `Esc` — Limpa a linha atual.  
- `F7` — Mostra histórico de comandos em forma de menu.  
- `Alt + F7` — Limpa o histórico.  
- `F9` — Pesquisa comando no histórico.  
- `Alt + F10` — Limpa macros do `doskey`.  
- `Tab` — Autocompleta nomes de arquivos e pastas.  

---

## Manipulando o prompt
- `echo` — Exibe mensagens na tela.  
- `vol` — Mostra nome e número de série do volume.  
- `ver` — Exibe a versão do Windows.  
- `winver` — Abre janela gráfica com detalhes da versão.  
- `date /t` — Exibe a data atual sem solicitar alteração.  
- `time /t` — Exibe a hora atual sem solicitar alteração.  
- `start` — Abre um programa, arquivo ou pasta em nova janela.  
- `doskey` — Cria macros e alias de comandos.  
- `systeminfo` — Mostra informações detalhadas do sistema.  

---

## Aparência
- `title` — Define o título da janela.  
- `color` — Altera cores do ```bato e fundo.  
- `mode` — Ajusta tamanho ou modo de exibição da tela (linhas, colunas).  
- `prompt` — Define o formato do prompt de comando.  

---

## Diretórios e arquivos
- `dir` — Lista conteúdo do diretório.  
- `cd` / `chdir` — Muda o diretório atual.  
  - `cd ..` — Volta um nível.  
  - `cd \` — Vai para a raiz.  
- `md` / `mkdir` — Cria diretório.  
- `rd` / `rmdir` — Remove diretório vazio.  
- `copy` — Copia arquivos.  
- `ren` / `rename` — Renomeia arquivo.  
- `move` — Move arquivos.  
- `del` / `erase` — Apaga arquivos.  
- `replace` — Substitui arquivos existentes.  
- `attrib` — Exibe ou altera atributos (oculto, somente leitura, sistema).  
- `path` — Mostra ou altera o caminho de pesquisa dos executáveis.  
- `tree` — Exibe estrutura de diretórios de forma hierárquica.  

---

## Rede
- `ipconfig /all` — Informações detalhadas de rede.  
- `ping endereço` — Testa conectividade com um host.  
- `netstat` — Exibe conexões ativas e portas abertas.  
- `ipconfig /displaydns` — Mostra cache DNS local.  
- `ipconfig /flushdns` — Limpa cache DNS.  
- `nslookup` — Consulta servidores DNS.  
- `arp -a` — Exibe tabela ARP (IP ↔ MAC).  
- `tracert endereço` — Mostra o caminho até um host na rede.  
- `netsh wlan export profile key=clear folder="C:\rede_perfil"` — Exporta perfis Wi‑Fi salvos em XML.  
- `netsh wlan connect name=SSID` — Conecta-se a uma rede Wi‑Fi pelo nome do perfil.  
- `net use` — Conecta, remove ou mostra conexões de rede compartilhadas.  
- `net view` — Lista computadores na rede local.  

---

## Disco e sistema
- `chkdsk` — Verifica e corrige erros no disco.  
- `sfc /scannow` — Verifica e repara arquivos protegidos do sistema.  
- `diskpart` — Gerencia discos e partições (uso avançado).  
- `format` — Formata um disco.  
- `wmic logicaldisk get name,size,freespace` — Mostra informações dos discos.  

---

## Processos e tarefas
- `tasklist` — Lista processos em execução.  
- `taskkill /IM nome.exe /F` — Encerra processo pelo nome.  
- `shutdown /s /t 0` — Desliga o computador imediatamente.  
- `shutdown /r /t 0` — Reinicia imediatamente.  

---

## Estrutura e fluxo de scripts

### Rótulos e GOTO
- `:label` — Define um marcador no script.  
- `goto label` — Redireciona execução para o marcador.  

Exemplo simples:
```bat
@echo off
echo Inicio
goto menu

:opcao1
echo Você escolheu a opção 1
goto fim

:menu
echo 1 - Opcao 1
echo 2 - Sair
set /p OP=Escolha: 

if "%OP%"=="1" goto opcao1
if "%OP%"=="2" goto fim
goto menu

:fim
echo Fim do script.
pause 
```


### CHOICE (menus)

- choice /C opcoes /M "mensagem" — Cria menus interativos com escolhas.

Exemplo:

```bat
@echo off
echo Menu principal
choice /C 123 /M "Escolha: 1=Backup, 2=Log, 3=Sair"

if errorlevel 3 goto sair
if errorlevel 2 goto log
if errorlevel 1 goto backup

:backup
echo Executando backup...
goto fim

:log
echo Gerando log...
goto fim

:sair
echo Saindo...

:fim
pause

``
`## IF / ELSE (condicionais)

Sintaxe básica

```bat
IF [NOT] ERRORLEVEL numero comando
IF [NOT] string1==string2 comando
IF [NOT] EXIST arquivo comando
``

`## Extensões com operadores

```bat
IF [/I] string1 op string2 comando
```

Operadores:

_ EQU – Igual

- NEQ – Diferente

- LSS – Menor que

- LEQ – Menor ou igual

- GTR – Maior que

- GEQ – Maior ou igual

Exemplo com arquivo

```bat
IF EXIST dados.txt (
    echo Arquivo encontrado.
) ELSE (
    echo Arquivo nao encontrado.
)
```

Exemplo com %ERRORLEVEL%

```bat
@echo off
ping 8.8.8.8 -n 1 >nul

IF %ERRORLEVEL% EQU 0 (
    echo Conexao OK.
) ELSE (
    echo Falha na conexao.
)
```

## FOR (loops)

Loop em lista fixa

```bat
@echo off
for %%i in (1 2 3 4 5) do (
    echo Numero: %%i
)

```
Loop em intervalo numérico

```bat
@echo off
rem (inicio,passo,fim)
for /L %%i in (1,1,10) do (
    echo Contador: %%i
)
```

Loop em arquivos do diretório

```bat
@echo off
for %%f in (*.txt) do (
    echo Arquivo: %%f
)
```

Loop recursivo em subpastas

```bat
@echo off
for /R %%f in (*.log) do (
    echo Log encontrado: %%f
)
```

Loop em linhas de um arquivo

```bat
@echo off
for /F "delims=" %%L in (lista.txt) do (
    echo Linha: %%L
)
```
Loop sobre saída de comando

```bat
@echo off
for /F "tokens=1,2" %%A in ('ipconfig ^| findstr /R "IPv4"') do (
    echo %%A %%B
)
```

Logs em batch

Redirecionamento básico
- > — Sobrescreve arquivo de log.

- >> — Acrescenta ao final.

- 2> — Redireciona erro.

- 2>&1 — Junta saída normal e erros no mesmo arquivo.

Exemplo simples:

```bat
@echo off
comando.exe > log.txt 2>&1
```

Log com timestamp

```bat
@echo off
set "LOGFILE=C:\logs\script.log"

echo %DATE% %TIME% - Script iniciado.>>"%LOGFILE%"
echo Fazendo alguma tarefa...>>"%LOGFILE%"
echo %DATE% %TIME% - Script finalizado.>>"%LOGFILE%"
```

Função de log reutilizável

```bat
@echo off
setlocal
set "LOGFILE=C:\logs\backup.log"

call :LOG "Inicio do script"

rem ... comandos aqui ...

call :LOG "Fim do script"
goto :EOF

:LOG
echo %DATE% %TIME% - %~1>>"%LOGFILE%"
goto :EOF
```

## Exemplo de script de backup simples

Backup de uma pasta de documentos para outro disco, com log.

```bat
@echo off
setlocal

set "SOURCE=C:\Users\Usuario\Documents"
set "DEST=D:\Backups\Documents"
set "LOG=D:\Backups\backup_log.txt"

echo ==================================================>>"%LOG%"
echo %DATE% %TIME% - Inicio do backup.>>"%LOG%"

if not exist "%SOURCE%" (
    echo %DATE% %TIME% - ERRO: origem nao existe: %SOURCE%>>"%LOG%"
    goto :FIM
)

if not exist "%DEST%" (
    mkdir "%DEST%"
)

echo Iniciando robocopy...
robocopy "%SOURCE%" "%DEST%" /MIR /R:1 /W:5 >>"%LOG%" 2>&1

echo %DATE% %TIME% - Backup finalizado.>>"%LOG%"

:FIM
echo Backup concluido. Veja o log em "%LOG%".
pause
endlocal
```

## Telnet

Usado para acesso remoto a serviços que escutam na porta Telnet (padrão 23). Considerado inseguro para conexões pela internet, pois transmite dados em texto claro. Usar apenas em redes confiáveis ou para testes locais.

- É necessário habilitar Telnet Client no cliente e Telnet Server no servidor (ou outro serviço compatível).

Conexão básica:

```bat
telnet IP porta
```

Depois, autenticar com usuário e senha conforme o serviço remoto.

---
