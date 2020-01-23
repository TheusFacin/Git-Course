#Git Course

Este é um repositório teste para aprender como o git e o github funcionam

[Comandos básicos](#comandos-básicos)
[Indicadores](#indicadores)
[Logs](#logs)
[Diff](#diff)

##Comandos básicos

Iniciar um repositório
```
git init
```

Adicionar um arquivo
```
git add [nome do arquivo]
git add .
```

Visualisar os status dos arquivos
```
git status
```

Dar um commit 
```
git commit -m "Mensagem do que foi alterado"
```

##Indicadores

####Linhas

**Verde**         - Linha adicionada
**Azul**          - Linha modificada
**Seta vermelha** - Linha apagada

####Arquivos

**U** - Untracked (não foi adicionado ainda)
**A** - Added (adicionado mas não commitado)
**M** - Modified (commitado e modificado)

Para visualisar todos os tipos de formatação no markdown, acesse esse [link](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax)

##Logs

Para dar um log mostrando cada commit, o autor, a data e a mensagem, basta usar
```
git log
```

Para mostrar detalhes mais avançados, como branchs e merges, usa-se
```
git log --decorate
```

Para filtrar pelo autor, utilizar
```
git log --author="Matheus"
```

Para um log mais básico, mostrando apenas os autores (em ordem alfabética) e seus commits (apenas as mensagens), usa-se
```
git shortlog
```

Para mostrar os autores e o número de commits de cada um, utiliza-se
```
git shortlog -sn
```

Para visualisar de forma gráfica os branchs e versões, basta usar
```
git log --graph
```

Para visualisar detalhes de uma commit, usar
```
git show [hash do commit]
```

##Diff

O diff mostra as diferenças entre os arquivos do último commit e os modificados
```
git diff
```

Para listar somente os nomes dos arquivos modificados, usar
```
git diff --name-only
```

