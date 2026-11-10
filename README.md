# 🌍 Centro Sísmico

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?style=for-the-badge&logo=leaflet&logoColor=white)
![Mapbox](https://img.shields.io/badge/Mapbox-000000?style=for-the-badge&logo=mapbox&logoColor=white)

Web que muestra en mapas interactivos los terremotos registrados en el mundo, con datos en tiempo real de la API del **USGS** (United States Geological Survey).

🔗 **Demo:** _(pendiente de añadir la URL de GitHub Pages)_

---

## ✨ Funcionalidades

### Mapa 1: Terremotos recientes
- Al cargar la web se piden a la API todos los terremotos de las **últimas 24 horas** y se pintan en el mapa.
- Cada terremoto se dibuja como un círculo con **color y tamaño según su magnitud**.
- Al pulsar un círculo se abre un **popup** con:
  - Título
  - Ubicación
  - Fecha y hora del evento
  - Código
  - Magnitud y tipo de magnitud

### Mapa 2: Resultados filtrados
- Formulario para filtrar por:
  - **Magnitud mínima** (slider de 0 a 7 que muestra el valor en vivo)
  - **Fecha de inicio** y **fecha final** (obligatorias)
- Rango máximo de **30 días** por búsqueda, con un límite de **300 resultados**, para que la petición no sea demasiado pesada.
- Cada nueva búsqueda **borra los resultados anteriores** antes de pintar los nuevos.

### Extras
- **Spinner de carga** animado en ambos mapas mientras llegan los datos.
- Mapa con capa satélite de **Mapbox**.
- Gestión de errores en las peticiones con `try/catch`.

---

## 🎨 Leyenda de magnitudes

Los colores siguen la clasificación que usan los sismólogos:

| Clase | Magnitud | Color |
|---|---|---|
| Micro | < 2 | 🟡 Amarillo claro |
| Menor | 2 – 3.9 | 🟡 Amarillo |
| Ligero | 4 – 4.9 | 🟠 Naranja |
| Moderado | 5 – 5.9 | 🔴 Naranja rojizo |
| Fuerte | ≥ 6 | 🩷 Magenta |
| Sin dato | — | ⚪ Gris |

---

## 🛠️ Tecnologías

- **HTML5** semántico (`header`, `main`, `search`, `section`, `footer`)
- **CSS3** con variables (custom properties)
- **JavaScript (ES6+)**: `async/await`, `fetch`, desestructuración, template literals, manipulación del DOM
- **[Leaflet](https://leafletjs.com/)** para los mapas
- **[Mapbox](https://www.mapbox.com/)** para la capa del mapa
- **[USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)** para los datos sísmicos

---

## 📁 Estructura del proyecto

```
Api-Map/
├── index.html    # Estructura de la página: filtros y los dos mapas
├── style.css     # Estilos, colores por magnitud y spinner
└── script.js     # Peticiones a la API y pintado de los mapas
```

---

## 🚀 Cómo ejecutarlo en local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/maridev-ve/Api-Map.git
   ```
2. Abre `index.html` en el navegador (o usa la extensión **Live Server** de VS Code).

No hace falta instalar nada: es una web estática sin dependencias.

---

## 🔌 Endpoints utilizados

- Terremotos del último día:
  `https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_day.geojson`
- Búsqueda filtrada por fecha y magnitud:
  `https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&starttime=...&endtime=...&minmagnitude=...&limit=300`


---

Datos proporcionados por el [USGS Earthquake Hazards Program](https://earthquake.usgs.gov/).
