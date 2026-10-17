# Plan Técnico Aprobado — Landing Page Oliver Arteaga

> **Estado:** Aprobado por el usuario.
> **Spec de referencia:** `specs/001-landing-artist/spec.md`
> **Reglas de proyecto:** `AGENTS.md`

## 1. Alcance y restricciones

- **Tecnologías**: solo HTML + CSS. Sin JavaScript ni frameworks.
- **Entrada/salida**: se modificará únicamente `index.html`, se creará `styles.css` y se generará un archivo de datos `data.json` con un **Mock** para la información no disponible.
- **No tocar**: `server.py`, `learn.json`, READMEs.
- **Verificación final**: `python3 server.py` en el puerto 3000.

## 2. Estructura de archivos (resultado final)

```
/workspaces/Landingpage-Artist-JEAA
├── index.html        → modificar
├── styles.css        → crear (nuevo)
├── data/
│   └── data.json     → crear (Mock de datos consumibles por la web)
└── assets/images/    → crear (foto del artista y decoraciones)
```

## 3. Datos: archivo JSON y Mock

### 3.1 Propósito
- Los datos que **no están disponibles** (textos, contactos, eventos, restaurantes, redes) se generarán como **Mock** en un archivo `data.json`.
- Este archivo **será consumido por la web** en el futuro y puede ser **alterado/modificado** sin tocar la estructura HTML/CSS.

### 3.2 Estructura del `data.json`
```json
{
  "artista": {
    "nombre": "Oliver Arteaga",
    "ocupacion": "Decoraciones Gastronómicas",
    "bio": "<texto placeholder>",
    "foto": "assets/images/retrato.jpg",
    "correo": "contacto@oliverarteaga.com",
    "telefonos": ["+34 600 000 000", "+34 900 000 000"],
    "redes": { "instagram": "...", "facebook": "..." }
  },
  "trayectoria": [ ... ],
  "eventos": [ ... ],
  "restaurantes": [ ... ]
}
```

### 3.3 Decisiones técnicas
- **JSON-LD**: los datos estructurados schema.org se emiten en `<head>` como bloque `application/ld+json` (datos estructurados, no lógica de aplicación), y se complementan con **Microdata** (`itemscope`/`itemtype`/`itemprop`) en el cuerpo cuando sea natural.
- **Consumo futuro**: el `data.json` queda listo para ser consumido en una iteración posterior (permite cambiar placeholders sin editar HTML).

## 4. Esqueleto del documento `index.html`

### 4.1 `<head>`
- `<!DOCTYPE html>` y `<html lang="es">`.
- `<meta charset>`, `<meta name="viewport">`, `<title>` (Oliver Arteaga — Decoraciones Gastronómicas).
- `<meta name="description">` y open graph opcional.
- `<link rel="stylesheet" href="styles.css">`.
- Bloque JSON-LD con schema.org.

### 4.2 `<body>` (estructura semántica y jerárquica)

| Orden | Elemento | Rol semántico | Contenido |
|---|---|---|---|
| 1 | `<header>` | Banner + nombre | Nombre/apellido en `<h1>` (único), ocupación |
| 2 | `<nav>` | Barra de navegación | Enlaces ancla a cada sección (una sola pantalla, sticky) |
| 3 | `<main>` | Contenido principal | Agrupa las secciones |
| 4 | `<section id="bienvenida">` | Presentación | `<h2>` + párrafo introductorio |
| 5 | `<section id="sobre-mi">` | Bio + foto | `<h2>`, `<figure>`+`<img alt>`+`<figcaption>`, biografía |
| 6 | `<section id="trayectoria">` | Trayectoria y eventos | `<h2>`, lista de eventos promocionales / hitos |
| 7 | `<section id="restaurantes">` | Restaurantes / demostración artística | `<h2>`, tarjetas/grid |
| 8 | `<footer>` | Contacto | Correo (`mailto:`), teléfonos (`tel:`), con `aria-label` |
| — | `<a href="#">` | Volver arriba (opcional) | Enlace con `aria-label` |

