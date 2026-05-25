# DUSHI Fragance - E-commerce Profesional & Asesoría Sensorial

¡Bienvenido al e-commerce profesional y portal corporativo oficial de **DUSHI Fragance**! Este es un proyecto web moderno, interactivo y de alta fidelidad estética, diseñado bajo una arquitectura de capas modular. La plataforma está orientada a la venta y personalización de perfumería y cosmética fina a partir del análisis del pH de la piel y las preferencias individuales del cliente.

---

## 🌟 Propuesta de Valor y Marca

**DUSHI** es una palabra de origen caribeño (del idioma papiamento) que evoca *dulzura*, *cariño*, *sofisticación*, *sexy* y *agradable*. Fundada en **2018**, la marca tiene la visión de liderar la perfumería personalizada en Colombia. 

El e-commerce está construido sobre un sistema de diseño visual premium que implementa una combinación de colores refinada en:
*   **Champagne Gold (`HSL 37, 23%, 60%` / `#b19e80`):** Simboliza exclusividad, suavidad y la esencia premium de las fragancias.
*   **Charcoal Dark (`HSL 210, 10%, 21%` / `#25292d`):** Aporta contraste clásico, elegancia y legibilidad óptima.
*   **Efectos Modernos:** Glassmorphism en barras de navegación, sombras dinámicas con resplandor dorado y micro-animaciones en botones y widgets.

---

## 📁 Arquitectura del Proyecto

El desarrollo sigue una **arquitectura por capas desacoplada** para facilitar el mantenimiento y la escalabilidad del código:

```text
dushi-web-profesional/
│
├── Document/                        # Biblioteca digital de archivos PDF oficiales de la marca
│   ├── Brandboard Profesional de Marca...pdf
│   ├── Brochure_Dushi_Insumos_Imagenes.pdf
│   └── Logo Dusi fragance JPG.pdf
│
├── assets/
│   ├── css/                         # CAPA DE ESTILOS (Cascading Style Sheets)
│   │   ├── variables.css            # Paleta de colores, tipografías y espaciados de la marca DUSHI
│   │   ├── base.css                 # Reset global, fuentes y estilos de scrollbar
│   │   ├── layout.css               # Grids responsivas, contenedores, cabecera y pie de página
│   │   └── components.css           # Botones, tarjetas, modales, carrito de compras y chatbot
│   │
│   ├── js/                          # CAPA DE CONTROLADORES Y DATOS (JavaScript)
│   │   ├── data.js                  # Base de datos local de productos (perfumes, cremas, geles), insumos y preguntas del test
│   │   ├── quizService.js           # Algoritmo lógico que procesa las respuestas del test sensorial y pH
│   │   ├── uiController.js          # Manejador de eventos del DOM, filtros, carrito de compras y chatbot DUSHI
│   │   └── app.js                   # Inicializador general de la aplicación web
│   │
│   └── images/                      # Activos gráficos ordenados (productos, marcas, banners)
│       ├── baners/
│       ├── insumos/
│       ├── logos/
│       └── productos/ (cremas, fragancias, geles, perfumes)
│
├── index.html                       # Página de Inicio (Identidad de Marca, Historia, Canvas y Mapa)
├── catalogo.html                    # Página de Catálogo (Buscador, Paginación y Carrito)
├── asesoria.html                    # Asesoría Sensorial (Test de pH y Chatbot DUSHI Embebido)
├── insumos.html                     # Sección de Insumos (Materias primas y normatividad INVIMA)
├── documentos.html                  # Biblioteca Digital (Visor de PDFs integrado)
└── README.md                        # Documentación técnica del proyecto (Este archivo)
```

---

## 🖥️ Módulos y Funcionalidades Clave

### 1. Portal Corporativo (`index.html`)
*   **Hero Slider:** Un carrusel dinámico en el fondo que alterna automáticamente imágenes de marca y banners promocionales.
*   **Misión, Visión e Historia:** Secciones que narran la esencia caribeña y los valores de DUSHI.
*   **Modelo Canvas Integrado:** Exposición estructurada de la propuesta de negocio y distribución de valor.
*   **Punto de Ubicación Físico:** Mapa interactivo de **Google Maps** que localiza físicamente el punto de atención en **Confama del Parque de Caldas, Antioquia**.

