# Eventos de Community Builders

[![Validate](https://github.com/ComBuildersES/events/actions/workflows/validate.yml/badge.svg)](https://github.com/ComBuildersES/events/actions/workflows/validate.yml)
[![Publish](https://github.com/ComBuildersES/events/actions/workflows/publish.yml/badge.svg)](https://github.com/ComBuildersES/events/actions/workflows/publish.yml)
[![OTE spec](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcombuilderses.github.io%2Fevents%2Ffeed.json&query=%24.specVersion&label=OTE%20spec&color=blue)](https://opentechevents.org/spec/)

Calendario público de **[Community Builders](https://combuilderses.github.io/)**:
encuentros entre las personas que dinamizan comunidades técnicas — meetups,
conferencias, grupos de colaboración y todo lo que las rodea.

**👉 [combuilderses.github.io/events](https://combuilderses.github.io/events/)** —
mira qué viene.

## Suscríbete

| Formato | URL | Para qué |
| --- | --- | --- |
| iCalendar | [`feed.ics`](https://combuilderses.github.io/events/feed.ics) | Añádelo a Google Calendar, Apple Calendar u Outlook — los eventos nuevos aparecen solos |
| RSS | [`feed.xml`](https://combuilderses.github.io/events/feed.xml) | Síguelo desde cualquier lector de feeds |
| JSON | [`feed.json`](https://combuilderses.github.io/events/feed.json) | Construye algo con ello — el feed [OTE](https://opentechevents.org/spec/) legible por máquinas |

En tu calendario busca "añadir calendario **por URL**" (no "importar
archivo") y pega el enlace de `feed.ics`: así se mantiene sincronizado en vez
de quedarse congelado.

## Reutiliza los datos — en serio, hazlo

Los datos de eventos de este repositorio se publican bajo
**[CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.es)**:
dominio público. Puedes copiarlos, republicarlos, montar una web o un bot con
ellos, o integrarlos en tu propio agregador — **sin pedir permiso y sin
obligación de atribuir**, aunque un enlace de vuelta siempre se agradece.

Para eso publicamos un feed. Si llevas un directorio, una newsletter o un
calendario comunitario, coge lo que necesites. Difundir estos eventos ya es
una forma de contribuir.

Ojo: la licencia cubre **los datos** — fechas, títulos, descripciones,
enlaces. No dice nada sobre los eventos en sí, sus grabaciones ni el material
que se presente en ellos.

## Echa una mano

¿Una fecha mal? ¿Falta un evento nuestro? Mira
**[CONTRIBUTING.md](CONTRIBUTING.md)** — hay un formulario web, sin git ni
JSON.

## Cómo funciona este repositorio

```
├── events/*.json          ← un archivo JSON por evento (los datos)
├── ote.config.json        ← metadatos del feed (título, licencia, organizadores)
├── docs/index.html        ← el panel que se publica en GitHub Pages
└── .github/workflows/     ← workflows finos que llaman a los reutilizables
                             de OpenTechEvents/ote-tools
```

Cada push valida los eventos contra la [especificación
OTE](https://opentechevents.org/spec/) y, si son válidos, reconstruye y
redespliega el sitio y los tres feeds. Nada inválido llega al feed publicado.

La validación, las exportaciones y la interfaz del editor no están en este
repositorio: viven en
[OpenTechEvents/ote-tools](https://github.com/OpenTechEvents/ote-tools) y
llegan hasta aquí a través de workflows reutilizables.

¿Quieres esto mismo para tu comunidad? Forkea la plantilla:
[OpenTechEvents/ote-template](https://github.com/OpenTechEvents/ote-template).

---

*English: this is the public event feed of Community Builders, a
Spanish-speaking community. The data is CC0 — reuse it freely. Machine-readable
feed: [`feed.json`](https://combuilderses.github.io/events/feed.json) (its
`title`/`description` are also available in English under `translations.en`).*
