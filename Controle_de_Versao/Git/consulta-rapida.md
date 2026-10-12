# Consulta rápida e Troubleshooting

## Sumário

- [Configuração inicial (setup)](#configuração-inicial-setup)
- [Criar / clonar repositório](#criar--clonar-repositório)
- [Fluxo básico (dia a dia)](#fluxo-básico-dia-a-dia)
- [Branches](#branches)
- [Remotos](#remotos)
- [Histórico e inspeção](#histórico-e-inspeção)
- [Utilitários](#utilitários)
- [Dicas rápidas](#dicas-rápidas)
- [Erros comuns e como resolver](#erros-comuns-e-como-resolver)

---

## Configuração inicial (setup)

| Comando | Descrição |
|---|---|
| `git config --global user.name "Nome"` | Define nome do autor |
| `git config --global user.email "email"` | Define email do autor |
| `git config --global init.defaultBranch main` | Nova branch padrão = `main` |
| `git config --global --list` | Lista configs globais |
| `git config --get <chave>` | Consulta uma config específica |
| `git config --unset <chave>` | Remove uma config (local) |
| `git config --global --unset <chave>` | Remove uma config (global) |
| `ssh -T git@github.com` | Testa autenticação SSH com GitHub |
| `ssh-keygen -t ed25519 -C "email"` | Gera nova chave SSH |
| `cat ~/.ssh/id_ed25519.pub` | Mostra a chave pública |

---

## Criar / clonar repositório

| Comando | Descrição |
|---|---|
| `git init` | Inicializa repositório |
| `git init -b main` | Inicializa já na branch `main` |
| `git clone <url>` | Clona repositório |
| `git clone <url> <pasta>` | Clona em pasta específica |
| `git clone --depth 1 <url>` | Clone raso (só último commit) |

---

## Fluxo básico (dia a dia)

| Comando | Descrição |
|---|---|
| `git status` | Estado dos arquivos |
| `git status -s` | Versão curta do status |
| `git add <arquivo>` | Adiciona um arquivo ao stage |
| `git add .` | Adiciona tudo do diretório atual |
| `git add -A` | Adiciona todas as mudanças (inclui deleções) |
| `git add -p` | Adiciona em modo interativo (pedaços) |
| `git commit -m "msg"` | Registra commit |
| `git commit -am "msg"` | Add + commit de arquivos já rastreados |
| `git commit --amend` | Corrige o último commit |
| `git push` | Envia para remoto (branch já rastreada) |
| `git push -u origin main` | Envia e define upstream |
| `git push --tags` | Envia tags |
| `git pull` | Baixa + merge do remoto |
| `git pull --rebase` | Baixa e reaplica commits por cima |
| `git fetch` | Baixa sem aplicar |

---

## Branches

| Comando | Descrição |
|---|---|
| `git branch` | Lista branches locais |
| `git branch -a` | Lista todas (locais + remotas) |
| `git branch <nome>` | Cria branch |
| `git branch -m <novo>` | Renomeia branch atual |
| `git branch -M main` | Renomeia forçado (ex: `master` → `main`) |
| `git branch -d <nome>` | Deleta branch (mergeada) |
| `git branch -D <nome>` | Deleta branch à força |
| `git checkout <branch>` | Navega entre branches |
| `git checkout -b <nome>` | Cria e muda para nova branch |
| `git switch <branch>` | Alterna branch (moderno) |
| `git switch -c <nome>` | Cria e alterna (moderno) |
| `git merge <branch>` | Une branches |
| `git merge --no-ff <branch>` | Merge sem fast-forward |
| `git rebase <branch>` | Reaplica commits sobre outra base |
| `git rebase -i HEAD~n` | Rebase interativo dos últimos n commits |

---

## Remotos

| Comando | Descrição |
|---|---|
| `git remote -v` | Lista remotos com URLs |
| `git remote add origin <url>` | Adiciona remote |
| `git remote set-url origin <url>` | Troca URL do remote (HTTPS ↔ SSH) |
| `git remote remove origin` | Remove remote |
| `git remote rename <antigo> <novo>` | Renomeia remote |
| `git push origin --delete <branch>` | Deleta branch no remoto |

---

## Histórico e inspeção

| Comando | Descrição |
|---|---|
| `git log` | Histórico de commits |
| `git log --oneline --graph --all` | Histórico compacto e visual |
| `git log -p <arquivo>` | Histórico de um arquivo |
| `git log --author="nome"` | Filtra por autor |
| `git diff` | Exibe diferenças não stagadas |
| `git diff --staged` | Diferenças já no stage |
| `git diff <branch1>..<branch2>` | Compara duas branches |
| `git show <hash>` | Mostra detalhes de um commit |
| `git blame <arquivo>` | Quem mudou cada linha |
| `git reflog` | Histórico do HEAD (salvavidas) |

---

## Utilitários

| Comando | Descrição |
|---|---|
| `git stash` | Salva mudanças temporárias |
| `git stash pop` | Restaura o último stash |
| `git stash list` | Lista stashes |
| `git cherry-pick <hash>` | Aplica commit específico |
| `git tag <nome>` | Cria tag leve |
| `git tag -a <nome> -m "msg"` | Cria tag anotada |
| `git worktree add <pasta> <branch>` | Múltiplas working trees |
| `git submodule add <url>` | Adiciona submódulo |
| `git submodule update --init --recursive` | Inicializa submódulos |
| `git clean -fd` | Remove arquivos não rastreados |
| `git reset --hard HEAD` | Descarta mudanças locais |
| `git reset --soft HEAD~1` | Desfaz último commit mantendo mudanças |
| `git revert <hash>` | Cria commit que desfaz outro |

---

## Dicas rápidas

| Situação | Comando |
|---|---|
| Ver qual remote está configurado | `git remote -v` |
| Trocar HTTPS → SSH | `git remote set-url origin git@github.com:user/repo.git` |
| Testar SSH no GitHub | `ssh -T git@github.com` |
| Ver email atual dos commits | `git config --get user.email` |
| Ver a config toda do projeto | `git config --local --list` |
| Ver a config global toda | `git config --global --list` |
| Descobrir onde uma config está definida | `git config --show-origin --get <chave>` |
| Desfazer `git add` de um arquivo | `git restore --staged <arquivo>` |
| Desfazer mudanças num arquivo | `git restore <arquivo>` |
| Voltar arquivo ao estado do último commit | `git checkout HEAD -- <arquivo>` |

---

## Erros comuns e como resolver

| Erro | Causa provável | Solução |
|---|---|---|
| `fatal: not a git repository` | Rodou comando fora de um repo | `git init` ou `cd` pra pasta certa |
| `error: src refspec main does not match any` | Branch `main` não existe ainda | `git branch -M main` |
| `fatal: 'origin' does not appear to be a git repository` | Remote não existe | `git remote add origin <url>` |
| `Password authentication is not supported` | GitHub não aceita senha | Use SSH ou PAT |
| `git: 'credential-manager' is not a git command` | Helper inválido configurado | `git config --unset credential.helper` |
| `Permission denied (publickey)` | Chave SSH não cadastrada | `ssh-keygen` + adicionar no GitHub |
| `Updates were rejected` | Remoto tem commits à frente | `git pull --rebase` |

---
