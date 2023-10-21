<div align="center">
  
  ![GitHub repo size](https://img.shields.io/github/repo-size/eruedasanchez/git-resume)
  ![GitHub stars](https://img.shields.io/github/stars/eruedasanchez/git-resume?style=social)
  ![GitHub forks](https://img.shields.io/github/forks/eruedasanchez/git-resume?style=social)
  [![Twitter Follow](https://img.shields.io/twitter/follow/RSanchez_Eze?style=social)](https://twitter.com/intent/follow?screen_name=RSanchez_Eze)
  <br />
  <br />

  <h2 align="center">Principios de Git & GitHub</h2>

  Resumen del curso de GitHub dictado por Braise Moure @mouredev. <br/>Todas las anotaciones están basadas fuertemente en el dictado de cada capitulo.
</div>

<br />

## Instalacion de Git (MacOS)

Comenzamos situandonos en una terminal y ejecutamos el siguiente comando:

```bash
$ brew install git
```

Una vez terminada la instalación de Git, ejecutamos el siguiente comando para chequear que Git se haya instalado correctamente:

```bash
$ git --version
``` 
ó

```bash
$ git -v
```

Con este comando, podemos chequear la versión de Git que hemos instalado.

## Configuración de Git

Para poder comenzar a trabajar con Git, necesitamos tener registrado tanto nuestro nombre de usuario como nuestro email. Para ello, lo realizamos de la siguiente manera:

* Accedemos a la carpeta donde estamos realizando el proyecto. Por ejemplo, **git-resumen** y ejecutamos el siguiente comando: 

```bash
$ cd git-resumen
```

Luego, registramos el nombre de usuario. Por ejemplo, ezequieldev:

```bash
$ git config --global user.name "ezequieldev"
```

Luego de registrar el usuario, registramos la dirección de email:

```bash
$ git config --global user.email "ezequiel.ruedasanchez@gmail.com"
```

Ahora, ya estamos en condiciones de poder comenzar a trabajar con Git.

## Git init

Actualmente tenemos nuestro proyecto situado en la carpeta `git-resumen` y se encuentra vacia. 

Ahora, situados en la carpeta `git-resumen`, vamos a crear nuestro primer archivo del proyecto que llamaremos `hellogit.py` ejecutando el siguiente comando:

```bash
$ touch hellogit.py
```

Escribimos un print en él y obtenemos el siguiente resultado:

![Git init](https://i.postimg.cc/W4y6RShM/git-1.jpg "Creacion de primer archivo en el proyecto")

Ahora, para indicar que queremos trabajar en este directorio (`git-resumen`) con Git, es decir, que queremos inicializar el contexto de un control de versiones en este directorio, ejecutamos en nuestro directorio raiz el siguiente comando:

```bash
$ git init
```

De este modo, indicamos que en este directorio se ha instalado un repositorio de Git. Una vez que ejecutamos el comando, obtenemos el siguiente resultado en la terminal:

![Git init](https://i.postimg.cc/3wJMdrrK/git-2.jpg "Ejecucion comando Git init")

## Ramas en Git

Una vez ejecutado en comando `git init`, nos indica que estamos parados en la rama `master`. Ahora, queremos cambiar el nombre de esta rama a `main`. Lo hacemos ejecutando el siguiente comando:

```bash
$ git branch -m main
```

De ahora en adelante, nuestra rama principal se llama `main`.

## Git add y Git commit 

Hemos estado realizando cambios a nuestro proyecto (creando y colocando código al archivo `hellogit.py` y editando nuestro resumen en `README.md`). Para ver el estado de nuestro repositorio ejecutamos el siguiente comando:

```bash
$ git status
```

Obteniendo el siguiente resultado:

![Git add y git commit](https://i.postimg.cc/bJp8NkCd/git-3.jpg "Ejecución comando git status")

Esto nos indica que en la rama `main` aún no hay commits y que los archivos `hellogit.py` y `README.md` existen pero los cambios realizados no han sido guardados. 

Ahora si quiero guardar/versionar estos archivos en mi repositorio de Git, tengo que agregarlos. Y ejecutamos el siguiente comando:

```bash
$ git add hellogit.py
```

Ahora, ejecutamos nuevamente el comando `git status` para ver en que estado se encuentra mi repositorio y obtenemos el siguiente resultado:

![Git add y Git commit](https://i.postimg.cc/CMscBt7c/git-4.jpg "Ejecucion comando git status luego de realizar un git add")

Aún no tenemos commits pero el archivo `hellogit.py` pasa al staging area, es decir, al escenario para que hagamos algo con el mientras que el archivo `README.md` no ha sido añadido en esta version/fotografia.

Finalmente, lanzamos nuestra versión/fotografia ejecutando el siguiente comando:

```bash
$ git commit -m "Este es mi primer commit"
```

Obteniendo el siguiente resultado:

![Git add y Git commit](https://i.postimg.cc/pXPk1DYd/git-5.jpg "Ejecucion comando git commit")

Podemos observar que la terminal nos indica que un archivo ha cambiado y 1 se ha insertado. Ademas, nos proporciona un numero de hash (`b243a1a`).

Por ultimo, si ejecutamos nuevamente el comando `git status`, obtenemos:

![Git add y Git commit](https://i.postimg.cc/wvjVWHdj/git-6.jpg "Ejecucion comando git status luego de git commit")

Ahora, podemos observar que ya se encuentran commits realizados pero que `README.md` aun no se encuentra ni en el staging area.

## Git status y git log

Para chequear que el cambio se haya realizado, ejecutamos el siguiente comando:

```bash
$ git log
```

Obteniendo el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/ZqpyNgGf/git-7.jpg "Ejecucion comando git log")

Donde nos indica que hasta el momento tenemos un `commit` con el identificador `b243a1a0f5dbc446e78bb39ed0254a895127d6b5` en la rama `main` con los datos del autor y la fecha en la que fue efectuado el commit.

Ahora, vamos a crear otro archivo `hellogit2.py` y vamos a colocarle el siguiente contenido:

![Git status y Git log](https://i.postimg.cc/gkh4zYs5/git-8.jpg "Ejecucion comando git log")

Ahora, si ejecutamos el comando `git status`, vemos que tenemos el archivo `hellogit2.py` sin commitear tambien.

Por lo tanto, si deseamos commitear ejecutamos el comando `git add hellogit2.py` para sumarlo al staging area y luego commitearlo obteniendo el siguiente resultado: 

![Git status y Git log](https://i.postimg.cc/4dCVFtkx/git-9.jpg "Ejecucion comando git commit")

Ahora, ejecutamos el comando `git log` para chequear los cambios realizados y obtenemos:

![Git status y Git log](https://i.postimg.cc/d3jf0wmG/git-10.jpg "Ejecucion comando git log luego del segundo commit")

Podemos observar que ahora se muestra tambien el segundo commit realizado.

Si editamos el archivo `hellogit.py` y ejecutamos el comando `git status` obtenemos el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/50NgmLwQ/git-11.jpg "Ejecucion comando git status luego de modificar un archivo")

Ahora, me indica que el archivo `hellogit.py` no es un archivo nuevo sino que es un archivo de tipo `modified` o `modificado`

Vamos a editar tambien el archivo `hellogit2.py` como se muestra en la imagen a continuación y ejecutamos el comando `git status` obteniendo el siguiente resultado:

![Git status y Git log](https://i.postimg.cc/zXqYWPQx/git-12.jpg "Ejecucion comando git status luego de modificar un archivo")

Finalmente, tenemos ahora los dos archivos .py modificados.

## Git checkout y reset

Ahora, supongamos que quiero volver al estado anterior del archivo `hellogit2.py`, es decir, quiero eliminar todos los números 2 que le coloque al final. Para ello, vamos a ejecutar el siguiente comando:

```bash
$ git checkout hellogit2.py
```

Obteniendo el siguiente resultado: 

![Git status y Git log](https://i.postimg.cc/RVyt08GD/git-13.jpg "Ejecucion comando git checkout")

Es importante notar que la modificación de agregado de los números 2 en el archivo `hellogit2.py` no se encontraba commiteada.

Ahora, si queremos volver al estado anterior del archivo `hellogit.py`, simplemente ejecutamos el comando `git checkout hellogit.py`. Notemos que al igual que en el otro archivo, los cambios no se habían commiteado.

Ahora, editamos el archivo `hellogit.py`.

![Git status y Git log](https://i.postimg.cc/44WGpHKD/git-14.jpg "Edicion de hellogit.py")

Y lo commiteamos ejecutando los siguientes comandos:

```bash
$ git add hellogit.py
$ git commit -m "Se actualiza el texto del print" 
```

Ejecutamos el comando `git log` para ver el historial de cambios y obtenemos:

![Git status y Git log](https://i.postimg.cc/g22bjzkY/git-15.jpg "Ejecucion git log luego del tercer commit")

Podemos notar que se suma el tercer commit al historial de cambios.

Ahora si ejecutamos el comando:

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

Obtenemos todo el historial de cambios como anteriormente pero no todos los hash enteros sino con solo el principio de cada uno de ellos.

![Git status y Git log](https://i.postimg.cc/KYX7Q5p4/git-18.jpg "Ejecucion git log --graph --decorate --all --oneline")

## Git alias

Para evitar tener que acordarnos cada vez que tenemos que escribir un comando largo o en el caso que tengamos que escribir una conjunción de comandos, podemos utilizar los **alias**.

Por ejemplo, podemos redefir el comando `git log --graph --decorate --all --oneline` como `git tree` de la siguiente manera:

```bash
$ git config --global alias.tree "log --graph --decorate --all --oneline"
```

Ahora, ejecutando el comando `git tree` obtenemos el mismo resultado:

![Git status y Git log](https://i.postimg.cc/Y9XfMBRy/git-19.jpg "Ejecución git tree")

## Gitignore

Para que `Git` ignore archivos y nunca los pase al staging area, creamos un archivo llamado `.gitignore` para ignorar todo aquello que no deseamos que se suba al repositorio. 

Colocamos por ejemplo al archivo `.gitignore` todas aquellas expresiones de `DS_Store` que son generadas por Mac de la siguiente manera:

![Git status y Git log](https://i.postimg.cc/J0fJKNRR/git-20.jpg "Creación archivo .gitignore")

Por ultimo, añadimos el `.gitignore` a nuestro repositorio y commiteamos de la siguiente manera:

```bash
$ git add .gitignore
$ git commit -m "Se añade el .gitignore"
```

## Git diff

Supongamos que modificamos el archivo `hellogit.py` de la siguiente manera (agrego al print with changes!):

![Git diff](https://i.postimg.cc/fLykSB6J/git-21.jpg "Modificación archivo .hellogit.py")

Ahora, supongamos que comenzamos a programar otros archivos pero no estoy seguro de querer hacerle una fotografia/versionar el archivo `hellogit.py` con el cambio realizado. 

Entonces, para ver que cambios realizamos desde el último commit puedo ejecutar el comando:

```bash
$ git diff
```

Obteniendo el siguiente resultado:

![Git diff](https://i.postimg.cc/GhdPH1X2/git-22.jpg "Resultado de ejecutar git diff")

Podemos observar que nos está indicando que estamos modificando (eliminando y agregando lineas de código) dos archivos: el archivo `README.md` con el nuevo texto que estamos escribiendo y el archivo `hellogit.py` con el agregado de "with changes!" al print.

## Desplazamiento

Comenzamos ejecutando el comando `git log` para ver nuestro historial de cambios:

![Desplazamiento](https://i.postimg.cc/jdYWjQd4/git-23.jpg "Historial de cambios git log")

Ahora, supongamos que queremos volver al estado donde se realizo el primer commit, es decir, al commit con el numero de hash `b243a1a0f5dbc446e78bb39ed0254a895127d6b5`.

Para ello, ejecutamos el comando:

```bash
$ git checkout b243a1a0f5dbc446e78bb39ed0254a895127d6b5
```

Obteniendo el siguiente error:

Esto se debe a que los archivos `hellogit.py` y `README.md` fueron modificados pero sus cambios nunca fueron commiteados.

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

Ejecutamos `git log` para chequear en que estado nos encontramos:

![Desplazamiento](https://i.postimg.cc/sXYpfVZ3/git-26.jpg "Ejecucion git log luego git checkout HEAD")

Y observamos que de esta manera, solo movemos la cabeza (HEAD) del proyecto al estado del primer commit.

Ahora, ejecutamos `git tree` y observamos lo siguiente:

![Desplazamiento](https://i.postimg.cc/nzXq7v5c/git-27.jpg "Ejecucion git tree luego git checkout HEAD")

Por lo tanto, si quiero volver al último estado de la rama (donde apunta `main`), coloco la cabeza (`HEAD`) de la rama
Apuntando allí de la siguiente manera:

```bash
$ git checkout 9f52593
```

Y si ejecutamos `git tree` nuevamente, obtenemos el resultado esperado.

![Desplazamiento](https://i.postimg.cc/X7s7MTqm/git-28.jpg "Ejecucion git tree luego git checkout 9f52593")

De este modo, se vuelven a restablecer los archivos `hellogit2.py` y `.gitignore`.

## Git reset hard y git reflog

Ahora, nos encuentramos al final de la rama. Supongamos que cometimos un error con los ultimos tres commits y quiero volver al estado correspondiente al segundo commit, es decir, al estado que tiene el hash `f7d6db2`. Para ello, puedo ejecutar el comando:

```bash
$ git reset --hard f7d6db2
```

![Git reset hard y git reflog](https://i.postimg.cc/N05J1LyD/git-29.jpg "Ejecucion git reset --hard f7d6db2")

Podemos observar como la cabeza (`HEAD`) de la rama ahora esta apuntando al estado correspondiente al segundo commit y se produce como una especie de borrado de todos los commits que se realizaron luego.

Ahora, si queremos ver toda la actividad que estuvimos realizando porque queremos volver al estado correspondiente al último commit ejecuto el siguiente comando:

```bash
$ git reflog
```

![Git reflog](https://i.postimg.cc/Y09H5YbF/git-30.jpg "Ejecucion git reflog")

Entonces, podemos ejecutar los comandos:

```bash
$ git checkout 9f52593
$ git checkout main
```

 Para volver al estado correspondiente al último commit y obtenemos lo que esperamos.

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

El comando `git add .` permite agregar a todos los archivos que esten pendientes al staging area.

Ahora, vamos a confirmar este nuevo punto commiteando estos cambios ejecutando siguiente comando:

```bash
$ git commit -m "Este es mi sexto commit"
```

Ahora, si ejecutamos `git tree`, observamos el nuevo historial de cambios.

![Git tag](https://i.postimg.cc/wvr8L7bJ/git-34.jpg "Ejecucion git tree luego de realizar el sexto commit")

La cabeza (`HEAD`) de la rama `main` ahora está apuntando al ultimo commit pero tenemos un **tag** que referencia al estado del commit anterior.

Si queremos desplazarnos al tag `clase_1`, ejecutamos el siguiente comando:

```bash
$ git checkout tags/clase_1
```

Y obtenemos el siguiente resultado:

![Git tag](https://i.postimg.cc/FzJ65GFC/git-35.jpg "Ejecucion git tree luego de realizar el sexto commit")

Podemos observar que la cabeza (`HEAD`) de la rama main ahora apunta al tag `clase_1`.

Si queremos regresar al estado correspondiente al ultimo commit, simplemente ejecutamos `git checkout main`.

Por último, si ejecutamos el comando:

```bash
$ git tag
```

Podemos ver todos los tags que fueron creados hasta el momento.

![Git tag](https://i.postimg.cc/Kj0X0Dbs/git-36.jpg "Ejecucion git tag para ver todos los tags creados")

## Git branch y git switch

Hasta el momento hemos trabajado solo en la rama `main`. Esto es una buena idea si trabajamos solos. Pero para trabajar en grupo, necesitamos incorporar el concepto de **rama o branch**.

Incorporamos una rama cuando queremos realizar algo que no tiene sentido que esté en la rama que nos encontramos actualmente.

Supongamos que quiero trabajar una funcionalidad pero como no se cuando la voy a terminar, quiero trabajar por separado y cuando la termine, la quiero integrar nuevamente a la rama principal `main`.

**Ejemplo** 

La funcionalidad que quiero desarrollador es un **login** pero no quiero que se mezcle con el contenido de la rama `main`. 

Para ello, ejecutamos el siguiente comando para crear una nueva rama con el nombre login:

```bash
$ git branch login
```

Ahora, si ejecutamos el comando `git tree`, obtenemos:

![Git branch](https://i.postimg.cc/ZRpGph0H/git-37.jpg "Ejecucion git tree luego de crear una nueva rama")

Ahora la cabeza (`HEAD`) sigue apuntando a la rama `main` pero en este punto se ha creado una nueva rama llamada `login`.

Para movernos hacia esa nueva rama, ejecutamos el siguiente comando:

```bash
$ git switch login
```

Obteniendo como resultado que estamos en la rama `login` (podemos observar que al lado del icono de rama ahora se muestra `login*`) y que ahora la cabeza (`HEAD`) apunta a `login`.

![Git branch](https://i.postimg.cc/76qL5XZ5/git-38.jpg "Ejecucion git tree luego de crear una nueva rama")

Ahora, a partir del commit con hash `d860439`, tenemos una rama donde la referencia es esa, es decir, tengo un nuevo flujo de trabajo donde en este punto contiene a todo lo que ya tenia en la rama principal (`main`).

Entonces, comenzamos a trabajar en el login. Creo el archivo `login.py`.

![Git branch](https://i.postimg.cc/pTYt3nzz/git-39.jpg "Creacion archivo login.py")

Entonces, una vez terminada la implementación del login, la agregamos al staging area y lo commiteamos ejecutando los siguientes comandos:

```bash
$ git add .
$ git commit -m "Login"
```

Podemos ver que efectivamente se commiteo en la rama `login` ejecutando `git tree`.

![Git branch](https://i.postimg.cc/hPgPpKFH/git-40.jpg "Ejecucion git tree luego de commitear el login")

Ahora, queremos volver a la rama `main`. Para ello, ejecutamos el siguiente comando:

```bash
$ git switch main
```

Obteniendo lo siguiente:

![Git branch](https://i.postimg.cc/mrQFt879/git-41.jpg "Ejecucion git tree luego de commitear el login")

Podemos observar varias cosas. Primero que el archivo `login.py` en la rama `main` no existe justamente porque fue creado en la rama `login` y que ahora la cabeza (HEAD) está apuntando a `main` como habiamos indicado.

Ahora, desde la rama `main` no tenemos ni idea que alguien está implementado un login. Entonces, podemos modificar el archivo `hellogit3.py` de la siguiente manera:

![Git branch](https://i.postimg.cc/FRbSYD5q/git-42.jpg "Modificacion archivo hellogit3.py")

Ahora, commiteo estos cambios ejecutando los siguientes comandos:

```bash
$ git add .
$ git commit -m "Git 3 v2"
```

Ejecutando `git tree` podemos observar lo siguiente:

![Git branch](https://i.postimg.cc/sxrPjmK6/git-43.jpg "Ejecucion git tree luego de cambios en hellogit3.py")

La cabeza sigue apuntando a la rama `main` y el último commit con hash `12ac8c7` se ubica luego del commit con hash `226b070` de la rama `login` pero en `main` no se impactan los cambios realizados por la rama `login`. Es decir, ambas ramas trabajan por separado.

## Git merge

Ahora, regresamos a la rama `login` ejecutando el comando:

```bash
$ git switch login
```

Una vez en la rama `login`, queremos ver si lo que se estuvo trabajando en la rama `main` sigue siendo compatible con lo que se viene desarrollando en la rama `login` para mantener los flujos actualizados.

Entonces, la idea es poder tener en la rama `login` la ultima actualización que se realizó en la rama `main`, es decir, todo el contenido que se encuentra en el estado con hash `12ac8c7`. Para ello, ejecuto el siguiente comando:

```bash
$ git merge main
```

Es decir, fusiono o "mergeo" la ultima actualización de la rama `main` dentro de la rama `login`.

Luego de ejecutar el comando, obtenemos lo siguiente:

![Git merge](https://i.postimg.cc/VkX5WwFh/git-44.jpg "Ejecucion git merge main")

Podemos observar que el archivo `hellogit3.py` tiene ahora "Hello Git 3 v2!" dentro del print (cambio que se habia realizado en la rama `main`)

Ahora, si ejecutamos el comando `git tree` obtenemos:

![Git merge](https://i.postimg.cc/yNRLXvQj/git-45.jpg "Ejecucion git tree luego de git merge main")


Y podemos observar que la cabeza (`HEAD`) apunta a la rama `login` con un nuevo hash `5ce078c` con la descripción "Merge branch 'main' into login", es decir, se fusiona el contenido de la rama `main` dentro de la rama `login` generando un nuevo commit con el contenido fusionado.

## Resolución de conflictos en Git

Estamos en la rama `login`. Y supongamos que cambiamos el print en el archivo `hellogit3.py` de "v2" por "login" de la siguiente manera:

![Conflictos Git](https://i.postimg.cc/Kvw0w6MF/git-46.jpg "Modificacion archivo hellogit3.py")

Ahora, realizo un commit de este cambio ejecutando los siguientes comandos:

```bash
$ git add .
$ git commit -m "Git 3 login"
```

Sin embargo, se modificó un archivo que en principio no se debería haber tocado porque en la rama `login` solo se deberia haber modificado el archivo `login.py`

Ahora, volvemos a la rama `main`. Y se modifica nuevamente el archivo `hellogit3.py` en el print agregando modificado de la siguiente manera:  

![Conflictos Git](https://i.postimg.cc/QxpS8XVN/git-47.jpg "Modificacion archivo hellogit3.py en rama main")

Guardamos los cambios y realizamos el comit ejecutando:

```bash
$ git add .
$ git commit -m "Git 3 v3 modficado por main"
```

Ahora, ejecutamos `git tree` para ver el nuevo historial de cambios y obtenemos lo siguiente:

![Conflictos Git](https://i.postimg.cc/SQG73gPj/git-48.jpg "Ejecucion git tree en rama main")

Nuevamente, volvemos a la rama `login` ejecutando el comando:

```bash
$ git switch login
```

Y queremos volver a actualizar el estado de la rama `main`. Para ello, tenemos que mergear la rama `main` en la rama `login` ejecutando:

```bash
$ git merge main
```

Y obtenemos el siguiente conflicto en `hellogit3.py`:

![Conflictos Git](https://i.postimg.cc/5tdWT9HB/git-49.jpg "Conflicto luego de ejecutar git merge main")

Esto se debe a que tanto la rama `main` como la rama `login` han tocado la misma linea de código. Si se modificaran distintas lineas de código, no habría problema al intentar realizar un `merge`.

Entonces, como este archivo pertenece a la rama `main`, dejamos el cambio que realizó la rama `main` (color azul).

Por lo tanto, para solucionar este conflicto tenemos que agregar la nueva modificación al staging area y commitearla ejecutando:

```bash
$ git add .
$ git commit -m "Correccion conflicto"
```

De este modo, se corrrige el conflicto, se "mergea" la rama `main` en `login` y volvemos a tener la rama `login` actualizada.

![Conflictos Git](https://i.postimg.cc/qMKTLCqJ/git-50.jpg "Conflicto resuelto")

## Git stash

Una vez resuelto el conflicto, volvemos a trabajar en la implementación de nuestro login en la rama `login` agregandole "v2" al print de la siguiente manera:

![Git stash](https://i.postimg.cc/Zn7xvRkX/git-51.jpg "Modificación login.py")

Ahora, supongamos que tenemos que resolver un conflicto en la rama `main`. Entonces, ejecutamos:

```bash
$ git switch main
```

Pero nos arroja el siguiente error:

![Git stash](https://i.postimg.cc/66vnNtpH/git-51.jpg "Error git switch main")

Este error nos indica que no nos podemos mover de rama porque tenemos un archivo `logn.py` que he modificado pero no lo he commiteado. Si decido cambiar de rama, voy a perder todos los cambios realizados.

Entonces, para almacenar temporalmente lo que estaba trabajando pero no commitearlo, ejecutamos el comando:

```bash
$ git stash
```

Luego, para listar los stash que tengo pendientes ejecutamos el comando:

```bash
$ git stash list
```

Ahora, nos cambiamos a la rama `main` ejecutando el comando:

```bash
$ git switch main
```

Una vez resuelto lo pedido en la rama `main`, vuelvo a la rama `login` ejecutando:

```bash
$ git switch login
```

Pero no tenemos la modificación realizada que guardamos en el `stash`

Entonces, para recuperar el estado que dejamos al ejecutar el `stash`, ejecutamos el comando:

```bash
$ git stash pop
```

La instrucción `pop` indica que trae/recupera todo lo que había quedado almacenado en el `stash`.

De este modo, volvemos al estado en el que nos habiamos quedado antes de movernos a la rama `main`.

![Git stash](https://i.postimg.cc/jCVP7kdY/git-53.jpg "Regreso al estado almacenado en el stash")

Arreglamos el cierre de comillas en el print, agregamos y commiteamos los cambios ejecutando:

```bash
$ git add .
$ git commit -m "Login v2"
```

Ahora, supongamos que seguimos trabajando en el `login` (agregando v3 en lugar de v2 en el print) y tenemos que nuevamente resolver un conflicto en la rama `main`. Entonces, ejecuto:

```bash
$ git stash 
$ git switch main 
```

Con esto, guardamos la última actualización y vamos a la rama `main`. Resolvemos el problema en la rama `main` y volvemos a la rama `login`.

Una vez en la rama `login`, vemos el listado que tengo en el `stash` ejecutando:

```bash
$ git stash list 
```

Pero si nos arrepentimos de todo lo que estuvimos haciendo y guardamos en ese `stash`, podemos olvidarnos de todo lo que estuvimos trabajando ejecutando el comando:

```bash
$ git stash drop 
```

Con esto, logramos que se reestablezca el "v2" en lugar de "v3" en el archivo `login.py`.

## Reintegración de ramas en Git

Una vez que ya terminamos de implementar el `login`, lo quiero integrar en la rama `main`.

Entonces, comenzamos trasladandonos a la rama `main` ejecutando:

```bash
$ git switch main 
```

Para chequear si tenemos algún posible conflicto que pueda surgir al intentar mergear la rama `login` en la rama `main`, podemos ejecutar el comando:

```bash
$ git diff login
```

Este comando nos indica todos los archivos distintos que tiene la rama `login` (archivo login.py) en relación con la rama `main`.

Una vez chequeado esto, podemos "mergear" la rama `login` en la rama `main` ejecutando el siguiente comando:

```bash
$ git merge login
```

Obteniendo el siguiente resultado:

![Reintregacion Ramas en Git](https://i.postimg.cc/pVsY2RNz/git-54.jpg "Mergeo rama login en rama main")

Podemos observar que se incorporó el archivo `login.py` a la rama `main`

Ahora, volvemos a la rama `login` y realizamos una pequeña modificación en `login.py` (agrego v final en el print).

Agregamos los cambios al staging area y commiteamos los cambios ejecutando:

```bash
$ git add .
$ git commit -m "Login v final"
```

Regresamos a la rama `main` y mergeo los nuevos cambios de la rama `login` en `main` ejecutando:

```bash
$ git switch main
$ git merge login
```

De este modo, se impactan los nuevos cambios en la rama `main` del archivo `login.py`

![Reintregacion Ramas en Git](https://i.postimg.cc/BvJ33d1L/git-55.jpg "Mergeo rama login en rama main")

Por último, podemos realizar modificaciones del archivo `login.py` desde la rama `main` (por ejemplo, agrego al print "Login v final modificado desde main"), agregamos los cambios y los commiteamos de la siguiente manera:

```bash
$ git add . 
$ git commit -m "Login modificado desde main"
```

Por lo tanto, pudimos mergear de la rama `login` a la rama `main` y seguir commiteando normalmente.

## Eliminación de ramas

Ya hemos reintegrado el `login` a la rama `main`. Entonces, podriamos pensar en descartar a la rama `login`.

Por lo tanto, para eliminar la rama `login` debemos estar situados en la rama `main` y ejecutar el siguiente comando:

```bash
$ git branch -d login 
```

Obteniendo el siguiente resultado:

![Eliminacion de ramas](https://i.postimg.cc/1tmsPb27/git-56.jpg "Eliminacion rama login")

Ahora, para chequear que la rama `login` se haya eliminado ejecutamos el comando:

```bash
$ git branch  
```

![Eliminacion de ramas](https://i.postimg.cc/MHzC1Rqs/git-57.jpg "Ejecucucion git branch")

Observando que solo tenemos activa la rama `main`. Pero si ejecutamos el comando `git tree`, podemos observar que vamos a seguir teniendo referencias a la rama `login` inclusive podriamos ejecutar `git checkout` y algun `hash` de la rama `login` y luego volver a la rama `main` con `git checkout main`.

Aunque si ejecutamos el comando:

```bash
$ git switch login  
```

Observamos que:

![Eliminacion de ramas](https://i.postimg.cc/NFMWNHPp/git-58.jpg "Ejecucion git switch login")


Tenemos una referencia invalida porque oficialmente no existe más la rama `login` pero aún tenemos referencias a ella. Basicamente, todas las referencias (hash) de la rama `login` se han "mergeado" en la rama `main` y por eso aún pueden ser accedidas.

## Git fetch y git pull

Una vez que subimos todos los archivos que fuimos creando en nuestro repo local, se van a visualizar de la siguiente manera:

![Git fetch y git pull](https://i.postimg.cc/DZhbJnD7/git-59.jpg "Vista actual del repositorio")

Ahora, si desde el repositorio agregamos el archivo `README.md`, podemos ver como queda ahora el repositorio:

![Git fetch y git pull](https://i.postimg.cc/WzZ9TMd5/git-60.jpg "Vista actual del repositorio")

Volvemos a nuestro repositorio local y vamos a editar el archivo `hellogit.py` de la siguiente manera:

![Git fetch y git pull](https://i.postimg.cc/Jh6mkWP9/git-61.jpg "Vista actual del repositorio")

Ahora, si intentamos agregar los cambios y commitearlos ejecutando:

```bash
$ git add .
$ git commit -m "Hello git modificado sin actualizar repo" 
$ git push 
```

Obtenemos el siguiente error:

![Git fetch y git pull](https://i.postimg.cc/TwKZZ5fP/git-62.jpg "Error al intentar pushear sin actualizar repo")

Este se debe a que creamos el archivo `README.md` pero no lo actualizamos en nuestro repositorio local.

Para intentar solucionar este problema, podemos ejecutar el comando:

```bash
$ git fetch
```

Ahora si ejecutamos el comando `git tree` obtenemos lo siguiente:

![Git fetch y git pull](https://i.postimg.cc/524gjHjN/git-63.jpg "Ejecucion git tree para ver historial de cambios")

Por lo tanto, el comando `git fetch` descarga el historial local pero sin los cambios.

Ejecutando el comando:

```bash
$ git pull
```

Se descarga el historial local pero con los cambios tambien. Y obtenemos la siguiente advertencia:

![Git fetch y git pull](https://i.postimg.cc/G2zRvTd3/git-64.jpg "Advertencia al ejecutar git pull")

Esta advertencia nos indica que tenemos varias ramas y tenemos que especificar como las queremos reconciliar.

Entonces, vamos a utilizar el mecanismo de "mergeado" que coincide con el comando `git config pull.rebase false  # merge` en la ayuda que nos brinda y luego si, vamos a descargar el historial local con los cambios. Esto lo hacemos ejecutando los siguientes comandos:

```bash
$ git config pull.rebase false
$ git pull origin main
```

Y podemos observar como ahora el repositorio se encuentra totalmente actualizado:

![Git fetch y git pull](https://i.postimg.cc/FzPXfY0t/git-65.jpg "Repositorio actualizado")

## Git clone

Ahora, supongamos que nos incorporamos al proyecto y queremos comenzar a trabajar en él. Una opción es descargarse el código en un zip y comenzar a trabajar. Otra opción es poder clonar el repositorio en nuestra computadora y comenzar a hacer cambios.

Esto lo hacemos clickeando en la solapa `Code` y copiando la URL como se muestra en la imagen a continuación.

![Git clone](https://i.postimg.cc/L88GWtGj/git-66.jpg "Clonando repositorio")

Luego, creamos una carpeta donde vamos a clonar el repositorio o simplemente nos ubicamos en el directorio donde queremos que se clone el repositorio y ejecutamos el comando:

```bash
$ git clone https://github.com/eruedasanchez/git-resumen.git
```

























