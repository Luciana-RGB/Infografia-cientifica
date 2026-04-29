Infografía Interactiva: Producción de Truchas
Proyecto de visualización de datos académicos construido exclusivamente con HTML, CSS y JavaScript puro (Vanilla). Presenta un conjunto de 12 métricas estadísticas que se mantienen ocultas inicialmente y se revelan dinámicamente a través de interacciones fluidas del usuario (hover o clic).

HTML5CSS3JavaScript

📋 Descripción
Este proyecto implementa una infografía de tipo "Estadística / datos" con un enfoque minimalista (Mobile First). Visualmente, la interfaz se presenta como un grid limpio de tarjetas con iconos. Sin embargo, bajo el capó, utiliza técnicas avanzadas de CSS para crear una experiencia de profundidad:

Efecto #15 (Tarjetas de la misma altura): Elevación y escalado suave (transform: scale) al pasar el cursor o tocar la pantalla.
Efecto #39 (Sombra interior): Uso de box-shadow: inset para simular que los datos numéricos revelados están "hundidos" o sumergidos en la interfaz.
El diseño es 100% responsivo, asegurando áreas táctiles adecuadas en dispositivos móviles mediante una lógica dual de interacción (Hover en escritorio, Toggle por Clic en táctil).

🚀 Cómo ejecutar el proyecto
Dado que es un proyecto frontend puro sin dependencias de build (como Node.js, npm o Webpack), su ejecución es directa:

Descarga o clona los archivos en tu máquina local.
Asegúrate de que el archivo index.html y la carpeta assets/ (si incluyes imágenes externas) mantengan su estructura.
Haz doble clic sobre el archivo index.html.
El archivo se abrirá automáticamente en tu navegador web predeterminado.
Nota: El archivo funciona perfectamente de forma local (file:///...). Sin embargo, si planeas conectar la función fetch() comentada en el JavaScript para leer un .json externo en el futuro, deberás servir el proyecto a través de un servidor local (como la extensión "Live Server" de VS Code) para evitar errores de CORS.

📁 Estructura de Archivos
La organización del proyecto está diseñada para ser simple y autocontenida:

/infografia-truchas │ ├── index.html          # Archivo principal (Contiene HTML, CSS embebido y JS) ├── README.md           # Documentación del proyecto (Este archivo) └── assets/             # (Opcional) Carpeta para recursos multimedia adicionales      └── imagenes/
🛠️ Características Técnicas
Sin Frameworks: Cero uso de librerías externas como Bootstrap, Tailwind, jQuery o React. Todo fue construido con Vanilla CSS y HTML semántico (<article>, <main>, <header>, <footer>).
Rendimiento: El script JavaScript se carga al final del cuerpo del documento (<script> antes de cerrar </body>), garantizando que el DOM renderice primero sin bloqueos.
Curva de Renderizado: Se utilizan propiedades de CSS como transform y opacity para las animaciones, las cuales son aceleradas por hardware (GPU) para lograr transiciones a 60fps sin marear al usuario.
Tipografía: Utiliza la fuente Inter via Google Fonts, optimizada extremadamente para pantallas digitales.
🎨 Paleta de Colores
El esquema cromático está definido mediante variables CSS (:root) y fue seleccionado por su alto contraste y accesibilidad visual:

Color Principal: #005F73 (Usado para tipografía principal y fondo del reverso de las tarjetas).
Color Secundario: #0A9396 (Usado para los trazos de los iconos SVG).
Color Acento: #94D2BD (Usado para resaltar las cifras estadísticas reveladas).
👤 Créditos
Datos y Temática: CECASEM. (2013). Manejo y producción de truchas: Manual básico.
Diseño y Desarrollo Front-end: Luciana Villón Contreras