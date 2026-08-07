# Cómo contribuir

¡Gracias por ayudar a que el calendario de Community Builders esté al día y sea
útil! Cuatro formas de echar una mano, de la más fácil a la más técnica.

## 1. Añadir un evento que falta

Rellena el formulario — sin git, sin JSON y sin permisos de escritura:

**👉 [Abre el editor OTE](https://tools.opentechevents.org/editor?repo=ComBuildersES/events)**

Genera los datos del evento por ti y abre una issue rellenada en este
repositorio. Un workflow la valida y la convierte en una pull request; alguien
del equipo la revisa y la fusiona. Minutos después el evento está publicado en
los feeds.

El mismo enlace está en el
[panel](https://combuilderses.github.io/events/).

## 2. Avisar de un error

¿Fecha equivocada, enlace roto, cambio de sitio, evento cancelado?
**[Abre una issue](../../issues/new/choose)**
contando qué falla. Las correcciones pequeñas son bienvenidas y se aplican en
un momento — no te calles una por parecerte menor.

## 3. Arreglarlo tú con una pull request

Los eventos son un archivo JSON por evento en [events/](events/); los nombres
de archivo son libres. La referencia de campos está en
[opentechevents.org/spec](https://opentechevents.org/spec/). Evento mínimo:

```json
{
  "specVersion": "0.3.0",
  "id": "https://combuilderses.github.io/events/2026-09-meetup",
  "name": "Encuentro de septiembre",
  "startDate": "2026-09-24T19:00",
  "timezone": "Europe/Madrid",
  "license": "CC0-1.0"
}
```

Los textos libres (`name`, `description`) van en castellano: es el idioma que
declara el feed en `textLanguage`, y cada evento lo hereda.

Cada pull request se valida automáticamente contra la especificación OTE, así
que no puedes romper el feed publicado: si la validación falla, la PR te dice
exactamente qué campo está mal, y no se publica nada hasta que pase y alguien
la fusione.

## 4. Difundirlos

Contribución de verdad, y no hace falta ni cuenta de GitHub: comparte los
eventos, añade el feed al calendario de tu comunidad o republica los datos en
tu web. Son [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.es)
— mira [Reutiliza los datos](README.md#reutiliza-los-datos--en-serio-hazlo) en
el README. URLs del feed:
[`feed.ics`](https://combuilderses.github.io/events/feed.ics) ·
[`feed.xml`](https://combuilderses.github.io/events/feed.xml) ·
[`feed.json`](https://combuilderses.github.io/events/feed.json)

## Licencia de lo que aportas

Los datos de eventos de este repositorio se publican bajo
[CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.es) — dominio
público, según lo declarado en [ote.config.json](ote.config.json). **Al aportar
un evento aceptas que se publique así**: cualquiera podrá reutilizarlo,
republicarlo o construir sobre él, sin pedir permiso y sin acreditarte.

Así que envía solo información de eventos que puedas publicar en esos términos:
datos públicos (título, fecha, lugar, enlaces públicos), no material que
alguien te haya compartido en privado ni texto copiado de una página con una
licencia más restrictiva.
