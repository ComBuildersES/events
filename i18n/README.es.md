# <Nombre de tu comunidad>

<!--
Descomenta esto cuando termines SETUP.md: sustituye your-user/your-repo por
tu fork en los dos primeros, y apunta el tercero a tu propio feed.json (es
un botón de suscripción, no un indicador de estado — tiene que llevar
directamente a algo que resuelva):

[![Validate](https://github.com/your-user/your-repo/actions/workflows/validate.yml/badge.svg)](https://github.com/your-user/your-repo/actions/workflows/validate.yml)
[![Publish](https://github.com/your-user/your-repo/actions/workflows/publish.yml/badge.svg)](https://github.com/your-user/your-repo/actions/workflows/publish.yml)
[![feed OTE](https://opentechevents.org/badge/ote-feed.es.svg)](https://your-user.github.io/your-repo/feed.json)
-->

<!-- ¿Fork nuevo? La guía de instalación de un solo uso está en SETUP.md. -->

Describe qué tipo de eventos incluye este feed — charlas, meetups, talleres,
conferencias…

**👉 [Mira qué viene](https://your-user.github.io/your-repo/)**

## Suscríbete

| Formato | URL | Para qué |
| --- | --- | --- |
| iCalendar | [`feed.ics`](https://your-user.github.io/your-repo/feed.ics) | Añádelo a Google Calendar, Apple Calendar u Outlook — los eventos nuevos aparecen solos |
| RSS | [`feed.xml`](https://your-user.github.io/your-repo/feed.xml) | Síguelo desde cualquier lector de feeds |
| JSON | [`feed.json`](https://your-user.github.io/your-repo/feed.json) | Construye algo con ello — el feed [OTE](https://opentechevents.org/spec/) legible por máquinas |

En tu calendario busca "suscribirse **por URL**" (no "importar archivo") y
pega el enlace de `feed.ics`: así se mantiene sincronizado en vez de
quedarse congelado en el momento de importarlo.

## Reutiliza los datos

Los datos de eventos de este repositorio se publican bajo la licencia
declarada en [`ote.config.json`](ote.config.json). ¿Llevas un directorio,
una newsletter o tu propio agregador? Coge lo que necesites — republicar
este feed ya es una forma de apoyar a esta comunidad.

## Contribuir

¿Has visto un error, o quieres añadir un evento? Mira
[CONTRIBUTING.md](CONTRIBUTING.md).
