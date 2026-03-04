# 📑 Índice Alfabético de Cmdlets do Active Directory PowerShell
#### *Organizado por substantivo após o verbo do cmdlet*



---

## 🔤 Índice por Categorias

- [A](#a) - Account, AccessRule, AccountAuthorizationGroup, AuthenticationPolicy
- [C](#c) - Computer, Clone, Contact, Context
- [D](#d) - Domain, DomainController, DefaultDomainPasswordPolicy
- [F](#f) - Forest, FineGrainedPasswordPolicy, FineGrainedPasswordPolicySubject
- [G](#g) - Group, GroupMember
- [L](#l) - LDAPFilterEntry, LogonHour
- [O](#o) - Object, OrganizationalUnit, OptionalFeature
- [P](#p) - PasswordReplicationPolicy, PrincipalGroupMembership
- [Q](#q) - QuotaEntry
- [R](#r) - ResourceProperty, ResourcePropertyList, ReplicationSite, ReplicationSiteLink, ReplicationConnection, RootDSE
- [S](#s) - ServiceAccount, ServiceAccountPassword
- [T](#t) - Trust, TrustRelationship
- [U](#u) - User

---

## A

### 🔑 Account

| Cmdlet | Descrição |
|--------|-----------|
| `Clear-ADAccountExpiration` | Remove a data de expiração de uma conta do AD |
| `Disable-ADAccount` | Desabilita uma conta do Active Directory |
| `Enable-ADAccount` | Habilita uma conta do Active Directory |
| `Get-ADAccountAuthorizationGroup` | Obtém os grupos de autorização de uma conta |
| `Search-ADAccount` | Pesquisa por contas do AD baseado em critérios (expirada, bloqueada, etc.) |
| `Set-ADAccountControl` | Modifica propriedades da conta (ex: não exigir senha) |
| `Set-ADAccountExpiration` | Define a data de expiração de uma conta |
| `Set-ADAccountPassword` | Altera a senha de uma conta do AD |
| `Unlock-ADAccount` | Desbloqueia uma conta do Active Directory |

### 🛡️ AccessRule e AuthorizationRule

| Cmdlet | Descrição |
|--------|-----------|
| `Add-ADCentralAccessPolicyMember` | Adiciona um membro a uma política de acesso central |
| `Add-ADResourcePropertyListMember` | Adiciona uma propriedade de recurso à lista de propriedades do recurso |
| `Get-ADCentralAccessPolicy` | Obtém uma ou mais políticas de acesso central |
| `Get-ADCentralAccessRule` | Obtém uma ou mais regras de acesso central |
| `New-ADCentralAccessPolicy` | Cria uma nova política de acesso central |
| `New-ADCentralAccessRule` | Cria uma nova regra de acesso central |
| `Remove-ADCentralAccessPolicy` | Remove uma política de acesso central |
| `Remove-ADCentralAccessPolicyMember` | Remove um membro de uma política de acesso central |
| `Remove-ADCentralAccessRule` | Remove uma regra de acesso central |
| `Set-ADCentralAccessPolicy` | Modifica uma política de acesso central |
| `Set-ADCentralAccessRule` | Modifica uma regra de acesso central |

### 🔐 AuthenticationPolicy

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADAuthenticationPolicy` | Obtém uma ou mais políticas de autenticação |
| `Get-ADAuthenticationPolicySilo` | Obtém um ou mais silos de política de autenticação |
| `New-ADAuthenticationPolicy` | Cria uma nova política de autenticação |
| `New-ADAuthenticationPolicySilo` | Cria um novo silo de política de autenticação |
| `Remove-ADAuthenticationPolicy` | Remove uma política de autenticação |
| `Remove-ADAuthenticationPolicySilo` | Remove um silo de política de autenticação |
| `Set-ADAuthenticationPolicy` | Modifica uma política de autenticação |
| `Set-ADAuthenticationPolicySilo` | Modifica um silo de política de autenticação |

---

## C

### 💻 Computer

| Cmdlet | Descrição |
|--------|-----------|
| `Add-ADComputerServiceAccount` | Adiciona contas de serviço gerenciadas a um computador |
| `Get-ADComputer` | Obtém um ou mais objetos de computador |
| `New-ADComputer` | Cria um novo objeto de computador |
| `Remove-ADComputer` | Remove um objeto de computador |
| `Remove-ADComputerServiceAccount` | Remove contas de serviço gerenciadas de um computador |
| `Set-ADComputer` | Modifica um objeto de computador existente |

### 👤 Contact

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADContact` | Obtém um ou mais contatos do AD |
| `New-ADContact` | Cria um novo contato no AD |
| `Remove-ADContact` | Remove um contato do AD |
| `Set-ADContact` | Modifica um contato existente no AD |

### 🔄 Clone

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADDCCloningExcludedApplicationList` | Obtém a lista de aplicativos excluídos da clonagem de DC |
| `New-ADDCCloneConfigFile` | Cria um arquivo de configuração para clonagem de DC |
| `Set-ADDCCloningConfigFile` | Modifica um arquivo de configuração para clonagem de DC |

### 📋 Context

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADPrincipalGroupMembership` | Obtém os grupos dos quais um principal é membro |
| `Move-ADDirectoryServer` | Move um servidor de diretório para um site diferente |
| `Move-ADDirectoryServerOperationMasterRole` | Move um ou mais papéis de operação mestre |
| `Rename-ADObject` | Renomeia um objeto do Active Directory |
| `Restore-ADObject` | Restaura um objeto excluído do AD |
| `Test-ADServiceAccount` | Testa se um computador pode usar uma conta de serviço gerenciada |

---

## D

### 🌐 Domain

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADDomain` | Obtém um domínio do Active Directory |
| `Get-ADTrust` | Obtém todas as relações de confiança para este domínio |
| `Set-ADDomain` | Modifica um domínio existente |
| `Set-ADDomainMode` | Define o modo funcional do domínio |

### 🖥️ DomainController

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADDomainController` | Obtém um ou mais controladores de domínio |
| `Get-ADDomainControllerPasswordReplicationPolicy` | Obtém a política de replicação de senha |
| `Get-ADDomainControllerPasswordReplicationPolicyUsage` | Obtém os princípios afetados pela política de replicação de senha |
| `Add-ADDomainControllerPasswordReplicationPolicy` | Adiciona princípios à política de replicação de senha |
| `Remove-ADDomainControllerPasswordReplicationPolicy` | Remove princípios da política de replicação de senha |

### 🔑 DefaultDomainPasswordPolicy

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADDefaultDomainPasswordPolicy` | Obtém a política de senha padrão do domínio |
| `Set-ADDefaultDomainPasswordPolicy` | Modifica a política de senha padrão do domínio |

---

## F

### 🌳 Forest

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADForest` | Obtém uma floresta do Active Directory |
| `Set-ADForest` | Modifica uma floresta do AD |
| `Set-ADForestMode` | Define o modo funcional da floresta |

### 🔐 FineGrainedPasswordPolicy

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADFineGrainedPasswordPolicy` | Obtém uma ou mais políticas de senha refinadas |
| `Get-ADFineGrainedPasswordPolicySubject` | Obtém os sujeitos vinculados a uma política de senha refinada |
| `New-ADFineGrainedPasswordPolicy` | Cria uma nova política de senha refinada |
| `Remove-ADFineGrainedPasswordPolicy` | Remove uma política de senha refinada |
| `Set-ADFineGrainedPasswordPolicy` | Modifica uma política de senha refinada existente |
| `Add-ADFineGrainedPasswordPolicySubject` | Adiciona um sujeito a uma política de senha refinada |
| `Remove-ADFineGrainedPasswordPolicySubject` | Remove um sujeito de uma política de senha refinada |

---

## G

### 👥 Group

| Cmdlet | Descrição |
|--------|-----------|
| `Add-ADGroupMember` | Adiciona um ou mais membros a um grupo do AD |
| `Get-ADGroup` | Obtém um ou mais grupos do AD |
| `Get-ADGroupMember` | Obtém os membros de um grupo do AD |
| `New-ADGroup` | Cria um novo grupo no AD |
| `Remove-ADGroup` | Remove um grupo do AD |
| `Remove-ADGroupMember` | Remove um ou mais membros de um grupo do AD |
| `Set-ADGroup` | Modifica um grupo existente no AD |

---

## L

### 🔍 LDAPFilterEntry

| Cmdlet | Descrição |
|--------|-----------|
| `Clear-ADClaimTransformLink` | Remove um link de transformação de declaração |
| `Get-ADClaimTransformPolicy` | Obtém uma ou mais políticas de transformação de declaração |
| `Get-ADClaimType` | Obtém um ou mais tipos de declaração |
| `New-ADClaimTransformPolicy` | Cria uma nova política de transformação de declaração |
| `New-ADClaimType` | Cria um novo tipo de declaração |
| `Remove-ADClaimTransformPolicy` | Remove uma política de transformação de declaração |
| `Remove-ADClaimType` | Remove um tipo de declaração |
| `Set-ADClaimTransformLink` | Define um link de transformação de declaração |
| `Set-ADClaimTransformPolicy` | Modifica uma política de transformação de declaração existente |
| `Set-ADClaimType` | Modifica um tipo de declaração existente |

### ⏰ LogonHour

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADUserResultantPasswordPolicy` | Obtém a política de senha resultante para um usuário |

---

## O

### 📁 Object

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADObject` | Obtém um ou mais objetos do AD |
| `Move-ADObject` | Move um objeto do AD para um novo local |
| `New-ADObject` | Cria um novo objeto no AD |
| `Remove-ADObject` | Remove um objeto do AD |
| `Restore-ADObject` | Restaura um objeto excluído do AD |
| `Set-ADObject` | Modifica um objeto existente no AD |
| `Sync-ADObject` | Sincroniza um objeto entre controladores de domínio |

### 📂 OrganizationalUnit

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADOrganizationalUnit` | Obtém uma ou mais unidades organizacionais |
| `New-ADOrganizationalUnit` | Cria uma nova unidade organizacional |
| `Remove-ADOrganizationalUnit` | Remove uma unidade organizacional |
| `Set-ADOrganizationalUnit` | Modifica uma unidade organizacional existente |

### 🔧 OptionalFeature

| Cmdlet | Descrição |
|--------|-----------|
| `Disable-ADOptionalFeature` | Desabilita um recurso opcional do AD |
| `Enable-ADOptionalFeature` | Habilita um recurso opcional do AD |
| `Get-ADOptionalFeature` | Obtém um ou mais recursos opcionais do AD |

---

## P

### 🔑 PasswordReplicationPolicy

| Cmdlet | Descrição |
|--------|-----------|
| `Add-ADDomainControllerPasswordReplicationPolicy` | Adiciona usuários, grupos ou computadores à política de replicação de senhas |
| `Get-ADDomainControllerPasswordReplicationPolicy` | Obtém a política de replicação de senhas para um controlador de domínio |
| `Get-ADDomainControllerPasswordReplicationPolicyUsage` | Obtém os usuários, grupos e computadores afetados pela política de replicação de senhas |
| `Remove-ADDomainControllerPasswordReplicationPolicy` | Remove usuários, grupos ou computadores da política de replicação de senhas |

### 👥 PrincipalGroupMembership

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADPrincipalGroupMembership` | Obtém os grupos dos quais um principal (usuário, grupo, computador) é membro |

---

## Q

### 📊 QuotaEntry

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADQuota` | Obtém uma ou mais entradas de cota |
| `New-ADQuota` | Cria uma nova entrada de cota |
| `Remove-ADQuota` | Remove uma entrada de cota |
| `Set-ADQuota` | Modifica uma entrada de cota existente |

---

## R

### 🏷️ ResourceProperty

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADResourceProperty` | Obtém uma ou mais propriedades de recurso |
| `New-ADResourceProperty` | Cria uma nova propriedade de recurso |
| `Remove-ADResourceProperty` | Remove uma propriedade de recurso |
| `Set-ADResourceProperty` | Modifica uma propriedade de recurso existente |

### 📋 ResourcePropertyList

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADResourcePropertyList` | Obtém uma ou mais listas de propriedades de recurso |
| `New-ADResourcePropertyList` | Cria uma nova lista de propriedades de recurso |
| `Remove-ADResourcePropertyList` | Remove uma lista de propriedades de recurso |
| `Remove-ADResourcePropertyListMember` | Remove um membro de uma lista de propriedades de recurso |
| `Set-ADResourcePropertyList` | Modifica uma lista de propriedades de recurso existente |

### 🔄 Replication

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADReplicationAttributeMetadata` | Obtém metadados de atributos de replicação |
| `Get-ADReplicationConnection` | Obtém conexões de replicação |
| `Get-ADReplicationFailure` | Obtém falhas de replicação |
| `Get-ADReplicationPartnerMetadata` | Obtém metadados de parceiros de replicação |
| `Get-ADReplicationQueueOperation` | Obtém operações na fila de replicação |
| `Get-ADReplicationSite` | Obtém um ou mais sites de replicação |
| `Get-ADReplicationSiteLink` | Obtém um ou mais links de site de replicação |
| `Get-ADReplicationSiteLinkBridge` | Obtém uma ou mais pontes de link de site de replicação |
| `Get-ADReplicationSubnet` | Obtém uma ou mais sub-redes de replicação |
| `Get-ADReplicationUpToDatenessVectorTable` | Obtém a tabela de vetores de atualização de replicação |
| `New-ADReplicationSite` | Cria um novo site de replicação |
| `New-ADReplicationSiteLink` | Cria um novo link de site de replicação |
| `New-ADReplicationSiteLinkBridge` | Cria uma nova ponte de link de site de replicação |
| `New-ADReplicationSubnet` | Cria uma nova sub-rede de replicação |
| `Remove-ADReplicationSite` | Remove um site de replicação |
| `Remove-ADReplicationSiteLink` | Remove um link de site de replicação |
| `Remove-ADReplicationSiteLinkBridge` | Remove uma ponte de link de site de replicação |
| `Remove-ADReplicationSubnet` | Remove uma sub-rede de replicação |
| `Set-ADReplicationConnection` | Modifica uma conexão de replicação existente |
| `Set-ADReplicationSite` | Modifica um site de replicação existente |
| `Set-ADReplicationSiteLink` | Modifica um link de site de replicação existente |
| `Set-ADReplicationSiteLinkBridge` | Modifica uma ponte de link de site de replicação existente |
| `Set-ADReplicationSubnet` | Modifica uma sub-rede de replicação existente |
| `Sync-ADObject` | Sincroniza um objeto entre controladores de domínio |

### 🌳 RootDSE

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADRootDSE` | Obtém o objeto RootDSE do servidor de diretório |

---

## S

### 👨‍💼 ServiceAccount

| Cmdlet | Descrição |
|--------|-----------|
| `Add-ADComputerServiceAccount` | Adiciona contas de serviço gerenciadas a um computador |
| `Get-ADServiceAccount` | Obtém uma ou mais contas de serviço gerenciadas |
| `Install-ADServiceAccount` | Instala uma conta de serviço gerenciada em um computador |
| `New-ADServiceAccount` | Cria uma nova conta de serviço gerenciada |
| `Remove-ADComputerServiceAccount` | Remove contas de serviço gerenciadas de um computador |
| `Remove-ADServiceAccount` | Remove uma conta de serviço gerenciada |
| `Reset-ADServiceAccountPassword` | Redefine a senha de uma conta de serviço gerenciada |
| `Set-ADServiceAccount` | Modifica uma conta de serviço gerenciada existente |
| `Test-ADServiceAccount` | Testa se um computador pode usar uma conta de serviço gerenciada |
| `Uninstall-ADServiceAccount` | Desinstala uma conta de serviço gerenciada de um computador |

---

## T

### 🤝 Trust

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADTrust` | Obtém uma ou mais relações de confiança do AD |
| `Get-ADTrustRelationship` | Obtém uma ou mais relações de confiança |
| `Set-ADTrust` | Modifica uma relação de confiança existente |

---

## U

### 👤 User

| Cmdlet | Descrição |
|--------|-----------|
| `Get-ADUser` | Obtém um ou mais usuários do AD |
| `Get-ADUserResultantPasswordPolicy` | Obtém a política de senha resultante para um usuário |
| `New-ADUser` | Cria um novo usuário no AD |
| `Remove-ADUser` | Remove um usuário do AD |
| `Set-ADUser` | Modifica um usuário existente no AD |
| `Unlock-ADAccount` | Desbloqueia uma conta de usuário |

---

## 📝 Notas Adicionais

### Comandos Relacionados (Não-PowerShell)

- `dcdiag` - Diagnostica problemas com controladores de domínio
- `repadmin` - Ferramenta de diagnóstico de replicação
- `netdom` - Gerencia domínios e relações de confiança
- `ntdsutil` - Gerencia o banco de dados do AD
- `dsacls` - Gerencia permissões do AD
- `dsquery` - Pesquisa objetos no AD
- `dsmod` - Modifica objetos no AD
- `dsmove` - Move objetos no AD
- `dsadd` - Adiciona objetos ao AD

### Aliases Comuns

- `gpupdate` - Atualiza políticas de grupo
- `gpresult` - Exibe resultados de políticas de grupo aplicadas

---

## 🔍 Dicas de Uso

1. **Filtrar resultados**: Use o parâmetro `-Filter` com operadores de comparação:
   ```powershell
   Get-ADUser -Filter {Department -eq "TI" -and Enabled -eq $true}
   ```

2. **Selecionar propriedades específicas**: Use o parâmetro `-Properties` para especificar quais propriedades você quer:
   ```powershell
   Get-ADUser -Identity "joao.silva" -Properties Department, Title, LastLogonDate
   ```

3. **Formatação de saída**: Use cmdlets como `Format-Table`, `Format-List`, ou `Select-Object` para personalizar a saída:
   ```powershell
   Get-ADUser -Filter * | Select-Object Name, SamAccountName, Enabled | Format-Table -AutoSize
   ```

4. **Exportar resultados**: Use `Export-Csv` para salvar resultados em um arquivo:
   ```powershell
   Get-ADUser -Filter * | Select-Object Name, SamAccountName | Export-Csv -Path "C:\Users.csv" -NoTypeInformation
   ```

5. **Utilizar o método Pipeline**: Combine comandos para operações em massa:
   ```powershell
   Get-ADUser -Filter {Department -eq "Vendas"} | Set-ADUser -Company "Contoso"
   ```

---
