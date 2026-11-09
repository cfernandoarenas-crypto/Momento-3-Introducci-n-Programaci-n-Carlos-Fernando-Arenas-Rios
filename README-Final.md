# Evaluación Institucional - Momento 3

## Descripción del proyecto

Página web del proceso de evaluación institucional. Tiene una portada, una sección con los aspectos que se pueden evaluar y un formulario para enviar la evaluación. Al enviar el formulario se muestra una página de confirmación. Está hecha con HTML, CSS y el framework Tailwind.

## Archivos

- `indexFinal.html`: página principal (encabezado, portada, aspectos, formulario y pie de página).
- `exito.html`: página que confirma que la evaluación fue registrada, con un botón para volver a la principal.
- `styleFinal.css`: estilos propios, micro-interacciones y media queries.
- `imagen.jpg`: imagen de la portada.

## Lo que se hizo en este momento

### 1. Interactividad visual (CSS puro)
- **Menú:** al pasar el mouse sobre un enlace aparece una línea debajo (pseudo-elemento `::after` con `transition`).
- **Tarjetas:** al pasar el mouse la tarjeta sube, se le agrega sombra y aparece una barra roja arriba (`:hover` y `::before`).
- **Etiquetas "Abierto" y "Cerrado":** tienen una animación suave con `@keyframes`.
- **Formulario:** los campos cambian de borde con `:focus` y el botón crece un poco con `:hover`.
- **Botón de la página de confirmación:** cambia de color y crece con `:hover`.

### 2. Diseño responsivo con Tailwind
Se agregó Tailwind con un CDN en el `<head>` del HTML. Se pasó a Tailwind el diseño con **Flex** de la portada, la galería de tarjetas y el pie de página, usando clases como `flex`, `flex-col`, `md:flex-row`, `justify-center`, `items-center` y `gap-5`. Esas reglas se quitaron del CSS para no repetir código.

En `styleFinal.css` se dejaron media queries explícitas (`@media`) para ajustes finos:
- `max-width: 768px` (tablet): reduce tamaños de letra y centra el texto de la portada.
- `max-width: 600px` (celular): el encabezado pasa a columna, las tarjetas ocupan todo el ancho y se ajusta el espacio del formulario.

## Integración con los otros módulos

Este es el Nivel 1 de integración: aquí solo está la parte visual (front-end), pero se conecta con los otros módulos del proyecto de la siguiente manera:

- **Formulario de evaluación (`indexFinal.html`):** captura el nombre, el rol, el aspecto a evaluar y los comentarios. En un entorno real, estos datos serían enviados al **Backend**, que los validaría (por ejemplo, que el nombre no esté vacío y que el aspecto sea uno de los permitidos).
- **Backend:** después de validar, el Backend enviaría la información a la **Base de Datos**, donde se guardaría en una tabla de evaluaciones relacionada con el aspecto evaluado y el rol de quien responde.
- **Página de confirmación (`exito.html`):** en este momento el formulario solo cambia de página. En un entorno real, esta página se mostraría cuando el Backend responda que la evaluación se guardó correctamente en la Base de Datos.
- **Aspectos de evaluación:** las tarjetas ("Docencia", "Infraestructura", etc.) y sus etiquetas "Abierto" o "Cerrado" son datos fijos por ahora. En un entorno real vendrían de la Base de Datos a través del Backend, para que el estado de cada aspecto se pueda cambiar sin editar el HTML.
- **Opciones del formulario:** las listas de roles y aspectos del formulario deberían coincidir con los registros de la Base de Datos para que los datos guardados sean consistentes.
- **Diseño responsivo:** al usar Tailwind y media queries, cualquier módulo que agregue páginas nuevas (por ejemplo, resultados o reportes) puede reutilizar los mismos estilos y se vería bien en computador, tablet y celular.

## Cómo ejecutar

1. Abrir la carpeta del proyecto en Visual Studio Code.
2. Abrir `indexFinal.html` con Live Server o directamente en el navegador.
3. Se necesita conexión a internet para que cargue Tailwind (CDN).
