# Índice A–Z de Comandos Git

---

## A

### `git add`
Adiciona arquivo(s) à área de stage para o próximo commit.
```bash
git add [file]      # Adiciona um arquivo específico
git add .           # Adiciona todos os arquivos modificados
```

### `git alias` *(via config)*
Cria atalhos para comandos Git.
```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

---

## B

### `git branch`
Gerencia branches locais e remotas.
```bash
git branch                 # Lista branches locais
git branch -av             # Lista todas as branches (local e remota)
git branch -vv             # Lista branches com seus upstreams
git branch -r              # Lista apenas branches remotas
git branch -d my_branch    # Deleta a branch especificada
git branch -m <novo_nome>  # Renomeia a branch atual
```

---

## C

### `git checkout`
Navega entre branches ou restaura arquivos.
```bash
git checkout my_branch          # Muda para a branch especificada
git checkout -b new_branch      # Cria e muda para nova branch
git checkout -                  # Volta para a branch anterior
git checkout <branch> -- <file> # Obtém um arquivo de outra branch
git checkout <hash>             # Restaura a partir de um hash (reflog)
```

### `git cherry-pick`
Aplica um commit específico de outra branch na branch atual.
```bash
git cherry-pick [commit_id]
git cherry-pick <commit_hash>
```

### `git clone`
Clona um repositório remoto.
```bash
git clone git_url                   # Clona na pasta padrão
git clone git_url my_directory      # Clona em pasta específica
git clone --recursive <url>         # Clona com submódulos
```

### `git commit`
Registra as mudanças staged no histórico.
```bash
git commit -m "mensagem"          # Commit com mensagem
git commit -am "mensagem"         # Commit de todos os arquivos rastreados
git commit --amend -m "nova msg"  # Reescreve a mensagem do último commit
git commit --amend --no-edit      # Altera o último commit sem mudar a mensagem
```

### `git config`
Configura opções do Git.
```bash
git config --global user.name "nome"
git config --global user.email "email"
git config --global color.ui auto
git config --global --edit        # Abre o arquivo de configuração global
```

---

## D

### `git diff`
Mostra diferenças entre estados do repositório.
```bash
git diff                    # Diff do que mudou mas não foi staged
git diff --staged           # Diff do que está staged mas não commitado
git diff branchB...branchA  # Diff do que está em A mas não em B
```

---

## F

### `git fetch`
Baixa branches e dados do repositório remoto.
```bash
git fetch [alias]
```

---

## I

### `.gitignore`
Arquivo que especifica quais arquivos/pastas o Git deve ignorar.
```
/logs/*
!logs/.gitkeep
.DS_store
node_modules
.sass-cache
```

---

## L

### `git log`
Exibe o histórico de commits.
```bash
git log                                            # Histórico da branch ativa
git log branchB..branchA                           # Commits em A que não estão em B
git log --follow [file]                            # Commits que alteraram um arquivo
git log --graph --decorate --all                   # Visualização gráfica de todas as branches
git log --pretty=oneline --graph --decorate --all  # Visualização compacta e visual
git log --stat -M                                  # Commits com indicação de caminhos movidos
git log --name-only <commit-id>                    # Arquivos alterados em um commit
git log --no-merges --name-only                    # Arquivos alterados (excluindo merges)
git log -<número>                                  # Limita aos últimos N commits
git log -n <número>                                # Limita aos últimos N commits (alternativo)
git log --max-count=<número>                       # Máximo de N commits
git log --after="AAAA-MM-DD HH:MM:SS ±HHMM"        # Commits mais recentes que uma data
git log --before="AAAA-MM-DD HH:MM:SS ±HHMM"       # Commits mais antigos que uma data
git log --author=<padrão>                          # Filtra por autor
git log --grep=<padrão>                            # Filtra por mensagem de commit
git log -S'<termo>'                                # Busca por conteúdo alterado
git log -p <arquivo>                               # Mudanças ao longo do tempo em um arquivo
git log --graph --decorate                         # Grafo da branch atual
git log --graph --decorate <branch>                # Grafo de uma branch específica
git log --graph --decorate <B>..<A>                # Grafo: commits em A não em B
```

---

## M

### `git merge`
Une uma branch na branch atual.
```bash
git merge branchA                     # Merge padrão
git merge --no-ff [alias]/[branch]    # Sem fast-forward
git merge --ff-only [alias]/[branch]  # Apenas fast-forward
git merge [alias]/[branch]            # Merge de branch remota
```

### `git mv`
Move ou renomeia um arquivo e registra a mudança.
```bash
git mv [caminho-existente] [novo-caminho]
```

---

## P

### `git pull`
Baixa e integra mudanças da branch remota rastreada.
```bash
git pull
```

### `git push`
Envia commits locais para o repositório remoto.
```bash
git push [alias] [branch]
git push origin -u <novo_nome>      # Push e define upstream
git push origin --delete <antiga>   # Deleta branch remota
```

---

## R

### `git rebase`
Reaplicar commits da branch atual sobre outra branch.
```bash
git rebase [branch]
```

### `git reflog`
Exibe o histórico de movimentação de HEAD e branches.
```bash
git reflog
git checkout <hash_do_commit_ou_branch>  # Restaura a partir do reflog
```

### `git remote`
Gerencia repositórios remotos.
```bash
git remote                          # Lista nomes dos remotos
git remote -v                       # Lista nomes e URLs
git remote add [alias] [url]        # Adiciona um remoto
git remote rm [nome]                # Remove um remoto
git remote set-url origin [url]     # Altera a URL do remoto
```

### `git reset`
Desfaz mudanças no stage ou no histórico.
```bash
git reset [file]      # Remove arquivo do stage (mantém mudanças)
git reset --hard      # Reverte tudo para o último commit
```

### `git restore`
Restaura arquivos no working directory ou stage.
```bash
git restore [file]           # Descarta mudanças não staged
git restore --staged [file]  # Remove do stage (mantém mudanças)
```

### `git rm`
Remove arquivo do projeto e registra a remoção para commit.
```bash
git rm [file]
```

---

## S

### `git show`
Exibe qualquer objeto Git em formato legível.
```bash
git show [SHA]
```

### `git stash`
Salva e restaura mudanças temporariamente.
```bash
git stash           # Salva mudanças modificadas e staged
git stash list      # Lista o stack de stashes
git stash pop       # Aplica o stash mais recente
git stash drop      # Descarta o stash mais recente
```

### `git status`
Mostra o estado dos arquivos no working directory e stage.
```bash
git status
```

### `git submodule`
Gerencia submódulos dentro do repositório.
```bash
git submodule add <url> <caminho>       # Adiciona submódulo
git submodule update                    # Atualiza submódulos
git submodule update --remote           # Atualiza com commits mais recentes
git submodule deinit <caminho>          # Remove submódulo (passo 1)
# Seguido de: git rm <caminho> e git commit
```

---

## T

### `git tag`
Marca o commit atual com uma tag.
```bash
git tag my_tag
```

---

## W

### `git worktree`
Gerencia múltiplas working trees vinculadas ao mesmo repositório.
```bash
git worktree add <caminho> [<branch>]      # Cria nova working tree
git worktree list                          # Lista todas as working trees
git worktree remove <caminho>              # Remove uma working tree
git worktree prune                         # Limpa working trees obsoletas
git worktree move <caminho_antigo> <novo>  # Move uma working tree
```

---

## Links Úteis

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [Referência Completa de Comandos](https://git-scm.com/docs)
- [Pro Git — Livro Gratuito Oficial](https://git-scm.com/book/pt-br/v2)
- [Git Cheat Sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)