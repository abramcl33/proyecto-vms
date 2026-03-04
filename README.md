# Proyecto: Infraestructura Base con Ubuntu Server 24.04 y Docker

Este repositorio contiene la documentación paso a paso para la creación, configuración y despliegue de un entorno de laboratorio compuesto por dos Máquinas Virtuales (VMs) gestionadas con VirtualBox.

## Objetivo del Proyecto
Establecer una infraestructura sólida, documentada y reproducible que cumpla con los siguientes requisitos técnicos:
- Particionado específico de discos (separación de Sistema y Datos).
- Configuración de red mixta (Salida a internet y conexión SSH directa desde el host físico).
- Configuración de seguridad inicial (Usuarios regulares con sudo, habilitación de root y cambio de puerto SSH al 2222).
- Instalación de utilidades de sistema modernas (eza, plocate, iperf3, htop, etc.).
- Despliegue de un motor de contenedores (Docker y Docker Compose) con una red puente personalizada.
- Estrategia de recuperación rápida mediante Snapshots de VirtualBox.

## Índice de Documentación

Toda la documentación técnica detallada con los comandos ejecutados se encuentra en la carpeta `docs/`. Puedes seguir el proceso cronológicamente en el siguiente orden:

1. [Fase 1: Instalación y Configuración Base de las VMs](docs/01-instalacion-vm.md)
2. [Fase 2: Instalación de Herramientas y Configuración del Entorno](docs/02-instalacion-herramientas.md)
3. [Fase 3: Instalación de Docker y Docker Compose](docs/03-instalacion-docker.md)
4. [Fase 4: Creación de Puntos de Control (Snapshots) y Pruebas](docs/04-creacion-pruebas-snapshots.md)
