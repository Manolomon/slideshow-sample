# Slideshow-sample

[![forthebadge](https://forthebadge.com/images/badges/check-it-out.svg)](https://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/makes-people-smile.svg)](https://forthebadge.com)

Esta es una verión que hace el port de `reveal.js` mucho más simple, y que permite por defecto el soporte para Markdown.
Se llama [`prez`](https://github.com/byteclubfr/prez). Con esta dependencia se puede hacer un directorio base, o en el caso de este ejemplo que ya está hecho, ejecutarlo.

## Instalación

```bash
npm install -g prez
```

### Crear un repositorio vacio

```
prez --init
```

### Ejecutar este ejemplo

```
prez --serve
```

## Edición

La ventaja principal con está dependencia, es la estructura y flexibilidad. Para ordenar las presentaciones, se usa el nombre, así como el título de cada archivo en la carpeta `/slides`. **Cada archivo es una slide**:

```
images/
js/
css/
slides/
  01-intro.md
  02-Chapter 1/
    01-hello-world.md
    02-bonjour-monde.md
  03-conclusion.md
```

Si una slide tiene sub-slides (Muy útil para hacer secciones), se hace una carpeta con el número y título de la slide correspondiente, y se agrega en ella las subslides con la misma nomenclatura.

Por defecto, `prez` soporta slides hechas en `Markdown` y `HTML`, en mi caso, las slides más simples las hice con `.md` y las que más complicadas, con estructuras más completas de `.html`.

## Customization

Para este ejemplo se hizo un tema propio llamado `space.css`, pero se pueden usar todos los temas disponibles en [`reveal.js`](https://revealjs.com/themes/), esto así como la información de la página (que servirá para los datos del `<head>` de la página) se editan en un archivo de configuración llamado `.prezrc`.
En el caso de este ejemplo, está configurado así:

```
{
    "title": "Space Checkers",
    "author": "Manolomon",
    "description": "Videojuego multijugador de Damas Chinas, creado para la Experiencia Educativa de Tecnologías para la Construcción de Software",
    "slides": "slides",
    "print": false,
    "printTheme": "space", <--- Aquí va el nombre del tema para exportar la presentación a pdf (Sí, se puede exportar a pdf)
    "theme": "space", <--- Aquí va el nombre del tema principal, que puede ser alguno propio de revealjs
    "highlightTheme": "space", <--- Aquí va el nombre del tema para el esílo de los chunks de código
    "suchNotes": true
}
```

La documentación adicional está en
- `prez`: https://github.com/byteclubfr/prez
- `revealjs` https://revealjs.com

## Exportado

Finalmente, los archivos de la ejecución se generan en la carpeta `/build`, esos son los que se tienen que agregar en el servidor  que vaya a hostear la página donde se publicará.
