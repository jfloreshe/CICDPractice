# Turorial
## Prerequisitos
Java
## Instalación
Descargar el archivo ```jenkins.war``` usando el siguiente enlace
```
http://mirrors.jenkins.io/war-stable/latest/jenkins.war
```
Ejecutar el jenkins.war
```
java -jar jenkins.war --httpPort=8080
```
Con esto ya podemos abrir un navegador y entrar a la interfaz de jenkins con el siguiente url
```
localhots:8080
```
Crearse una cuenta o logearse directamente

![Login](https://github.com/jfloreshe/CICDPractice/blob/master/images/login.PNG)
## Integración
### Creación de un nuevo pipeline
Para empezar tenemos que crear una nueva tarea
![NuevaTarea](https://github.com/jfloreshe/CICDPractice/blob/master/images/nuevatarea.PNG)

Agregamos un nombre, seleccionamos Pipeline y clickeamos OK
![NuevaTarea1](https://github.com/jfloreshe/CICDPractice/blob/master/images/nuevatarea1.PNG)

### Configuración del pipeline
La integración que realizaremos será mediante un repositorio, para esto una vez creado el nuevo pipeline se redirigirá a la ventana de configuración de este tenemos que ir a la opción ***Pipeline***
![Configuracion](https://github.com/jfloreshe/CICDPractice/blob/master/images/configuracion.PNG)

Ahora tenemos que seleccionar que la integración será mediante un repositorio en git, para esto cambiamos ***Definition*** a la opción _Italic Pipeline script from SCM here_, en ***SCM*** seleccionamos _Italic Git here_ y en ***Repository URL*** colocamos nuestro repositorio al que deseamos hacerle integración continua, en mi caso ```https://github.com/jfloreshe/CICDPractice```.
Por último tenemos que ingresar en ***Script Path*** donde se encuentra nuestro archivo de configuración de Jenkins en el projecto, en nuestro caso está en el root, para finalizar dar click en Guardar.
![Configuracion1](https://github.com/jfloreshe/CICDPractice/blob/master/images/configuracion1.PNG)

### Configurando Jenkinsfile
Este archivo nos permitirá configurar el pipeline de jenkins asignandole stages que serán ejecutados secuencialmente, en este ejemplo habrán 3 stages _Italic Build, Test y Deploy here_, simulando estos 3 pasos de la integración continua, en build con un proyecto más grande podriamos hacer que se haga la construcción automática con un cmake, maven u otras herramientas.
![Jenkinsfile](https://github.com/jfloreshe/CICDPractice/blob/master/images/jenkinsfile.PNG)

### Jenkins haciendo su trabajo
Para poder ejecutar luego de configurar nuestro Jenkinsfile debemos darle click en Construir ahora y esperar por los resultados
![Ejecutando](https://github.com/jfloreshe/CICDPractice/blob/master/images/ejecutando.PNG)

### Resultados
Los resultados se visualizarán en ***Historia de tareas*** o ***Status*** en este caso hay 2 resultados.
![Resultados](https://github.com/jfloreshe/CICDPractice/blob/master/images/resultados.PNG)

El resultado de cada stage se podrá ver en su respectivo Log, para esto sólo debemos poner el mouse sobre un stage y hacerle click en Logs
![Resultados1](https://github.com/jfloreshe/CICDPractice/blob/master/images/resultados1.PNG)

En este caso Checkout SCM nos muestra el proceso de clonado y configuración del repositorio en git
![Resultados2](https://github.com/jfloreshe/CICDPractice/blob/master/images/resultados2.PNG)






