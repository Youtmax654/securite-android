# Installation de Headwind MDM

Pour installer Headwind MDM, il faut au minimum Ubuntu 22.04 LTS server avec au minimum 4Gb de RAM, 2xCPU et 20Gb de stockage.

## 1. Installer les logiciels prérequis

```
sudo apt update
sudo apt install -y aapt tomcat9 postgresql vim certbot unzip net-tools
```

Sous Ubuntu 24.04, le package tomcat9 n'est pas disponible par défaut. Il faut donc lancer cette commande pour pouvoir installer tomcat9.

```
add-apt-repository -y -s "deb http://archive.ubuntu.com/ubuntu/ jammy main universe"
```

## 2. Mettre en place la base de données

```
sudo -u postgres psql

postgres=# CREATE USER hmdm WITH PASSWORD 'topsecret';
postgres=# CREATE DATABASE hmdm WITH OWNER=hmdm;
postgres=# \q
exit
```

## 3. Télécharger et unzip l'installeur

```
wget https://h-mdm.com/files/hmdm-5.36-install-ubuntu.zip
unzip hmdm-5.36-install-ubuntu.zip
cd hmdm-install/
```

## 4. Installer Headwind MDM

```
./hmdm_install.sh
```

***

On a pas pu aller au bout de la story car nous n'avions pas d'appareil à enrôler, notamment car il fallait réinitialiser un appareil pour accéder au mode "entreprise" de l'appareil.