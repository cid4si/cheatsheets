# PowerShell para Active Directory

## Índice

- [Introdução](#introdução)
- [Instalação e Configuração](#instalação-e-configuração)
- [Gerenciamento de Usuários](#gerenciamento-de-usuarios)
- [Gerenciamento de Grupos](#gerenciamento-de-grupos)
- [Gerenciamento de Computadores](#gerenciamento-de-computadores)
- [Gerenciamento de Unidades Organizacionais](#gerenciamento-de-unidades-organizacionais)
- [Consultas e Filtros](#consultas-e-filtros)
- [Segurança e Políticas](#seguranca-e-politicas)
- [Domínios e Florestas](#dominios-e-florestas)
- [Replicação e Manutenção](#replicacao-e-manutencao)
- [Exemplos Avançados](#exemplos-avancados)
- [Links Úteis](#links-uteis)

* * *

## Introdução

O módulo Active Directory para Windows PowerShell fornece uma forma eficiente de gerenciar ambientes do Active Directory Domain Services (AD DS) através de linha de comando. Este documento serve como referência rápida para os principais cmdlets relacionados ao AD.

* * *

## Instalação e Configuração

```powershell
# Instalar as Ferramentas de Administração Remota do Servidor (RSAT)
Add-WindowsFeature RSAT-AD-PowerShell

# Importar o módulo do Active Directory
Import-Module ActiveDirectory

# Verificar os cmdlets disponíveis
Get-Command -Module ActiveDirectory
```

* * *

## Gerenciamento de Usuários

### Principais Cmdlets para Usuários

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADUser` | Obtém um ou mais usuários do Active Directory |
| `New-ADUser` | Cria um novo usuário no AD |
| `Set-ADUser` | Modifica as propriedades de um usuário existente |
| `Remove-ADUser` | Remove um usuário do AD |
| `Enable-ADAccount` | Habilita uma conta de usuário |
| `Disable-ADAccount` | Desabilita uma conta de usuário |
| `Unlock-ADAccount` | Desbloqueia uma conta de usuário |
| `Set-ADAccountPassword` | Altera a senha de uma conta |
| `Search-ADAccount` | Pesquisa contas com base em critérios específicos |

### Exemplos de Uso

```powershell
# Criar um novo usuário
New-ADUser -Name "João Silva" -GivenName "João" -Surname "Silva" -SamAccountName "joao.silva" -UserPrincipalName "joao.silva@contoso.com" -Path "OU=Usuarios,DC=contoso,DC=com" -AccountPassword (ConvertTo-SecureString "Senha@123" -AsPlainText -Force) -Enabled $true

# Obter um usuário específico
Get-ADUser -Identity "joao.silva" -Properties *

# Modificar propriedades de um usuário
Set-ADUser -Identity "joao.silva" -Department "TI" -Title "Analista de Sistemas"

# Resetar a senha de um usuário
Set-ADAccountPassword -Identity "joao.silva" -Reset -NewPassword (ConvertTo-SecureString "NovaSenha@123" -AsPlainText -Force)

# Desabilitar uma conta de usuário
Disable-ADAccount -Identity "joao.silva"

# Habilitar uma conta de usuário
Enable-ADAccount -Identity "joao.silva"

# Desbloquear uma conta de usuário
Unlock-ADAccount -Identity "joao.silva"

# Encontrar contas expiradas
Search-ADAccount -AccountExpired

# Encontrar contas que nunca expiram
Search-ADAccount -AccountNeverExpires

# Encontrar contas inativas (não logadas há mais de 30 dias)
$data = (Get-Date).AddDays(-30)
Get-ADUser -Filter {LastLogonDate -lt $data} -Properties LastLogonDate
```

* * *

## Gerenciamento de Grupos

### Principais Cmdlets para Grupos

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADGroup` | Obtém um ou mais grupos do Active Directory |
| `New-ADGroup` | Cria um novo grupo no AD |
| `Set-ADGroup` | Modifica as propriedades de um grupo existente |
| `Remove-ADGroup` | Remove um grupo do AD |
| `Add-ADGroupMember` | Adiciona um ou mais membros a um grupo |
| `Remove-ADGroupMember` | Remove um ou mais membros de um grupo |
| `Get-ADGroupMember` | Obtém os membros de um grupo do AD |
| `Get-ADPrincipalGroupMembership` | Obtém os grupos dos quais um principal é membro |

### Exemplos de Uso

```powershell
# Criar um novo grupo
New-ADGroup -Name "Equipe TI" -GroupScope Global -GroupCategory Security -Path "OU=Grupos,DC=contoso,DC=com"

# Obter informações de um grupo
Get-ADGroup -Identity "Equipe TI" -Properties *

# Adicionar membros a um grupo
Add-ADGroupMember -Identity "Equipe TI" -Members "joao.silva","maria.souza"

# Listar membros de um grupo
Get-ADGroupMember -Identity "Equipe TI" | Select-Object Name, SamAccountName

# Verificar em quais grupos um usuário é membro
Get-ADPrincipalGroupMembership -Identity "joao.silva" | Select-Object Name

# Remover um membro de um grupo
Remove-ADGroupMember -Identity "Equipe TI" -Members "joao.silva" -Confirm:$false
```

* * *

## Gerenciamento de Computadores

### Principais Cmdlets para Computadores

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADComputer` | Obtém um ou mais computadores do Active Directory |
| `New-ADComputer` | Cria um novo objeto de computador no AD |
| `Set-ADComputer` | Modifica as propriedades de um computador existente |
| `Remove-ADComputer` | Remove um computador do AD |
| `Test-ComputerSecureChannel` | Verifica a conexão segura entre um computador e o domínio |

### Exemplos de Uso

```powershell
# Criar um novo objeto de computador
New-ADComputer -Name "PC-TI01" -Path "OU=Computadores,DC=contoso,DC=com"

# Obter informações de um computador
Get-ADComputer -Identity "PC-TI01" -Properties *

# Modificar propriedades de um computador
Set-ADComputer -Identity "PC-TI01" -Description "Computador do Departamento de TI"

# Listar todos os computadores que não logaram nos últimos 30 dias
$data = (Get-Date).AddDays(-30)
Get-ADComputer -Filter {LastLogonDate -lt $data} -Properties LastLogonDate | Select-Object Name, LastLogonDate

# Mover um computador para outra OU
Move-ADObject -Identity "CN=PC-TI01,OU=Computadores,DC=contoso,DC=com" -TargetPath "OU=TI,OU=Computadores,DC=contoso,DC=com"

# Verificar a conexão segura de um computador com o domínio
Test-ComputerSecureChannel -Repair
```

* * *

## Gerenciamento de Unidades Organizacionais

### Principais Cmdlets para OUs

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADOrganizationalUnit` | Obtém uma ou mais OUs do Active Directory |
| `New-ADOrganizationalUnit` | Cria uma nova OU no AD |
| `Set-ADOrganizationalUnit` | Modifica as propriedades de uma OU existente |
| `Remove-ADOrganizationalUnit` | Remove uma OU do AD |
| `Move-ADObject` | Move um objeto AD para outra localização |

### Exemplos de Uso

```powershell
# Criar uma nova OU
New-ADOrganizationalUnit -Name "Financeiro" -Path "DC=contoso,DC=com" -ProtectedFromAccidentalDeletion $true

# Obter informações de uma OU
Get-ADOrganizationalUnit -Identity "OU=Financeiro,DC=contoso,DC=com" -Properties *

# Modificar propriedades de uma OU
Set-ADOrganizationalUnit -Identity "OU=Financeiro,DC=contoso,DC=com" -Description "Departamento Financeiro"

# Desproteger uma OU para permitir exclusão
Set-ADOrganizationalUnit -Identity "OU=Financeiro,DC=contoso,DC=com" -ProtectedFromAccidentalDeletion $false

# Remover uma OU
Remove-ADOrganizationalUnit -Identity "OU=Financeiro,DC=contoso,DC=com" -Confirm:$false

# Listar todas as OUs
Get-ADOrganizationalUnit -Filter * | Select-Object Name, DistinguishedName
```

* * *

## Consultas e Filtros

### Principais Cmdlets para Consultas e Filtros

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADObject` | Obtém um ou mais objetos do Active Directory |
| `Search-ADAccount` | Pesquisa contas do AD com base em critérios específicos |
| `Get-ADAccountAuthorizationGroup` | Obtém os grupos de autorização de uma conta |

### Exemplos de Uso

```powershell
# Pesquisar objetos por nome
Get-ADObject -Filter {Name -like "*TI*"} -Properties *

# Pesquisar usuários por departamento
Get-ADUser -Filter {Department -eq "TI"} -Properties * | Select-Object Name, SamAccountName, Department

# Pesquisar contas bloqueadas
Search-ADAccount -LockedOut | Select-Object Name, SamAccountName

# Pesquisar contas com senha expirada
Search-ADAccount -PasswordExpired | Select-Object Name, SamAccountName

# Pesquisar contas inativas
Search-ADAccount -AccountInactive -TimeSpan 30.00:00:00 | Select-Object Name, SamAccountName

# Obter todos os grupos de autorização para um usuário
Get-ADAccountAuthorizationGroup -Identity "joao.silva" | Select-Object Name
```

* * *

## Segurança e Políticas

### Principais Cmdlets para Segurança e Políticas

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADDefaultDomainPasswordPolicy` | Obtém a política de senha padrão do domínio |
| `Set-ADDefaultDomainPasswordPolicy` | Modifica a política de senha padrão do domínio |
| `Get-ADFineGrainedPasswordPolicy` | Obtém políticas de senha refinadas |
| `New-ADFineGrainedPasswordPolicy` | Cria uma nova política de senha refinada |
| `Set-ADFineGrainedPasswordPolicy` | Modifica uma política de senha refinada existente |
| `Remove-ADFineGrainedPasswordPolicy` | Remove uma política de senha refinada |

### Exemplos de Uso

```powershell
# Obter a política de senha padrão do domínio
Get-ADDefaultDomainPasswordPolicy

# Modificar a política de senha padrão do domínio
Set-ADDefaultDomainPasswordPolicy -Identity "contoso.com" -MinPasswordLength 12 -MaxPasswordAge "90.00:00:00" -PasswordHistoryCount 24

# Criar uma política de senha refinada
New-ADFineGrainedPasswordPolicy -Name "Política Executivos" -Precedence 10 -MinPasswordLength 14 -MaxPasswordAge "60.00:00:00" -PasswordHistoryCount 24

# Aplicar uma política de senha refinada a um grupo
Add-ADFineGrainedPasswordPolicySubject -Identity "Política Executivos" -Subjects "Executivos"

# Listar todas as políticas de senha refinadas
Get-ADFineGrainedPasswordPolicy -Filter * | Select-Object Name, Precedence, MinPasswordLength
```

* * *

## Domínios e Florestas

### Principais Cmdlets para Domínios e Florestas

| Cmdlet | Descrição |
| --- | --- |
| `Get-ADDomain` | Obtém um domínio do Active Directory |
| `Get-ADForest` | Obtém uma floresta do Active Directory |
| `Get-ADDomainController` | Obtém um ou mais controladores de domínio |
| `Get-ADTrust` | Obtém relações de confiança do domínio |
| `Get-ADRootDSE` | Obtém as informações do RootDSE do AD |

### Exemplos de Uso

```powershell
# Obter informações do domínio atual
Get-ADDomain

# Obter informações da floresta atual
Get-ADForest

# Listar todos os controladores de domínio
Get-ADDomainController -Filter * | Select-Object Name, Site, IPv4Address

# Obter informações sobre um controlador de domínio específico
Get-ADDomainController -Identity "DC01"

# Listar as relações de confiança do domínio
Get-ADTrust -Filter * | Select-Object Name, Direction, TrustType

# Obter informações do RootDSE
Get-ADRootDSE
```

* * *

## Replicação e Manutenção

### Principais Cmdlets e Ferramentas para Replicação

| Cmdlet/Ferramenta | Descrição |
| --- | --- |
| `Get-ADReplicationPartnerMetadata` | Obtém metadados de parceiros de replicação |
| `Get-ADReplicationFailure` | Obtém falhas de replicação |
| `Get-ADReplicationQueueOperation` | Obtém operações na fila de replicação |
| `Sync-ADObject` | Sincroniza um objeto do AD entre controladores de domínio |
| `repadmin` | Ferramenta de linha de comando para gerenciar replicação |

### Exemplos de Uso

```powershell
# Obter metadados de replicação para todos os DCs
Get-ADReplicationPartnerMetadata -Target * -Scope Server

# Verificar falhas de replicação
Get-ADReplicationFailure -Target *

# Sincronizar um objeto específico entre DCs
Sync-ADObject -Object "CN=João Silva,OU=Usuarios,DC=contoso,DC=com"

# Forçar sincronização entre todos os DCs usando repadmin
repadmin /syncall /AdeP

# Mostrar status de replicação
repadmin /replsummary

# Verificar a topologia de replicação
repadmin /showrepl
```

* * *

## Exemplos Avançados

### Gerenciamento em Massa

```powershell
# Importar usuários de um CSV
Import-Csv -Path "C:\Temp\usuarios.csv" | ForEach-Object {
    New-ADUser -Name $_.Nome -GivenName $_.Nome -Surname $_.Sobrenome -SamAccountName $_.Login -UserPrincipalName "$($_.Login)@contoso.com" -Department $_.Departamento -Path $_.OU -AccountPassword (ConvertTo-SecureString $_.Senha -AsPlainText -Force) -Enabled $true
}

# Exportar usuários para CSV
Get-ADUser -Filter * -Properties Department, Title, Manager | 
    Select-Object Name, SamAccountName, Department, Title, @{Name="Manager";Expression={$_.Manager -replace "CN=|,.*"}} |
    Export-Csv -Path "C:\Temp\usuarios_exportados.csv" -NoTypeInformation -Encoding UTF8

# Modificar múltiplos usuários com base em critérios
Get-ADUser -Filter {Department -eq "Vendas"} | Set-ADUser -Company "Contoso" -Description "Departamento de Vendas"

# Desabilitar contas inativas há mais de 90 dias
$data = (Get-Date).AddDays(-90)
Get-ADUser -Filter {LastLogonDate -lt $data -and Enabled -eq $true} -Properties LastLogonDate | 
    Disable-ADAccount
```

### Scripts Avançados

```powershell
# Relatório de usuários recém-criados (últimos 7 dias)
$data = (Get-Date).AddDays(-7)
Get-ADUser -Filter {whenCreated -ge $data} -Properties whenCreated | 
    Select-Object Name, SamAccountName, @{Name="DataCriação";Expression={$_.whenCreated}} |
    Sort-Object whenCreated

# Inventário de computadores por sistema operacional
Get-ADComputer -Filter * -Properties OperatingSystem | 
    Group-Object -Property OperatingSystem | 
    Select-Object Name, Count

# Relatório de expiração de senhas de usuários
Get-ADUser -Filter {Enabled -eq $true} -Properties Name, SamAccountName, PasswordLastSet, PasswordNeverExpires |
    Select-Object Name, SamAccountName, PasswordLastSet, PasswordNeverExpires,
        @{Name="ExpirationDate";Expression={
            if($_.PasswordNeverExpires -eq $true) {"Nunca expira"}
            else {
                $policy = Get-ADDefaultDomainPasswordPolicy
                $expiry = $_.PasswordLastSet + $policy.MaxPasswordAge
                $expiry.ToString("dd/MM/yyyy")
            }
        }}

# Monitoramento de contas privilegiadas
Get-ADGroupMember -Identity "Domain Admins" | 
    Get-ADUser -Properties Name, Enabled, LastLogonDate, PasswordLastSet |
    Select-Object Name, Enabled, LastLogonDate, PasswordLastSet
```

* * *

## Links Úteis

- [Documentação oficial do PowerShell para AD](https://docs.microsoft.com/pt-br/powershell/module/activedirectory)
- [SS64 - Referência de Comandos PowerShell AD](https://ss64.com/ps/ad.html)
- [Microsoft Learn - Gerenciar Active Directory Domain Services](https://learn.microsoft.com/pt-br/training/modules/manage-active-directory-domain-services-use-powershell-cmdlets/)

* * *