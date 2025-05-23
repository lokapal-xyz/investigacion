---
date: '2025-03-09T16:43:23-03:00'
draft: false
title: 'El Confinamiento en las DAOs: Motivos, Rasgos y Desaciertos'
cover:
  image: "img/Wooden_fence_in_Si_Phan_Don.jpg"
tags:
- dao
- confinado
- no-confinado
- confinamiento
---

Las DAOs son inherentemente interactivas, ya que surgen como una respuesta a las necesidades de gobernanza en el espacio Web3. Pero estas interacciones pueden alterar radicalmente el comportamiento y los objetivos de una DAO. Los límites que una DAO establece sobre su interactividad son cruciales, pero muchas veces pasan desapercibidos. Normalizarlos o ignorarlos puede sabotear cualquier DAO, e incluso dejarla expuesta a ataques.

Compartiremos un conjunto de conceptos que pueden ayudar a visibilizar el confinamiento de una DAO y promover su éxito.

---

## Confinado / No Confinado

Los límites de un sistema son el resultado de sus componentes y de su comportamiento. En el caso de las DAOs, sus contratos inteligentes, la arquitectura de control de acceso y la infraestructura de red son algunos de los componentes que condicionarán su interactividad. No vamos a profundizar en cómo cada componente maneja el confinamiento, sino en la estructura de límites en sí. También es importante recordar que los límites afectan no sólo el comportamiento on-chain, sino también su posible integración con mecanismos off-chain, estructuras legales y gobernanza en el mundo real.

Por defecto, las DAOs están abiertas a la interacción externa. La mayoría de ellas tienen sistemas de votación basados en tokens que permiten a cualquiera con acceso a dichos tokens participar en su gobernanza. Además, las redes compatibles con la EVM son la norma para crear una DAO, lo que hace que sus contratos inteligentes sean ampliamente legibles. Llamaremos **DAO no confinada** a una que implemente este tipo de estructura de límites abiertos. Por lo tanto, si estamos interactuando con una DAO, *es razonable asumir en principio que no está confinada*. Un examen más detallado especificará su estructura real de límites.

Por otro lado, una **DAO confinada** implementa restricciones en su nivel de interactividad. Esto puede expresarse mediante sistemas de votación cerrados, redes incompatibles con la EVM, contratos no actualizables, etc. Algunas de estas restricciones son difíciles de implementar, lo que desincentiva a las DAOs confinadas y reduce su frecuencia. La terminología confinada/no confinada puede aplicarse tanto a las **intenciones** como a la **configuración** de una DAO. Proponemos una distinción entre el confinamiento como **rasgo** (basado en los componentes) y como **motivo** (basado en prioridades de diseño).

---

## El Confinamiento Como Rasgo

La mayoría de las veces podemos evaluar el confinamiento de una DAO examinando sus **componentes**. Algunos son directos: los sistemas de control de acceso cierran los límites de la DAO, inclinándola hacia la categoría **confinada**. Otros son más problemáticos: la interoperabilidad entre cadenas es un rasgo **no confinado**, pero puede requerir restricciones en otras áreas para evitar ataques.

Esta complejidad requiere un **espectro de confinamiento**, uno que pueda considerar cómo cada componente intenta orientar a la DAO hacia lo confinado o lo no confinado. Además, la gobernanza, los mecanismos de votación y los contratos inteligentes de una DAO pueden desarrollarse con el tiempo. Estos cambios modificarán su posición dentro del espectro. El confinamiento de una DAO puede llegar a ser tan complejo que puede requerir analizar varias **capas** del espectro, cada una de ellas con aspectos específicos de su interactividad.

```mermaid
%%{init: {"quadrantChart": {"pointLabelFontSize": 16}}}%%
quadrantChart
    title Espectro de Confinamiento (Ejemplo)
    x-axis Confinado --> No Confinado
    y-axis Impacto On-Chain --> Impacto Off-chain
    Red No-EVM: [0.20, 0.5]
    Sistema de Votacion con Tokens: [0.68, 0.5]
    Administracion de RR.PP.: [0.65, 0.69]
    Potencial de Actualizacion: [0.70, 0.20]
    Control de Accesos: [0.20, 0.34]
    Anonimato de Miembros: [0.30, 0.78]
```

Tan importante como este espectro es incorporar a nuestro análisis los principios de diseño y las motivaciones que afectan los límites de una DAO.

---

## El Confinamiento Como Motivo

Durante su etapa de diseño, cualquier DAO debe tomar decisiones importantes que afectarán sus resultados. Estas decisiones pueden tener una dimensión de confinamiento, incluso si sus diseñadores no son conscientes de ello. Por ejemplo, elegir una red L2 reducirá los costos operativos. Esta elección puede realizarse por motivos estrictamente económicos, pero también puede ser una decisión intencional para fomentar la participación en la gobernanza. Si este último es el caso, nos encontramos con una **DAO no confinada**, no determinada por sus componentes sino por su motivación de diseño.

