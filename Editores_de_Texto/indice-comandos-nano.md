# Indice A-Z de Comandos do Nano

> Legenda: `^` = Ctrl | `M-` = Alt (Meta)

---

## A

### `Alt+A` — Definir ou remover marcacao (mark)
Inicia ou cancela a selecao de texto a partir da posicao do cursor. Equivalente a clicar e arrastar o mouse.
```
M-A
```

### `Alt+:` — Iniciar/parar gravacao de macro
Comeca ou encerra a gravacao de uma sequencia de teclas como macro para reproducao posterior.
```
M-:
```

### `Alt+;` — Reproduzir macro
Executa a macro gravada mais recentemente.
```
M-;
```

---

## B

### `Ctrl+B` — Busca retroativa (backward search)
Inicia uma busca pelo texto digitado, movendo-se para tras no documento.
```
^B
```

### `Alt+B` — Proxima ocorrencia para tras
Encontra a ocorrencia anterior do termo buscado.
```
M-B
```

### `Alt+Bsp` — Deletar palavra a esquerda
Apaga a palavra imediatamente antes do cursor.
```
M-Backspace
```

---

## C

### `Ctrl+C` — Exibir posicao do cursor
Mostra na barra de status a linha, coluna e posicao atual do cursor no arquivo.
```
^C
```

### `Alt+C` — Ativar/desativar informacao de posicao constante
Alterna a exibicao continua da posicao do cursor na barra de status.
```
M-C
```

### `Alt+3` — Comentar/descomentar linha ou regiao
Adiciona ou remove o caractere de comentario da linha atual ou da regiao selecionada.
```
M-3
```

### `Ctrl+]` — Autocompletar palavra
Completa a palavra sendo digitada com base nas palavras ja presentes no buffer.
```
^]
```

---

## D

### `Ctrl+D` — Deletar caractere sob o cursor
Remove o caractere na posicao atual do cursor (equivalente ao Delete).
```
^D
```

### `Alt+D` — Contar linhas, palavras e caracteres
Exibe estatisticas do buffer atual: numero de linhas, palavras e caracteres.
```
M-D
```

### `Ctrl+Del` — Deletar palavra a direita
Apaga a proxima palavra a partir do cursor.
```
^Del
```

### `Alt+Del` — Deletar linha atual
Remove completamente a linha onde o cursor esta posicionado.
```
M-Del
```

---

## E

### `Ctrl+E` — Ir ao fim da linha
Move o cursor para o ultimo caractere da linha atual.
```
^E
```

### `Alt+E` — Refazer ultima acao desfeita (redo)
Reaplica a ultima acao que foi desfeita com `Alt+U`.
```
M-E
```

### `Alt+End` — Ir para a ultima linha visivel
Move o cursor para a ultima linha exibida na janela atual (viewport).
```
M-End
```

---

## F

### `Ctrl+F` — Busca para frente (forward search)
Inicia uma busca pelo texto digitado, movendo-se para frente no documento.
```
^F
```

### `Alt+F` — Proxima ocorrencia para frente
Encontra a proxima ocorrencia do termo buscado.
```
M-F
```

---

## G

### `Ctrl+G` — Exibir ajuda (help)
Abre o texto de ajuda integrado do nano com a lista completa de atalhos.
```
^G
```

### `Alt+G` — Ir para linha especificada
Solicita um numero de linha e move o cursor diretamente para ela.
```
M-G
```

---

## H

### `Ctrl+H` — Deletar caractere antes do cursor
Remove o caractere imediatamente anterior ao cursor (equivalente ao Backspace).
```
^H
```

### `Alt+Home` — Ir para a primeira linha visivel
Move o cursor para a primeira linha exibida na janela atual (viewport).
```
M-Home
```

---

## I

### `Tab` — Indentar regiao marcada
Adiciona indentacao (tab ou espacos) em todas as linhas da regiao selecionada.
```
Tab
```

---

## J

### `Ctrl+J` — Justificar paragrafo ou regiao
Reformata o paragrafo atual (ou a regiao selecionada) para caber na largura da tela.
```
^J
```

### `Alt+J` — Justificar o buffer inteiro
Reformata todo o conteudo do arquivo aberto.
```
M-J
```

---

## K

### `Ctrl+K` — Recortar linha atual
Corta a linha inteira onde o cursor esta e a coloca no buffer de recorte.
```
^K
```

---

## L

### `Ctrl+L` — Atualizar a tela
Redesenha a interface do nano, util quando a exibicao e corrompida por saidas de outros programas.
```
^L
```

---

## M

### `Alt+\` — Ir para o inicio do buffer
Move o cursor para a primeira linha do arquivo.
```
M-\
```

### `Alt+/` — Ir para o fim do buffer
Move o cursor para a ultima linha do arquivo.
```
M-/
```

---

## N

### `Ctrl+N` — Descer uma linha
Move o cursor uma linha para baixo.
```
^N
```

