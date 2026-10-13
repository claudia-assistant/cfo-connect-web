# CFO Connect — web

Web del ciclo **CFO Connect · Learn · Link · Lead**: comunidad de directores
financieros de Andalucía Occidental.

## Qué hay aquí

| Fichero | Qué es |
|---|---|
| `index.html` | **Lo que se publica**: landing de una sola pantalla (50 KB). Logo, lema, descripción breve y pie. |
| `web-completa.html` | Versión larga con todas las secciones (20 KB). Guardada por si vuelve a hacer falta; **no se sirve**. |
| `CNAME` | Fija el dominio `cfo-connect.es`. Si se borra, la web vuelve a la dirección `github.io`. |

## Cero dependencias externas

`index.html` no llama a nadie: la tipografía Archivo va **incrustada en
base64** dentro del propio fichero (subset latino, el que cubre el español).
Sin analítica, sin cookies, sin JavaScript, sin imágenes remotas. Por eso no
necesita banner de cookies: el visitante no habla con ningún tercero.

Eso es deliberado y hay que mantenerlo. Las fuentes de Google ceden la IP del
visitante a un tercero fuera de la UE, que es justo lo que se quiso evitar.

`web-completa.html` **sí** sigue llamando a Google Fonts: si algún día se
publica, hay que incrustarle las fuentes igual que a la landing.

## La cabecera no es opcional

Las cinco primeras líneas (`<!DOCTYPE>`, `<html lang="es">`, `<head>`,
`<meta charset="utf-8">`, viewport) son obligatorias. Sin la declaración de
codificación, cualquier alojamiento que no la mande en la respuesta HTTP hace
que el navegador caiga en latin-1 y la página se lea «AndalucÃ­a Occidental».
Comprobado sirviendo el fichero con `Content-Type: text/html` sin charset.

## Ver en local

```bash
python3 -m http.server 8000     # y abrir http://localhost:8000
```

Nota: la portada tiene una animación de entrada de ~2,5 s (el arco se dibuja,
el texto sube). Para capturar la pantalla hay que esperar a que termine.

## Publicación

GitHub Pages desde `main`, raíz del repositorio, dominio `cfo-connect.es`.

**Pendiente:** el DNS del dominio está en Hostinger y apunta a su página de
dominio aparcado (`2.57.91.91`). Para que Pages sirva la web hay que cambiar
en la zona de Hostinger el registro `A` de `@` por los cuatro de GitHub
(`185.199.108.153`, `.109.153`, `.110.153`, `.111.153`) y dejar el `CNAME` de
`www` apuntando a `claudia-assistant.github.io`. Después, activar «Enforce
HTTPS» en Pages.
