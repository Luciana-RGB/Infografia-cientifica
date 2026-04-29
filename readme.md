# 🐟 Infografía Interactiva — Manejo y Producción de Truchas

Infografía estadística interactiva sobre producción, parámetros del agua y sanidad en cultivos de trucha arcoíris (*Oncorhynchus mykiss*), desarrollada como recurso educativo de visualización de datos académicos.

---

## 📁 Estructura del proyecto

```
infografia-truchas/
│
├── infografia_truchas.html     ← Archivo principal (todo en uno)
│
├── css/                        ← (Opcional) Estilos separados
│   └── estilos.css
│
├── js/                         ← (Opcional) Scripts separados
│   └── infografia.js
│
├── data/                       ← (Opcional) Datos externos
│   └── estadisticas.json
│
└── README.md                   ← Este archivo
```

> **Nota:** En su versión actual, el proyecto está contenido en un único archivo `infografia_truchas.html` autosuficiente. Las carpetas `css/`, `js/` y `data/` están preparadas para una futura separación modular.

---

## 🛠️ Tecnologías utilizadas

| Tecnología | Versión | Rol en el proyecto |
|---|---|---|
| HTML5 semántico | — | Estructura y accesibilidad |
| CSS3 puro (Vanilla CSS) | — | Estilos, animaciones y layout responsivo |
| JavaScript ES6+ | — | Interactividad (clic, teclado, fetch) |
| Google Fonts | CDN | Tipografía: *DM Serif Display* + *DM Sans* |
| SVG inline | — | Íconos temáticos y gráficos donut |

No se utiliza ningún framework CSS (Bootstrap, Tailwind) ni librería JS externa. Todo el código es estándar web nativo.

---

## 🎨 Decisiones de diseño

### Paleta de colores

| Nombre | Hex | Uso |
|---|---|---|
| Principal | `#005F73` | Títulos, íconos activos, estadísticas grandes |
| Secundario | `#0A9396` | Barras de progreso, bordes en hover, donuts |
| Acento | `#94D2BD` | Fondos suaves, elementos de apoyo |
| Fondo | `#E9F5F5` | Fondo general de la página |

### Tipografía

- **DM Serif Display** → cifras estadísticas y título principal (jerarquía visual)
- **DM Sans** → cuerpo de texto, etiquetas, descripciones (legibilidad)

### Efectos aplicados

- **Efecto #15 — Tarjetas de la misma altura:** `min-height` uniforme + `transform: translateY(-6px) scale(1.018)` en hover.
- **Efecto #39 — Sombra interior / revelación:** el contenido estadístico (cifra, descripción, gráfico) parte con `opacity: 0` y `transform: translateY(10px)`, y se revela con transición suave al interactuar.
- **Transiciones:** `all 0.32s cubic-bezier(0.4, 0, 0.2, 1)` para suavidad sin mareo.

---

## 🚀 Cómo visualizar la infografía localmente

### Opción A — Abrir directamente en el navegador (más simple)

Válida solo si **no** se cargan datos desde un archivo `.json` o `.csv` externo.

1. Descarga o clona este repositorio.
2. Haz doble clic en `infografia_truchas.html`.
3. Se abrirá automáticamente en tu navegador predeterminado.

> ⚠️ Si activas la carga de datos externos (`fetch`), el navegador bloqueará la petición por política CORS. En ese caso usa la Opción B.

---

### Opción B — Servidor local con Python (recomendado)

Requiere tener **Python 3** instalado.

```bash
# 1. Navega a la carpeta del proyecto
cd ruta/al/proyecto/infografia-truchas

# 2. Inicia el servidor local
python -m http.server 8080

# 3. Abre en el navegador
# http://localhost:8080/infografia_truchas.html
```

---

### Opción C — Servidor local con Node.js

Requiere tener **Node.js** instalado.

```bash
# Instala el paquete serve de forma global (solo la primera vez)
npm install -g serve

# Navega a la carpeta y lanza el servidor
cd ruta/al/proyecto/infografia-truchas
serve .

# Abre en el navegador la URL que aparezca en la terminal
# (por defecto: http://localhost:3000)
```

---

### Opción D — Extensión Live Server (VS Code)

1. Instala la extensión **Live Server** de Ritwick Dey en VS Code.
2. Abre la carpeta del proyecto en VS Code.
3. Haz clic derecho sobre `infografia_truchas.html` → **"Open with Live Server"**.
4. El navegador se abrirá automáticamente y se recargará al guardar cambios.

---

## 📊 Conexión a datos externos (opcional)

El script incluye una llamada `fetch` comentada lista para activarse. Para usarla:

**1. Crea el archivo `data/estadisticas.json`** con esta estructura:

```json
{
  "cards": [
    {
      "id": "crecimiento",
      "stat": "1.5",
      "unit": "kg/m³/día",
      "desc": "Rendimiento promedio en sistemas de cultivo intensivo."
    },
    {
      "id": "temperatura",
      "stat": "12–18",
      "unit": "°C",
      "desc": "Rango óptimo para el desarrollo de la trucha arcoíris."
    }
  ]
}
```

**2. En `infografia_truchas.html` (o en `js/infografia.js`), descomenta el bloque:**

```javascript
fetch('./data/estadisticas.json')
  .then(response => {
    if (!response.ok) throw new Error('Error al cargar datos');
    return response.json();
  })
  .then(data => {
    data.cards.forEach(item => {
      const card = document.querySelector(`[data-id="${item.id}"]`);
      if (card) {
        const statEl = card.querySelector('.card__stat');
        if (statEl) statEl.textContent = item.stat + (item.unit || '');
      }
    });
  })
  .catch(err => console.warn('No se cargó el JSON externo:', err));
```

**3. Asegúrate de usar un servidor local** (Opción B, C o D) para que `fetch` funcione correctamente.

---

## ♿ Accesibilidad

- Navegación completa por teclado: `Tab` para moverse entre tarjetas, `Enter` o `Espacio` para activarlas.
- Atributos `role`, `aria-label` y `tabindex` en todos los elementos interactivos.
- Enlace de salto `#main-content` para lectores de pantalla.
- Contraste de color revisado para cumplir con los niveles AA de WCAG 2.1.

---

## 📱 Diseño responsivo

El layout usa un grid CSS con enfoque **Mobile First**:

| Ancho de pantalla | Columnas |
|---|---|
| < 480 px (móvil) | 1 columna |
| 480 – 767 px (tablet pequeña) | 2 columnas |
| 768 – 1023 px (tablet) | 3 columnas |
| ≥ 1024 px (escritorio) | 4 columnas |

---

## 📚 Fuente de datos

> CECASEM. (2013). *Manejo y producción de truchas: Manual básico.*

---

## ✏️ Créditos

**Diseño e implementación:** Luciana Villón Contreras