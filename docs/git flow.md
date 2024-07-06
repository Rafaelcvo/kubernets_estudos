# Git Flow Guide

 Este guia fornece um passo a passo completo para usar o Git Flow, desde a criação de uma branch de feature até a criação de um release e a atualização do GitHub.

## Inicializar o Git Flow

Execute este comando apenas uma vez para configurar o Git Flow no seu repositório:

 ```bash
 git flow init
 ```

## Criar e Trabalhar em uma Feature Branch

1. **Mudar para a branch develop** (caso você esteja na main):

```bash
git checkout develop
```

2. **Criar uma nova feature branch**:

```bash
git flow feature start minha-feature
```

3. **Trabalhar na feature**:

## Faça suas alterações no código e comite:

```bash
 echo "Alguma alteração" >> exemplo.txt
 git add exemplo.txt
 git commit -m "Adiciona alguma alteração ao xemplo.txt"
```

4. **Finalizar a feature branch**:

```bash
git flow feature finish minha-feature
```

## Criar um Release

1. **Criar uma release branch**:

```bash
git flow release start 1.0.0
```

2. **Finalizar a release branch**:

```bash
git flow release finish 1.0.0
```

## Atualizar o Repositório no GitHub

Envie as mudanças para o repositório remoto:

```bash
git push origin main
git push origin develop
```


## Adicionar o arquivo ao Git
```bash
git add GIT_FLOW_GUIDE.md
```

## Comitar as mudanças
```bash
git commit -m "Adiciona guia de referência do Git Flow"
```

## Enviar para o repositório remoto
```bash
git push origin develop
```
