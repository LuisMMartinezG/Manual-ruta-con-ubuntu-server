# Manual de instalación de ruta
### _Con Ubuntu Server 20.04 LTS_
***
### Objetivo
Proporcionar un manual que le permita al personal de los departamentos de ingeniería, implementación y soporte de IES, instruirse en la instalación de ruta con Ubuntu server 20.04 LTS.

***
### En este manual veremos lo siguiente:

- Instalación del sistema operativo Ubuntu Server 20.04 LTS
- Instalación de los programas necesarios para su correcto funcionamiento
- Creación y edición de archivos necesarios
- Instalar librerias necesarias
- Dar permisos, asignar grupo, usuario y ubicar a los archivos de ruta
- Generar las imagenes y montar contenedores en Docker-compose 
***
## ¿Qué es Ubuntu server y por qué lo elegimos?
Ubuntu server es una variante de Ubuntu, dedicado a ser utilizado en entornos de servidores, ya que este es muy liviano y consume pocos recursos, esto es gracias a que no tiene entornos gráficos y tampoco tiene programas instalados por defecto. Practicamente está vacío. Por esto es que elegimos esta variante de Ubuntu.
***
## Instalación de Ubuntu Server 20.04 LTS

Lo primero es hacer la memoria booteble con el sistema operativo Ubuntu Server 20.04 LTS.
Para hacer la memoria booteable, veremos este [tutorial de cómo hacer una memoria booteable](https://www.youtube.com/watch?v=Aey3uyToZXQ). Una vez que tengamos la memoria booteable con el sistema operativo, procedemos con su instalación a nuestra maquina, para esto, seguiremos estas indicaciones:

- Introducir memoria USB en algún puerto del minipc
- Reiniciar pc
- Presionar la tecla F11 mientras se enciende
- Seleccionar la USB booteada
- Configuraciones:
-- Teclado (elegir idioma español)
-- Conexiones de red (conectarse a la red internet con cable)
-- Proxy (ignorar)
-- Ubuntu archive mirror (ignorar)
-- Guide storage (ignorar)
-- Storage (ignorar y confirmar)
- Configuración perfil:
-- Su nombre: ruta
-- El nombre del servidor: ruta
-- Elije un nombre de usuario: ruta
-- elija una contraseña: ruta123*.*
-- Confirme contraseña: ruta123*.*
- Configuración de SSH (ignorar)
- Futured server snaps (ignorar)
- Esperar instalación y reiniciar equipo
***
## Instalación de programas necesarios

Una vez instalado el sistema operativo correctamente, procedemos a instalar sus programas necesarios, estos son:

- [aptitude](https://es.wikipedia.org/wiki/Aptitude)
- [firefox ](https://es.wikipedia.org/wiki/Mozilla_Firefox)
- [pcmanfm](https://es.wikipedia.org/wiki/PCManFM)
- [lightdm](https://es.wikipedia.org/wiki/LightDM)
- [gnome-terminal](https://es.wikipedia.org/wiki/GNOME_Terminal)
- [x11-xserver-utils](https://packages.debian.org/es/sid/x11-xserver-utils)
- [openbox](https://es.wikipedia.org/wiki/Openbox)
- [obconf](https://ubunlog.com/como-instalar-openbox-en-ubuntu/)
- [mysql-client](https://es.quora.com/Cu%C3%A1l-es-la-diferencia-entre-un-servidor-MySQL-y-un-cliente-MySQL)
- [psmisc](http://www.escomposlinux.org/lfs-es/lfs-es-5.0/appendixa/psmisc.html) 
- [alsa-utils](http://www.escomposlinux.org/lfs-es/blfs-es-1.0/multimedia/alsa-utils.html)
- [feh](https://wiki.archlinux.org/index.php/Feh_(Espa%C3%B1ol))
- [Docker](https://es.wikipedia.org/wiki/Docker_(software))
- [Docker Compose](https://dev.to/ebarrioscode/que-demonios-es-docker-docker-compose-y-como-dockerizar-dotnet-core-webapi-y-sql-server-en-un-ambiente-de-desarrollo-ideal-95a)
- [Qt](https://es.wikipedia.org/wiki/Qt_(biblioteca))
***
## Instalación aptitude
```sh
sudo apt-get install aptitude
```

## Instalación firefox
```sh
sudo aptitude install firefox
```

## Instalación pcmanfm
```sh
sudo aptitude install pcmanfm
```

## Instalación lightdm
```sh
sudo aptitude install lightdm
```

## Instalación gnome-terminal
```sh
sudo aptitude install gnome-terminal
```

## Instalación x11-xserver-utils
```sh
sudo aptitude install x11-xserver-utils
```

## Instalación openbox
```sh
sudo aptitude install openbox
```

## Instalación obconf
```sh
sudo aptitude install x11-xserver-utils
```

## Instalación mysql-client
```sh
sudo aptitude install x11-xserver-utils
```

## Instalación psmisc
```sh
sudo aptitude install x11-xserver-utils
```

## Instalación alsa-utils
```sh
sudo aptitude install x11-xserver-utils
```

## Instalación feh
```sh
sudo aptitude install feh
```

***
## Instalación Docker
```sh
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
``` 
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
``` 
```sh
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
``` 
```sh
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io
``` 
***
## Instalación Docker Compose
```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```sh
sudo chmod +x /usr/local/bin/docker-compose
```

```sh
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
***
## Instalación Qt
- Entrar al siguiente link: [Página oficial de instalación de Qt](https://www.qt.io/download-qt-installer?hsCtaTracking=99d9dd4f-5681-48d2-b096-470725510d34%7C074ddad0-fdef-4e53-8aa8-5e8a876d6ab4)
- Dar click en Download
- Confirmar descarga
- Dar permisos de ejecución:
```sh
sudo chmod +x /usr/local/bin/docker-compose
```
- Iniciar:
```sh
./qt-unified-linux-x64-4.1.0-online.run
```
- Escribir credenciales y loguearse
- Aprobar las obligaciones
- Habilitar el envío de estadisticas
- Crear una carpeta llamada qt en la ruta /home/ruta/Documents/
-- Seleccionar la carpeta creada en la opción "Especificar carpeta"
-- Seleccionar la opción "Custom installation"
- Seleccionar solo la opción "Archive"
-- Filter
-- Qt
-- Versión 5.9.5
- Seleccionar la opción de haber leido los terminos y condiciones
- Instalar
***
## Cración y/o edición de archivos necesarios

### _Creación y modificación de archivo autostart_
Este archivo debe estar en una carpeta llamada openbox en la ruta **/home/ruta/.config/** Asi que primero debemos crear esta carpeta.

Comando:
```sh
sudo mkdir openbox /home/ruta/.config/
```

Ahora si creamos el archivo autostart
Comando:
```sh
sudo nano /home/ruta/.config/autostart
```

El anterior comando nos permite crear y modificar el archivo. El archivo debe contener lo siguiente:
```
xset s off         # don't activate screensaver
xset -dpms         # disable DPMS (Energy Star) features.
xset s noblank     # don't blank the video device

start=$(date +%s)
sleep 8
#feh //bg/scale /home/ruta/imagenes/1.png
for c in `seq 3 16`
do
  feh --bg-scale /home/ruta/imagenes/$c.png
  sleep 1
sleep 7
done

sleep 8
export LD_LIBRARY_PATH=/home/ruta/Documents/qt/5.9.2/gcc_64/lib &
sleep 1
manager &
sleep 1
#anydesk &
sleep 1
#wmctrl -r anydesk &
sleep 1
./RUTA/Lanzador/Lanzador.x86_64
```

### _Modificación de archivo sudoers_
Escribir el siguiente comando en la terminal:
```
sudo visudo
```

Agregar la siguiente línea 
```
ruta ALL=(ALL:ALL) ALL
```
En la sección **"# User privilege specification"**

### _Creación de carpeta RUTA_
Esta carpeta debe estar ubicada en la ruta **/home/ruta/**

Comando:
```sh
sudo mkdir RUTA /home/ruta/
```

### _Crear y modificar el archivo lightdm.conf_
Escribir el siguiente comando en la terminal:
```sh
sudo nano /etc/lightdm/lightdm.conf
```

Introducir el siguiente texto:
```
[SeatDefaults]
autologin-user = ruta 
autologin-user-timeout=0
```

### _Crear y modificar el archivo 10_ies.rules_
Escribir el siguiente comando en la terminal:
```sh
sudo nano /etc/udev/rules.d/10_ies.rules
```

Introducir el siguiente texto:
```
KERNEL=="js*", SUBSYSTEM=="input", ATTRS{idVendor}=="0079", ATTRS{idProduct}=="0006", SYMLINK+="ies/key%n", MODE:="0666"
```

### _Modificación del archivo crontab_
Escribir el siguiente comando en la terminal:
```sh
sudo nano /etc/crontab
```

Ingresar en la última línea:
```
01 *    * * *   root    find    /RUTA/Screenshots/* -mtime +1 -delete
```
***
## Instalar librerias necesarias
### Instalar la librería mysql-client

Descargar automaticamente dando click en el siguiente **[enlace](https://repo.mysql.com/apt/ubuntu/pool/mysql-5.7/m/mysql-community/libmysqlclient20_5.7.33-1ubuntu18.04_amd64.deb)**

**Ejecutar los siguientes comandos:**
```
sudo dpkg -i libmysqlclient20_5.7.33-1ubuntu18.04_amd64.deb
sudo apt-get update
sudo apt-get install libmysqlclient20
```

### Librerías necesarias
```sh
sudo aptitude install libqt5printsupport5
sudo aptitude install libqt5serialport5
sudo aptitude install libqt5websockets5
sudo aptitude install libqt5sql5
sudo aptitude install libqt5quick5
sudo aptitude install qml-module-qtmultimedia
sudo aptitude install qml-module-qtquick-window2
```
***
## Dar permisos, asignarles grupo, usuario y ubicar a los archivos de ruta

Para este paso es necesario haber descargado todos los archivos necesarios de ruta y haberlos descomprimido

### Archivos libICT_bill
Dar permisos:
```sh
sudo chmod +x libICT_bill.s*
```

Asignar grupo y usuario:
```sh
sudo chown root:root libICT_bill.s*
```

Ubicar:
```sh
sudo mv libICT_bill.s* /usr/lib/
```

### Carpeta kbitech_ICT
Dar permisos:
```sh
sudo chmod 777 kbitech_ICT
```

Asignar grupo y usuario:
```sh
sudo chown root:root kbitech_ICT
```

Ubicar:
```sh
sudo mv kbitech_ICT /usr/include/
```

### Carpeta manager, configuration, genericModals y docker-clean
Dar permisos:
```sh
sudo chmod +x manager configuration genericModals docker-clean
```

Asignar grupo y usuario:
```sh
sudo chown ruta:ruta manager configuration genericModals docker-clean
```

Ubicar:
```sh
sudo mv manager configuration genericModals docker-clean /usr/local/bin/
```

### Archivo tty_enable.sh
Dar permisos:
```sh
sudo chmod +x tty_enable.sh
```

Asignar grupo y usuario:
```sh
sudo chown root:root tty_enable.sh
```

Ubicar:
```sh
sudo mv tty_enable.sh /usr/bin/
```

### Archivo billetero.ini
Dar permisos:
```sh
sudo chmod 777 billetero.ini
```

Asignar grupo y usuario:
```sh
sudo chown ruta:ruta billetero.ini
```

Ubicar:
```sh
sudo mv billetero.ini /etc/ruta/
```

### autoverificacion.sh
Dar permisos:
```sh
sudo chmod +x autoverificacion.sh
```

Asignar grupo y usuario:
```sh
sudo chown root:root autoverificacion.sh
```

Ubicar:
```sh
sudo mv autoverificacion.sh /usr/bin/
```

### Servicio tty-enable.service
Dar permisos:
```sh
sudo chmod +x tty-enable.service
```

Asignar grupo y usuario:
```sh
sudo chown root:root tty-enable.service
```

Ubicar:
```sh
sudo mv tty-enable.service /etc/systemd/system/
```

Habilitar:
```sh
sudo systemctl enable ttys-enable.service
```

Comenzar:
```sh
sudo systemctl start ttys-enable.service
```

### Asignación de permiso de ejecución a los archivos ejecutables de los juegos
Comando:
```sh
chmod +x /home/ruta/RUTA/*/*.x86_64
```

### Asignación de todos los permisos a los archivos .xml de los juegos
Comando:
```sh
chmod 777 /home/ruta/RUTA/*/*/*/*.xml
```

### Creación de carpeta db
Esta carpeta debe estar en la ruta **/home/ruta/RUTA/**
Comando:
```sh
sudo mkdir db /home/ruta/RUTA/
```
***
## Generar las imagenes y montar contenedores en Docker-compose
Comandos:
```sh
cd  /home/ruta/Documents/docker/
sudo docker-compose -f docker-compose.yml build
sudo docker-compose -f docker-compose.yml up -d
```

Reiniciar el equipo con comando:
```sh
reboot
```

## Ubuntu Server vs Xubuntu
|Ejecución|Proceso|Ubuntu Server (seg)|Xubuntu (seg)|Ubuntu Server|Xubuntu|
|-|-|-|-|-|-|
|*Encendido*|Tiempo en encender|2,40|2,37|  | ✓ | 
|*Lanzador*|CPU(%)|53-63|65-70| ✓ | |
||RAM(Gb)|2,18|2,16| | ✓ | 
|*Blackjack*|Tiempo 1ra vez|6 s|5,59| | ✓ | 
||Tiempo >=2 vez|3,5|3,66| ✓ | |
||CPU(%)|100-114|100-140| ✓ | |
||RAM(Gb)|2,49|2,50| ✓ | |
|*Ruleta*|Tiempo 1ra vez(seg)|6|7,48| ✓ | |
||Tiempo >=2(seg)|3|3,50| ✓ | |
||CPU(%)|120-150|110-179| ✓ | |
||RAM(Gb)|2,69|2,78| ✓ | |
|*Dados*|Tiempo 1ra vez(seg)|8.78|8.83| ✓ | |
||Tiempo >=2(seg)|3|3.71| ✓ | |
||CPU(%)|120-155|100-144|  | ✓ | 
||RAM(Gb)|2.77|2.9| ✓ | |
|*La24*|Tiempo 1ra vez(seg)|6|7.34|✓ | |
||Tiempo >=2(seg)|3|3.73|✓ | |
||CPU(%)|130-153|130-160|✓ | |
||RAM(Gb)|2.69|2.89|✓ | |
|*Poker*|Tiempo 1ra vez(seg)|11|9.32| | ✓ | 
||Tiempo >=2(seg)|3|3.37|✓ | |
||CPU(%)|115-229|90-276|✓ | |
||RAM(Gb)|2.7|3.14|✓ | |
|*Rieles*|Tiempo 1ra vez(seg)|3.50|3.62|✓ | |
||Tiempo >=2(seg)|2.11|3.23|✓ | |
||CPU(%)|45-215|70-210|✓ | |
||RAM(Gb)|2.70|2.97|✓ | |
||||*Total*|22 (81.48%)|5 (18.52%)|

|||Lanzador|Blacjack|Rieles|Poker|Dados|Ruleta|
|-|-|-|-|-|-|-|-|
|**Ubuntu Server**|*CPU(%)*|53-63 ✓|100-114 ✓|45-215 ✓|115-229|120-155|120-150|
|**Xubuntu**|*CPU(%)*|65-70|100-140|70-210|90-276 ✓|100-144 ✓|110-179 ✓|
|**Ubuntu Server**|*RAM(Gb)*|2,18|2,49 ✓|2.70 ✓|2.70 ✓|2.77 ✓|2.69 ✓|
|**Xubuntu**|*RAM(Gb)*|2,16✓|2,50|2.97|2.97|2.9|2.78|

