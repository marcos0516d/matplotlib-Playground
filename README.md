# Matplotlib Playground

Plataforma web interactiva para aprender Matplotlib de forma práctica. El usuario escribe código Python en el navegador y lo ejecuta contra tests automáticos.

**Versión**: 1.0.0 | **Última actualización**: Septiembre 2026

---

## Tecnologías

| Tecnología | Versión | Función |
|------------|---------|---------|
| HTML5 | - | Estructura |
| CSS3 | - | Estilos y responsive |
| JavaScript vanilla | - | Lógica de la aplicación |
| Bootstrap | v5.3.3 | Responsive mobile nav, tabs y layout |
| Pyodide | v0.26.4 | Python en WebAssembly |
| Monaco Editor | v0.45.0 | Editor de código (el mismo de VS Code) |
| Matplotlib | latest | Librería de visualización de datos |
| NumPy | latest | Operaciones numéricas |
| Service Worker | v1 | Caché de archivos estáticos con estrategia network-first |

---

## Estructura del Proyecto

```
Matplotlib Playground/
├── index.html                    # Página principal
├── principiante.html             # Grid de lecciones principiante
├── intermedio.html               # Grid de lecciones intermedio
├── avanzado.html                 # Grid de lecciones avanzado
├── desafio.html                  # Desafío final (3 retos)
├── lecciones_principiante.html   # Playground principiante (14 lecciones)
├── lecciones_intermedio.html     # Playground intermedio (13 lecciones)
├── lecciones_avanzado.html       # Playground avanzado (12 lecciones)
├── Botella_ensayo.png            # Logo del proyecto (header + favicon + OG image)
├── botella_ensayo.webp           # Logo alternativo
├── robots.txt                    # Reglas para motores de búsqueda
├── sitemap.xml                   # Mapa del sitio para indexación
├── sw.js                         # Service Worker v1 (network-first)
├── vercel.json                   # Configuración Vercel (estático)
├── .vercelignore                 # Exclusiones Vercel
└── README.md                     # Esta documentación
```

---

## Niveles de Aprendizaje

