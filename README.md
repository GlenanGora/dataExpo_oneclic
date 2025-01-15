# Obten los datos de exportaciones y tenlos disponibles en Looker Studio con un solo clic!!!

En este proyecto básico de ingeniería de datos vamos a descargar los achivos de exportaciones disponible en la plataforma de Aduanas de Sunat (de la última semana) y analizarlos en Looker Studio, para ello  no vamos a usar aplicacciones o software instaladas en nuestra Pc, sino lo haremos utilizando las herramientas y plataformas disponibles de forma gratuita en la nube, y que a partir **de un solo click** tengamos disponible los datos para analizarlos en Looker Studio!!!.

Existe una dirección pública dentro de [Operatividad Aduanera](http://www.aduanet.gob.pe/aduanas/informae/presentacion_bases_web.htm) donde Sunat comparte los archivos de exportaciones e importaciones de cada semana, de los últimos dos meses, para este proyecto se descargará de forma automática el último archivo de la última semana disponible.


## Arquitectura
La aplicación lo que realizará es descargar los datos desde la página de Sunat hacia google drive, antes transformando esos datos a un formato legible para cargar hacia una hoja de google sheets y pueda ser consumida esa información con Looker Studio, todo ello será realizado usando google colaboratory  que es una plataforma de programación en el lenguaje Python mediante jupyter notebooks.

<image src="images/arquitectura.jpg" alt="Arquitectura del proyecto">

El desarrollo del tablero no está automatizado porque tiene que construirse manualmente de acuerdo a las necesidades de cada usuario.
## Manos a la obra
Antes de seguir los siguientes pasos, el único requisito es que tengas una cuenta en gmail ;-)  
* Ve al siguiente enlace para crear una cuenta en Google Colab https://colab.research.google.com/ (si tienes una cuenta en gmail solo tienes que iniciar sesión)
* Abre mi notebook de Jupyter que he compartido: [downDataSunat.ipynb](https://colab.research.google.com/drive/1lxpl5YPgDsI7R4wRnxyznjvOGmabrJM2?usp=sharing),  **OJO**: una vez abierto el notebook tienes que hacer clic en el menú:  `Archivo --> Guardar una copia en Drive` para que el archivo se guarde en tu cuenta personal, cierra mi notenook que abriste anteriormente.

    <image src="images/fullCode.jpg" alt="Arquitectura del proyecto">

* Antes de ejecutar el codigo fuente crea un archivo de google sheets en tu drive, y renómbralo como:  `dataSunat`, luego ciérralo.

    <image src="images/Clipboard_01-12-2025_07.jpg" alt="Google Sheets">

* Vuelve a tu archivo notebook de Jupyter y en el menú ejecuta la siguiente opción: `Entorno de ejecución->Ejecutar todas`.

    <image src="images/ejecutar.jpg" alt="Arquitectura del proyecto">

* Primero instalará unos paquetes faltantes para poder procesar los datos, luego en una sección aparecerá una ventana  solicitando permisos y autorizaciones que debe tener google colab a tu drive y crear el archivo google sheets, si sabes como hacerlo da todos los permisos, de lo contrario [aqui te enseño](tutos/otorgarPermisos.md) como hacerlo.
* En la ultima celda, después de ejecutar aparecerá un mensaje al final: `x06120125.TXT se ha cargado satisfactoriamente a Google Sheets`, indicando que todo se ha ejecutado correctamente.
* Podemos ver los archivos descargados y procesados a nuestro drive haciendo clic en el icono que se muestra en la imagen, en este caso ha descargado la data correspondiente al archivo **x06120125.zip** (datos desde el 06 de enero al 12 de enero del 2025)

    <image src="images/Clipboard_achivos descargados.jpg" alt="Ejecutar Celda">

    *No te sorprendas cuando cierras la ventana de google Colab tus archivos desaparezcan, ya que una vez se cierra el entorno, la plataforma limpia todos los datos que pudiste haber cargado, esto al final no te va a servir de mucho ya que la información la tenemos cargada en google sheets*

* Si abrimos el archivo `dataSunat` de google sheets que hemos generado previamente podemos observar que ya se encuentra con la data cargada, disponible para explotarlo con Looker Studio!!!.

    <image src="images/datasunat.jpg" alt="Ejecutar Celda">

* Si no sabes como conectar tu google Sheets a Looker Studio para explotar tu información [aqui te enseño como hacerlo](tutos/otorgarPermisos.md). 

## Looker Studio
Luego de haber realizado la conexión hacia la hoja de google sheets donde se encuentra la información que hemos cargado, y realizar algunos trabajos adicionales para incorporar algunas fuentes de información para analizar mejor la información podemos construir un tablero asombroso como el siguiente:

<image src="images/looker.jpg" alt="Ejecutar Celda">

Este tablero de muestra lo puedes encontrar en el siguiente link: [tablero Looker Studio - Google Sheets](https://lookerstudio.google.com/reporting/c075a43a-20e5-4bfa-8f30-7eb353bcc9d7), ojo que es un tablero básico, tu puedes construir tu propio tablero de acuerdo a tus necesidades.

## Finalmente...

Este proyecto está pensado para estudiantes, investigadores, profesionales e interesados en general, que no estan familizarizados con la programación o el uso de las herramientas que hemos usado, y que a partir de un solo clic puedan analizar la información de exportaciones de la última semana compartida por Sunat, o si tienes conocimientos mas técnicos te puede servir de base para guardar la data a tu base de datos local o conectarlo a servicios en la nube y consumirlos desde ahi...el cielo es el limite!!!.

Eres libre de contribuir a mejorar este proyecto.

Si vas a copiar este proyecto, no te olvides de dar créditos al autor ;-)