### 4.3 Navegación (criterio 2)
- `<nav aria-label="Navegación principal">` con `position: sticky`/`fixed`.
- Enlaces `#bienvenida`, `#sobre-mi`, `#trayectoria`, `#restaurantes`, `#contacto`.

### 4.4 Accesibilidad (criterios 6 y 7)
- Un único `<h1>`; `h2` por sección; `h3` para sub-elementos.
- `aria-label` en `<nav>`, iconos y enlaces de contacto.
- `alt` descriptivo en todas las imágenes.

## 5. Datos estructurados schema.org (criterio 8)
- Tipo: `Person` (con `additionalType` a `Artist` o descripción de ocupación).
- Propiedades: `name`, `jobTitle`/`description`, `url`, `email`, `telephone`, `image`, `sameAs`.
- JSON-LD en `<head>` + complemento con Microdata si aplica.

## 6. Hoja de estilos `styles.css`
- **Variables CSS** (`:root`): paleta gastronómica elegante, tipografías, espaciados.
- **Reset/base**: box-sizing, scroll-behavior suave.
- **Componentes**: navbar sticky, header/hero, secciones alternadas, tarjetas de eventos y restaurantes (grid), footer.
- **Responsive**: `@media (max-width: 768px)`.
- Sin inline styles; todos los estilos por clases.

## 7. Imágenes
- Carpeta `assets/images/`.
- Placeholder para retrato, decoraciones/eventos y restaurantes.
- Siempre con `alt` descriptivo.

## 8. Orden de implementación (fases)
1. **Fase 1** — Crear `data/data.json` con el Mock de datos.
2. **Fase 2** — Esqueleto HTML semántico completo en `index.html` (head + JSON-LD + secciones jerárquicas).
3. **Fase 3** — Completar contenido real usando los valores del Mock.
4. **Fase 4** — Crear `styles.css` y enlazarlo; estilos base + layout.
5. **Fase 5** — Responsive y refinamiento visual.
6. **Fase 6** — Auto-revisión contra los 11 criterios de aceptación + prueba con `python3 server.py`.

## 9. Mitigación de riesgos
- **JSON-LD vs "sin JS"**: JSON-LD es datos estructurados (no lógica); documentado en el spec. Alternativa estricta: solo Microdata.
- **Imágenes inexistentes**: placeholders para no romper el renderizado.
- **Nav en una pantalla**: contrastar que no genere scroll propio dentro de la barra.

## 10. Criterios de Aceptación

1. El archivo `index.html` tiene una estructura básica de HTML válida con `lang` correcto.
2. Existe una barra de navegación visible en una sola pantalla que enlaza a todas las secciones de la página.
3. El encabezado muestra el nombre y apellido "Oliver Arteaga".
4. Están presentes las secciones: Bienvenida, Sobre mí (biografía + foto), Trayectoria y eventos promocionales, Trayectoria en prestigiosos restaurantes o demostración artística, y Footer con correo y números de contacto.
5. El footer incluye correo y al menos un número de contacto (pueden ser placeholders).
6. Todos los elementos de interacción e iconos tienen `aria-label`; todas las imágenes tienen `alt`.
7. La jerarquía de etiquetas es correcta: existe un único `<h1>` y los encabezados siguen un orden jerárquico.
8. Se incluyen datos estructurados de schema.org (JSON-LD o Microdata) que describen al artista.
9. Solo se usa HTML y CSS: no hay JavaScript ni frameworks en la implementación.
10. Los estilos CSS se importan desde el `<head>` mediante `<link>` y generan un estilo moderno y atractivo.
11. La página se renderiza correctamente con el servidor (comando indicado en el README) sin errores.
12. Existe el archivo `data/data.json` con el Mock de datos (textos, contactos, eventos, restaurantes) listo para ser consumido y alterado en el futuro.
13. El contenido del landing page utiliza coherentemente los valores definidos en el `data.json`.

## 11. Definición de Done
Todos los criterios de aceptación del plan (1–13) verificados, `data.json` (Mock) creado y página visible en `http://localhost:3000`.