### Principiante
- **Color**: Verde (#00d4aa) + Morado (#667eea)
- **Lecciones**: 14
- **Temas**: Importar matplotlib, primer gráfico, scatter, barras, títulos/etiquetas, leyendas, colores/estilos, líneas múltiples, gráfico de áreas, subplots básicos, fill_between, gráfico circular, personalización completa, subplots 2x2

### Intermedio
- **Color**: Naranja (#f39c12)
- **Lecciones**: 13
- **Temas**: Subplots verticales, subplots múltiples, grid 2x2, estilos predefinidos, rcParams, heatmaps, histogramas avanzados, boxplots, violin plots, heatmaps con etiquetas, error bars, barras con error, stackplot

### Avanzado
- **Color**: Rojo (#e74c3c)
- **Lecciones**: 12
- **Temas**: Gráficos 3D, scatter 3D, superficies 3D, animaciones FuncAnimation, guardar GIFs, exportar PNG alta resolución, exportar SVG/PDF, tamaño/proporción de figura, fuentes personalizadas, flechas/anotaciones, twin axes, dashboard completo

### Desafío
- **Color**: Morado (#667eea → #764ba2)
- **Retos**: 3
- **Retos**: Dashboard Completo, Visualización de Datos, Gráficos Interactivos

**Total: 39 lecciones + 3 desafíos**

---

## Funcionalidades

### Editor de Código
- Monaco Editor con syntax highlighting para Python
- Números de línea y autocompletado
- Atajos: Ctrl+Enter (ejecutar test)

### Panel de Salida
- Gráficos SVG renderizados desde matplotlib
- Salida de texto para `print()` y errores
- Filtro de warnings (UserWarning, DeprecationWarning ignorados)
- Visualización de GIFs animados (nivel avanzado)

### Sistema de Tests
- Validación en tiempo real
- **Checklist visual** con tests pasados/fallidos
- Los tests verifican el código del usuario (no ejecutan código automático)
- Contador de tests pasados
- Mensaje de error guía al fallar tests

### Guía Educativa
- **Modal de guía** con contenido por nivel (principiante, intermedio, avanzado)
- Cada guía cubre las funciones y conceptos del nivel correspondiente
- Acceso desde el botón "📖 Guía Educativa"
- Se cierra con Escape o clic fuera del modal

### Progreso
- Guarda en localStorage
- Indicadores visuales por nivel
- Persiste entre sesiones

### Responsive (Mobile)
- Bootstrap 5.3.3 en todas las páginas de lecciones
- Mobile Nav: 3 tabs (Instrucciones, Editor, Resultado)
- Animación de paneles
- Botón de documentación matplotlib con imagen

### Header
- Logo: botella de ensayo (`Botella_ensayo.png`)
- Barra de progreso por nivel

---

## Almacenamiento Local

| Clave | Contenido |
|-------|-----------|
| `mplCompleted` | Lecciones principiante completadas |
| `mplCompletedIntermedio` | Lecciones intermedio completadas |
| `mplCompletedAvanzado` | Lecciones avanzado completadas |
| `mplDesafioCompleted` | Desafíos completados |

---

## Instalación

Es un proyecto **100% estático**. Para desarrollo local:

```bash
# Opción 1: Python
python -m http.server 8000

# Opción 2: Node.js
npx serve .
```

Luego abre `http://localhost:8000` en tu navegador.

**Importante**: Pyodide y los Service Workers no funcionan con el protocolo `file://`. Siempre usa un servidor local.

**Para producción**: Sube los archivos a Vercel, Netlify, GitHub Pages o cualquier hosting estático.

---

## Cómo Funciona

1. El usuario selecciona un nivel (o el Desafío)
2. Elige una lección del grid
3. Pyodide + matplotlib se cargan en background (desde CDN)
4. Escribe código en el editor Monaco
5. Puede consultar la **guía educativa** con "📖 Guía Educativa"
6. Los gráficos se renderizan como SVG en el panel de salida
7. Los `print()` aparecen como texto
8. Ejecuta tests con Ctrl+Enter
9. Si hay un error, se muestra el checklist de tests
10. Si pasa, se marca como completada y se muestra el gráfico
11. El progreso se guarda automáticamente en localStorage
12. En visitas posteriores, la caché del Service Worker acelera la carga
13. Los motores de búsqueda indexan el sitio mediante meta tags, Open Graph y sitemap.xml

---

## SEO y Optimización para Motores de Búsqueda

### Meta Tags por Página

| Página | Title | Description | robots |
|--------|-------|-------------|--------|
| `index.html` | Matplotlib Playground - Aprende Matplotlib Gratis en Linea | Plataforma interactiva gratuita para aprender matplotlib... | `index, follow` |
| `principiante.html` | Lecciones Principiante - Matplotlib Playground | 14 lecciones de matplotlib para principiantes... | `index, follow` |
| `intermedio.html` | Lecciones Intermedio - Matplotlib Playground | 13 lecciones intermedias de matplotlib... | `index, follow` |
| `avanzado.html` | Lecciones Avanzado - Matplotlib Playground | 12 lecciones avanzadas de matplotlib... | `index, follow` |
| `desafio.html` | Desafios - Matplotlib Playground | 3 desafios de matplotlib para poner a prueba... | `index, follow` |

### Open Graph (Redes Sociales)

Todas las páginas principales incluyen:
- `og:title` — Título descriptivo
- `og:description` — Descripción concisa (155 caracteres)
- `og:type` — `website`
- `og:url` — URL canónica
- `og:image` — Logo del proyecto (`botella_ensayo.png`)
- `og:site_name` — "Matplotlib Playground"
- `og:locale` — `es_ES`

### Twitter Card

- `twitter:card` — `summary_large_image`
- `twitter:title` — Igual a og:title
- `twitter:description` — Igual a og:description
- `twitter:image` — Logo del proyecto

### JSON-LD (Schema.org)

Estructura de datos en `index.html`:
```json
{
    "@context": "https://schema.org",
    "@type": "WebApplication",
    "name": "Matplotlib Playground",
    "description": "...",
    "applicationCategory": "EducationalApplication",
    "operatingSystem": "Web",
    "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
    "inLanguage": "es"
}
```

### Archivos SEO

| Archivo | Propósito |
|---------|-----------|
| `robots.txt` | Permite indexación de todas las páginas |
| `sitemap.xml` | 5 URLs priorizadas con `lastmod` y `changefreq` |
| `Botella_ensayo.png` | Favicon + imagen para OG/Twitter cards |

### Jerarquía de Prioridad (sitemap.xml)

```
/ (1.0) > principiante (0.9) ≈ intermedio (0.9) ≈ avanzado (0.9) > desafio (0.8)
```

### Accesibilidad (SEO-friendly)

- `lang="es"` en todas las páginas
- `alt` descriptivo en todas las imágenes
- Títulos jerárquicos (`<h1>`, `<h2>`, `<h3>`)
- Contraste de colores WCAG AA
- Responsive design (mobile-first)

---

## Notas Técnicas

### Renderizado de Gráficos
Los gráficos se renderizan usando `plt.savefig('output.svg')` en Python + inserción del SVG en el DOM. Esto permite gráficos vectoriales de alta calidad.

### Pyodide + Matplotlib
- Pyodide v0.26.4 carga matplotlib desde CDN
- Se usa `matplotlib.use('Agg')` para renderizado sin GUI
- Los GIFs se guardan con `pillow` y se muestran como base64
- `plt.close('all')` se ejecuta antes de cada test para evitar gráficos acumulados

### Funcionalidad de Tests
- Los tests verifican el código del usuario usando `user_code`
- No se ejecuta código automático en los tests
- `captureStdout()` ejecuta el código sin mostrar gráficos hasta que todos los tests pasen
- Se filtra `UserWarning` y `non-GUI backend` de la salida

### Service Worker
- Estrategia **network-first** (v1)
- Cachea: HTML, CSS, JS, fuentes, CDN de Pyodide y Monaco
- Permite actualizaciones sin limpiar caché manualmente

### Nivel Avanzado - Animaciones
- FuncAnimation se ejecuta en el backend Agg
- Los GIFs se guardan temporalmente y se muestran como base64
- Se limpian archivos `.gif` antes de cada ejecución para evitar resultados obsoletos
- La lección de animaciones interactivas (mpl_connect) fue removida por incompatible con Agg

---

## Lecciones por Nivel

### Principiante (14 lecciones)
1. Importar Matplotlib
2. Tu primer gráfico
3. Gráfico de dispersión
4. Gráfico de barras
5. Títulos y etiquetas
6. Leyendas
7. Colores y estilos de línea
8. Múltiples líneas
9. Gráfico de áreas
10. Subplots básicos
11. Fill between
12. Gráfico circular
13. Personalización completa
14. Subplots 2x2

### Intermedio (13 lecciones)
1. Subplots con plt.subplots()
2. Subplots verticales
3. Grid de subplots 2x2
4. Estilos predefinidos
5. Personalización con rcParams
6. Heatmaps con imshow
7. Histogramas avanzados
8. Boxplots
9. Violin plots
10. Heatmaps con etiquetas
11. Error bars
12. Barras con error
13. Stackplot (áreas apiladas)

### Avanzado (12 lecciones)
1. Gráficos 3D con Axes3D
2. Scatter 3D
3. Superficies 3D
4. Animaciones con FuncAnimation
5. Guardar animaciones
6. Exportar PNG de alta resolución
7. Exportar SVG y PDF
8. Tamaño y proporción de figura
9. Fuentes y texto personalizado
10. Flechas y anotaciones
11. Twin axes (ejes duplicados)
12. Dashboard completo

### Desafíos (3 retos)
1. Dashboard Completo — 4 subplots con diferentes tipos de gráficos
2. Visualización de Datos — Lineas, barras, scatter y boxplot
3. Gráficos Interactivos — Twin axes, heatmap, stackplot y barras horizontales

---

*Versión 1.0.0 - Septiembre 2026*
