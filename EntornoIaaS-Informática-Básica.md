# Práctica 01. El Entorno de trabajo IaaS para la asignatura


NOTA: Revisarlo TODO entero teniendo en cuenta que se trata de alumnado de primero
      Reproducir TODO en el centro de cálculo. Particularmente todo lo relacionado con MS Visual Studio Code


### Objetivos

Los objetivos de esta práctica son:

* Realiar algunas tareas administrativas previas para facilitar el trabajo en la asignatura 
* Conocer y configurar el entorno de trabajo de la asignatura en el sistema Linux del IaaS 
* Configurar y practicar el uso del Visual Studio Code para editar ficheros en la máquina IaaS de la asignatura
* Editar, compilar y ejecutar `hello_world.cpp`

### Rúbrica de evaluacion del ejercicio
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará positivamente que el alumnado haya realizado las tareas propuestas con anterioridad a la sesión de prácticas
* Se valorará la realización de las diferentes tareas que se proponen

**Avise al profesor** al finalizar la realización de cada uno de los pasos que se indican a continuación. No inicie una nueva tarea sin haber revisado la anterior.

### Tareas previas
1. Para el trabajo en las prácticas de la asignatura se utilizará intensivamente el Sistema Operativo Linux,
trabajando fundamentalmente en una máquina virtual disponible a través de la infraestructura [IaaS de la
ULL](https://www.ull.es/servicios/stic/2015/10/27/nuevo-servicio-iaas/).
Es por ello que resulta muy conveniente que el alumnado tenga acceso en su ordenador personal con el que
trabaje en casa de un sistema Linux. 
Hay básicamente tres opciones para ello, que enumeramos a continuación:

    1.1. Si dispone Ud. de un ordenador propio que pueda formatear (borrando por tanto toda la información)
		instale directamente Ubuntu en él siguiendo (por ejemplo) [estas
		instrucciones](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview). 
		Para esta instalación necesitará Ud. crear un pendrive desde el que pueda arrancar el ordenador. 
		Siga para ello (por ejemplo) [estas instrucciones](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview).

    1.2. Otro

    1.3.


1. Previamente a la sesión de laboratorio, estudie el documento 
[Manual de administración de Máquinas PDI](https://docs.google.com/document/d/1nj-dxu7LXrNhj3ewCdfaPSc8OV4e_TYpGTQdK78YExY/edit).
Tenga en cuenta que el acceso a la infraestructura IaaS está ligado a que esté Ud. registrada/o en el Aula
Virtual de la Asignatura.
Siga las instrucciones de ese documento para acceder a la [interfaz web de las máquinas IaaS](https://iaas.ull.es) y configure la
conexión desde su casa para poder acceder al entorno IaaS usando VPN.
Para configurar la conexión VPN siga las instrucciones de la página [Servicio de VPN de la ULL](https://www.ull.es/servicios/stic/2016/05/10/servicio-de-vpn-de-la-ull/).
Para el trabajo en la asignatura se recomienda que disponga en casa de una máquina con Linux.
Si inicialmente quiere Ud. conectarse a las máquinas Linux del entorno IaaS desde una máquina Windows se
recomienda instalar en Windows [el programa PuTTY](https://www.putty.org/) que puede Ud. descargar
libremente.

Con anterioridad a la sesión de prácticas, debe Ud. asimismo estudiar los documentos que se enlazan desde
éste así como realizar todas las tareas que aquí se proponen en las que no encuentre dificultad.

2. Acceda al [portal de gestión de usuarios](https://usuarios.ull.es/autogestion/cambio_alias/)
del Servicio TIC de la ULL y configure allí una dirección de correo electrónico alternativa a su dirección
`aluXXXX@ull.edu.es`.
Las direcciones (alias) alternativas que el sistema le ofrece han de incluir necesariamente dos dígitos
numéricos (sin significado específico alguno) y permiten que su dirección de correo sea más legible y fácil de
recordar, sobre todo para otras personas.
Podrá utilizar indistintamente las direcciones `aluXXXX@ull.edu.es` y el alias que configure.

3. [GitHub](https://github.com/) es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git.
Cree una cuenta en [GitHub](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home). 
Configure el perfil de esa cuenta de modo que incluya una imagen (fotografía) en la que se le reconozca y haga que la cuenta de e-mail asociada sea la dirección institucional o su alias.
Para la configuración de esa cuenta se le recomienda usar su nombre real, puesto que sus repositorios de código en GitHub
pasarán a formar parte de su curriculum profesional.

4. Para editar algunos ficheros en esta sesión se usará el editor [vim](https://www.vim.org/).
Estudie los primeros pasos de [este tutorial](https://blog.desdelinux.net/usando-vim-tutorial-basico/) para que
aprenda lo básico sobre cómo modificar un fichero usando vi.
Con el estudio de este otro [tutorial interactivo on-line](https://www.openvim.com/) debe aprender lo mínimo que necesita
para usar vi en esta sesión.
Si está Ud. interesada/o en aprender vim (es un editor muy potente pero los comienzos son difíciles) dispone
de muchos tutoriales en la web. 
[Este tutorial](https://github.com/Izaird/Vim-primeros-pasos) explica lo básico de vim a través de ejemplos concretos con ficheros de texto.

Para editar algunas líneas concretas de un fichero de texto usando vi siga estas indicaciones:
* Use las teclas con flechas arriba/abajo para mover el cursor a la línea que desee editar.
* Antes de modificar el texto ha de presionar `i` para acceder al modo de inserción de vim.
* Cuando acabe de modificar el texto, pulse ESC (para salir del modo de inserción)
* Ahora escriba `:wq!` y presione ENTER para guardar los cambios en disco. W es para escribir (Write), Q para salir (Quit) y ! se usa para forzar la escritura.

### El Entorno ULL-IaaS
1. Inicie sesión en Linux en alguno de los PCs de la sala del Centro de Cálculo. 
En este documento se denominará máquina remota a la máquina virtual (VM) del [IaaS-ULL](https://www.ull.es/servicios/stic/2015/10/27/nuevo-servicio-iaas/) 
y máquina local al PC del centro de cálculo en el que está trabajando.

2. Acceda a la [interfaz web](https://iaas.ull.es/ovirt-engine/sso/login.html) 
de la plataforma IaaS-ULL y autentifíquese en esa interfaz con sus credenciales (username + password) de la cuenta institucional. 
Vea el estado de la máquina y arránquela para comenzar a trabajar con ella.
Tome nota de la Dirección IP de la máquina, que se muestra en el apartado "Detalles" de la máquina.
La [dirección IP](https://en.wikipedia.org/wiki/IP_address) es una secuencia de números (de la forma `172.16.254.1`) que identifican de forma unívoca a cualquier dispositivo conectado a Internet.
Esta dirección será necesaria para establecer conexiones directas a la máquina a través de ssh desde su casa o desde las salas del Centro de Cálculo de la ESIT. 
Anote esa dirección IP puesto que la máquina conserva esa dirección IP de forma estable. 
Si en algún momento experimenta dificultades de conexión, conecte a través de la interfaz web y compruebe que
la dirección de la máquina no ha cambiado.
Para consultar la IP en un terminal Linux utilice el comando:
```
$ ifconfig -a
```

3. Acceda a la consola de la máquina (VNC Console (Browser)) y compruebe el sistema operativo y versión del mismo:
```
$ lsb_release -a
```
Tendrá que cambiar el password (que inicialmente es "usuario") de acceso a esa máquina remota la primera vez que entre en ella. 
El username será siempre "usuario".  
Utilice el comando `password` para cambiar la contraseña de acceso a la máquina.
El comando le solicitará que introduzca la contraseña actual (que es `usuario`) y que escriba dos veces la
nueva contraseña elegida.
No se preocupe por la contraseña por ahora puesto que siempre la puede cambiar en el futuro con el comando
`passwd` pero **anote** el password que elija para no perderlo u olvidarlo. 
Simplemente elija un password que sea robusto y sobre todo fácil de recordar para Ud.

4. Actualice el software (paquetes) de la máquina siguiendo las indicaciones de [esta página](https://linuxconfig.org/how-to-update-ubuntu-packages-on-18-04-bionic-beaver-linux) (por ejemplo).
Los comandos que tendrá que utilizar son:
```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt autoremove
```
Cuando el sistema le pregunte si hacerlo, indique No instalar `grub`.

5. Edite los ficheros necesarios para [cambiar el nombre lógico de la máquina](https://askubuntu.com/questions/9540/how-do-i-change-the-computer-name) que le ha sido asignada. 
Se propone utilizar como nombre algo como Ubuntu-18-IB-XXX (cambiando "XXX" por lo que Ud. quiera), aunque puede Ud. usar para su máquina el nombre que más le guste.
Para realizar ese cambio ha de editar Ud. los siguientes ficheros (necesita usar `sudo` para tener permisos de
root al tratarse de ficheros del sistema):
```
$ sudo vi /etc/hostname
$ sudo vi /etc/hosts
```
	
Para que este cambio tenga efecto, ha de reiniciar la máquina:
```
$ sudo reboot
```

6. Siga [estas instrucciones](http://www.linuxproblem.org/art_9.html) 
para establecer la configuración de la máquina de modo que se pueda conectar a ella sin necesidad de escribir el password en cada conexión. 
Para poder conectarse por ssh con las máquinas virtuales de IaaS ull ha de autentificarse en la página [acceso.ull.es](acceso.ull.es).  
En caso de acceder desde fuera de la red de la ULL ha de hacerlo mediante una conexión VPN. 
Consulte [esta referencia](https://www.ull.es/servicios/stic/2016/05/10/servicio-de-vpn-de-la-ull/) 
(en el Centro de Cálculo, por ahora no lo necesita) para conectarse a través de vpn.

7. También resulta conveniente utilizar alguno de los métodos (ssh config o alias) que se presentan en 
[estas instrucciones](https://scotch.io/tutorials/how-to-create-an-ssh-shortcut) 
de modo que se simplifique la conexión con la máquina remota pudiendo escribir algo como:
```
$ ssh mi_maquina_ibasica
```
para conectarse a la máquina remota.

4. En la máquina local ejecute el Microsoft Visual Studio Code y siga [estas instrucciones](https://code.visualstudio.com/docs/remote/ssh)
para configurar la edición remota de ficheros.

9. Consiga que se pueda subir código desde su máquina PAI hacia su cuenta GitHub sin necesidad de autentificación. 
Consulte para ello las instrucciones “[Adding a new SSH key to your GitHub account][10] y compruebe que es Ud. capaz de subir (commit) un fichero desde la máquina remota hacia su cuenta GitHub.

10. Clone en su máquina IaaS el repositorio con el código que se ha entregado (git classroom) con el enunciado de la práctica:
```
git clone git@github.com:ULL-ESIT-INF-PAI-2019-2020/2019-2020-PAI-P01-Entorno-XXX.git
```

Recuerde colocar en el directorio `src` de ese repositorio una copia de todos los ficheros que haya modificado.
 
13. Ejecute en modo consola (sin usar un navegador) el código de ejemplo `computePI.js` que hemos estudiado en clase.
14. Codifique y compruebe el funcionamiento del programa que resuelve el ejercicio "[FizzBuzz][14].
15. Dedique el tiempo restante a probar diferentes códigos (los que más interés le susciten) de [este tutorial][15].

## Referencias
[8]: https://scotch.io/tutorials/how-to-create-an-ssh-shortcut "How to Create an SSH Shortcut"
[10]: https://help.github.com/en/enterprise/2.15/user/articles/adding-a-new-ssh-key-to-your-github-account 	"Adding a new SSH key to your GitHub account"
