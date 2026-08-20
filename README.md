# 📐 Plan PAP · Diseño de Interiores · IDC

![Versión](https://img.shields.io/badge/Versión-1.0.0-009c9d)
![HTML5](https://img.shields.io/badge/HTML5-Semántico-E34F26?logo=html5)
![CSS3](https://img.shields.io/badge/CSS3-Animaciones-1572B6?logo=css3)
![JavaScript](https://img.shields.io/badge/JS-Vanilla-F7DF1E?logo=javascript)

Interfaz web interactiva y accesible diseñada para la estructuración, formulación y generación del **Plan del Proyecto de Aplicación Profesional (PAP)** del programa de Diseño de Interiores del **Instituto de Diseño y Comunicación (IDC)**.

---

## 🎯 Objetivo del Proyecto

Proporcionar a los estudiantes de Diseño de Interiores una herramienta digital intuitiva y profesional que guíe paso a paso la elaboración de su proyecto final. El sistema aplica principios de diseño centrado en el usuario asegurando una experiencia fluida y fuertemente educativa.

---

## ✨ Características Principales

* **Formulario Dinámico:** Gestión dinámica de integrantes (hasta múltiples autores) y campos requeridos para la correcta formulación del plan.
* **Autoguardado Local:** Función de guardado automático (borrador) integrada con el `localStorage` del navegador.
* **Diseño Accesible y Responsivo:** Diseño semántico y completamente adaptable a pantallas de móviles, tablets y escritorio.
* **Estilos Visuales Avanzados:** 
    * Tarjetas con efectos de refracción holográfica (`.param-card`).
    * Componentes interactivos en 3D (*Flip cards*) para las secciones de apéndices.
    * Botón de generación con animación de líquido envolvente.
* **Gráficos Interactivos:** Integración con **Chart.js** para la visualización de métricas y datos de los proyectos.
* **Soporte PWA (Progressive Web App):** Capacidad de instalación nativa en el dispositivo de los usuarios.
* **Optimizado para Impresión:** Hoja de estilos de impresión (`@media print`) específicamente diseñada para limpiar la interfaz, esconder elementos interactivos (menús, botones) y permitir exportar en formato PDF de manera limpia y tipográficamente correcta.

---

## 🛠️ Tecnologías y Recursos Utilizados

* **Front-end:** HTML5, CSS3 (Custom Properties, Grid/Flexbox) y Vanilla JavaScript (ES6+).
* **Frameworks/Librerías Auxiliares:** Bootstrap 5 (Base y utilidades).
* **Visualización de Datos:** Chart.js.
* **Tipografía Institucional:** *Bricolage Grotesque* (Títulos), *Manrope* (Lectura) y *JetBrains Mono* (Código).
* **Paleta de Colores:** Turquesa IDC (`#009c9d`), Azul (`#0072b9`) y Naranja de acento (`#f3a100`).

---

## 🚀 Instalación y Despliegue

Este proyecto no requiere de instalaciones complejas ni dependencias de backend, dado que se ejecuta 100% en el entorno del cliente web.

1.  Descarga los archivos del repositorio o realiza un `git clone`.
2.  Abre el archivo principal `index.html` en cualquier navegador web moderno (Google Chrome, Mozilla Firefox, Safari, Microsoft Edge).
3.  *(Opcional)* Para testear el "Botón de instalación PWA" en un entorno seguro, sirve la carpeta a través de un servidor HTTP local (por ejemplo, con la extensión *Live Server* de Visual Studio Code o usando `npx serve`).

---

## 👨‍🏫 Autoría

Desarrollado y estructurado por:
**Mario Rafael Quiroz Martínez**
*Docente y Especialista Técnico* Instituto de Diseño y Comunicación (IDC)