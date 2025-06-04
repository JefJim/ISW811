# Workshop01

En este workshop lo que hicimos fue aprender a crear una máquina virtual usando Vagrant y VirtualBox
## Pasos realizados

1. Verificar y habilitar la virtualización en el BIOS/UEFI en caso de aparecer inhabilitada en el administrador de tareas
2. Instalar VirtualBox y Vagrant desde sus páginas oficiales
3. Configurar la red en VirtualBox
4. Inicializar y configurar la máquina virtual
5. Levantar y verificar la máquina virtual
6. Instalar Apache en la máquina virtual
7. Apagar la máquina virtual antes de apagar la máquina principal para evitar apagar de "botonazo" la VM
8. Documentar el workshop para subirlo al campus

## Comandos utilizados

### Comandos básicos de terminal
- `cd`: Nos permite navegar entre directorios
- `mkdir`: Crea un nuevo directorio/carpeta
- `ls` / `ls -la`: Lista archivos y la segunda nos permite ver archivos ocultos
- `pwd`: Muestra la ruta actual
- `touch`: Crea un archivo vacío
- `code`: Para abrir Visual Studio Code

### Comandos Vagrant
- `vagrant init`: Inicializa el entorno Vagrant
- `vagrant up`: Iniciar la máquina virtual
- `vagrant status`: Muestra el estado de la VM
- `vagrant ssh`: Conectar a la VM via SSH
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