# Three.js Animated Galaxy

Proyecto de galaxia animada desarrollado con **Three.js**, **JavaScript** y **GLSL Shaders**.

El objetivo del proyecto es generar una galaxia procedural formada por miles de partículas, animadas directamente desde la GPU mediante shaders personalizados. Cada partícula representa una estrella con posición, color, tamaño y movimiento propio.

## Descripción

La galaxia se construye mediante código, sin usar modelos 3D importados.

Cada estrella se calcula matemáticamente usando ángulos, radios y valores aleatorios para crear una distribución en forma de espiral.

El resultado es una escena visualmente atractiva donde las partículas giran alrededor del centro, simulando el movimiento de una galaxia.

## Tecnologías utilizadas

- Three.js
- JavaScript
- WebGL
- GLSL
- Vite

## Cómo funciona

El proyecto genera una geometría de partículas usando **BufferGeometry**.

Cada partícula contiene información propia:

- Posición en el espacio 3D
- Color
- Tamaño individual
- Aleatoriedad para evitar una forma demasiado perfecta

La animación se realiza en el **vertex shader**, lo que permite mover miles de partículas de forma eficiente usando la GPU.

El aspecto visual de cada estrella se controla desde el **fragment shader**, donde cada partícula se dibuja como un punto luminoso en lugar de un cuadrado plano.

## Matemáticas principales

La posición de cada estrella se calcula usando trigonometría:

- **Math.cos()** calcula la posición en el eje X.
- **Math.sin()** calcula la posición en el eje Z.
- El radio determina la distancia de cada estrella al centro.
- El ángulo determina en qué dirección se coloca cada estrella.

Fórmula base:

    x = cos(angle) * radius
    z = sin(angle) * radius

Gracias a esto, las partículas pueden distribuirse alrededor del centro formando brazos de galaxia.

## Animación

La rotación de la galaxia se calcula en el shader usando el tiempo.

Las estrellas cercanas al centro giran más rápido, mientras que las estrellas más alejadas giran más despacio. Esto crea un efecto de espiral más natural.

Lógica principal:

    angleOffset = (1.0 / distanceToCenter) * uTime * speed

Esto significa que cuanto menor es la distancia al centro, mayor es la velocidad de rotación.

## Instalación

Instalar dependencias:

    npm install

Ejecutar el proyecto en local:

    npm run dev

Generar versión de producción:

    npm run build

## Objetivo del proyecto

Este proyecto forma parte de mi aprendizaje de Three.js y shaders, profundizando en conceptos como:

- Partículas
- Geometrías procedurales
- Shaders personalizados
- Animación en GPU
- Trigonometría aplicada a gráficos 3D
- Renderizado en tiempo real con WebGL

## Autor

Proyecto desarrollado por **David Llona**.
