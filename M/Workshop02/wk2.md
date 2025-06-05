# Workshop02 - LAMP on Debian


## Pasos realizados

Vimos un resumen de LAMP presentada por el profe Misael al incio de clases y de elementos que intervienen en la publicación de una web y arrancando la VM _Debian/Bookworm_.

Posterior arrancamos la máquina virtual

```bash
cd C/Users/jefry/OneDrive/Documentos/ISW811/VMs/webserver
vagrant up
```

Podemos verificar que la máquina está en ejecución desde VB

![Imagen de VirtualBox](./images/prueba1.png "Máquina en ejecución")

Posterior creamos una nueva carpeta "Workshop02" con el README.md y subirlo a git en la carpeta M

```bash
cd c/Users/jefry/OneDrive/Documentos/ISW811/M
mkdir Workshop02
touch README.md
mkdir images
git add README.md /images
git commit "Inicializar repositorio"
git push
```

Continuamos con la enseñanza de comprimir un archivo taz.gz "Workshop02-Jefry.tar.gz" para posterior subirlo al campus

```bash
tar cvfz Workshop02-Jefry.tar.gz Workshop02
```

Nos movemos a donde está la VM para acceder mediante SSH

```bash
cd c/Users/jefry/OneDrive/Documentos/ISW811/VMs/webserver
vagrant up
vagrant ssh
```

Creamos un archivo nuevo con el comando nano y agregamos el texto "Hola mundo soy Jefry" y ejecutamos le combinación de teclas ctrl+o para guardar con el nombre "saludo.txt" y nos salimos del editor de texto con ctrl+x

```bash
nano
```

![Imagen nano](./images/prueba2.png "creación del archivo")


Ahora vamos a cambiar el nombre host una vez conectados en a la VM, aplicando los mismos pasos de antes solo borramos el nombre bookworm y ponemos webserver

```bash
sudo hostnamectl set-hostname webserver
sudo nano /etc/hosts
```

![Imagen nano editando hosts](./images/prueba3.png "cambio de nombre")

## Comandos utilizados

### Comandos básicos de terminal
- `cd`: Nos permite navegar entre directorios
- `mkdir`: Crea un nuevo directorio/carpeta
- `ls` / `ls -la`: Lista archivos y la segunda nos permite ver archivos ocultos
- `file`: + nombreDeArchivo nos permite ver que tipo de archivo es
- `pwd`: Muestra la ruta actual
- `touch`: Crea un archivo vacío
- `code`: Para abrir Visual Studio Code
- `tar cvfz "nombreFinalArchivo" "CarpetaAComprimir"`: Este comando se utiliza para comprimir archivos 

### Comandos Vagrant
- `vagrant init`: Inicializa el entorno Vagrant
- `vagrant up`: Iniciar la máquina virtual
- `vagrant status`: Muestra el estado de la VM
- `vagrant ssh`: Conectar a la VM via SSH
- `vagrant halt`: Apagar la VM
- `sudo nano /etc/hosts`: acceder al archivos hosts para cambiar el nombre
- `vagrant halt`: Apagar la VM

### Comandos de red y sistema
- `ping`: Verificar conexión 
- `sudo`: Ejectutar comandos con previlegios de super usuario
- `apt-get update`: Actualizar paquetes del sistema
- `apt-get install`: Instalar paquetes

## Detalles de implementación

### Configuración inicial
```bash
vagrant init debian/bookworm64
# code Vagrantfile
# Descomentar línea 35 del archivo y configurar IP privada y utilizar la 192.168.56.10
# config.vm.network "private_network", ip: "192.168.56.10"