# CFO Connect — web

Página del ciclo **CFO Connect · Learning by sharing**.

Una sola página estática, un solo fichero: `index.html` (20 KB). Los logos
van como SVG en línea, así que no hay carpeta de imágenes ni dependencias
que se puedan romper. Lo único que se pide fuera es la tipografía (Archivo
y Newsreader, de Google Fonts).

## Ver en local

No hace falta servidor ni compilar nada: basta abrir `index.html` en el
navegador. Si se prefiere servirlo:

```bash
python3 -m http.server 8000     # y abrir http://localhost:8000
```

## Publicación

Se publica con GitHub Pages desde la rama `main`, en el dominio
`cfo-connect.es` (con `www` redirigido a la raíz) y HTTPS obligatorio.

El fichero `CNAME` de la raíz es el que fija el dominio: si se borra, la
web vuelve a la dirección `github.io`.

## Estructura de la página

Secciones, en orden: portada · qué es · el logo · las reglas · la sesión ·
los temas · 2027 · pertenecer.

La navegación es por anclas (`#que-es`, `#reglas`, `#sesion`…), con
desplazamiento suave y tema oscuro fijo.

## Tipografías

Se cargan de Google Fonts. Si algún día la página tiene que funcionar sin
internet o sin llamadas a terceros, hay que descargar los `.woff2` y
servirlos desde el propio repositorio — es el único punto externo que
queda.