### `Alt+N` — Ativar/desativar numeracao de linhas
Exibe ou oculta os numeros de linha na margem esquerda.
```
M-N
```

---

## O

### `Ctrl+O` — Salvar como (write file)
Solicita um nome de arquivo e salva o conteudo atual, sem fechar o editor.
```
^O
```

---

## P

### `Ctrl+P` — Subir uma linha
Move o cursor uma linha para cima.
```
^P
```

### `Alt+P` — Mostrar/ocultar espacos em branco
Torna visiveis os caracteres de espaco, tabulacao e quebra de linha.
```
M-P
```

---

## R

### `Ctrl+R` — Inserir arquivo no buffer atual
Abre um prompt para selecionar um arquivo e insere seu conteudo na posicao do cursor.
```
^R
```

### `Alt+R` — Iniciar sessao de substituicao (replace)
Permite buscar e substituir texto no arquivo. Pode-se confirmar cada substituicao ou aceitar todas.
```
M-R
```

---

## S

### `Ctrl+S` — Salvar arquivo atual
Salva o arquivo sem solicitar confirmacao de nome (somente se o arquivo ja tiver nome).
```
^S
```

### `Alt+S` — Ativar/desativar quebra de linha suave (softwrap)
Faz com que linhas longas sejam exibidas em multiplas linhas na tela, sem inserir quebras reais.
```
M-S
```

### `Shift+Tab` — Remover indentacao da regiao marcada
Remove um nivel de indentacao das linhas da regiao selecionada.
```
Shift+Tab
```

---

## T

### `Ctrl+T` — Executar comando externo
Abre um prompt para digitar e executar um comando do sistema dentro do nano.
```
^T
```

### `Ctrl+T Ctrl+S` — Verificacao ortografica (spell check)
Executa o verificador ortografico no texto do buffer atual (requer o pacote `spell` instalado).
```
^T ^S
```

### `Ctrl+T Ctrl+Y` — Verificacao de sintaxe
Executa um verificador de sintaxe no arquivo atual, se disponivel para o tipo de arquivo.
```
^T ^Y
```

### `Ctrl+T Ctrl+O` — Formatar arquivo
Executa um formatador automatico no buffer atual, se configurado.
```
^T ^O
```

### `Alt+T` — Recortar ate o fim do buffer
Corta todo o texto desde a posicao atual do cursor ate o final do arquivo.
```
M-T
```

---

## U

### `Ctrl+U` — Colar conteudo do buffer de recorte
Cola o texto que foi cortado ou copiado na posicao atual do cursor.
```
^U
```

### `Alt+U` — Desfazer ultima acao (undo)
Reverte a ultima modificacao feita no arquivo.
```
M-U
```

---

## V

### `Ctrl+V` — Descer uma pagina
Move o cursor uma pagina para baixo no arquivo.
```
^V
```

### `Alt+V` — Inserir proximo pressionamento literalmente (verbatim)
O proximo caractere digitado sera inserido como texto literal, sem ser interpretado como atalho.
```
M-V
```

---

## W

### `Ctrl+W` — Buscar texto (search)
Equivalente a `Ctrl+F` em muitas versoes: abre o prompt de busca para encontrar texto no arquivo.
```
^W
```

---

## X

### `Ctrl+X` — Fechar buffer / Sair do nano
Fecha o arquivo atual. Se houver alteracoes nao salvas, o nano perguntara se deseja salvar.
```
^X
```

### `Alt+X` — Mostrar/ocultar linhas de ajuda
Exibe ou oculta as duas linhas de atalhos na parte inferior da tela.
```
M-X
```

---

## Y

### `Ctrl+Y` — Subir uma pagina
Move o cursor uma pagina para cima no arquivo.
```
^Y
```

---

## Z

### `Alt+Z` — Mostrar/ocultar barras de informacao
Exibe ou oculta a barra de titulo e a barra de status, maximizando o espaco de edicao.
```
M-Z
```

---

## Referencia Rapida

| Atalho | Acao |
|---|---|
| `^S` | Salvar |
| `^O` | Salvar como |
| `^X` | Sair |
| `^K` | Recortar linha |
| `^U` | Colar |
| `Alt+6` | Copiar linha |
| `^F` / `^B` | Busca frente / tras |
| `M-R` | Substituir texto |
| `M-U` | Desfazer |
| `M-E` | Refazer |
| `^G` | Ajuda |
| `^C` | Posicao do cursor |
| `M-G` | Ir para linha |
| `^T` | Executar comando |
| `M-A` | Marcar texto |
| `^J` | Justificar paragrafo |

---

## Links Uteis

- [Documentacao Oficial do GNU nano](https://www.nano-editor.org/docs.php)
- [Cheatsheet Oficial de Atalhos](https://www.nano-editor.org/dist/latest/cheatsheet.html)
- [Manual Completo do nano](https://www.nano-editor.org/dist/latest/nano.html)
- [Configuracao do nanorc](https://www.nano-editor.org/dist/latest/nanorc.5.html)