# Spec 001 — Landing Page Artista: Oliver Arteaga

## Descripción

Crear un landing page para el artista **Oliver Arteaga**, que realiza **decoraciones gastronómicas** que se muestran en eventos del rubro y en eventos privados.

El landing page debe estar desarrollado **solo con HTML y CSS**, sin incorporar ninguna otra tecnología como JavaScript o frameworks.

## Estructura

- **Barra de navegación** en una sola pantalla.
- **Encabezado** con el nombre y apellido del artista.
- **Bienvenida** y presentación del artista.
- **Sobre mí**: biografía y foto del artista.
- **Trayectoria y eventos promocionales**.
- **Trayectoria en prestigiosos restaurantes** o demostración artística.
- **Footer** con correo y números de contacto.

## Requisitos

### Generales
- Solo se trabajará sobre HTML y CSS; no se incorporará JavaScript ni frameworks.
- El CSS debe importarse desde el `<head>` mediante una etiqueta `<link>`.
- Los estilos CSS deben generar un estilo moderno y atractivo.
- Las páginas deben ser responsivas (adaptables a una sola pantalla).

### HTML
- Uso de HTML semántico y etiquetas de marcado de schema.org (JSON-LD o Microdata).
- Uso de etiquetas de accesibilidad para invidentes.
- Las etiquetas deben organizarse según su jerarquía (un solo `<h1>`).
- Debe ser apto para lectores de pantalla: uso de atributos `aria-label` y textos alternativos (`alt`).

### Estructura de navegación
- Barra de navegación visible en una sola pantalla, con enlaces que permitan desplazarse a cada sección de la página.

### Datos del artista
- Los datos del artista serán **ficticios** y se encontrarán en un **archivo JSON editable** (`data/data.json`).
- Dicho archivo será consumido por la web y podrá ser alterado en el futuro sin modificar la estructura HTML/CSS.

## Datos estructurados (schema.org)

- Describir al artista con datos estructurados (JSON-LD o Microdata), incluyendo al menos:
  - Nombre
  - Tipo (Artista / Persona)
  - Descripción / ocupación (decoraciones gastronómicas)
  - Enlace a la página
  - Redes y/o datos de contacto si aplican

## Criterios de Aceptación

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
12. Los datos del artista son ficticios y se encuentran en un archivo JSON editable (`data/data.json`).