### 2. Catálogo e-commerce con Carrito de Compras (`catalogo.html`)
*   **Buscador y Filtros:** Búsqueda en tiempo real de fragancias y cremas con filtro por categorías (Perfumes, Cremas, Geles).
*   **Paginación Inteligente:** Visualización fluida de los productos en bloques de 8 en 8 para optimizar el rendimiento de la página.
*   **Carrito de Compras Persistente (`localStorage`):** El carrito retiene el listado de productos aun cuando el usuario navegue a otras secciones del portal.
*   **Panel Deslizable Lateral (Drawer):** Despliegue interactivo para aumentar, disminuir o eliminar cantidades.
*   **Checkout Automatizado por WhatsApp:** Genera dinámicamente un mensaje pre-estructurado y codificado con el detalle de la compra (productos, cantidades, precios individuales y total general) para enviarlo al número oficial de DUSHI (`+57 301 518 10 54`).

### 3. Asesoría Sensorial y Chatbot DUSHI (`asesoria.html`)
*   **Test Olfativo Inteligente (Wizard):** Cuestionario interactivo paso a paso que recopila la ocasión de uso, intensidad, notas preferidas y la emoción deseada. El sistema calcula la concentración y la fragancia recomendada cruzando los datos con el pH de la piel.
*   **Chatbot DUSHI Embebido:**
    *   **Identidad Visual:** Botón flotante animado y avatar del chat que lucen el logotipo oficial de DUSHI.
    *   **Menú Conversacional Numerado:** Opciones de navegación ordenadas numéricamente para evitar cajas de texto vacías y garantizar una experiencia interactiva veloz.
    *   **Recomendador Olfativo Integrado:** Opción *"6. Descubrir mi fragancia ideal"* que guía al usuario mediante 2 preguntas numéricas para sugerirle el perfume o crema perfecto basado en su perfil.
    *   **Efectos Orgánicos:** Indicador de escritura animado (tres puntos en movimiento) con retardo de 800ms para simular interacción humana y scroll automático hacia el último mensaje recibido.

### 4. Biblioteca Digital de Documentos (`documentos.html`)
*   **Catálogo de Entregables:** Permite la consulta del Brandboard de Marca, Brochure Técnico de Insumos y Logotipos.
*   **Visor de PDF en Ventana Emergente:** Al hacer clic en "Ver", el PDF se carga en un iframe dentro de un modal integrado en la misma página (evitando redirigir al usuario fuera del sitio). Cuenta con un botón de cierre fácil en la cabecera y cierre al hacer clic en el fondo oscuro.

### 5. Insumos de Producción (`insumos.html`)
*   Muestra técnica de las 7 materias primas fundamentales utilizadas (esencias de Francia y España, alcohol extrapuro vegetal desodorizado al 96%, envases de vidrio premium resistentes a luz UV y herramientas de laboratorio de precisión) bajo normatividad INVIMA.

---

## 🛠️ Instalación y Despliegue Local

Al ser un proyecto implementado con tecnologías estándar del navegador sin dependencias de compiladores externos, no requiere instalaciones pesadas:

1.  Clona el repositorio o extrae los archivos en una carpeta local.
2.  Abre el archivo `index.html` en cualquier navegador web moderno (Chrome, Edge, Firefox, Safari) haciendo doble clic, o utiliza una extensión de desarrollo como **Live Server** en VS Code para correrlo sobre un servidor local.
3.  Asegúrate de que la estructura de carpetas `assets` y `Document` se mantenga relativa a los archivos HTML.

---

## 📞 Redes Sociales & Contacto Oficial

*   **Correo Electrónico:** `dushifragance@gmail.com`
*   **Teléfono de Asistencia WhatsApp:** `+57 301 518 10 54`
*   **Instagram Oficial:** [dushi.fragance](https://www.instagram.com/dushi.fragance)
*   **Facebook Oficial:** [Dushi Fragance](https://www.facebook.com/share/1EQdrPPe1k/)
*   **Punto de Atención:** Confama del Parque de Caldas, Antioquia.
