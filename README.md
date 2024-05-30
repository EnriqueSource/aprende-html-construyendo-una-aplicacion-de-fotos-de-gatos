[![Netlify Status](https://api.netlify.com/api/v1/badges/a3de49a8-cea9-4d35-88e1-fb00e9cf8a71/deploy-status)](https://app.netlify.com/sites/cat-photo-app-bde/deploys)

# Aprende HTML construyendo una aplicación de fotos de gatos

- Los comentarios se abren con `<!--` y se cierran con `-->` . Se pueden añadir tantas líneas como se desee.
- Para hacer referencia a los diferentes elementos html se utilizan etiquetas. Las etiquetas de apertura se abren con `<nombre-del-elemento>` y se cierran con `</nombre-del-elemento>`.
- El elemento `<image>` es auto-cerrado (no tiene etiqueta de cierre).
- Los atributos tienen la forma `nombre="valor"` y van siempre dentro de la etiqueta de apertura.
- El elemento `<main>` es donde se aloja el contenido principal. Solo puede haber un elemento `<main>` en toda la pagina.
- El atributo target del elemento `<a>` especifica donde desplegar la url contenida en un elemento anchor. puede ser por ejemplo `target="_blank"` , que abrira una nueva pestana del navegador con la pagina enlazada cargada.
- crear imagenes link (imagen dentro de una etiqueta anchor)
- elemento `<section>` para separar elementos dentro de nuestra pagina.
- el atrubuto `id` para identificar a un elemento html de forma inequivoca
- Listas:
	- Lista desordenada: `<ul>`
	- Lista ordenada: `<ol>`
	- Lista de item dentro de la lista: `<li>`
- Atributos para especificar la ruta de un recurso:
	- atributo `href` para links `<a>`
	- atributo `src` (source) para imagenes `<img>`
- el elemento `<figure>` encapsula un elemento (por ejemplo una imagen) dentro de un contexto independiente. de ese modo se puede poner un subtitulo a una imagen.
	- el elemento `<figcaption>`, anidado en un `<figure>` , inserta texto debajo de una imagen, estando en el contexto independiente de la imagen.
- Resaltar texto:
	- El elemento `<strong>`: importancia (negrita)
	- El elemento `<em>` para enfatizar (cursiva)
- el elemento `<form>` para formularios. Mediante formularios podemos obtener informacion que el usuario insertara dentro del formulario
	- El atributo `action` del elemento `<form>` indica a donde deben ser enviados los datos que contenga el formulario.
	- el elemento `<input>` permite muchas y diferentes formas de recolectar informacion desde un formulario web. El elemento `<input>` , al igual que el elemento `<image>`  es un elemento autocerrado, es decir no necesita etiqueta de cierre.
		- con el atributo type de `<input>` podemos crear diferentes tipos de `<input>` como por ejemplo `type="text"`
		- el atributo `name` permite asignar un nombre al campo de texto para poder enviar al servidor datos con clave-valor
		- el atributo `name` es necesario
		- el `placeholder` se añade al campo de texto con una letra muy suave. Esto puede ayudar al usuario a saber que es lo que debe insertar en el campo de texto.
		- el atributo `required` , insertado en el elemento `<input>` asegura que el usuario no deje el formulario sin completar. `required` no tiene valor, por lo que solo debemos asegurarnos de que tenga espacio entre el y el resto de atributos de `<input>`.
	- el elemento `<botton>` añade un botón. El comportamiento predeterminado de un botón sin atributos dentro de un formulario, es enviar la información a la ubicación especificada en el atributo `action` del formulario.
		- Aunque no es necesario, añadir el atributo `submit`  al elemento botón es una buena práctica, ya que deja claro que hace el botón al pulsarlo.
	- los elementos `<input>` y `<button>` son elementos _inline_. Esto quiere decir que no añaden una nueva línea a la pagina, sino que se colocan automáticamente al lado del elemento anterior.
	- `<input>` de tipo **radio** para preguntas con una sola respuesta posible: `<input type="radio"> Indoor`
	- los elementos `<label>` son usados para asociar el texto de un elemento `<input>` con el propio `<input>`. Esto es muy util para el uso de tecnologias de asistencia, como por ejemplo un lector de pantalla. El elemento `<label>` debe envolver al `<input>` en el que se va a utilizar: `<label><input type="radio"> Indoor </label>`
	- Si tenemos mas de un "radio-button" (input de tipo radio), por defecto podran quedarse marcados los dos al mimo tiempo. Evidentemente esto es un error. Para que cuando uno de los dos se marque y el otro quede desmarcado, debemos de anadir a ambos `<input>` un atributo `name`  con el mismo valor en ambos `<input>`. Ejemplo: `name="indoor-outdoor"`
	- Si un radio-button no tiene un valor (value), por defecto al pulsar el boton (submit) se enviaran los datos del formulario incluyendo `indoor-outdoor=on` , cosa que no es muy util si tenemos varios radio-butons o botones. Para evitar esto, hay que darle un valor a cada uno de los radio-buttons . Por convenio, se le da al elemento, el mismo valor que su `id` .
	- el elemento `<fieldset>` es usado para agrupar `<input>` y `<label>` relacionados de forma conjunta en un formulario web. `<fieldset>` es un elemento de bloque, por lo que todos los elementos dentro del mismo apareceran en una nueva linea.
	  - el elemento `<legend>` actua como subtitulo para los elementos que hay dentro de un `<fieldset>` . El elemento ofrece contexto al usuario sobre que debe introducir en esa parte del formulario.
	- cuando la pregunta que hacemos al usuario tiene varias respuestas posibles, utilizamos el atributo `type="checkbox"` . Recuerda dejar siempre un espacio entre el elemento `<input>` y el nombre que este mostrara junto a la casilla de verificacion: `<input …. > Loving` 
	- Hay otra manera de asociar un texto con un elemento `<input>`. Se puede añadir un texto a un elemento `<label>` y añadirle un atributo `for` que contenga el mismo nombre que el `id` del `<input>`. Es importante que el elemento `<label>` se coloque detras del elemento `<input>` y no delante. De lo contrario no funcionara como es debido (al menos en el curso de freecodecamp).
		Ejemplo:
    ```
    <input id="loving" type="checkbox>
    <label for="loving"> Loving </label>
    ```
    
	- Es recomendable añadir a un input-checkbox  un atributo `name` . Aunque es algo que no se vera en la pagina web, hará que para el servidor sea mas fácil procesar el formulario web, especialmente cuando hay múltiples checkbox . Es importante que todos los checkbox  que pertenezcan a un mismo grupo, tengan el mismo `name` .
		Ejemplo:
  ```
		<input id="loving"type="checkbox"name="personality"> <label  for="loving">  Loving </label>
		<input id="lazy"type="checkbox"name="personality"> <label for="lazy"> Lazy </label>
		<input id="energetic"type="checkbox"name="personality"> <label  for="energetic"> Energetic </label>
  ```
  
  - Al igual que en los `<input>` de tipo radio-button, en los `<input>` de tipo checkbox los datos de formulario son enviados basados en los atributos `name` y `value` . Aunque el atributo `value`  es opcional, es una buena practica incluirlo en cualquier radio-button o checkbox  de una pagina.
  - Podemos hacer que un radio-button o checkbox  estén seleccionados (marcados) por defecto. Para hacer esto solo debemos añadir el atributo `checked`  al `<input>` en concreto. El atributo `checked`  no necesita un valor, por lo que solo debes de asegurarte de que existan espacios entre él atributo y el resto de atributos.
- El elemento `<footer>` es usado para definir un pie de pagina para un documento o sección. Normalmente, un `<footer>` contiene informacion sobre el autor del documento, datos de copyright, enlaces a los términos de uso , información de contacto, …
- Hasta ahora, todo lo que hemos visto va dentro de un elemento `<body>`. Pero existen otro tipo de información que también es importante. Este tipo de información va dentro de un elemento `<head>`. El elemento `<head>` contiene el titulo de la pagina, la dirección a diferentes hojas (como las hojas de estilo), script, etc … A los datos que van dentro del elemento `<head>` se les conoce como **metadatos**.
- Toda la pagina web esta envuelta en un elemento `<html>`
- el atributo `lang` especifica el idioma del contenido de la pagina web
	Ejemplo:
  ```
	<html lang="en">
	o
	<html lang="es">
  ```
  
- Todas las paginas deben comenzar con `<!DOCTYPE html>` . Esta cadena es conocida como una "declaración" y se asegura de que el navegador intente cumplir las especificaciones de la industria. La declaración escrita arriba le indica al navegador que la pagina es un documento HTML5, la cual es la ultima versión de HTML.
- Se puede configurar el comportamiento del navegador agregando elementos `<meta>`. Los elementos `<meta>` son de cierre automático.
	Ejemplo:
	`<meta charset="utf-8">`
	El valor _utf-8_ le dice al navegador que codifique los caracteres de la pagina con utf-8.

Fin
