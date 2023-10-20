<div align="center">
  
  ![GitHub repo size](https://img.shields.io/github/repo-size/eruedasanchez/git-resume)
  ![GitHub stars](https://img.shields.io/github/stars/eruedasanchez/git-resume?style=social)
  ![GitHub forks](https://img.shields.io/github/forks/eruedasanchez/git-resume?style=social)
  [![Twitter Follow](https://img.shields.io/twitter/follow/RSanchez_Eze?style=social)](https://twitter.com/intent/follow?screen_name=RSanchez_Eze)
  <br />
  <br />

  <h2 align="center">Principios de Git & GitHub</h2>

  Resumen del curso de GitHub dictado por Braise Moure @mouredev. <br/>Todas las anotaciones están basadas fuertemente en el dictado de cada capitulo.

  <a href="https://casmart-moda-ecommerce.vercel.app/" target="_blank"><strong>➥ Live Demo</strong></a>

</div>

<br />

### Instalacion de Git (MacOS)

Comienza situandote en una terminal y ejecuta el siguiente comando:

```bash
$ brew install git
```

Una vez terminada la instalacion de Git, ejecuta el siguiente comando para chequear que Git se haya instalado correctamente:

```bash
$ git --version
``` 
o

```bash
$ git -v
```

Con este comando, podemos chequear la version de Git que hemos instalado.

### Configuracion de Git

Para poder comenzar a trabajar con Git, necesitamos tener registrado tanto nuestro nombre de usuario como nuestro email. Esto lo logramos ejecutando los siguiente manera:

Accede a la carpeta donde estas realizando tu proyecto. Por ejemplo, **git-resumen** y ejecuta el siguiente comando: 

```bash
$ cd git-resumen
```

Luego, registra tu nombre de usuario. Por ejemplo, ezequieldev:

```bash
$ git config --global user.name "ezequieldev"
```

Luego de registrar tu usuario, registra tu dirección de email:

```bash
$ git config --global user.email "ezequiel.ruedasanchez@gmail.com"
```

Ahora, ya estamos en condiciones de poder comenzar a trabajar con Git.

## Git Init

Actualmente tenemos nuestro proyecto situado en la carpeta **git-resumen** vacia. 

Ahora, situados en la carpeta **git-resumen**, vamos a crear nuestro primer archivo del proyecto que llamaremos **hellogit.py** ejecutando el siguiente comando:

```bash
$ touch hellogit.py
```

Escribimos el contenido que deseemos en él obteniendo el siguiente resultado:

![Git init](https://i.postimg.cc/W4y6RShM/git-1.jpg "Creacion de primer archivo en el proyecto")

Ahora, para indicar que queremos trabajar en este directorio (**git-resumen**) con Git, es decir, que queremos inicializar el contexto de un control de versiones en este directorio, ejecutamos en nuestro directorio raiz el siguiente comando:

```bash
$ git init
```

De este modo, se indica que en este directorio se ha instalado un repositorio de Git. Una vez que ejecutamos el comando, obtenemos el siguiente resultado en la terminal:

![Git init](https://i.postimg.cc/3wJMdrrK/git-2.jpg "Ejecucion comando Git init")

## Ramas en Git

Una vez ejecutado en comando **git init**, nos indica que estamos parados en la rama **master**. Ahora, queremos cambiar el nombre de esta rama a **main**. Esto lo hacemos ejecutando el siguiente comando:

```bash
$ git branch -m main
```

De ahora en adelante, nuestra rama principal se llama **main**.

## Git add y Git commit 

Ahora, como hemos estado realizando cambios a nuestro proyecto (creando y colocando codigo al archivo **hellogit.py** y editando nuestro resumen en **README.md**), podemos ver el estado de nuestro repositorio ejecutando el siguiente comando:

```bash
$ git status
```

Obteniendo el siguiente resultado:

![Git add y Git commit](https://i.postimg.cc/bJp8NkCd/git-3.jpg "Ejecucion comando git status")

Esto nos indica que en la rama **main** aun no hay commits y que los archivos **hellogit.py** y **README.md** existen pero los cambios realizados no han sido guardados. 

Ahora si quiero guardar/versionar estos archivos en mi repo de Git, tengo que agregarlos. Es decir, ejecutar el siguiente comando:

```bash
$ git add hellogit.py
```

Ahora, ejecutamos nuevamente el comando **git status** para ver en que estado se encuentra mi repo y obtenemos el siguiente resultado:

![Git add y Git commit](https://i.postimg.cc/CMscBt7c/git-4.jpg "Ejecucion comando git status luego de realizar un git add")

Ahora, aun no tenemos commits pero el archivo **hellogit.py** pasa al staging area, es decir, al escenario para que hagamos algo con el mientras que el archivo **README.md** no ha sido añadido en esta version/fotografia.

Finalmente, lanzamos nuestra version/fotografia ejecutando el siguiente comando:

```bash
$ git commit -m "Este es mi primer commit"
```

Obteniendo el siguiente resultado:

![Git add y Git commit](https://i.postimg.cc/pXPk1DYd/git-5.jpg "Ejecucion comando git commit")

Podemos observar que la terminal nos indica que un archivo ha cambiado y 1 se ha insertado. Ademas, nos proporciona un numero de hash (**b243a1a**).

Por ultimo, si ejecutamos nuevamente el comando **git status**, obtenemos:

![Git add y Git commit](https://i.postimg.cc/wvjVWHdj/git-6.jpg "Ejecucion comando git status luego de git commit")

Ahora, podemos observar que ya se encuentran commits realizados pero que **README.md** aun no se encuentra ni en el staging area.

## Git status y Git log

Para chequear que el cambio se haya realizado, vamos a ejecutar el siguiente comando:

```bash
$ git log
```

Obteniendo el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/ZqpyNgGf/git-7.jpg "Ejecucion comando git log")

Donde nos indica que hasta el momento tenemos un **commit** con el identificador **b243a1a0f5dbc446e78bb39ed0254a895127d6b5** en la rama **main** y los datos del autor y la fecha en la que fue efectuado el commit.

Ahora, vamos a crear otro archivo **hellogit2.py** y vamos a colocarle el siguiente contenido:

![Git status y Git log](https://i.postimg.cc/gkh4zYs5/git-8.jpg "Ejecucion comando git log")

Ahora, si ejecuto el comando **git status**, voy a ver que tengo al archivo **hellogit2.py** sin commitear tambien.

Por lo tanto, si deseo commitearlo ejecuto el comando **git add hellogit2.py** para sumarlo al staging area y luego lo commiteo obteniendo el siguiente resultado: 

![Git status y Git log](https://i.postimg.cc/4dCVFtkx/git-9.jpg "Ejecucion comando git commit")

Ahora, ejecutamos el comando **git log** para chequear los cambios realizados y obtenemos:

![Git status y Git log](https://i.postimg.cc/d3jf0wmG/git-10.jpg "Ejecucion comando git log luego del segundo commit")

Podemos observar que ahora se muestra tambien el segundo commit realizado.

Si editamos el archivo **hellogit.py** y ejecutamos el comando **git status** obtenemos el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/50NgmLwQ/git-11.jpg "Ejecucion comando git status luego de modificar un archivo")

Ahora, me indica que el archivo **hellogit.py** no es un archivo nuevo sino que es un archivo de tipo **modified** o **modificado**

Vamos a editar tambien el archivo **hellogit2.py** como se muestra en la imagen a continuación y ejecutamos el comando **git status** obteniendo el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/zXqYWPQx/git-12.jpg "Ejecucion comando git status luego de modificar un archivo")

Finalmente, tenemos ahora los dos archivos .py modificados.

## Git checkout y reset

Ahora, supongamos que quiero volver al estado anterior del archivo **hellogit2.py**, es decir, quiero eliminarle todos los numeros 2 que le coloque al final. Para ello, vamos a ejecutar el siguiente comando:

```bash
$ git checkout hellogit2.py
```

Obteniendo el siguiente resultado: 

![Git status y Git log](https://i.postimg.cc/RVyt08GD/git-13.jpg "Ejecucion comando git checkout")

Es importante notar que la modificación de agregado de los numeros 2 en el archivo **hellogit2.py** no se encontraba commiteada.

Ahora, si quiero volver al estado anterior del archivo **hellogit.py**, simplemente ejecuto el comando **git checkout hellogit.py**. Notemos, que al igual que en el otro archivo, los cambios no se habian commiteado.

Ahora, edito el archivo **hellogit.py**

![Git status y Git log](https://i.postimg.cc/44WGpHKD/git-14.jpg "Edicion de hellogit.py")

Y lo commiteo ejecutando los siguientes comandos:

```bash
$ git add hellogit.py
$ git commit -m "Se actualiza el texto del print" 
```

Ejecuto el comando **git log** para ver el historial de cambios y obtengo:

![Git status y Git log](https://i.postimg.cc/g22bjzkY/git-15.jpg "Ejecucion git log luego del tercer commit")

Podemos notar que se suma el tercer commit al historial de cambios.

Ahora si ejecuto el comando:

```bash
$ git log --graph 
```

Obtenemos el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/SRXR96GG/git-16.jpg "Ejecucion git log --graph")

Podemos notar como se muestran los commits pero ya todo organizado con ramas.

Ahora ejecutando el comando:

```bash
$ git log --graph --pretty=oneline
```

Obtenemos el mismo historial de cambios pero donde solo se muestra el hash con el nombre del commit.

![Git status y Git log](https://i.postimg.cc/sf7fSgPy/git-17.jpg "Ejecucion git log --graph --pretty=oneline")

Ahora si ejecuto el comando:

```bash
$ git log --graph --decorate --all --oneline
```

Obtenemos todo el historial de cambios como anteriormente pero con no todos los hash enteros sino con solo el principio de cada uno de ellos.

![Git status y Git log](https://i.postimg.cc/KYX7Q5p4/git-18.jpg "Ejecucion git log --graph --decorate --all --oneline")

## Git alias

Para evitar tener que acordarme cada vez que tenga que escribir un comando largo o en el caso que tenga que escribir una conjunción de comandos, puedo utilizar los **alias**.

Por ejemplo, podemos redefir el comando **git log --graph --decorate --all --oneline** como **git tree** de la siguiente manera:

```bash
$ git config --global alias.tree "log --graph --decorate --all --oneline"
```

Ahora, ejecutando el comando **git tree** obtenemos el mismo resultado:

![Git status y Git log](https://i.postimg.cc/Y9XfMBRy/git-19.jpg "Ejecución git tree")

## Gitignore

Ahora para que git ignore archivos y nunca los pase al staging area, creamos un archivo llamado **.gitignore** para ignorar todo aquello que no deseamos que se suba al repositorio. 

Colocamos por ejemplo al archivo **.gitignore** todas aquellas expresiones de **DS_Store** que son generadas por Mac de la siguiente manera:

![Git status y Git log](https://i.postimg.cc/J0fJKNRR/git-20.jpg "Creación archivo .gitignore")

Por ultimo, añadimos el **.gitignore** a nuestro repositorio y commiteamos de la siguiente manera:

```bash
$ git add .gitignore
$ git commit -m "Se añade el .gitignore"
```

## Git diff

Ahora, supongamos que modifico el archivo **hellogit.py** de la siguiente manera (agrego al print with changes!):

![Git diff](https://i.postimg.cc/fLykSB6J/git-21.jpg "Modificación archivo .hellogit.py")

Ahora, supongamos que comence a programar otros archivos pero no estoy seguro de querer hacerle una fotografia/versionar el archivo **hellogit.py** con el cambio realizado. 

Entonces, para ver que cambios realice desde el ultimo commit puedo ejecutar el comando:

```bash
$ git diff
```

Obteniendo el siguiente resultado:

![Git diff](https://i.postimg.cc/GhdPH1X2/git-22.jpg "Resultado de ejecutar git diff")

Podemos observar que nos esta indicando que estamos modificando (eliminando y agregando lineas de código) dos archivos: el archivo **README.md** con el nuevo texto que estamos escribiendo y el archivo **hellogit.py** con el agregado de "with changes!" al print.

## Desplazamiento

Comenzamos ejecutando el comando **git log** para ver nuestro historial de cambios:

![Desplazamiento](https://i.postimg.cc/jdYWjQd4/git-23.jpg "Historial de cambios git log")

Ahora, supongamos que queremos volver al estado donde se realizo el primer commit, es decir, al commit con el numero de hash **b243a1a0f5dbc446e78bb39ed0254a895127d6b5**.

Para ello, ejecutamos el comando:

```bash
$ git checkout b243a1a0f5dbc446e78bb39ed0254a895127d6b5
```

Obteniendo el siguiente error:

Esto se debe a que los archivos **hellogit.py** y **README.md** fueron modificados pero sus cambios nunca fueron commiteados.

![Desplazamiento](https://i.postimg.cc/52CFg4Nb/git-24.jpg "Error git checkout")

Para ello podemos ejecutar:

```bash
$ git checkout hellogit.py
$ git checkout README.md
```

Ahora que ya tenemos todo actualizado, podemos volver al estado del primer commit ejecutando el comando:

```bash
$ git checkout b243a1a0f5dbc446e78bb39ed0254a895127d6b5
```

Obteniendo el siguiente resultado:

![Desplazamiento](https://i.postimg.cc/HxdgK2wB/git-25.jpg "Ejecucion git checkout b243a1a0f5dbc446e78bb39ed0254a895127d6b5")

Ahora, si queremos volver al ultimo commit, ejecutamos el comando:

```bash
$ git checkout HEAD
```

Ejecutamos **git log** para chequear en que estado nos encontramos:

![Desplazamiento](https://i.postimg.cc/sXYpfVZ3/git-26.jpg "Ejecucion git log luego git checkout HEAD")

Y observamos que de esta manera, solo movemos la cabeza (HEAD) del proyecto al estado del primer commit.

Ahora, ejecutamos **git tree** y observamos lo siguiente:

![Desplazamiento](https://i.postimg.cc/nzXq7v5c/git-27.jpg "Ejecucion git tree luego git checkout HEAD")

Por lo tanto, si quiero volver al ultimo estado de la rama (donde apunta main), coloco la cabeza (HEAD) de la rama
Apuntando allí de la siguiente manera:

```bash
$ git checkout 9f52593
```

Y si ejecutamos **git tree** nuevamente, obtenemos el resultado esperado.

![Desplazamiento](https://i.postimg.cc/X7s7MTqm/git-28.jpg "Ejecucion git tree luego git checkout 9f52593")

De este modo, se vuelven a restablecer los archivos **hellogit2.py** y **.gitignore**.

## Git reset hard y git reflog

Ahora, me encuentro al final de la rama. Supongamos que cometi un error con los ultimos tres commits y quiero volver al estado correspondiente al segundo commit, es decir, al estado que tiene el hash **f7d6db2**. Para ello, puedo ejecutar el comando:

```bash
$ git reset --hard f7d6db2
```

![Git reset hard y git reflog](https://i.postimg.cc/N05J1LyD/git-29.jpg "Ejecucion git reset --hard f7d6db2")

Podemos observar ahora como la cabeza (HEAD) de la rama ahora esta apuntando al estado correspondiente al segundo commit y se produce como una especie de borrado de todos los commits que se realizaron luego.

Ahora, si quiero ver toda la actividad que estuve realizando porque quiero volver al estado correspondiente al ultimo commit ejecuto el siguiente comando:

```bash
$ git reflog
```

![Git reflog](https://i.postimg.cc/Y09H5YbF/git-30.jpg "Ejecucion git reflog")

Entonces, podemos ejecutar los comandos:

```bash
$ git checkout 9f52593
$ git checkout main
```
 Para volver al estado correspondiente al ultimo commit y obtenemos lo que esperamos.

![Git reflog](https://i.postimg.cc/qvzWh72x/git-31.jpg "Ejecucion git tree luego de que HEAD vuelva a apuntar a main")

## Git tag

Los tags se utilizan para guardar referencias importantes comno por ejemplo las versiones en las aplicaciones. 

Por ejemplo, puedo crear un tag que referencie al ultimo commit ejecutando el siguiente comando:

```bash
$ git tag "clase_1"
```

Obteniendo el siguiente resultado:

![Git tag](https://i.postimg.cc/vm4VXnSZ/git-32.jpg "Ejecucion git tag clase_1")

Con esto podemos observamos que la cabeza (HEAD) de la rama main está apuntando al ultimo commit pero ademas tiene un **tag** asociado llamado **clase_1**. Es decir, le colocamos un nombre identificatorio al ultimo commit.

Ahora, voy a crear un nuevo archivo que voy a llamar **hellogit3.py** con un print como se muestra a continuación.

![Git tag](https://i.postimg.cc/MGWbzXT7/git-33.jpg "Creacion archivo hellogit3.py")

Una vez creado el archivo, vamos a agregar todo al staging area ejecutando el siguiente comando:

```bash
$ git add .
```

El comando **git add .** permite agregar a todos los archivos que esten pendientes al staging area.





























































































### Technologies

* [React Js](): Version 18.2.0
* [HTML](): Version 5 
* [CSS](): Version 3
* [Node Js](): Version 18.16.1
* [Ion Icons](): Version 5.2.3
* [GIT](): Version 2.40

### Prerequisites

Before you begin, ensure you have met the following requirements:

* [Git](https://git-scm.com/downloads "Download Git") must be installed on your operating system.
* [Node Js](https://nodejs.org/es/download "Download Node Js") must be installed on your operating system.

### Run Locally

To run **Casmart** locally, run this command on your git bash:

Linux and macOS:

```bash
$ sudo git clone https://github.com/eruedasanchez/casmart-ecommerce.git
$ cd casmart-ecommerce
$ npm start
```

Windows:

```bash
$ sudo git clone https://github.com/eruedasanchez/casmart-ecommerce.git
$ cd casmart-ecommerce
$ npm start
```

### Contact

If you want to contact with me you can reach me at [LinkedIn](https://www.linkedin.com/in/e-ruedasanchez/).

### License

This project is **free to use** and does not contains any license.