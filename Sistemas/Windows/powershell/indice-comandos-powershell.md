# Índice A-Z de Comandos do PowerShell

## Sumário

- [Introdução](#introducao)
- [Conceitos Fundamentais](#conceitos-fundamentais)
- [Comandos por Categoria](#comandos-por-categoria)
- [Comandos em Ordem Alfabética](#comandos-em-ordem-alfabetica)
- [Dicas de Utilização](#dicas-de-utilizacao)
- [Links Úteis](#links-uteis)

---

## Introdução

Este documento oferece uma referência completa dos comandos (cmdlets) disponíveis no PowerShell. Os comandos seguem a convenção de nomenclatura "Verbo-Substantivo" e estão organizados tanto por categoria quanto em ordem alfabética para facilitar a consulta.

---

## Conceitos Fundamentais

O PowerShell é uma linguagem de script baseada em objetos, o que significa que ao contrário de outros shells que retornam texto, o PowerShell trabalha com objetos .NET. Alguns conceitos importantes incluem:

- **Cmdlets**: Comandos leves do PowerShell (Verbo-Substantivo)
- **Pipes (|)**: Passam objetos (não apenas texto) entre comandos
- **Aliases**: Atalhos para comandos mais longos
- **Provedores**: Acessam diferentes tipos de armazenamento de dados
- **Scripts**: Arquivos .ps1 que contêm comandos PowerShell

---

## Comandos por Categoria

### Manipulação de Arquivo e Diretório

- **Get-ChildItem** - Listar arquivos e diretórios (alias: dir, ls)
- **Set-Location** - Alterar diretório atual (alias: cd)
- **Get-Content** - Ler conteúdo de arquivos (alias: cat, type)
- **Copy-Item** - Copiar arquivos e diretórios (alias: copy, cp)
- **Move-Item** - Mover ou renomear arquivos (alias: move, mv)
- **Remove-Item** - Excluir arquivos ou diretórios (alias: del, rm)
- **New-Item** - Criar novos itens (arquivo, diretório, etc.)
- **Set-Content** - Escrever conteúdo em arquivo (substituindo)
- **Add-Content** - Adicionar conteúdo a arquivo (anexando)

### Gerenciamento de Sistema

- **Get-Process** - Listar processos em execução (alias: ps)
- **Stop-Process** - Encerrar processos (alias: kill)
- **Get-Service** - Listar serviços
- **Start-Service** - Iniciar serviço
- **Stop-Service** - Parar serviço
- **Restart-Service** - Reiniciar serviço
- **Get-EventLog** - Visualizar logs de eventos
- **Get-WmiObject** - Obter informações WMI

### Rede

- **Test-Connection** - Testar conexão de rede (ping)
- **Invoke-WebRequest** - Fazer solicitações web (alias: curl, wget)
- **Test-NetConnection** - Testar conectividade de rede
- **Get-NetAdapter** - Listar adaptadores de rede
- **Get-NetIPAddress** - Mostrar endereços IP

### Utilitários e Formatação

- **Get-Help** - Exibir ajuda sobre comandos (alias: help)
- **Get-Command** - Listar todos os comandos disponíveis
- **Format-List** - Formatar saída como lista (alias: fl)
- **Format-Table** - Formatar saída como tabela (alias: ft)
- **Select-Object** - Selecionar propriedades específicas (alias: select)
- **Where-Object** - Filtrar objetos (alias: where)
- **Sort-Object** - Ordenar objetos (alias: sort)
- **Measure-Object** - Calcular propriedades numéricas (alias: measure)

---

## Comandos em Ordem Alfabética

### A

- **Add-AppxPackage** - Adicionar pacote de aplicativo Windows
- **Add-Content** - Adicionar conteúdo a arquivos
- **Add-History** - Adicionar entradas ao histórico de sessão
- **Add-Member** - Adicionar membro a objeto
- **Add-PSSnapin** - Adicionar snap-ins PowerShell ao shell
- **Add-Type** - Adicionar classe .NET ao PowerShell

### B

- **Backup-GPO** - Fazer backup de Objetos de Política de Grupo
- **Begin** - Parte de bloco de script
- **Break** - Sair de loop ou switch

### C

- **Clear-Content** - Limpar conteúdo de arquivo sem excluí-lo
- **Clear-History** - Limpar histórico de comandos
- **Clear-Host** - Limpar tela (alias: cls, clear)
- **Clear-Item** - Limpar valor de item
- **Clear-Variable** - Limpar valor de variável
- **Compare-Object** - Comparar dois conjuntos de objetos (alias: diff)
- **Complete-Transaction** - Completar transação
- **Compress-Archive** - Comprimir arquivos em arquivo ZIP
- **ConvertFrom-Csv** - Converter string CSV em objeto
- **ConvertFrom-Json** - Converter string JSON em objeto
- **ConvertTo-Csv** - Converter objeto em string CSV
- **ConvertTo-Html** - Converter objeto em HTML
- **ConvertTo-Json** - Converter objeto em string JSON
- **ConvertTo-Xml** - Converter objeto em XML
- **Copy-Item** - Copiar arquivos e diretórios (alias: copy, cp)

### D

- **Debug-Process** - Depurar processo
- **Disable-PSBreakpoint** - Desabilitar breakpoint
- **Disable-PSRemoting** - Desabilitar acesso remoto via PowerShell
- **Disconnect-PSSession** - Desconectar sessão PowerShell

### E

- **Enable-PSBreakpoint** - Habilitar breakpoint
- **Enable-PSRemoting** - Habilitar acesso remoto via PowerShell
- **Enter-PSSession** - Iniciar sessão PowerShell interativa
- **Exit-PSSession** - Sair de sessão PowerShell remota
- **Export-Alias** - Exportar aliases para arquivo
- **Export-Csv** - Exportar objetos para arquivo CSV
- **Export-PSSession** - Exportar comandos de sessão
- **Expand-Archive** - Extrair arquivos de arquivo ZIP

### F

- **Filter** - Filtrar dados em pipeline
- **ForEach-Object** - Processar cada item em pipeline (alias: foreach, %)
- **Format-Custom** - Formatar saída usando visualização customizada
- **Format-List** - Formatar saída como lista (alias: fl)
- **Format-Table** - Formatar saída como tabela (alias: ft)
- **Format-Wide** - Formatar saída em colunas (alias: fw)

### G

- **Get-Acl** - Obter permissões de segurança (ACL)
- **Get-Alias** - Listar aliases definidos
- **Get-AuthenticodeSignature** - Verificar assinatura digital
- **Get-ChildItem** - Listar arquivos e diretórios (alias: dir, ls)
- **Get-Command** - Listar todos os comandos disponíveis
- **Get-ComputerInfo** - Obter informações detalhadas do sistema
- **Get-Content** - Ler conteúdo de arquivos (alias: cat, type)
- **Get-Credential** - Solicitar credenciais do usuário
- **Get-Culture** - Obter informações de cultura atual
- **Get-Date** - Obter data e hora atual
- **Get-Event** - Obter eventos na fila de eventos
- **Get-EventLog** - Obter entradas do log de eventos
- **Get-ExecutionPolicy** - Mostrar política de execução atual
- **Get-Help** - Exibir ajuda sobre comandos (alias: help, man)
- **Get-History** - Obter histórico de comandos (alias: history)
- **Get-Host** - Obter informações do host PowerShell
- **Get-Item** - Obter item em localização especificada
- **Get-ItemProperty** - Obter propriedades de item
- **Get-Job** - Obter jobs em segundo plano
- **Get-Location** - Mostrar diretório atual (alias: pwd)
- **Get-Member** - Listar propriedades e métodos de objeto (alias: gm)
- **Get-Module** - Listar módulos carregados
- **Get-Process** - Listar processos em execução (alias: ps)
- **Get-PSBreakpoint** - Listar breakpoints definidos
- **Get-PSProvider** - Listar provedores PS disponíveis
- **Get-PSSession** - Obter sessões PowerShell
- **Get-Service** - Listar serviços
- **Get-TimeZone** - Obter fuso horário atual
- **Get-Transaction** - Obter transação ativa
- **Get-UICulture** - Obter cultura de UI atual
- **Get-Unique** - Mostrar itens únicos de uma lista
- **Get-Variable** - Obter variável PowerShell
- **Get-WmiObject** - Obter informações WMI (alias: gwmi)

### H

- **Help** - Exibir ajuda sobre comandos (alias para Get-Help)

### I

- **Import-Alias** - Importar aliases de arquivo
- **Import-Csv** - Importar arquivo CSV como objetos
- **Import-Module** - Importar módulo na sessão atual
- **Import-PSSession** - Importar comandos de outra sessão
- **Invoke-Command** - Executar comandos em computadores locais ou remotos
- **Invoke-Expression** - Executar string como comando (alias: iex)
- **Invoke-History** - Executar comandos do histórico
- **Invoke-Item** - Executar item padrão (alias: ii)
- **Invoke-RestMethod** - Fazer solicitações REST
- **Invoke-WebRequest** - Fazer solicitações web (alias: curl, wget)

### J

- **Join-Path** - Combinar caminhos de arquivo
- **Join-String** - Juntar strings de entrada

### L

- **Limit-EventLog** - Limitar tamanho de log de eventos
- **Login-PSSession** - Logar em sessão PowerShell

### M

- **Measure-Command** - Medir tempo de execução de script/comando
- **Measure-Object** - Calcular propriedades numéricas (alias: measure)
- **Move-Item** - Mover ou renomear arquivos (alias: move, mv)
- **Move-ItemProperty** - Mover propriedade de um item para outro

### N

- **New-Alias** - Criar novo alias
- **New-Event** - Criar novo evento
- **New-EventLog** - Criar novo log de eventos
- **New-Item** - Criar novos itens (arquivo, diretório, etc.)
- **New-Module** - Criar novo módulo na memória
- **New-Object** - Criar instância de objeto .NET (alias: new)
- **New-PSDrive** - Criar novo drive mapeado
- **New-PSSession** - Criar nova sessão PowerShell
- **New-PSSessionOption** - Criar opções para sessão
- **New-Service** - Criar novo serviço Windows
- **New-TimeSpan** - Criar objeto TimeSpan
- **New-Variable** - Criar nova variável

### O

- **Out-Default** - Enviar saída para manipulador padrão
- **Out-File** - Enviar saída para arquivo
- **Out-GridView** - Exibir saída em janela interativa
- **Out-Host** - Enviar saída para host
- **Out-Null** - Eliminar saída (descartar saída)
- **Out-Printer** - Enviar saída para impressora
- **Out-String** - Enviar objetos para string

### P

- **Pop-Location** - Mudar para último local salvo (alias: popd)
- **Push-Location** - Salvar local atual e mover para novo (alias: pushd)

### R

- **Read-Host** - Ler linha de entrada do console
- **Receive-Job** - Obter resultados de job em segundo plano
- **Register-EngineEvent** - Registrar evento de motor
- **Register-ObjectEvent** - Registrar evento de objeto
- **Register-PSSessionConfiguration** - Criar configuração de sessão
- **Remove-Item** - Excluir arquivos ou diretórios (alias: del, rm)
- **Remove-ItemProperty** - Remover propriedade de item
- **Remove-Job** - Remover job em segundo plano
- **Remove-Module** - Remover módulo da sessão atual
- **Remove-PSBreakpoint** - Remover breakpoint
- **Remove-PSDrive** - Remover drive mapeado
- **Remove-PSSession** - Remover sessão PowerShell
- **Remove-Variable** - Remover variável
- **Rename-Item** - Renomear item (arquivo, diretório, etc.)
- **Reset-ComputerMachinePassword** - Redefinir senha de máquina
- **Resolve-Path** - Resolver caminho com caracteres curinga
- **Restart-Computer** - Reiniciar computador
- **Restart-Service** - Reiniciar serviço
- **Restore-Computer** - Restaurar sistema a partir de backup

### S

- **Select-Object** - Selecionar propriedades específicas (alias: select)
- **Select-String** - Buscar strings em arquivos/texto (alias: sls)
- **Send-MailMessage** - Enviar e-mail
- **Set-Acl** - Definir permissões de segurança (ACL)
- **Set-Alias** - Criar ou modificar alias
- **Set-AuthenticodeSignature** - Assinar script ou arquivo
- **Set-Content** - Escrever conteúdo em arquivo (substituindo)
- **Set-Date** - Definir data e hora do sistema
- **Set-ExecutionPolicy** - Definir política de execução
- **Set-Item** - Alterar valor de item
- **Set-ItemProperty** - Definir propriedade de item
- **Set-Location** - Alterar diretório atual (alias: cd)
- **Set-PSBreakpoint** - Definir breakpoint em script
- **Set-Service** - Definir propriedades de serviço
- **Set-StrictMode** - Habilitar modo estrito
- **Set-Variable** - Definir variável PowerShell
- **Set-WmiInstance** - Modificar instância WMI
- **Sort-Object** - Ordenar objetos (alias: sort)
- **Split-Path** - Retornar parte específica de caminho
- **Start-Job** - Iniciar job em segundo plano
- **Start-Process** - Iniciar processo (alias: start)
- **Start-Service** - Iniciar serviço
- **Start-Sleep** - Pausar execução de script (alias: sleep)
- **Start-Transaction** - Iniciar transação
- **Start-Transcript** - Iniciar gravação de sessão
- **Stop-Computer** - Desligar computador
- **Stop-Job** - Parar job em segundo plano
- **Stop-Process** - Encerrar processos (alias: kill)
- **Stop-Service** - Parar serviço
- **Stop-Transcript** - Parar gravação de sessão
- **Suspend-Service** - Suspender serviço

### T

- **Tee-Object** - Salvar saída em arquivo e passar para pipeline
- **Test-Connection** - Testar conexão de rede (ping)
- **Test-Path** - Verificar se caminho existe
- **Trace-Command** - Rastrear comando com debug

### U

- **Unblock-File** - Desbloquear arquivo baixado da internet
- **Undo-Transaction** - Desfazer transação
- **Unregister-Event** - Cancelar registro de evento
- **Update-FormatData** - Atualizar dados de formatação
- **Update-Help** - Atualizar arquivos de ajuda
- **Update-TypeData** - Atualizar dados de tipo estendido
- **Use-Transaction** - Incluir comando em transação

### W

- **Wait-Event** - Aguardar evento específico
- **Wait-Job** - Aguardar término de jobs
- **Wait-Process** - Aguardar término de processos
- **Where-Object** - Filtrar objetos (alias: where, ?)
- **Write-Debug** - Escrever mensagem de depuração
- **Write-Error** - Escrever objeto de erro
- **Write-EventLog** - Escrever entrada em log de eventos
- **Write-Host** - Escrever na tela (não no pipeline)
- **Write-Output** - Enviar objeto para pipeline (alias: echo)
- **Write-Progress** - Exibir barra de progresso
- **Write-Verbose** - Escrever mensagem detalhada
- **Write-Warning** - Escrever mensagem de aviso

---

## Dicas de Utilização

### Ajuda e Descoberta

- Use `Get-Help [comando] -Examples` para ver exemplos práticos
- Use `Get-Help [comando] -Online` para abrir a documentação web
- Use `Get-Command -Verb [verbo]` ou `Get-Command -Noun [substantivo]` para encontrar comandos
- Use `Get-Member` para descobrir propriedades e métodos de objetos

### Pipelines e Filtros

- Use `|` para conectar comandos em pipeline (passando objetos, não texto)
- Use `Where-Object {$_.Propriedade -eq "Valor"}` para filtrar resultados
- Use `Select-Object` para escolher quais propriedades exibir

### Formatação

- Use `Format-Table` para exibir dados em formato tabular
- Use `Format-List` para exibir propriedades em formato de lista
- Use `-AutoSize` com Format-Table para melhorar a exibição

### Segurança

- Use `Set-ExecutionPolicy` para configurar a política de execução de scripts
- Use `Get-Credential` para trabalhar com credenciais de forma segura
- Use `ConvertTo-SecureString` para trabalhar com senhas seguras

### Aliases

- Use `Get-Alias` para listar todos os aliases disponíveis
- Comandos comuns como `ls`, `dir`, `cd`, `rm` funcionam como aliases

## Links Úteis

- [Documentação do PowerShell](https://learn.microsoft.com/pt-br/powershell/)

---
