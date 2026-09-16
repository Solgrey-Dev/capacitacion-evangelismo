# Capacitación de Evangelismo

Aplicación web estática, sin dependencias de build, diseñada para que los estudiantes repasen el contenido de la capacitación en cualquier lugar (celular, tablet o PC) durante el año 2026.

## Cómo abrirla

No requiere instalación ni servidor. Basta con abrir `index.html` directamente en el navegador.

## Estructura

```text
├── index.html              # Punto de entrada: vistas Inicio y Contenido
├── Corazon-Dios.html        # Página independiente de la Lección 2 (enlace directo/compartible)
├── css/
│   └── styles.css          # Estilos de todo el sitio
└── js/                     # (sin uso por ahora; el JS vive inline en cada página)
```

## `index.html`

Aplicación de una sola página con navegación por vistas (sin recargar):

- **Inicio** — portada con acceso rápido a cada lección.
- **Contenido** — acordeón con las lecciones disponibles. Solo una lección permanece abierta a la vez, para no mezclar el material.

Cada lección incluye su propio estudio (tarjetas de contenido, versículos destacados) y su propio mazo de **flashcards** de repaso (tarjeta que se voltea al tocarla, con navegación Anterior/Siguiente).

Lecciones actuales:

| #  | Lección                       | Flashcards |
| -- | ------------------------------ | ---------- |
| 01 | La importancia de la Palabra  | 4          |
| 02 | El corazón de Dios            | 7          |

## Agregar una lección nueva

1. Duplicar un bloque `.leccion-item` dentro de la vista Contenido en `index.html` (contenido de estudio + su propio `flashcard-deck` con ids únicos, por ejemplo `-3`).
2. Agregar su mazo de preguntas/respuestas al objeto `mazos` en el `<script>` del mismo archivo.
3. Agregar la tarjeta correspondiente en el selector de la vista Inicio (`lesson-picker`).

## Fuente del contenido

El texto de cada lección proviene tal cual de las capacitaciones dictadas (transcripción), sin agregar ni quitar información. Las citas bíblicas completas de los versículos referenciados se tomaron de las presentaciones (PPT) de cada lección.
