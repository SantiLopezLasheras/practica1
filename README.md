# Práctica 1

## Introducción a Git

### ¿Qué es Git?

Git es un sistema de control de versiones distribuido que nos facilita el trabajo de desarrollo en proyectos grandes, ya que cada vez que realizamos algún cambio y lo guardamos, se crea una instantánea del estado de nuestro proyecto en ese momento. Estas instantáneas nos permiten deshacer cambios o errores, o volver a versiones anteriores en caso de que sea necesario.
        
Es distribuido porque cada vez que un desarrollador se descarga el proyecto, se crea una copia completa del repositorio, de manera que cada desarrollador tiene localmente todos los archivos del proyecto.
        
Además, Git nos permite crear diversas ramas de nuestro proyecto. Por ejemplo, podemos tener una rama principal que sería nuestro proyecto ya en producción y live para los usuarios que lo visite, y aparte otras ramas o bifurcaciones en las que el equipo de desarrollo está introduciendo cambios, probando nuevas funcionalidades, etc.

### ¿En qué consiste la metodología Git Flow?

Git Flow es una metodología popularizada por Vincenet Driessen que organiza de forma más estricta el trabajo con distintas ramas, es decir, establece unas reglas acerca de cuánto y cómo interactúan las distintas ramas entre sí.

La metodología consiste en dos ramas principales: la rama master que contiene siempre el código listo para producción y la rama develop que contiene siempre los últimos cambios desarrollados para la próxima versión del proyecto. Cuando el código de la rama develop ya ha sido testeado y es estable, se integra o fusiona con la rama master para lanzar la nueva versión del proyecto.

Aparte de las dos ramas principales, tenemos otros 3 tipos de ramas: 

- Ramas de funcionalidad (feature branches): son bifurcaciones de la rama de desarrollo para añadir nueva funcionalidad al proyecto. Una vez se termina de añadir la nueva funcionalidad, se fusiona con la rama de desarrollo.

- Ramas de versión (release branches): cuando nuestra rama de desarrollo tienes suficientes features o funcionalidades nuevas o hay alguna fecha de lanzamiento de una nueva versión cerca, es momento de crear una rama de versión. En esta rama ya no se añaden más cambios o funcionalidades, pero sí que se corrigen errores. Una vez corregidos y comprobado que la versión funciona correctamente, se fusiona con las ramas master y develop.

- Ramas de parches (hotfix branches): este tipo de ramas son las únicas que se deben bifurcar directamente de la rama master y se utilizan para corregir errores urgentes del código. Una vez solucionado, se fusiona tanto con la rama master y con la de desarrollo para que ambas ramas principales estén actualizadas con el error corregido.

### ¿Por qué utilizar Git Flow?

Se recomienda utilizar Git Flow en equipos de trabajo que tengan al menos más de 2 personas y donde en el proyecto se realicen cambios bastante frecuentes. La implementación de Git Flow es este tipo de proyectos tiene ciertas ventajas:

- aumenta la velocidad a la hora de entregar al equipo de pruebas código ya terminado
- disminuyen los errores humanos al mezclar ramas
- elimina la dependencia de funcionalidades al momento de entregar código para producción
- facilita la organización del trabajo con las distintas ramas

## Documentación de la práctica

En esta práctica vamos a simular que un cliente nos ha pedido crear una página web sencilla con un curso sobre manipulación del DOM mediante JavaScript. Simularemos que somos un equipo de 3 personas (Santiago López, Jane Doe y John Smith) que nos encargaremos de las distintas secciones de la página web y utilizaremos la metodología Git Flow para facilitarnos el desarrollo en equipo. Los pasos seguidos para la realización del proyecto son:

1. El usuario Santiago Lopez se ha encargado de crear primero el repositorio para el curso en GitHub.
<img src="/assets/images/practica1.png" alt="creando un repositorio en GitHub" width="500">

2. A continuacion, ha utilizado el comando git clone para clonar el repositorio localmente y ha iniciado el flujo de trabajo Git Flow con el comando git flow init, estableciendo las ramas principales main y development, y el resto de bifurcaciones para features, hotfixes y releases.
   
<img src="/assets/images/practica2.png" alt="creando un repositorio en GitHub" width="500">

3. El siguiente paso ha sido subir el repositorio ya configurado con la metodología git flow a GitHub, para ello se ha usado el comando git push --set-upstream origin development.

<img src="/assets/images/practica3.png" alt="creando un repositorio en GitHub" width="500">

4. Santiago Lopez se ha encargado de crear la primera versión de la página web del curso de JavaScript, que contiene la página HOME con una breve introducción del curso. Una vez finalizada la página inicial, se ha hecho un commit del proyecto. Esto se lleva a cabo, como de costumbre, en la rama development.

<img src="/assets/images/practica4.png" alt="creando un repositorio en GitHub" width="500">

5. A contunuación hemos actualizado el repositorio en GitHub.