En este aspecto del confinamiento, confinado y no confinado son elecciones **binarias**. Las **prioridades** de una DAO se convierten en el atributo principal para el análisis. A pesar de que cada decisión de desarrollo tiene su influencia, se forma una jerarquía de prioridades, ya sea de forma intencional o como resultado de las elecciones de diseño. Y esta jerarquía apuntará hacia un resultado confinado o no confinado. Las prioridades de confinamiento pueden estar segmentadas: una DAO podría aspirar a no estar confinada on-chain, pero restringir su interactividad off-chain.

| **ASPECTO DE CONFINAMIENTO** | **ATRIBUTO PRINCIPAL** | **DINAMICA DE CONFINAMIENTO** |
|---|---|---|
| Rasgo | Componentes | Espectro |
| Motivo | Prioridades | Binario |

Una evaluación defectuosa de los componentes y prioridades de una DAO nos llevará a gestionar mal su diseño y desarrollo, como veremos a continuación.

---

## Desaciertos en el Confinamiento 

Si las prioridades de una DAO no están bien establecidas, no hay una base clara para orientar las decisiones. Nuestra falta de conciencia fomentará falsas expectativas y una capacidad de respuesta deficiente. Por ejemplo: el control de acceso es una gran herramienta para limitar la interactividad. Pero podemos configurarlo de forma descuidada si no somos conscientes de la prioridad que está sirviendo. Si lo agregamos como parte de una lista de tareas en lugar de como una prioridad clara, no podemos sorprendernos cuando un administrador pierda sus llaves y terminemos sin acceso.

Pero esa no es la única forma en que puede gestionarse mal el confinamiento. Volvamos al ejemplo de la red L2. Incluso si una DAO elige una L2 por motivaciones no confinadas, esto puede salir mal. Aunque una L2 sea más barata operativamente, también es más difícil de operar para usuarios sin experiencia. Esto puede crear una incongruencia entre los motivos y los rasgos del confinamiento, lo que lleva a expectativas incumplidas en el rendimiento de la DAO.

La incongruencia también puede producirse incluso si las prioridades están bien establecidas y ejecutadas. Por ejemplo, una DAO podría priorizar el anonimato de sus miembros después de su lanzamiento. Pero si no se establecieron medidas adecuadas desde el inicio, los administradores podrían haber dejado rastros de sus identidades. En el futuro, ese desacierto inicial podría exponer a sus miembros por fuera de la red. Este es solo un pequeño ejemplo de la abundancia de formas en que el confinamiento suele gestionarse mal. Antes de terminar, repasemos un caso de estudio para desarrollar mejor nuestra terminología.

---

## Caso de Estudio: DAO DAO

El framework [**DAO DAO**](https://daodao.zone/) permite la creación de DAOs en el ecosistema Cosmos y utiliza Rust para sus contratos inteligentes. Cosmos y Rust son poco comunes, lo que restringe la interacción con "agentes externos". Se trata claramente de un framework **confinado**, al menos en cuanto a rasgos. Sería posible construir con DAO DAO una plataforma no confinada, pero estaría *nadando contra la corriente*.

Las DAOs creadas con DAO DAO se ubicarán en un espectro de confinamiento, pero sus componentes — de forma intencional o no intencional — priorizan fuertemente el distanciamiento del ecosistema blockchain y más allá. Este ejemplo también ofrece un aspecto interesante del confinamiento. Si en el futuro Cosmos y Rust se convierten en opciones predominantes, las DAOs construidas con DAO DAO podrían cambiar su clasificación de confinamiento. Esto refuerza nuestro argumento sobre la complejidad de los límites en las DAOs, que nunca son estáticos.

![banner](../../img/banner.png)

Hemos cubierto algunos aspectos clave del confinamiento en las DAOs y dos términos que pueden ayudar en el análisis de sus límites: confinada y no confinada. Como pudieron ver, este tema está lejos de agotarse; quedan muchas vías de exploración activas. Esperamos que este marco les haya resultado útil, y los invitamos a aplicarlo al analizar DAOs. Sigan en contacto con **DAO Horizontes** para futuras publicaciones que ampliarán estas ideas.

¿Tienen preguntas o sugerencias? Por favor contacten a [**Lokapal Investigación**](../../contacto/) y sigamos construyendo un mejor horizonte para las DAOs. ¡Gracias!

---

*Imagen de portada por Basile Morin desde [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Wooden_fence_in_Si_Phan_Don.jpg). Licenciado bajo [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)