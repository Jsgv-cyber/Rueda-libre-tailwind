# Rueda Libre - migración a Tailwind CSS

## Archivos
- `index.html`: estructura de la página.
- `css/input.css`: entrada de Tailwind y estilos complementarios.
- `css/tailwind.css`: archivo generado por Tailwind CLI (se crea al ejecutar el comando).

## Requisitos
Este proyecto está preparado para Tailwind CSS v4 y `@tailwindcss/cli`.

Si los paquetes aún no están instalados en la carpeta del proyecto:
```bash
npm.cmd install -D tailwindcss @tailwindcss/cli
```

## Generar el CSS
Desde la carpeta raíz del proyecto:
```bash
npx.cmd @tailwindcss/cli -i ./css/input.css -o ./css/tailwind.css --watch
```
Deja esa terminal abierta mientras desarrollas. Para generar una versión final sin `--watch`:
```bash
npx.cmd @tailwindcss/cli -i ./css/input.css -o ./css/tailwind.css
```

## Ubicación de las imágenes
El HTML utiliza estas rutas relativas:
- `img/Bicilceta 1.png` (se conserva la ortografía del nombre del archivo original)
- `img/Bicicleta 2.png` hasta `img/Bicicleta 9.png`

Copia las nueve imágenes originales a la carpeta `img` de este proyecto y verifica que los nombres coincidan exactamente, incluyendo espacios, extensión y mayúsculas/minúsculas. Si tus archivos tienen `.webp` o `.jpeg`, modifica el `src` correspondiente en el HTML.

## Funcionalidades sin JavaScript
- Menú móvil: `<details>` y `<summary>`.
- Formulario desplegable: `<details>` y `<summary>`.
- Modo nocturno: checkbox oculto + selector CSS `:has()`.
- Catálogo: carrusel horizontal nativo con `overflow-x`, `scroll-snap` y enlaces de navegación.

El tema oscuro no se guarda al recargar la página, porque no se utiliza JavaScript ni almacenamiento del navegador. El formulario está maquetado, pero no envía reservas a un negocio hasta conectarlo a un backend o servicio de formularios.
