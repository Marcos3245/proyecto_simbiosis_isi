# Historias de usuario de búsqueda

| Campo | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Fecha | [dd/mm/aaaa] |
| Versión | [Versión de trabajo] |
| Estado | Borrador |

## Fuentes comunes

- [Acta de UC-21 Buscar recetas](../captura/acta-acuerdos-uc-21-buscar-recetas.md), v1.1, Vigente.
- [Catálogo de requisitos](catalogo-requisitos.md), UR-08 y FR pertinentes.
- [Modelo de casos de uso](../modelos/modelo-casos-de-uso.md), UC-21.

## Épica de búsqueda

Como usuario registrado, quiero buscar recetas en la plataforma mediante diferentes criterios, para gestionar mi dieta y controlar los síntomas de mi enfermedad.

**Estado:** descompuesta en US-01, US-02 y US-03. Conserva la necesidad conjunta.

## Justificación de la división

Dividir la búsqueda en tres historias, una por criterio, nos facilita la medición y comprobación de reusltados obtenibles, además de no perder la utilidad para el usuario de forma independiente.

## US-01

**Título:** Buscar recetas por ingrediente

Como usuario registrado, quiero poder buscar recetas por ingrediente incluido, para poder obtener un listado de recetas que usen ese ingrediente.

**Fuentes:** UR-08; UC-21; FR-86; acta, Criterios de búsqueda y Búsqueda sin resultados.

### Criterios de aceptación

- **CA-01.** Dado que existen dos recetas en la base de datos que contienen el ingrediente "zanahoria", cuando el usuario realiza una búsqueda por el ingrediente "zanahoria", entonces el sistema muestra las dos recetas existentes.
- **CA-02.** Dado que no existen recetas con el ingrediente "grosellas", cuando el usuario realiza una búsqueda con la palabra "grosellas", entonces el sistema indica la inexistencia de recetas con ese ingrediente.
- **CA-03.** Dado un ingrediente que no existe en la base de datos, cuando el usuario realiza una búsqueda por ese ingrediente, entonces el sistema muestra un error de que no se reconoce el ingrediente.

## US-02

**Título:** Buscar recetas por palabra o frase clave

Como usuario registrado, quiero buscar recetas por palabra o frase clave, para obtener un listado de recetas que cumplan mi criterio.

**Fuentes:** UR-08; UC-21; FR-85; acta, Criterios de búsqueda y Búsqueda sin resultados.

### Criterios de aceptación

- **CA-01.** Dadas diez recetas que contienen la frase clave "sin gluten", cuando el usuario realiza una búsqueda por la frase clave "sin gluten", entonces el sistema muestra las diez recetas que contienen esta frase.
- **CA-02.** Dado que no hay recetas con la palabra clave "montaña", cuando el usuario realiza una búsqueda por esta palabra clave, entonces el sistema informa de que no existen recetas con esta palabra clave.
- **CA-03.** Dado que existen recetas con la frase clave "sin sal" y otras que no la contienen, cuando el usuario busca por la frase clave "sin sal", entonces el sistema muestra únicamente aquellas recetas que tienen la frase "sin sal".

## US-03

**Título:** Buscar recetas por ingrediente excluido

Como usuario registrado, quiero buscar recetas excluyendo ingredientes, para obtener un listado de recetas que no tengan los ingredientes que no quiero usar.

**Fuentes:** UR-08; UC-21; FR-87; acta, Criterios de búsqueda y Búsqueda sin resultados.

### Criterios de aceptación

- **CA-01.** Dado que existen en la base de datos cinco recetas que no utilizan el ingrediente "aguacate", cuando el usuario realiza una búsqueda excluyendo este ingrediente, entonces el sistema muestra todas las recetas que existen.
- **CA-02.** Dado que existen recetas que no contienen ni "aguacate" ni "tomate", cuando el usuario realiza una búsqueda excluyendo estos ingredientes, entonces el sistema muestra todas las recetas que no contienen dichos ingredientes.
- **CA-03.** Dado que arroz está incluido y excluido, cuando el usuario realiza una búsqueda, entonces el sistema debe informar del error y no realizar la búsqueda.

## Revisión INVEST

La revisión abarca US-01, US-02 y US-03. «Aplicado» indica si se ha realizado la comprobación. «Cumple» indica si todas las historias cumplen el criterio. Si alguna no lo cumple, indicar «No» e identificar la historia y el motivo en la justificación. Si no se ha realizado la comprobación o faltan datos, indicar «Pendiente» en «Cumple».

| Criterio | Pregunta de revisión | Aplicado | Cumple | Justificación |
| --- | --- | --- | --- | --- |
| Independiente | ¿Puede implementarse cada historia y ofrecer un resultado útil sin implementar antes las otras historias del conjunto? Puede compartir infraestructura con ellas. | Sí | Sí | Las historias son independientes y pueden implementarse sin jerarquía; cada una aporta un valor propio. |
| Negociable | ¿Cada historia explica qué necesita la persona y deja margen para discutir los detalles de la solución, respetando los acuerdos confirmados? | Sí | Sí | En ningún momento se baja a nivel de diseño y únicamente se impone cómo debe comportarse el sistema y no cómo hacerlo |
| Valiosa | ¿La parte «para…» de cada historia explica el beneficio que obtiene la persona al usar esa capacidad? | Sí | Sí | Cada historia presenta una beneficio único para el usuario y cada funcionalidad de usará de forma independiente aunque puedan cooperar |
| Estimable | ¿Están claros el alcance y los datos necesarios para estimar el trabajo de cada historia? | Sí | Sí | Los criterios de aceptación y las actas limitan los accesos y los datos posibles |
| Pequeña | ¿Se centra cada historia en una única capacidad de alcance manejable? | Sí | Sí | Cada historia contempla una funcionalidad única e independiente el resto |
| Comprobable | ¿Los criterios de aceptación de cada historia describen acciones y resultados observables que permiten distinguir un comportamiento correcto de uno incorrecto? | Sí | Sí | Los criterios permiten comprobar de forma fiable la el correcto funcionamiento de la funcionalidad.  |

## Dudas pendientes

[Cuestiones pendientes de aclaración. Si no quedan cuestiones, indicar «Ninguna».]
