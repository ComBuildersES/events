# Cómo contribuir

¡Gracias por ayudar a que este calendario de eventos esté al día! Varias
formas de ayudar, de la más fácil a la más técnica.

## 1. Añadir un evento que falta

Rellena el formulario — sin git, sin JSON y sin permisos de escritura:

**👉 [Abre el editor OTE](https://tools.opentechevents.org/editor?repo=your-user/your-repo)**

Genera los datos del evento por ti y abre una issue rellenada en este
repositorio. Un workflow la valida y la convierte en una pull request;
alguien del equipo la revisa y la fusiona. Minutos después está publicado.

## 2. Avisar de un error

¿Fecha equivocada, enlace roto, cambio de sitio, evento cancelado? [Abre una
issue](../../issues/new/choose) contando qué falla. Las correcciones
pequeñas son bienvenidas — no te calles una por parecerte menor.

## 3. Arreglarlo tú con una pull request

Los eventos son un archivo JSON por evento en [events/](events/) — mira
[events/README.md](events/README.md) para el formato y un ejemplo mínimo.

Cada pull request se valida automáticamente contra la especificación OTE,
así que no puedes romper el feed publicado: si la validación falla, la PR te
dice exactamente qué campo está mal, y no se publica nada hasta que pase y
alguien la fusione.

## 4. Difundirlos

Una contribución de verdad, y no hace falta ni cuenta de GitHub: comparte
los eventos, añade el feed al calendario de tu propia comunidad, o
republica los datos en tu web. Mira [Reutiliza los
datos](README.md#reutiliza-los-datos) en el README para la licencia y las
URLs del feed.

## Licencia de lo que aportas

Los datos de eventos de este repositorio se publican bajo la licencia
declarada en [ote.config.json](ote.config.json). Al aportar un evento
aceptas que se publique bajo esa licencia: reutilizable, republicable y
sobre el que cualquiera puede construir, sin pedir permiso.

Así que envía solo información de eventos que puedas publicar en esos
términos — datos públicos (título, fecha, lugar, enlaces públicos), no
material que alguien te haya compartido en privado, y no texto copiado de
una página con una licencia más restrictiva.
