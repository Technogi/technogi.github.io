---
layout: post
title:  "Software Testing"
date:   2017-11-01 23:03:05
description: Software Testing.
categories:
- micro trainning
- software
- testing
permalink: software-testing
author: Juan Francisco
---
## Humanos (imperfectos) desarrollando/utilizando software (perfecto)
- Al ser humanos por naturaleza cometemos errores.
- El Software a construir es cada vez más especializado y complejo, así como los requerimientos para su desarrollo y construcción.
- Desarrolladores introducen bugs/errors en la programación.
- Ineficiente análisis, diseño, interpetración y construcción.
- El usuario final no tiene un completo conocimiento del uso del Software (Plataforma/App/WebApp).
- Se efectua un uso incorrecto uso del Software (Maliciosamente).
- Se estresa el Software en condiciones para las cuales no fue diseñado.
- Diferentes setups y ambientes

## Impacto de Bugs/Errors en Software
- Los errores tienen un impacto en el Software, así cómo en las Personas que lo utilizan:
  - Poco importante
    - Texto mal redactado.
    - Redondeos en Montos (Compra, Venta de Productos).
  - Costoso en el rubro económico
    - La organización invierte en el Software para generar ganancias y/o reducir costos.
  - Peligroso
    - Atenta contra la vida, bienestar e integridad de las personas.

## Cómo reduzco y mitigo los riesgos
- Pruebas, pruebas y más pruebas
  - Existen muchos tipos de pruebas, incluso gente especializada en éste rubro.
    - Unit testing
    - Integration testing
    - System testing
    - User acceptance testing
- Automatizar la mayor cantidad de pruebas (sin caer en lo excesivo, por cuestiones de mantenimiento).
  - Pyramid Testing Model
    - Unit
    - Integration
    - Component
    - End to End (E2E)
    - Exploratory
- Emplear las herramientas idóneas para cada tipo de prueba.
- Probar múltiples escenarios:
  - No conformarse con el happy path
  - Probar siempre escenarios de excepción (contemplando escenarios reales y poniendonos el sombrero de tester así cómo de usuario)
  - Probar con distintos valores 
    - Frontera: mínimos, medios, máximos
    - Erróneos
    - Faltantes

## En mi desarrollo ¿Qué pruebo?
- Acceso a datos (DAO)
  - Un querie muy complejo
  - Un querie muy abstracto
- Métodos de negocio (Services/Domain)
  - Métodos con varias Reglas de Negocio.
  - Métodos con Reglas de Negocio o funcionalidad importantes.
  - Métodos con gran cantidad de Excepciones.
  - Métodos con múltiples caminos.
  - Métodos con datos sensibles, de alto impacto, o trascendencia.
  - Probar happy path y múltiples escenarios
  - Métodos con dependencias a otros servicios (microservicios, apis, sistemas o servicios externos)
    - No probar la funcionalidad de la dependencia, más bien simular la dependencia:
      - Mocks
      - Stubs
  - Métodos relacionados a la seguridad del sistema
- Rest Endpoints (APIs)
  - Endpoints con gran cantidad de Excepciones.
  - Endpoints con múltiples caminos.
  - Endpoints con datos sensibles, de alto impacto, o trascendencia.
  - Endpoints con dependencias a otros servicios (microservicios, apis, sistemas o servicios externos)
  - Endpoints relacionados a la seguridad del sistema
- Interfaz de Usuario
  - Widgets o Elementos con comportamiento especial
  - Aspectos de seguridad
- Apoyarme siempre de un buen framework para testing
- Mecanismos de abstracción
  - Dummy
  - Fake
  - Stubs
  - Spies
  - Mocks
- Las dependencias a Middleware, Componentes se pueden embeber en la misma prueba, o bien levantar un ambiente idóneo para probar los escenarios necesarios.
  - Data Bases
  - Work Queues
  - Stream Channels
  - Schedulers
  - Others

## Extras
- Realizar pruebas no garantiza un Software Perfecto ni libre de bugs/errores, más bien provee la identificación y mitigación de estos.
- Genera un sentido de bienestar con uno mismo y con en el usuario final.
- La automatización de pruebas se traduce en:
  - Incremento en el costo del desarrollo del Software
    - Al inicio se invierte mucho tiempo en la automatización de las pruebas.
    - En ocasiones existe más código para probar el Software que el código del propio Software
  - Reduce el tiempo de las pruebas
  - Garantiza la adición, o en su defecto la detección de bugs/errors en la refactorización de código o adición de nueva funcionalidad.

## Enlaces recomendados
- [4 Types of Software Testing and When You Should Use Them](https://www.process.st/types-of-software-testing/)
- [Why is software testing so important? How to share the value with your team](https://www.atlassian.com/blog/software-teams/why-software-testing-is-important)
- [Why Test Software and APIs?](https://www.soapui.org/testing-dojo/world-of-api-testing/why-test.html)
- [TestPyramid](https://martinfowler.com/bliki/TestPyramid.html)
- [The Forgotten Layer of the Test Automation Pyramid](https://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid)
- [Testing Strategies in a Microservice Architecture](https://martinfowler.com/articles/microservice-testing/)
- [Testing Microservices](http://www.hamvocke.com/blog/testing-microservices/)
- [The Testing Pyramid](http://www.agilenutshell.com/episodes/41-testing-pyramid)
- [Mocks Aren't Stubs](https://martinfowler.com/articles/mocksArentStubs.html)