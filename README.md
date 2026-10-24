# 🏟️ Complejo Deportivo Arena Viva - Landing Page

Este repositorio contiene el código fuente de una *landing page* desarrollada para un complejo deportivo ficticio. El proyecto forma parte de una evaluación práctica de desarrollo frontend, enfocada en la implementación de interfaces modernas, accesibles y responsivas.

## 🚀 Características Principales

* **Diseño Responsive (Mobile-First):** Interfaz adaptable a dispositivos móviles, tablets y computadoras de escritorio.
* **Sistema de Diseño Personalizado:** Uso de la directiva `@theme` para aplicar la regla de color 60-30-10 (Dominante, Secundario, Acento) y colores semánticos.
* **Modo Oscuro (Dark Mode):** Alternancia manual entre tema claro y oscuro implementada con JavaScript y clases de Tailwind (`dark:`).
* **Componentes Interactivos:** 
  * Menú hamburguesa para navegación móvil.
  * Acordeón de Preguntas Frecuentes (FAQ).
* **Validación de Formularios:** Validación del lado del cliente (JavaScript puro) de campos obligatorios y formato de correo electrónico, con una notificación flotante (Toast) de éxito.
* **Accesibilidad (A11y):** Contrastes adecuados (4.5:1), estados de foco visibles (`focus:ring-2`) y uso de etiquetas estructurales.

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

Al analizar el código en el validador de la W3C, se presentarán dos advertencias relacionadas con el atributo `type="text/tailwindcss"` y la directiva `@theme`. Estos son falsos positivos inherentes al uso del Play CDN de Tailwind v4, ya que el validador estándar evalúa CSS tradicional y no reconoce el motor en tiempo de ejecución del framework. El código es completamente funcional.

## 👨‍💻 Autor

**[Tu Nombre]**
*Estudiante de Ingeniería de Sistemas*
