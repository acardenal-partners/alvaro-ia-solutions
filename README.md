# alvaro-ia-solutions — Álvaro IA Solutions, consultoría de inteligencia artificial

Landing de una sola página de **Álvaro IA Solutions**: consultoría de IA para negocios («La IA que tu negocio necesita.
No hablamos de IA. La construimos.»).

- **Web publicada:** https://acardenal-partners.github.io/alvaro-ia-solutions/
- **Para quién:** pymes, negocios locales y profesionales que quieren poner la IA a trabajar (automatizaciones,
  asistentes, formación) sin conocimientos técnicos.

## Estado actual

- **Último commit:** 16-07-2026. Versión publicada en GitHub Pages, sin cambios desde entonces.

## Contenido de la página

1. **Cabecera** con titular, llamada a «Diagnóstico gratis» y botón «Ver casos reales».
2. **Posicionamiento:** «No hablamos de IA. La construimos.»
3. **Propuesta** «Diseña la infraestructura del futuro de tu negocio».
4. **Casos** «Sistemas que ya están funcionando».
5. **Servicios:** tres formas de ponerte la IA a trabajar.
6. **Método:** tres pasos, sin sorpresas.
7. **Cierre** y **asistente de diagnóstico**: chat guiado (sin IA en servidor) con preguntas de botones que al final
   genera un resumen para enviarlo por **WhatsApp** o **email** con un clic.

## Stack y arquitectura

| Pieza | Tecnología |
|---|---|
| Página | HTML + CSS + JavaScript en un solo `index.html`, sin framework, sin build, sin backend |
| Tipografías | Google Fonts |
| Imágenes | Generadas con IA (Higgsfield), servidas desde un CDN externo |
| Animaciones | CSS + `IntersectionObserver` (apariciones y contadores) |
| Chat de diagnóstico | Flujo de preguntas en JS puro; envío por enlaces `wa.me` y `mailto:` |

```
alvaro-ia-solutions/
└── index.html     Página completa (estilos, contenido y scripts en línea)
```

Los destinos de contacto del chat se configuran en las constantes `CONTACTO_WHATSAPP` y `CONTACTO_EMAIL` del script
(el propio código indica que hay que revisarlas antes de usar la página en serio).

## Cómo arrancarlo desde cero en un ordenador nuevo

Solo hace falta Git y un navegador.

```bash
git clone https://github.com/acardenal-partners/alvaro-ia-solutions.git
cd alvaro-ia-solutions
npx serve .            # o: python -m http.server 8080, o abrir index.html directamente
```

Para editar: cambia `index.html`, comprueba en local y haz `git push` a `main`.

## Variables de entorno

Ninguna. Es una página estática sin backend ni claves.

## Despliegue y servicios externos

- **GitHub Pages** desde la rama `main`, carpeta raíz: cada push a `main` publica.
- **Servicios externos:** Google Fonts, CDN de Higgsfield (imágenes), WhatsApp (`wa.me`) y el cliente de correo del
  visitante (`mailto:`).

## Pendientes

- Revisar y confirmar los datos de contacto de `CONTACTO_WHATSAPP` y `CONTACTO_EMAIL` (marcados en el código como
  «cambiar por el real»), y valorar si deben estar escritos en el código público.
- Dominio propio y analítica de visitas/conversiones.
- Guardar copia propia de las imágenes (dependen de un CDN externo).
- Decidir su relación con la web corporativa de Partners IA Solutions (contenidos parecidos) para no duplicar mensajes.
