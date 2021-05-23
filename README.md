![logo](https://user-images.githubusercontent.com/84646649/119243644-a6714000-bb36-11eb-8acf-bee3f2454414.png)

# SciTool

SciTool es una librería JavaScript para especialistas y no-especialistas en desarrollo de software, diseñada para escribir 100% en JavaScript el front-end de aplicaciones web, facilitando el desarrollo, especialmente en proyectos de Data Science. La interfaz de usuario se basa en un escritorio ilimitado con ventanas flotantes que permiten multitarea, llamadas **Documentos**.

## Uso

Se debe incorporar el archivo scitool.js en el index.html como cualquier librería, y escribir el programa con JavaScript y SciTool dentro del "<body>" o en archivos .js como componentes.
Se recomienda que cada documento (ventana) o componente se escriba en un archivo aparte, para lograr una estructura clara que ayude a la mantención o actualización del software, y que además permita su reutilización en otros proyectos.
Crear una aplicación web es tan sencillo como escribir AddDocument, AddButton, AddLabel, etc. para crear una interfaz de usuario, y codificar sus eventos que SciTool crea automáticamente como funciones nombradas con el mismo nombre de los objetos más el nombre del evento.

### Características:

- Los documentos se muestran al usuario instantáneamente, sin que deba esperar su descarga desde internet como sucede con las páginas web tradicionales, pues ya se descargaron en segundo plano al inicio.

- Cada documento puede escribirse en un archivo con la interfaz de usuario, datos y métodos, como un componente completo.

- No se requiere crear funciones de eventos. Estos están listos para ser programados en funciones como: function NombreObjeto_OnNombreEvento() {código...}

- Los componentes no se deben referenciar entre sí ni a sus objetos, para lograr componentes completamente reutilizables. Esto se puede conseguir porque cada objeto dispone de un método *Talk* a través del cual emitir mensajes, y un método *Listen* que escucha a todos los demás, de modo de poder programar las reacciones que correspondan en los objetos que deban reaccionar a uno o más mensajes en particular.

- Se incluye validación de datos automática, como enteros, reales, rangos, alfanuméricos, etc.

- Además, el usuario dispone de un escritorio ilimitado con infinitas mesas de trabajo para organizar sus documentos como desee.
  
### ¡Hola mundo!

El siguiente código crea un documento flotante con el mensaje *!Hola mundo!* que aparece automáticamente cuando se carga.

Archivo: index.html
```
<!DOCTYPE html>
<html>
    <head>
        <script type="text/javascript" src="scitool.js"></script> //Importar SciTool.
    </head>

    <body>
        <script>
            sci.Begin() //Inicializar SciTool.
            sci.LoadComponent('DocHolaMundo.js') //Cargar documento.
        </script>
    </body>
</html>
```

Archivo: DocHolaMundo.js
```
sci.AddDocument(0,0,400,200,'','DocHolaMundo') //Crear documento.
DocHolaMundo.AddLabel(10,30,'¡Hola Mundo!') //Añadir un label al documento.

function ComponentDocHolaMundo_OnLoaded() { //Abrir el documento cuando esté cargado.
    DocHolaMundo.Bring()
}
```

## PARTICIPACIÓN

Este proyecto es open source, y queda disponible a la comunidad tanto para su uso como para participar activamente, sea programando nuevas características, escribiendo el manual, realizando pruebas, difundiendo o aportando ideas. Todos son bienvenidos.

Para colaborar desarrollando:

Puedes tomar uno de los issues o proponer uno nuevo, y luego crea una rama para desarrollarlo. Cuando termines, realiza un Pull Request.
El archivo a editar es el que está escrito en TypeScript.

# Licencia

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2021, Gabriel Lucero
