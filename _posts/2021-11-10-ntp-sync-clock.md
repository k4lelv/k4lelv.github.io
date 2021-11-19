---

layout: single
title: Como Sincronizar hora con NTP en Linux
excerpt: "Uno de los comandos mas útiles en Linux es NTP (Network Time Protocol) el cual se encarga de sincronizar de forma automática la hora de nuestro servidor en red y esto es un punto delicado cuando hablamos de un equipo en ambientes productivos ya que una mala sincronización de la hora puede llegar a afectar diversas tareas y mas si el equipo es un servidor."
date: 2021-11-10
classes: wide
header:
    teaser: #https://k4lelv.github.io/k4lelvBlog.github.io/assets/images/slae32.png
categories:
    - utilidades
    - linux
tags:
    - utilidades
    - linux
    - sync
    - automatizacion

---
![](https://images.unsplash.com/photo-1499686934070-fde9d797e48c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80)


Uno de los comandos mas útiles en Linux es NTP (Network Time Protocol) el cual se encarga de sincronizar de forma automática la hora de nuestro [servidor en red](https://www.solvetic.com/page/recopilaciones/s/recopilacion/mejores-distribuciones-para-servidor-linux) y esto es un punto delicado cuando hablamos de un equipo en ambientes productivos ya que una mala sincronización de la hora puede llegar a afectar diversas tareas y mas si el equipo es un servidor.

El equipo puede hacer permitir que el reloj del sistema haga uso del Tiempo Universal Coordinado (UTC) en lugar de la hora local para estar mucho mas acorde a la hora requerida. Como administradores, la forma clásica de realizar la sincronización de la hora es haciendo uso del comando ntpdate, el cual se encarga de configurar la hora del sistema desde un servidor horario NTP establecido.

### Veamos como seria hacer uso de NTP en linux.
---------------
1. Instalamos NTP en nuestra maquina linux

```
sudo apt-get install ntpdate (Debian/Ubuntu)
sudo yu install ntpdate      (CentOS/RHEL)
sudo dnf install ntpdate     (Fedora)
```
2. Cómo usar NTP desde linux

```
// Asi establecemos el servidor como servidor NTP
sudo ntp co.pool.ntp.org
```

```
// Si deseamos consultar el servidor pero sin configurar el reloj ni usar un puerto sin privilegios para enviar los paquetes y para evitar los firewalls, debemos ejecutar 
sudo ntpdate -qu co.pool.ntm.org
```

Toda la lista de servidores NTP disponibles la encontramos en [SERVIDORES NTP](http://www.pool.ntp.org/es/)

Allí en la parte de la derecha, econtramos cada una de  las regiones mundiales.

![](https://www.solvetic.com/uploads/monthly_04_2018/tutorials-7463-0-25672700-1525073397.png)

Al pulsar sobre un continente, y el respectivo pais de su elección se puede observar la lista de todos los servidores disponibles para usar.

![](https://www.solvetic.com/uploads/monthly_04_2018/tutorials-7463-0-74176500-1525073396.png)


#### En algunas distribuciones de linux mas reciente, las cuales cuentan con Systemd, es posible actualizar la hora atravez del archivo timesyncd.conf, lo puede usar con cualquier editor de texto que use.

```
sudo nano /etc/systemd/timesyncd.conf
```

### Allí debemos descomentar las siguientes líneas bajo [Time] y añadir el servidor según sea necesario

```
NTP=server 0.south-america.pool.ntp.org
FallbackNTP=ntp.ubuntu.com 0.arch.pool.ntp.org
```

![](https://www.solvetic.com/uploads/monthly_04_2018/tutorials-7463-0-20505900-1525073396.png)

Luego será necesario hacer el cambio efectivo al servidor NTP 

```
sudo timedatectl set-ntp true
timedatectl status
```

Y listo!!


Para mas detalles visitar [https://www.solvetic.com](https://www.solvetic.com/tutoriales/article/5327-como-sincronizar-hora-con-ntp-en-linux/)