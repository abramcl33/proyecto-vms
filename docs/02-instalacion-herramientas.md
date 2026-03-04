# 02. Instalación de Herramientas y Configuración del Entorno

## 1. Actualización del Sistema operativo
`sudo apt update && sudo apt upgrade -y`

## 2. Instalación de Paquetes y Utilidades
Se instalan las herramientas solicitadas (se utilizan `eza` y `plocate` por ser las versiones modernas soportadas en Ubuntu 24.04 para `exa` y `mlocate` respectivamente):
`sudo apt install htop net-tools iperf3 git curl wget nano vim ufw eza plocate figlet tmux molly-guard -y`

*(Nota: Durante la configuración de iperf3 se eligió NO ejecutarlo como demonio automático para poder lanzarlo de forma manual en las pruebas de red).*

## 3. Configuración del Entorno (.bashrc)
Se mejoró la experiencia en la terminal editando el archivo `~/.bashrc` del usuario para añadir alias útiles y un prompt visual.

**Añadido al final del archivo:**
# Mis Alias Personalizados
alias ll='eza -lh --icons'
alias la='eza -lha --icons'
alias update='sudo apt update && sudo apt upgrade -y'
alias puertos='netstat -tulanp'
alias buscar='locate'

# Prompt personalizado
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

Aplicar los cambios sin reiniciar la sesión:
`source ~/.bashrc`
