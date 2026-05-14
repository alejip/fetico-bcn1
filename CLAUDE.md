# FETICO BCN1 — Landing Page Electoral

## Descripción del proyecto
Landing page de campaña electoral para el **comité de empresa de Amazon BCN1** en El Prat de Llobregat, representada por el sindicato **FETICO** (Confederación Sindical Independiente).

El objetivo es dar a conocer al equipo de delegados, informar sobre FETICO y captar afiliaciones a través de un formulario conectado con Google Forms.

---

## Diseño y estilo

### Paleta de colores
```css
--green:      #00e64d   /* Verde corporativo FETICO — principal */
--green-dim:  #00b33c
--green-dark: #004d1a
--black:      #050505   /* Fondo principal */
--black2:     #0a0a0a
--grey:       #1a1a1a   /* Tarjetas y bloques */
--grey2:      #222
--text:       #e8e8e8   /* Texto general */
--accent:     #ff3300   /* Acento puntual */
```

### Tipografías (Google Fonts)
- **Black Ops One** — títulos principales y BCN1
- **Bebas Neue** — subtítulos, nombres de miembros
- **Rajdhani** (400/600/700) — texto de cuerpo
- **Share Tech Mono** — etiquetas, monoespaciado técnico

> El prompt original mencionaba **Road Rage** (dafont.com) para encabezados. Si se quiere usar, requiere descarga manual e inclusión como @font-face.

### Estilo visual
- Fondo negro con detalles en verde neón
- Toque **sindical/punk** sin ser excesivamente recargado
- Grid perspectiva en hero con efecto parallax
- Efectos glitch en hover sobre "BCN1"
- Banda ticker animada (verde sobre negro)
- Scrollbar personalizada en verde
- Noise overlay sutil en toda la página
- Animaciones: `floatSkull`, `scanline`, `fadeInUp/Down`, `reveal` por scroll

---

## Estructura de secciones

| # | ID | Contenido |
|---|-----|-----------|
| Hero | `#hero` | Logo calavera SVG + título FETICO BCN1 + CTAs |
| 01 | `#fetico` | Qué es FETICO — texto + estadísticas (tarjetas) |
| 02 | `#equipo` | Delegados electos y LOLS — tarjetas con foto |
| 03 | `#funciones` | Funciones de delegados electos vs. LOLS |
| 04 | `#ofrecemos` | Beneficios por 5€/mes — grid de cards |
| 05 | `#afiliacion` | Formulario de afiliación |
| — | `footer` | Links y copyright |

---

## Equipo de delegados

### Delegados/as Electos (Comité de Empresa)
| Nombre | Turno | Nota |
|--------|-------|------|
| Pili García | ONIWA | |
| Cristian Romano | Rin | |
| Isa Vásquez | ONIWA | Delegada PRL |
| Josemi Caicedo | Ros | |
| Carles Rins Cano | RONW4 | |

### Delegados/as LOLS (Sección Sindical)
| Nombre | Turno |
|--------|-------|
| Alain Garví | OL |
| Marc González | PIN |
| Josef Villagrasa | ON |

---

## Fotos de los delegados

**PENDIENTE — el usuario proporcionará las fotos con sus nombres de archivo.**

Las fotos irán en la sección `#equipo` dentro de `.member-photo`. Actualmente hay SVGs placeholder generados con ilustraciones. Cuando se entreguen las fotos:
- Colocar en carpeta `/assets/fotos/`
- Formato recomendado: JPG o WebP, ratio 3:4 (portrait)
- Reemplazar el SVG placeholder por `<img src="assets/fotos/NOMBRE.jpg" alt="Nombre delegado" style="width:100%;height:100%;object-fit:cover;">`

---

## Logos e imágenes

### Logo calavera BCN1
**PENDIENTE — el usuario proporcionará el archivo del logo.**
- Actualmente existe como SVG inline en el hero y en el nav
- Cuando se entregue, guardar en `/assets/logo-calavera.png` (o SVG)
- Puede usarse también como: favicon, marca de agua de fondo, decoración en esquinas

### Logo FETICO corporativo
- Disponible en [fetico.es](https://fetico.es)
- Guardar en `/assets/logo-fetico.png`

---

## Formulario de afiliación

**URL del Google Form:**
```
https://docs.google.com/forms/d/e/1FAIpQLSeunfAAr7suhjKois-nZW-ur5nTZaea8n05YBZ5mpwnu65R6w/viewform
```

**Endpoint para envío POST (no-cors):**
```
https://docs.google.com/forms/d/e/1FAIpQLSeunfAAr7suhjKois-nZW-ur5nTZaea8n05YBZ5mpwnu65R6w/formResponse
```

### Campos del formulario
| Campo HTML | `entry.ID` real |
|------------|-----------------|
| nombre | ⚠️ Pendiente extraer los `entry.XXXXXXXXX` reales del formulario |
| apellidos | |
| email | |
| telefono | |
| turno | |
| departamento | |
| consulta | |

> **IMPORTANTE:** Los `entry.ID` actuales en el HTML son placeholders (`entry.1000000001`, etc.). Para que el formulario envíe correctamente los datos hay que inspeccionar el Google Form e identificar los IDs reales. Ver: Clic derecho en campo del form → Inspeccionar → buscar `name="entry.XXXXXXXXX"`.

---

## Instagram de referencia
```
https://www.instagram.com/fetico_bcn1amazon
```
Usarlo como fuente de contenido adicional, imágenes, comunicados y tono de voz.

---

## Estructura de archivos prevista

```
fetico/
├── CLAUDE.md
├── index.html          ← archivo principal (basado en fetico-bcn1.html)
├── assets/
│   ├── logo-calavera.png   (pendiente)
│   ├── logo-fetico.png
│   └── fotos/
│       ├── pili-garcia.jpg       (pendiente)
│       ├── cristian-romano.jpg   (pendiente)
│       ├── isa-vasquez.jpg       (pendiente)
│       ├── josemi-caicedo.jpg    (pendiente)
│       ├── carles-rins.jpg       (pendiente)
│       ├── alain-garvi.jpg       (pendiente)
│       ├── marc-gonzalez.jpg     (pendiente)
│       └── josef-villagrasa.jpg  (pendiente)
└── README.md
```

---

## Archivo de referencia de diseño
El diseño de referencia se encuentra en:
```
/Users/sinvellomac2/Downloads/fetico-bcn1.html
```
Mantener ese diseño como base visual. No introducir cambios de estilo o layout que no estén alineados con la estética punk/sindical verde sobre negro.

---

## Notas de desarrollo
- El HTML es un archivo único autocontenido (sin build tools ni dependencias npm)
- Despliegue previsto: estático (puede ser GitHub Pages, Netlify, Vercel u hosting simple)
- Responsive: el menú se oculta en móvil (< 768px); pendiente implementar menú hamburguesa
- El efecto parallax usa `requestAnimationFrame` implícito vía scroll listener; no hay librería externa
- La tipografía Road Rage del prompt original no está implementada — se puede añadir via `@font-face` si se descarga de dafont.com
