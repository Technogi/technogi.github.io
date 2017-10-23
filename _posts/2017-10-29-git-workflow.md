---
layout: post
title:  "Git Workflow"
date:   2017-10-20 23:56:45
description: Git workflow standar.
categories:
- micro trainning
- git
permalink: git-workflow
author: Carlos
---
## Reglas
- Se trabaja sobre un branch por featur/bug de JIRA
- El nombre del branch es el mismo del bug que ataca
- Una vez terminado se debe hacer un merge sobre master
- Durante el desarrollo del feature / bug se debe de hacer rebase
- Al terminar el desarrollo se debe hacer un merge
- los rebases se deben de hacer al menos una vez al día
- Se debe hacer push sobre el branch dos veces al día mínimo

## Proceso general
```
git checkout master
git fetch origin
git merge master
```

## Como hacer un branch nuevo
```
git checkout -b PRJ-123-awesome-feature
```

## Como hacer rebase
```
git fetch origin
git rebase origin/master
```
## Como hacer el merge final
```
git rebase -i origin/master
git checkout master
git pull origin master

git merge --no-ff PRJ-123-awesome-feature
```

## Videos recomendados
- [It' not "pure CI"](https://youtu.be/9SZ7kSQ2424)
- [What ir a pull request](https://youtu.be/B78AdLNZBQQ)

