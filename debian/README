# Paquete DEB vx-dga-c-google-drive

Paquete DEB encargado de instalar y configurar **grive2**, **https://github.com/vitalif/grive2**, en equipos Linux sin entorno gráfico (Debian [Server], Ubuntu Server, etc.).  En concreto, lo que hace es clonar el siguiente repositorio de **grive2** y lo configura como servicio del sistema y asegurando una sincronización de los cambios locales o remotos.

```
git clone https://github.com/vitalif/grive2
```

# Usuarios Destinatarios

Usuarios, profesores y alumnos que hacen uso de Google Drive.

# Aspectos Interesantes:

Por defecto, el usuario con el que se lanza el servicio al iniciarse el equipo es **profesor**, y el directorio local de sincronización **/var/nfs/privado/Drive**.  En caso de querer personalizar estos datos se recomienda hacer lo siguiente:

1. Crear el directorio local de sincronización de Google Drive y asegurarse de que el propietario de dicho directorio es el usuario con el que deseamos realizar la sincronización:

```
sudo mkdir -p DIR_SYNCR
sudo chown USER_DRIVE:USER_DRIVE DIR_SYNCR
```

2. Crear el fichero de variables usado por el paquete durante su instalación, y personalizar sus valores de la siguiente forma:

```
echo "
[Confgrive]
grive2_users = USER_DRIVE
grive2_default_dir = DIR_SYNCR
git_grive2_install = 0
grive2_destino = 1
grive2_first_sync = 0
" > /etc/default/vx-variables-grive2
```

3. Durante el proceso de instalación de este paquete éste detectará el fichero de configuración anterior, **/etc/default/vx-variables-grive2**, al que habrá que indicarle que lo mantenga.

# Como Crear el paquete DEB a partir del codigo de GitHub
Para crear el paquete DEB será necesario encontrarse dentro del directorio donde localizan los directorios que componen el paquete.  Una vez allí, se ejecutará el siguiente comando (es necesario tener instalados los paquetes apt-get install debhelper devscripts):

```
apt-get install debhelper devscripts
/usr/bin/debuild --no-tgz-check -us -uc
```

En caso de no querer crear el paquete para tu distribución, si simplemente quieres obtenerlo e instalarlo, puedes hacer uso del que está disponible para los servidores Caché Debian 8 del programa de Software Libre Vitalinux (*Debian 8*) desde el siguiente repositorio:

[Respositorio de paquetes DEB del Servidor Caché Debian 8 del programa Vitalinux](http://migasfree.educa.aragon.es/repo/Debian8/STORES/base/)

# Como Instalar el paquete generado vx-dga-l-*.deb:
Para la instalación de paquetes que estan en el equipo local puede hacerse uso de ***dpkg*** o de ***gdebi***, siendo este último el más aconsejado para que se instalen también las dependencias correspondientes.
```
gdebi vx-dga-c-*.deb
```
