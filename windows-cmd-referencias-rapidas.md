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
- `color` — Altera cores do texto e fundo.  
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

---