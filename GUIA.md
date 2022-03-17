# Guía Básica para el uso de Git y GitHub 

**Gobierno de Datos**

## 1.- Introducción

Con el objetivo de facilitar el trabajo transparente y colaborativo entre los equipos de la **DAI**, se ha generado esta guía sobre el uso de **Git** y **GitHub**, herramientas que permiten trabajar conservando un registro del control de versiones de proyectos en que participan varias personas simultáneamente. 
Primero se muestran instrucciones sobre la instalación de **Git**, **GitHub**, **R** y **RStudio**, y posteriormente se explica cómo configurar e iniciar un proyecto.

<p align="center">         
<img src="imagen/logo1.png" alt="git" style="width:300px;"/> 
</p>

### Git

**Git** es un software creado por [Linus Torvals](https://es.wikipedia.org/wiki/Linus_Torvalds) diseñado para mejorar la eficiencia, confiabilidad y compatibilidad de versiones de aplicaciones cuando están compuestas por un gran número de código fuente y participan varias personas simultáneamente ([Wikipedia](https://es.wikipedia.org/wiki/Git), [Git](https://git-scm.com/)).

Con esta herramienta es posible actualizar el código desarrollado de manera colaborativa conservando un registro y control de versiones.

<p align="center">   
<img src="imagen/logo2.png" alt="Files" style="width:180px;"/>
</p>

### GitHub

**GitHub** es la plataforma más popular para controlar versiones de código, pues permite publicar, compartir y socializar (como una red social digital) el código de programación. 
Además, registra cada cambio en el código y las carpetas de trabajo para rastrear la evolución de proyectos y, si es necesario, revertir los cambios. Esta plataforma fue adquirida por [Microsoft en 2018](https://news.microsoft.com/es-es/2018/06/04/microsoft-adquirira-github-por-7-500-millones-de-dolares/). 

## 2.- Instrucciones

###  Crear cuenta y repositorio en GitHub

Primero, debes acceder a este **[enlace](https://github.com/)**  y crear una cuenta de **GitHub**. Para ello se necesita una dirección de correo electrónico, generar un nombre de usuario y una contraseña.

1.- Una vez creada la cuenta, en la parte superior derecha de la página de **GitHub** se observará un símbolo ' + '. 

2.- Se debe abrir esa pestaña y hacer clic en "New Repository". 

3.- Ahora, aparecerán las opciones de configuración donde se tendrá la opción de agregar un documento README.md. 

4.- Listo, una vez seleccionadas las preferencias de configuración, el nuevo repositorio se habrá creado.

###  Instalación de Git en Linux, Windows y macOS

Para descargar el archivo de instalación de **Git** usa este **[enlace](https://git-scm.com/downloads)**, selecciona el archivo correspondiente al sistema operativo que se utilice y se sigues las instrucciones. 
Las opciones predeterminadas permitirán el funcionamiento adecuado de **Git** en tu ordenador.

#### Configuración de Git

Para vincular **Git** con la cuenta de **GitHub** es necesario agregar las credenciales de la forma en que se muestra a continuación. Cabe mencionar que el procedimiento se lleva a cabo en **Git Bash**.

- `git config --global user.name "<Nombre de usuario>"`
	
- `git config --global user.email <Cuenta de correo electrónico>` 

Si usas Windows, se _recomienda_ crear una carpeta "repositorio" en la siguiente ubicación de tu ordenador:

- `C:/Usuarios/<Nombre de usuario>/Documents/<Repositorio>`
  
En esta ubicación se generará el repositorio que podrá usarse en el futuro. Una vez instalado **Git** se puede seguir los siguientes pasos para clonar un repositorio. Como recordatorio, la forma de correr una línea de código generalmente es pulsando **Ctrl + Enter**.

Luego, para seleccionar la carpeta que se generó y clonar un repositorio en esa ubicación, se debe usar los siguientes comandos:

-  `cd Documents/<Repositorio>`  

- `git clone <URL>`

Donde \<URL\> es el enlace para clonar desde la página de **GitHub**, su obtención se explica en la siguiente sección. 

#### Autenticación 

Para vincular un repositorio de **GitHub** a **RStudio** desde **Git**, será necesario el enlace del repositorio en que se quiera trabajar.

Para obtener el enlace HTTPS o SSH se debe de dirigir al repositorio en **GitHub** y dar clic al botón verde con la leyenda "Code".

<p align="center">         
<img src="imagen/link.png" alt="link" style="width:350px;"/>
</p>

A este procedimiento se le conoce como **autenticación**. Es importante mencionar que existen dos opciones para vincular un repositorio: los protocolos HTTPS y SSH, sus características se muestran en la siguiente tabla.

<br/>

| Protocolo | Características|
|-----------|-----------------|
| - **HTTPS**| Si se elige el protocolo HTTPS, esto le permitirá usar un administrador de credenciales para almacenar en memoria cache las credenciales de **GitHub** en **Git**.<br/> Para seguir este protocolo se sugiere seguir lo siguientes pasos, retomados por la guía oficial de **GitHub**:  <br/> - Instalar GitHub CLI. <br/> - En la terminal de GitBash, escribir: gh auth login   , y seguir las instrucciones.|
|- **SSH**| Al elegir la opción SSH, será necesario crear claves SSH en cada computadora que use para el respectivo proyecto, ya sea para enviar o extraer información del repositorio en **GitHub**.<br/> Para establecer la configuración SSH o cambiar de HTTPS a SSH se puede consultar el siguiente **[enlace](https://docs.github.com/es/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-t)**.|


Por cuestiones de seguridad se sugiere el uso del protocolo HTTPS, ya que este protocolo reduce los riesgos de  *[Tampering](https://owasp.org/www-community/attacks/Web_Parameter_Tampering)*. 
	
Para más información sobre administración de repositorios remotos puedes consultar el siguiente *[sitio](https://docs.github.com/en/get-started/quickstart/set-up-git)*.


## 3.- Trabajar desde Git Bash
	
Al abrir **Git Bash** siempre se debe seleccionar el repositorio o carpeta donde se encuentren los archivos que se desean actualizar:

-  `cd  /Documents/<Nuevo repositorio>`

### Actualización o descarga de repositorio local

Para estar al tanto de los cambios que se han realizado en el repositorio de **GitHub** se debe hacer una actualización de los cambios realizados en la nube. 
Por otro lado, cuando se quiere subir cambios a una rama (`push`), previamente se debe actualizar, ya que en caso de que haya cambios no registrados en el repositorio local podría haber un error y no ejecutar la función `push`.

Comandos para actualizar el repositorio local a la última versión:
-  `cd <Nuevo repositorio>`
-  `git pull --verbose`

### Publicar cambios en el repositorio remoto GitHub

Para agregar las modificaciones realizadas a todos los archivos contenidos en el repositorio local se debe actualizar el repositorio y seguir el procedimiento que se menciona a continuación. 
 
-  `git add .`
-  `git commit -m "<Mensaje sobre la actualización realizada>"`
-  `git push`

### Publicar cambios en un solo archivo

Si se requiere publicar los cambios realizados en un solo archivo, en lugar de escribir un punto (`.`), se escribe el nombre del archivo y su extensión:

- `git add <Archivo.extensión>` 
- `git commit -m "<Mensaje sobre la actualización realizada>"`
- `git push`

### Ignorar archivos

Los Sistemas de Control de Versiones (VCS) permiten ignorar archivos mediante el contenido del archivo `.gitignore`. Debido a que todos los archivos y directorios son suceptibles a ser compartidos en los repositorios, es necesario declarar explicitamente a **Git** cuáles archivos o directorios se omitirán.

Existen varias formas de indicar cuáles elementos ignorar, y esto dependerá de qué es lo que se busca omitir. Usualmente se crea el archivo `.gitignore` en la rama principal para ignorar archivos de un sólo repositorio, como se muestra a continuación:

- `touch .gitignore`

Lo anterior crea un archivo `.gitignore` en blanco. Dentro de este, se deberá incluir en formato de texto todos los archivos por omitir. Usualmente es posible pasar por alto tipos de archivo (tales como .log, .md), paqueterías (tales como .rar, .zip, etc.), claves privadas y *tokens*.

NOTA: Para desvincular tu cuenta de un repositorio colaborativo puedes consultar la siguiente [documentación](https://docs.github.com/es/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/removing-yourself-from-a-collaborators-repository).

### Comandos Git

Para facilitar el uso de **Git** y resolver posibles dificultades con el uso de funciones se agrega una sección con los comandos y funciones más utilizadas:

| Comando | Uso |
|----------|--------|     
| `git --help` | Se mostrará en pantalla una lista de los comandos más usados (incluidos los enlistados en está tabla) y una breve explicación|
| `git <Comando> --help` | Para consultar las características de uso y función de un comando en específico|
| `git clone <URL>` | Descargar un repositorio existente|
| `git add <Archivo>` | Agregar archivo a área de aterrizaje|
| `git commit -m "<Mensaje de descripción de cambios>"`|Guardar cambios que se subieron al área de documentos que están listos para ser compartidos|
| `git pull <Repositorio> [<Rama>]`|Actualizar los cambios de un repositorio remoto|
| `git push <Repositorio> [<Rama>]`|Actualizar los cambios de tu rama al repositorio remoto asociado|
| `git branch <Rama>`|Crear una nueva rama|  
| `git branch --list `|Visualizar ramas existentes| 
| `git branch -d <Rama>`|Eliminar rama| 
| `git checkout <Rama>`|Para cambiar de una rama a otra <sup>(1)</sup>|
| `git merge <Rama Fuente> <Rama Destino>`|Mezclar los cambios de las ramas|
| `git rm -r --cached <Directorio>`|Eliminar repositorio y su contenido|
| `git rm <Archivo>`|Eliminar un archivo en particular| 
| `cd repositorio`<br/>`rm -rf .git`| Eliminar un repositorio local|
  
<sup>(1)</sup> Para usar este comando, previamente hay que verificar o guardar los cambios en la rama actual. La rama que se desea verificar debe estar en su repositorio local.

En caso de querer profundizar en el manejo de esta herramienta y sus comandos avanzados, se sugiere descargar la guía oficial de **Git** a través del siguiente link [Downloads](https://git-scm.com/book).

## 4.- Vincular Git con Rstudio
<p align="center">         
<img src="imagen/Rstudio.png" alt="RStudio" style="width:200px;"/>
</p>

###  Instalar R y RStudio

Primero se debe instalar **R**, para ello se consulta el siguiente sitio, donde se puede [Descargar R](https://cran.r-project.org/bin/windows/base/).
Las opciones de configuración predeterminadas permitirán el funcionamiento adecuado de **R**. Además, para saber cuál versión descargar (32 o 64 bits), en Windows puedes seguir los siguientes pasos:

1. Ingresar a **Configuración** de su equipo de cómputo.

2. Seleccionar **Sistema**.

3. Hacer clic en **Acerca de ...**.

4. Visualizar la opción de **Tipo de Sistema**. Ahí se identifica si es de 32 o 64 bits. 

Una vez que se tiene instalado **R**, es posible descargar **RStudio** desde aquí: [Descargar RStudio](https://www.rstudio.com/products/rstudio/download/#download)

### Preparar RStudio 
<p align="center">         
<img src="imagen/git.png" alt="funny" style="width:150px;"/>
</p>

Para poder vincular **GitHub** con **RStudio** es necesario hacer el siguiente procedimiento:

0. Abrir Rstudio. 

1. Ingresar las siguientes líneas de código dentro de la consola (es decir, en la sección superior izquierda).

- `install.packages("usethis")`
- `library(usethis)`

2. Escribir su nombre de usuario y correo electrónico que usó para generar la cuenta en GitHub en la siguiente línea de código. 

- `usethis::use_git_config(user.name = "<Nombre de usuario>", user.email = "<Cuenta de correo electrónico>")`

Se sugiere que en este punto se tenga una cuenta de **GitHub** y un repositorio. Si no es así, puede ir a la sección sobre **Crear cuenta y repositorio en GitHub**, de este documento. 

#### Uso de RStudio para clonar

Para vincular **RStudio** al proyecto en **GitHub**, es necesario seguir las siguientes instrucciones.

1. Hacer clic en **”Files”**, luego **”New Project”**.

<p align="center">         
<img src="imagen/File_RStudio.png" alt="Files" style="width:350px;"/>
</p>

2. Dar clic en "**New Directory**", posteriormente verá un listado de opciones, seleccionar "**New Project**". Se abrirá una imagen relativa a crear un proyecto nuevo.

<p align="center">         
<img src="imagen/new_project.png" alt="New Project" style="width:350px;"/>
</p>

3. Una vez en la pestaña que se muestra, escriba el nombre del directorio, seleccione "**Create a git repository**" y se sugiere "**Open in new session**".

4. Para terminar, se cierra el proyecto desde **File -> Close Project** antes de cerrar **RStudio** a fin de evitar errores al recargar la interfaz en otra ocasión.

Si se desea conocer más sobre la vinculación de **Git y RStudio**, se sugiere consultar el siguiente [Documento](https://cfss.uchicago.edu/setup/git-with-rstudio/).

### Trabajar en RStudio desde una rama local 

Para evitar problemas tales como actualizaciones mientras se está trabajando sobre un repositorio, o dificultades al unir dos nuevas actualizaciones, se sugiere usar una *rama local*.

Para el uso de una *rama local* se puede seguir estos pasos: 

1. **Importante** haga clic en el símbolo morado para crear una rama local en la cual trabajaremos.
<p align="center">         
<img src="imagen/morado.png" alt=" " style="width:250px;"/>
</p>

La cual se configura únicamente para trabajar de manera local como se muestra en la siguiente imagen.  

<p align="center">         
<img src="imagen/local.png" alt=" " style="width:250px;"/>
</p>

Este paso se realiza para evitar problemas cuando haya cambios en la rama principal `main`. De preferencia, se hace esta acción cada vez que inicie un nuevo proyecto. Para evitar errores más adelante, el nombre de la rama no debe contener símbolos especiales, puntos, acentos o espacios; se sugiere usar `local`.

2. Se trabaja normalmente, y se realizan todas las acciones y actualizaciones dentro de esta rama local.

3. Se presiona `Commit` dentro de la pestaña **Git** y escribe los comentarios necesarios para explicar nuestro trabajo realizado en la ventana que se abre. Asegúrese de seleccionar solo los archivos que deseemos actualizar.

4. Junto al nombre de la rama local `<Rama local>` en la pestaña **Git** aparece un triángulo que apunta hacia abajo, se hace clic en él y se cambia a la rama principal `main` Esto abre un mensaje que, si no se presentan errores, indicará que ha cambiado a la rama principal.

5. Nuevamente se realiza `pull` porque podría haber actualizaciones realizadas por otro colaborador.

6. En caso de que haya actualizaciones después de **descargar** la última versión del repositorio, nuevamente se hace `commit`.  Note que ya se encuentra en la rama principal `main` del proyecto.

7. Se abre una consola a partir del menú `Tools -> Shell`.

8. En la consola se escribe el siguiente comando: `git merge <Rama local>` es decir el nombre que se asignó a la rama local en la cual se trabajó. Esto se hace para **combinar** el trabajo local con la rama principal `main`  antes de subir las actualizaciones al repositorio. Se cierra la consola.

9. A continuación, se hace `push` del trabajo. Esto se logra seleccionando la flecha verde que apunta hacia arriba. Esto actualizará el repositorio.

10. Se elimina la *rama local* al escribir en la consola el siguiente comando: `git branch -d <Rama local>` . Una vez hecho esto, se cierra la consola.

11. Para concluir se cierra el proyecto desde `File -> Close Project` antes de cerrar **RStudio** para evitar errores al cargar la interfaz en una próxima ocasión.

12. Cuando se reabra el proyecto una próxima vez, se puede comenzar desde acceder a una *rama local*.

## 5.- Buenas prácticas en el uso de Sistemas de Control de Versiones

Para garantizar el control de la información y de los flujos de trabajo se recomienda lo siguiente:

- Si se quiere proteger el código y la información, en primera instancia se recomienda configurar los repositorios como **privados**.

- En el uso de datos, es importante evaluar la existencia de datos **personales y/o sensibles** para removerlos o anonimizarlos antes de subirlos a los repositorios.

- Agregar un archivo que describa las características del proyecto.

- Generar metadatos para conocer las características de las bases de datos y procedimientos que se les han aplicado.

- Hacer uso de ramas para trabajar colaborativamente. Esto reducirá problemas de sobre-escritura y conflictos al hacer actualizaciones.
	
## 6.-  Glosario

| Concepto | Definición | 
|-----------|----------------|
| Rama (Branch) | Es una divergencia de la línea principal de desarrollo, la cual permite trabajar sin arruinar la línea principal. |
| CVS 			| "Es un sistema que registra los cambios sobre el tiempo de un archivo o conjunto de ellos, para que sea posible recuperar versiones específicas posteriormente". |
| Git 			| Es un Sistema de Control de Versiones que permite dar seguimiento de forma colaborativa a un proyecto. |
| GitHub 		| Plataforma para publicar, compartir y socializar código de programación. |
| Git Bash     | Acrónimo en inglés de Bourne Again Shell. Es una aplicación que ofrece un entorno para emular líneas de comandos. |
| HTTPS  	| Hypertext Transfer Protocol Secure por su significado en Inglés, es una versión del protocolo HTTP, que usa protocolos SSL/TLS para encriptar y autentificar.	|
| Línea de Comandos  | También conocido como Command Line Interface (CLI), procesa instrucciones en forma de texto para un programa de computadora. |
| Biblioteca		| "Es un conjunto de rutinas [computacionales] preestablecidas, que un [programador] puede emplear". |
| Markdown 		| Es un lenguaje de marcado que se emplea para modificar documentos de texto plano. El lenguaje de marcado se refiere al formato y presentación del texto. |
| R  			| "Es un lenguaje y ambiente para el cómputo estadístico y científico". |
| R Markdown  	| Es un formato para escribir el lenguaje de marcado de un documento  desde R. |
| R Script 		| Archivo de texto editable que contiene código y comentarios que posteriormente pueden ser ejecutados. |
| RStudio 		| Es un Ambiente de Desarrollo (IDE), incluye herramientas como consola, apoyo sintáctico, así como otras opciones. |
| SSH  	| Secure Shell, por su significado en Inglés. Es una llave de acceso que usa el protocolo SSH, el cuál establece la conexión con un cliente y in servidor. |
| Tampering | Es un parámetro de seguridad que consiste en manipular el intercambio de información entre usuarios y computadoras para modificar datos, tales como credenciales o permisos. |

## Referencias 

* Benjamin Soltoff (2021). Computing for the Social Sciences. Consultado en: https://cfss.uchicago.edu/
* GitHub (2022). GitHub Docs. Consutado en: https://docs.github.com/es/get-started
* Git (2022). Git Branching - Branches in a Nutshell. Consultado en:  https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell#ch03-git-branching
* R Foundation (2022). What is R?. Consultado en : https://www.r-project.org/about.html
* RStudio (2022). RStudio. Consultado en: https://www.rstudio.com/products/rstudio/#:~:text=RStudio%20is%20an%20integrated%20development,history%2C%20debugging%20and%20workspace%20management.
* SSH (2022). SSH Protoco  Secure Remote Login and File Transfer. Consultado en : https://www.ssh.com/academy/ssh/protocol
* SSL (2022). What is HTTPS?. Consultado en: https://www.ssl.com/faqs/what-is-https/
* Webopedia (2021). Library. Consultado en : https://www.webopedia.com/definitions/library/
