# 01. Instalación y Configuración Base de las Máquinas Virtuales

## 1. Creación de la VM en VirtualBox
- **Sistema Operativo:** Ubuntu 24.04 Server (64-bit).
- **RAM:** 2048 MB.
- **Disco Duro:** 40 GB (VDI, Reservado dinámicamente).
- **Red:** 1 Adaptador configurado como **Adaptador Puente (Bridged Adapter)** conectado a la tarjeta física para obtener una IP de la red local.

## 2. Instalación del Sistema y Particionado
Durante la instalación con la ISO de Ubuntu Server 24.04, se configuró un **Custom storage layout** (Particionado manual):
- **Partición Raíz (`/`):** 20 GB en formato `ext4`.
- **Partición de Datos (`/datos`):** Resto del espacio en formato `ext4`.
- **Usuarios:** Se creó un usuario regular con pertenencia al grupo `sudo`.
- **SSH:** Se marcó la opción de instalar OpenSSH Server durante el asistente.

## 3. Configuración de Usuarios
Activación y asignación de contraseña al usuario `root`:
`sudo passwd root`

## 4. Cambio del Puerto SSH (2222)
Al usar Ubuntu 24.04, SSH funciona mediante sockets de *systemd*. Se forzó el uso del puerto 2222 sobre IPv4:
`sudo systemctl edit ssh.socket`

Contenido modificado:
[Socket]
ListenStream=
ListenStream=0.0.0.0:2222

Aplicar los cambios y reiniciar el servicio:
`sudo systemctl daemon-reload`
`sudo systemctl stop ssh.service`
`sudo systemctl restart ssh.socket`

## 5. Clonación de la Máquina (VM2)
Para crear la segunda máquina sin repetir la instalación:
1. Apagado de VM1 (`sudo poweroff`).
2. Clonación completa en VirtualBox generando **nuevas direcciones MAC** para todos los adaptadores de red.
3. En la nueva VM2, cambio de nombre de host para evitar conflictos:
`sudo hostnamectl set-hostname vm2`
`sudo nano /etc/hosts` (Se sustituyó 'vm1' por 'vm2' en la línea 127.0.1.1)
`sudo reboot`