<img src="/assets/images/practica5.png" alt="creando un repositorio en GitHub" width="500">

6. En GitHub podemos ver que los archivos se han subido correctamente a la rama development (la rama main sin embargo sigue vacía porque aún no hemos pasado los cambios a producción)

<img src="/assets/images/practica6.png" alt="creando un repositorio en GitHub" width="500">

7. Nuestra compañera Jane Doe se ha descargado el repositorio con un git pull y ha empezado a trabajar también en el proyecto. En este caso, se ha encardago de añadir nuevas funcionalidades a la página web del curso. Primero ha iniciado una rama feature para añadir una nueva sección al curso que consistirá en un explicación de cómo modificar contenido HTML mediante el uso de JavaScript. La rama se ha creado con el comando "git flow feature start".

<img src="/assets/images/practica13.png" alt="creando un repositorio en GitHub" width="500">

8. Una vez creado el contenido de la sección, se ha hecho commit para guardar los cambios.
   
<img src="/assets/images/practica14.png" alt="creando un repositorio en GitHub" width="500">

9. Como esta funcionalidad ya está terminada, hemos terminado esta rama con el comando "git flow feature finish", mediante el cual la rama feature se ha eliminado y fusionado con la rama principal development.
      
<img src="/assets/images/practica15.png" alt="creando un repositorio en GitHub" width="500">

10. Jane Doe también ha añadido una segunda sección acerca del manejo de los atributos HTML mediante JavaScript. Para ello, ha creado una nueva bifurcación con el comando "git flow feature start".
    
<img src="/assets/images/practica18.png" alt="creando un repositorio en GitHub" width="500">

11. Del mismo modo, una vez terminada la sección, se ha fusionado esta subrama con la rama principal development haciendo uso del comando "git flow feature finish". Después ha subido los cambios al repositorio de GitHub para que este estuviera actualizado.
    
<img src="/assets/images/practica19.png" alt="creando un repositorio en GitHub" width="500">

12. Nuestro compañero John Smith tiene más conocimientos sobre estilos en CSS y se ha encargado de crear una sección sobre esto en la página web. Se ha descargado el repositorio en su estado actual con un "git pull origin" y ha creado una nueva subrama localmente con "git flow feature start" para la sección de estilos CSS.
    
<img src="/assets/images/practica20.png" alt="creando un repositorio en GitHub" width="500">

13. Al finalizar su parte del trabajo, ha fusionado esta subrama con la de development gracias al comando "git flow feature finish".
    
<img src="/assets/images/practica21.png" alt="creando un repositorio en GitHub" width="500">

14. Como el proyecto ya tiene las funcionalidades requeridadas implementadas (secciones HOME, Modificar contenido HTML, Modificar atributos HTML y Modificar estilos CSS), el usuario John Smith se ha ocupado de preparar una versión release del proyecto para enviarla a producción. Para ello, ha usado el comando "git flow release start v1.0".

<img src="/assets/images/practica22.png" alt="creando un repositorio en GitHub" width="500">

15. Cuando la versión v1.0 de la página web ya estaba lista para ser publicada, ha utilizado el comando "git flow release finish v1.0". Con este comando, la subrama release se ha eliminado y ha sido fusionada con ambas ramas principales (main y development). Se ha añadido una etiqueta v1.0 para poder identificar las distintas versiones de la web en un futuro.
    
<img src="/assets/images/practica23.png" alt="creando un repositorio en GitHub" width="500">

16. Para que el proyecto esté actualizado en el repositorio remoto de GitHub, nuestro compañero ha subido ambas ramas main y development con el comando "git push origin"
    
<img src="/assets/images/practica24.png" alt="creando un repositorio en GitHub" width="500">

17. Santiago Lopez ha comprobado la versión 1.0 de la página web, pero ha detectado algunos errores de estilo en la sección de Modificar Contenido HTML. Ha creado una bifurcación de main con el comando "git flow hotfix start" para corregir estos errores, y ha guardado los cambios haciendo commit.
    
<img src="/assets/images/practica25.png" alt="creando un repositorio en GitHub" width="500">

18. Finalmente, una vez añadido los estilos que faltaban en la sección, ha concluido la subrama con el comando "git flow hotfix finish", de manera que esta se ha fusionado con la rama main y development, para que estos cambios estén actualizados en ambas ramas principales. Este hotfix se ha etiquetado como milloresV_1_0 para poder referenciarlo en un futuro. Después ha subido los cambios al repositorio de GitHub con git push.
    
<img src="/assets/images/practica26.png" alt="creando un repositorio en GitHub" width="500">

19. Una vez finalizado el proyecto, hemos creado esta rama gh-pages para proceder a la publicación de la página web del curso, incluyendo el presente documento README.md con una introducción teórica sobre Git y Git Flow, así como un resumen del proceso de trabajo para crear el proyecto.
