# Workshop01 - Bookworm con Vagrant

## Instalación de VirtualBox

Se procede a descargar VirtualBox desde el siguiente enlace.
[Descargar VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Instalación de Vagrant

Se procede a descargar Vagrant desde el siguiente enlace.
[Descargar Vagrant](https://www.vagrantup.com/downloads)

## Instalación de Cygwin

Se procede a descargar Cygwin desde el siguiente enlace.
[Descargar Cygwin](https://www.cygwin.com/install.html)

## Instalación de Git for Windows

Se procede a descargar Git for Windows desde el siguiente enlace.
[Descargar Git for Windows](https://git-scm.com/download/win)

## Instalación de VSCode

Se procede a descargar VSCode desde el siguiente enlace.
[Descargar VSCode](https://code.visualstudio.com/)

## Instalación de Notepad++

Se procede a descargar Notepad++ desde el siguiente enlace.
[Descargar Notepad++](https://notepad-plus-plus.org/downloads/)

## Aprovisionar máquina Debian

Para aprovisionar una máquina Debian necesitaremos crear la estructura de directorios que almacenará las definiciones de las máquinas virtuales, de la siguiente manera.

```bash
cd ~                         #nos redirige a home
mkdir -p ISW/VMs/webserver   #crea directorios -p crea todos si no existen
cd ISW/VMs/webserver         #ingresamos al directorio creado
```

Ahora creamos el Vagrantfile

```bash
vagrant init debian/bookworm64
```

Luego editamos el Vagrantfile para habilitar la red privada con la ip 192.168.56.10 vamos a editar y descomentar la línea 35, dejandola de la sig manera: 

```bash
config.vm.network "private_network", ip: "192.168.56.10"
```

Antes de lanzar el aprovisionamiento de la máquina virtual debemos asegurarnos de que a nivel VirtualBox exista la definición de la `VBoxnet` de la red privada que se desea utilizar con la máquina Vagrant.

<!-- acá mostramos la imagen -->

![Configuración de VBoxNet](./images/Captura%20de%20pantalla%202023-09-19%20212703.png "VBoxNet")

A continuación algunos comandos para iniciar Vagrant desde Bash:

```bash
vagrant up         #para encender máquina
vagrant ssh        #para entrar a máquina
exit               #salir de ssh
vagrant halt       #para apagar máquina
```