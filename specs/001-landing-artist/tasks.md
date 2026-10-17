# Tasks 001 — Landing Page Oliver Arteaga

> **Referencias:** `spec.md` y `plan.md` de `specs/001-landing-artist/`.

## Fase 1 — Datos (Mock JSON)

- [x] Crear carpeta `data/`.
- [x] Crear `data/data.json` con datos **ficticios** del artista:
  - [x] `artista`: nombre, ocupación, bio, foto, correo, teléfonos, redes.
  - [x] `trayectoria`: hitos cronológicos.
  - [x] `eventos`: eventos promocionales/privados.
  - [x] `restaurantes`: prestigiosos restaurantes o demostraciones artísticas.
- [x] Validar que `data/data.json` es JSON válido y editable.

## Fase 2 — Esqueleto HTML (`index.html`)

- [x] Definir `<!DOCTYPE html>` y `<html lang="es">`.
- [x] Configurar `<head>`: charset, viewport, `<title>` y meta description.
- [x] Enlazar `styles.css` con `<link>` en `<head>`.
- [x] Añadir bloque JSON-LD (schema.org) en `<head>` describiendo al artista (Person/Artist: name, jobTitle, url, email, telephone, image, sameAs).
- [x] Crear `<header>` con el nombre/apellido "Oliver Arteaga" en un único `<h1>`.
- [x] Crear `<nav aria-label="Navegación principal">` con enlaces ancla a todas las secciones.
- [x] Abrir `<main>` y crear `<section id="bienvenida">` con `<h2>` + presentación.
- [x] Crear `<section id="sobre-mi">` con `<h2>`, bio, `<figure>` con `<img alt>` y `<figcaption>`.
- [x] Crear `<section id="trayectoria">` con `<h2>` y lista de hitos/eventos promocionales.
- [x] Crear `<section id="restaurantes">` con `<h2>` y tarjetas/grid de restaurantes o demostraciones artísticas.
- [x] Crear `<footer>` con correo (`mailto:`) y teléfonos (`tel:`) con `aria-label`.
- [x] (Opcional) Añadir enlace "Volver arriba" con `aria-label`.
- [x] Verificar jerarquía: un solo `<h1>`, `h2` por sección, `h3` por sub-elementos.

## Fase 3 — Contenido (según Mock)

- [x] Completar textos de bienvenida y presentación usando valores de `data.json`.
- [x] Completar biografía y foto del sobre mí con valores de `data.json`.
- [x] Completar trayectoria y eventos promocionales con valores de `data.json`.
- [x] Completar restaurantes / demostraciones artísticas con valores de `data.json`.
- [x] Completar footer (correo y teléfonos) con valores de `data.json`.
- [x] Complementar con Microdata (itemscope/itemtype/itemprop) donde aplique.
- [x] Asegurar `aria-label` en todos los elementos de interacción e iconos.
- [x] Asegurar `alt` descriptivo en todas las imágenes.
- [x] No incluir JavaScript ni frameworks en ninguna parte del HTML.

## Fase 4 — Estilos (`styles.css`)

- [x] Crear `styles.css` enlazado desde `<head>`.
- [x] Definir variables CSS (`:root`): paleta gastronómica elegante, tipografías y espaciados.
- [x] Aplicar reset/base: box-sizing y scroll suave.
- [x] Estilizar navbar sticky visible en una sola pantalla.
- [x] Estilizar header/hero como banner de bienvenida.
- [x] Estilizar secciones alternadas.
- [x] Estilizar tarjetas de eventos y restaurantes (grid).
- [x] Estilizar footer de contacto.
- [x] Evitar estilos inline; usar clases.

## Fase 5 — Responsive y refinamiento

- [x] Añadir `@media (max-width: 768px)` para móvil.
- [x] Ajustar grid a una columna en pantallas pequeñas.
- [x] Verificar que la navbar no genere scroll propio.
- [x] Afinar hover states, sombras y bordes (estilo moderno y atractivo).

## Fase 6 — Imágenes

- [x] Crear carpeta `assets/images/`.
- [x] Añadir placeholder del retrato del artista.
- [x] Añadir placeholders de decoraciones/eventos.
- [x] Añadir placeholders de restaurantes.
- [x] Referenciar las imágenes con `alt` descriptivo.

## Fase 7 — Verificación final (criterios de aceptación)

- [x] Validar HTML básico con `lang` correcto (AC 1).
- [x] Verificar navbar en una sola pantalla con enlaces a todas las secciones (AC 2).
- [x] Verificar encabezado con "Oliver Arteaga" (AC 3).
- [x] Verificar presencia de todas las secciones y footer con contacto (AC 4 y 5).
- [x] Verificar `aria-label` y `alt` en todos los casos (AC 6).
- [x] Verificar jerarquía de encabezados, un único `<h1>` (AC 7).
- [x] Verificar datos estructurados schema.org (JSON-LD/Microdata) (AC 8).
- [x] Confirmar ausencia de JavaScript/frameworks (AC 9).
- [x] Confirmar CSS por `<link>` con estilo moderno y atractivo (AC 10).
- [x] Confirmar que los datos son ficticios y están en `data/data.json` editable (AC 12).
- [x] Confirmar coherencia entre el contenido del landing y `data.json`.
- [x] Ejecutar `python3 server.py` y comprobar la página en `http://localhost:3000` sin errores (AC 11).