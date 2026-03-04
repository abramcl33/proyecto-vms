# 03. Instalación de Docker y Docker Compose

## 1. Añadir el Repositorio Oficial de Docker
Para obtener la versión más reciente, se configuró el repositorio oficial:
`sudo apt-get update`
`sudo apt-get install ca-certificates curl -y`
`sudo install -m 0755 -d /etc/apt/keyrings`
`sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc`
`sudo chmod a+r /etc/apt/keyrings/docker.asc`

`echo \`
  `"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \`
  `$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \`
  `sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

## 2. Instalación de los Paquetes
`sudo apt-get update`
`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y`

## 3. Configuración de Permisos (Post-instalación)
Se añadió el usuario regular al grupo de Docker para evitar el uso constante de sudo:
`sudo usermod -aG docker $USER`
`newgrp docker`

Comprobación de funcionamiento: `docker run hello-world`

## 4. Creación de Red Personalizada
Se generó una red *bridge* aislada para la comunicación interna de los futuros contenedores:
`docker network create mi_red_proyecto`

Comprobación: `docker network ls`
