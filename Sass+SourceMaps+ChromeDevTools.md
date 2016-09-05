# La Magia de Oz

## Introducción

Es posible utilizar [las herramientas de desarrollo de Google Chrome](https://developer.chrome.com/devtools) para modificar las especificaciones de un archivo `.scss`, hacerlas efectivas en este archivo, recompilar el `css` y refrescar los resultados en el navegador con tan sólo guardar los cambios en el Inspector de Chrome. Sin morir en el intento.

## El Camino de Baldosas Amarillas

### Instalar Sass

Es una gema de ruby:

    gem install sass

### Preparar  DevTools

Hay que asegurarse que Chrome está preparado para utilizar los *source maps* que genera Sass al compilar el archivo css.

1.  Se abre el Inspector.
2.  Menú hamburguesa a la derecha -> Settings.
3.  En el apartado **Sources** debe estar marcada la casilla **Enable CSS source maps**.

### Necesito un corazón

Hay que lanzar Sass para que compile el css, vigile automáticamente los cambios y recompile. Para ello, en la terminal:

    sass --watch carpeta_scss/archivo.scss:carpeta_css/archivo.css

Con este comando Sass compila y vigila los cambios que se produzcan en el archivo scss. A la vez que se genera el archivo css, se crea un homónimo *.css.map*.

### La Oficina

Hay que crear un **Workspace**. Por pasos:

1.  Menú hamburguesa -> Settings -> Workspace.
2.  Presionar el botón *Add Folder*.
3.  Elegir la carpeta del proyecto.
4.  Permitir a Google que acceda a la carpeta.

### El Palacio del Mago

Ya no queda mucho. Volvemos a la pantalla principal del Inspector y ahí se accede a **Sources**. En esta sección se podrá ver la carpeta del proyecto que se acaba de incorporar.

Se elige el archivo scss correspondiente, clic derecho -> **Map to network resource**. Se acepta, se abre el archivo scss en el inspector de Chrome y desde ahí se pueden hacer cambios, estos se envían al archivo scss que cambia, compila el css y se refrescan las modificaciones en el navegador. 

La Magia en funcionamiento. Gratis. Con herramientas libres. Sin aparatosos IDE. Sólo un poco de la vieja línea de comandos y el asombroso e inabarcable poder de Chrome DevTools. Y un puñado de estándares.

## Ante todo, limpieza

Si en el proyecto se está utilizando Git y se quiere que el entorno permanezca limpio y ordenado, probablemente no sea mala idea añadir los archivos `*.css.map` al archivo `.gitignore`.

## Agradecimientos

Gracias a [esta fuente](https://robots.thoughtbot.com/sass-source-maps-chrome-magic) descubrí el prodigio.
