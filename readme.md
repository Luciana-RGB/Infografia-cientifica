Infografía Interactiva: Producción de Truchas
Una infografía web de tipo estadística/datos desarrollada con HTML, CSS y JavaScript puro (Vanilla). El diseño presenta un estado inicial visualmente minimalista que oculta las cifras complejas, revelándolas dinámicamente a través de interacciones fluidas del usuario (hover o clic).

LicenciaTecnologías

🎯 Características del Diseño
La interfaz aplica conceptos avanzados de UI/UX educativa:

Efecto #15 (Tarjetas de la misma altura): Las tarjetas mantienen una cuadrícula visual perfecta. Al interactuar, experimentan un crecimiento sutil (transform: scale) y una elevación en el eje Z (box-shadow).
Efecto #39 (Sombra interior): Al revelarse los datos, el fondo utiliza un box-shadow: inset pronunciado combinado con un degradado, creando la ilusión óptica de profundidad, como si los datos estuvieran "bajo la superficie" del elemento.
Responsive Mobile First: Diseñado estrictamente desde móviles hacia escritorio. En pantallas táctiles, la interacción cambia inteligentemente de :hover a un sistema de alternancia por click (tap).
Cero Dependencias: No utiliza frameworks CSS (Bootstrap/Tailwind) ni librerías JS (jQuery). Carga instantánea.
🛠️ Tecnologías Utilizadas
HTML5 Semántico: Uso de etiquetas <article>, <main>, <header> y <footer> para garantizar la accesibilidad y el SEO del contenido.
CSS3 Vanilla:
Diseño de layout mediante CSS Grid y Flexbox.
Variables CSS (:root) para la gestión centralizada de la paleta de colores.
Transiciones físicas usando cubic-bezier para evitar animaciones robóticas.
Media queries @media (hover: hover) para separar lógicas de escritorio y móvil.
JavaScript (ES6+):
Manipulación básica del DOM para la gestión de clases (classList.toggle).
Delegación de eventos para optimizar el rendimiento en dispositivos táctiles.
Tipografía: Google Fonts (Inter).
📁 Estructura del Proyecto
El proyecto está condensado en una arquitectura de archivo único para facilitar su despliegue inmediato y evitar errores de rutas relativas:

/infografia-truchas │ └── index.html      # Contiene el HTML, el CSS (<style>) y el JS (<script>)
Nota sobre la arquitectura: Aunque en entornos de producción estrictos se separan los archivos (.html, .css, .js), para infografías interactivas académicas o de presentación, el formato de archivo único es el estándar de la industria (similar a cómo funcionan CodePen o Figma exports) porque garantiza que el archivo se pueda enviar por email, alojar en cualquier servidor básico o abrir localmente sin que se rompan las fuentes o los íconos.

🚀 Cómo visualizar la infografía localmente
No necesitas instalar Node.js, Python ni ningún servidor web complejo. Sigue estos pasos:

Opción 1: Doble clic (La más fácil)
Simplemente haz doble clic sobre el archivo index.html. Se abrirá automáticamente en tu navegador predeterminado (Chrome, Safari, Edge, etc.). Todas las funciones visuales e interactivas funcionarán al 100%.

Opción 2: Extensión Live Server (Recomendado para desarrolladores)
Si estás usando Visual Studio Code y quieres que la página se actualice automáticamente al guardar cambios:

Abre la carpeta del proyecto en VS Code.
Ve a la pestaña de Extensiones (Ctrl+Shift+X o Cmd+Shift+X).
Busca e instala la extensión "Live Server" (de Ritwick Dey).
Haz clic derecho sobre el archivo index.html y selecciona "Open with Live Server".
🎨 Paleta de Colores
Rol
Código Hex
Uso principal
Principal #005F73 Fondos de revelado, textos H1/H2
Secundario  #0A9396 Iconos SVG, textos de soporte
Acento  #94D2BD Números estadísticos, líneas de borde
Fondo Base  #F4F8F8 Fondo general del cuerpo (Body)

📚 Créditos y Fuentes
Datos y Contenido: CECASEM. (2013). Manejo y producción de truchas: Manual básico.
Diseño e Interactividad: Luciana Villón Contreras.
Iconografía: SVGs personalizados basados en la bibliografía de acuicultura.
Proyecto desarrollado con fines educativos y de visualización de datos académicos.
```