# 🏟️ Complejo Deportivo Arena Viva - Landing Page

Este repositorio contiene el código fuente de una *landing page* desarrollada para un complejo deportivo ficticio. El proyecto forma parte de una evaluación práctica de desarrollo frontend, enfocada en la implementación de interfaces modernas, accesibles y responsivas asistidas por Inteligencia Artificial.

## 🚀 Características Principales

* **Diseño Responsive (Mobile-First):** Interfaz adaptable a dispositivos móviles, tablets y computadoras de escritorio.
* **Sistema de Diseño Personalizado:** Uso de la directiva `@theme` para aplicar la regla de color 60-30-10 (Dominante, Secundario, Acento) y colores semánticos.
* **Modo Oscuro (Dark Mode):** Alternancia manual entre tema claro y oscuro implementada con JavaScript y clases de Tailwind (`dark:`).
* **Componentes Interactivos:** Menú hamburguesa para navegación móvil y acordeón de Preguntas Frecuentes (FAQ).
* **Validación de Formularios:** Validación del lado del cliente (JavaScript puro) de campos obligatorios y formato de correo electrónico, con una notificación flotante (Toast) de éxito.
* **Accesibilidad (A11y):** Contrastes adecuados (4.5:1), estados de foco visibles (`focus:ring-2`) y uso de etiquetas estructurales (ARIA).

## 🤖 Prompt Maestro

Para la generación inicial del código base de este proyecto, se estructuró el siguiente *Prompt Maestro* siguiendo las mejores prácticas de ingeniería de prompts:

> **Rol:** Actúa como desarrollador frontend senior especializado en Tailwind CSS 4, diseño responsive y accesibilidad web.
> 
> **Contexto:** Voy a crear la landing page de "Complejo Deportivo Arena Viva", un centro deportivo que ofrece reservas de canchas sintéticas de fútbol, piscinas, pistas de tenis y canchas de voleibol. El objetivo del sitio es mostrar las instalaciones deportivas y captar solicitudes de reserva mediante un formulario.
> 
> **Tareas:** Construye una página web de una sola página con estas secciones en orden:
> 1. Navbar fija con el logo textual, enlaces de navegación, botón de modo oscuro y menú hamburguesa para móviles (funcional con JS).
> 2. Hero con título principal (H1), subtítulo, imagen de fondo oscurecida y botón "Reservar cancha".
> 3. Sección "Instalaciones" con un grid de tarjetas (1 columna en celular, 2 en tablet, 4 en desktop). Cada tarjeta debe tener imagen, título, descripción, precio por hora en pesos colombianos y efecto hover.
> 4. Sección "Nosotros" con un texto breve y una imagen representativa.
> 5. Preguntas frecuentes implementadas con un componente de acordeón interactivo con JavaScript.
> 6. Formulario de reserva pidiendo Nombre, Correo, Deporte a reservar y Fecha. Debe tener validación JS (campos obligatorios y formato de correo). Mostrar errores en texto rojo bajo cada input. Al ser exitoso, mostrar un componente "Toast" verde flotante que diga "Reserva solicitada con éxito" y desaparezca a los 4 segundos.
> 7. Footer sencillo con redes sociales y derechos reservados.
> 
> **Restricciones:** Usa únicamente HTML, Tailwind CSS 4 mediante su Play CDN oficial (`https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`) y JavaScript puro al final del body. No uses librerías externas. Define el tema con `@theme` dentro de `<style type="text/tailwindcss">` aplicando la regla 60-30-10: fondo claro `#F8FAFC` (60%), azul oscuro `#1E293B` (30%) y acento verde `#16A34A` (10%), además de colores de éxito y error. Usa las fuentes de Google Fonts Montserrat e Inter. El diseño debe ser mobile-first, accesible (contraste 4.5:1, focus states visibles `focus:ring-2`, textos alternativos en imágenes).
> 
> **Formato de salida:** Entrega un único bloque de código con el archivo `index.html` completo, indentado, con comentarios en español separando cada sección y la lógica JavaScript claramente explicada.

## 📖 Bitácora de Prompts (Iteraciones con IA)

Tras la generación inicial, se realizaron las siguientes 5 iteraciones principales para corregir errores y mejorar la interfaz:

| # | PROMPT DE AJUSTE ENVIADO | PROBLEMA QUE BUSCABA RESOLVER | RESULTADO OBTENIDO | ¿FUNCIONÓ? |
| :--- | :--- | :--- | :--- | :--- |
| 1 | *"El menú hamburguesa no se cierra cuando hago clic en uno de los enlaces hacia las secciones. Por favor, arregla el script."* | Mejorar la experiencia de usuario en móvil al navegar (Single Page App). | Se añadió un `forEach` en JS a `.mobile-link` que añade la clase `hidden` al contenedor. | Sí. |
| 2 | *"Las tarjetas de las instalaciones se ven muy simples. Añade un efecto hover que amplíe ligeramente la imagen interior sin desbordarse."* | Falta de interactividad visual en la sección de servicios. | Se aplicó `overflow-hidden` al contenedor y `group-hover:scale-110 transition duration-500` a la etiqueta `<img>`. | Sí. |
| 3 | *"El texto rojo de error del formulario deforma el diseño cuando aparece. Haz que aparezca abajo del input con un margen pequeño."* | Saltos de diseño (layout shift) bruscos por errores de validación. | Se usó `text-xs mt-1 hidden` para el error, controlando la aparición sin romper el padding de la tarjeta. | Sí. |
| 4 | *"El botón del acordeón de preguntas no muestra visualmente si está abierto o cerrado. Agrégale una flecha que gire."* | Poca claridad heurística (visibilidad del estado del sistema). | Se añadió un `<span>` con un ícono (▼) y lógica JS para rotarlo a 180deg cuando está abierto. | Sí. |
| 5 | *"El Toast verde de éxito aparece de golpe, haz que entre deslizándose desde abajo (animación de entrada)."* | La alerta visual se veía tosca y poco profesional. | Se combinaron clases Tailwind `translate-y-20 opacity-0` y un `setTimeout` en JS para manipularlas y crear un fade-in hacia arriba. | Sí. |

## 🛠️ Tecnologías Utilizadas

* **HTML5:** Estructura semántica.
* **Tailwind CSS v4:** Framework *utility-first* cargado mediante su Play CDN oficial.
* **JavaScript (Vanilla):** Lógica de interacción y validación, sin librerías externas.
* **Google Fonts:** Tipografías *Montserrat* e *Inter*.

## ⚙️ Instalación y Uso

1. Clona este repositorio o descarga el código.
2. No se requiere instalación de dependencias (npm/Node.js) ya que Tailwind se ejecuta mediante CDN.
3. Abre el archivo `index.html` directamente en tu navegador. 
4. *Nota:* Para ejecutar pruebas de Google Lighthouse, se recomienda abrir el proyecto usando una extensión como **Live Server** en Visual Studio Code para servirlo bajo el protocolo HTTP.

## 📝 Notas sobre la Validación W3C

Al analizar el código en el validador de la W3C, se presentarán dos advertencias relacionadas con el atributo `type="text/tailwindcss"` y la directiva `@theme`. Estos son falsos positivos inherentes al uso del Play CDN de Tailwind v4, ya que el validador estándar evalúa CSS tradicional y no reconoce el motor en tiempo de ejecución del framework. 

## 👨‍💻 Autor

**Juan Manuel Marin Castro**
*Estudiante de Ingeniería de Software*
