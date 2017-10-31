---
layout: post
title:  "¿Como lidiar con un BUG?"
date:   2017-10-30 17:10:00
description: Como tratar errores [Desarrolladores].
categories:
- micro trainning
- error
- code
- bug
- dev
permalink: bug-handling
author: Carlos
---
## No grito, no corro no empujo

- ¿Que pasa? ¿Que debería pasar?
- Pedir detalles para poder reproducir

## Encontrar el problema

- Lograr reproducir el error
- Lograr repoducirlo consistentemente
- Encontrar patrones
- Acotar el error

## Deslinde de responabilidades

- ¿Es verdaderamente un errors?
- ¿Yo lo puedo arreglar?
- ¿Quien lo puede resolver?
- ¿Fué provocado por el último cambio?

## Resolver el error

- Crear rama para investigar el error
- Crear rama para resolver el error
- Activar logs y hacer un rastreo operativo
- LEER las excepciones
- Hacer rastreo por código

## Una vez resuelto el bug

- Crear la/las preubas que automaticen el escenario que genera el bug
- Validar el resolución del bug en producción

## Extra

- Utilicen herramientas de debug