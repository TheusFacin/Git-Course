# Git Course

Este é um repositório teste para aprender como o git e o github funcionam

* [Comandos básicos](#comandos-básicos)
* [Indicadores](#indicadores)
  - [Linhas](#linhas)
  - [Arquivos](#arquivos)
* [Logs](#logs)
* [Diff](#diff)
* [Desfazendo Coisas](#desfazendo-coisas)
  - [Desfazendo um Commit](#desfazendo-um-commit)
  - [Revert](#revert)
* [Repositório Remoto](#repositório-remoto)
  - [Apagando remotamente](#apagando-remotamente)
* [Fork](#fork)
* [Branchs](#branchs)
* [Merge](#merge)
* [Rebase](#rebase)
* [Stash](#stash)

Para visualisar todos os tipos de formatação no markdown, acesse esse [link](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax)

## Comandos básicos

Iniciar um repositório
```
git init
```

Adicionar um arquivo
```
git add <nome do arquivo>
git add .
```

Visualisar os status dos arquivos
```
git status
```

Dar um commit 
```
git commit -m "Para apenas dar um commit"
git commit -am "Para adicionar todos os arquivos e dar commit"
```

## Indicadores

### Linhas

**Verde**         - Linha adicionada  
**Azul**          - Linha modificada  
**Seta vermelha** - Linha apagada  

### Arquivos

**U** - Untracked (não foi adicionado ainda)  
**A** - Added (adicionado mas não commitado)  
**M** - Modified (commitado e modificado)  

## Logs

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
git show <hash do commit>
```

## Diff

O diff mostra as diferenças entre os arquivos do último commit e os unstageds
```
git diff
```

Para listar somente os nomes dos arquivos modificados, usar
```
git diff --name-only
```

## Desfazendo coisas

Para desfazer as modificações de um arquivo unstaged, voltando ele para o estado do último commit, usa-se
```
git checkout <nome do arquivo>
```

Para dar unstaged num arquivo staged, basta usar
```
git reset HEAD <nome do arquivo>
```

### Desfazendo um commit

Para apenas desfazer o commit e deixar os arquivos intactos e em staged, pronto para fazer o commit novamente, usar
```
git reset --soft <hash do commit anterior>
```

Para desfazer o commit e voltar os arquivos para unstaged, usa-se
```
git reset --mixed <hash do commit anterior>
```

Para desfazer o commit e todas as alterações dos arquivos, utilizar
```
git reset --hard <hash do commit anterior>
```

### Revert

O revert serve para criar um novo commit revertendo as mudanças de um commit anterior

Por exemplo, digamos que acabamos de dar um commit e ele está sendo responsável por erros em produção, para voltarmos ao código anterior, sem apagar esse commit, usamos
```
git reset <hash do commit a ser revertido>
```

Assim, ele cria um novo commit sem as alterções desse selecionado

## Repositório remoto

Para linkar com um repositório do GitHub, basta usar os seguintes comandos
```
git remote add origin <endereço do repositório>
git push -u origin master
```

A partir daí é só usar
```
git push
```

Para baixar a última versão do repositório, utilizar
```
git pull
```

Para verificar os repositórios remotos conectados, usa-se
```
git remote
```

Para clonar um repositório para a máquina, usar
```
git clone <endereço do repositório> <diretório alvo>
```
### Apagando remotamente

Para apagar uma branch num repositório remoto, usa-se
```
git push origin :<nome da branch>
```

A mesma coisa para tags
```
git push origin :<nome da tag>
```

## Fork

O fork serve para trabalhar em um repositório de outra pessoa ou organização e depois enviar um pull request

Para isso deve-se acessar o repositório e clicar no botão fork

## Branchs

Para criar um branch, utiliza-se
```
git checkout -b <nome do branch>
```

Para verificar os branchs existentes, usar
```
git branch
```

Para navegar entre os branchs, utilizar
```
git checkout <nome do branch>
```

Para apagar um branch, usa-se
```
git branch -D <nome do branch>
```

## Merge

O merge une duas branchs diferentes criando um novo commit e mantendo as anteriores

```
git merge <branch a ser mesclado>
```

Pros   | Contras
:----: | :-----:
Não destroi commits | Cria um commit extra  
. | Deixa o histórico poluído

## Rebase

Move os commits para o branch de destino

```
git rebase <branch a ser mesclado>
```

Pros   | Contras
:----: | :-----:
Evita commits extras | Perde a ordem cronológica
Histórico linear |

## Stash

O git stash serve para armazenar mudanças em progresso sem ter que dar commit 

```
git stash
```

Para aplicar as mudanças armazenadas, usa-se
```
git stash aply
```

Para listar as mudanças, utilizar
```
git stash list
```

Para limpar todos os stashs armazenados, usar
```
git stash clear
```

## Alias

Para criar um alias de comando, usa-se
```
git config --global alias.<alias> <comando>
```

Assim, ao invés de usar `git <comando>`, usa-se `git <alias>`

## Tags

A tag pode ser usado para criar uma versão, por exemplo
```
git tag -a <tag> -m "<mensagem>"
```

Para apagar a tag, usa-se
```
git tag -d <tag>
```