<div style="font-family: Arial, sans-serif; font-size: 12pt; text-align: justify;">

# Universidad Tecnológica del Norte de Guanajuato  
<img src="./imagenes/Universidad_Tecnológica_del_Norte_de_Guanajuato_(UTNG).png" alt="Prueba local" width="500"/>

## Carrera: Ingeniería en Redes Inteligentes y Ciberseguridad  
## Grupo: GIRI5091-E  
## Unidad I: Entornos de desarrollo en la automatización de redes  

### Proyecto: Implementación de entorno de desarrollo para automatización de redes  

**Alumno(s):**  
- Nombre: José Manuel Gutiérrez Pérez  
- Número de Control: 1222100502  

**Fecha de entrega:** 10/06/2025  

---

</div>

# Índice
1. [Introducción](#introducción)
2. [Descripción de las herramientas utilizadas para automatización](#descripción-de-las-herramientas-utilizadas-para-automatización)
   1. [Docker Engine](#docker-engine)
      - [Características principales](#características-principales)
      - [Comandos básicos de Docker Engine](#comandos-básicos-de-docker-engine)
   2. [Docker Compose](#docker-compose)
      - [Características principales](#características-principales-1)
      - [Comandos básicos de Docker Compose](#comandos-básicos-de-docker-compose)
   3. [Docker Swagger](#docker-swagger)
      - [Características principales](#características-principales-2)
      - [Comandos básicos para usar Swagger con Docker](#comandos-básicos-para-usar-swagger-con-docker)
3. [Procedimiento de Instalación de Visual Studio Code](#procedimiento-de-instalación-de-visual-studio-code)
   1. [Descargar Visual Studio Code](#1-descargar-visual-studio-code)
   2. [Ejecutar el instalador](#2-ejecutar-el-instalador)
   3. [Inicio del asistente de instalación](#3-inicio-del-asistente-de-instalación)
   4. [Selección de directorio de instalación](#4-selección-de-directorio-de-instalación)
   5. [Instalación](#5-instalación)
   6. [Finalización](#6-finalización)
   7. [Verificación](#7-verificación)
4. [Procedimiento de Instalación y Configuración de Git](#procedimiento-de-instalación-y-configuración-de-git)
   1. [Descargar Git](#1-descargar-git)
   2. [Instalar Git](#2-instalar-git)
   3. [Verificar la instalación](#3-verificar-la-instalación)
   4. [Configuración de Git](#4-configuración-de-git)
5. [Instalación y configuración de dockerfile](#instalación-y-configuración-de-dockerfile)
    1. [Configurar el repositorio oficial de Docker](#1-configurar-el-repositorio-oficial-de-docker)
    2. [Instalar Docker Engine](#2-instalar-docker-engine)
    3. [Post-instalación](#3-post-instalación)
6. [Ejecutar la imagen “hello-world”](#ejecutar-la-imagen-hello-world-para-verificar-el-funcionamiento-de-docker)
7. [Ejecutar un archivo “.YML”](#ejecutar-un-archivo-yml-para-verificar-el-funcionamiento-de-contenedores)
    1. [Ejecutar un archivo ](#ejecutar-un-archivo-php-con-docker-compose)
8. [Conclusión](#conclución)
9. [Bibliografias](#bibliografias)

# Introducción
En este reporte se documenta el procedimiento realizado para la instalación y configuración de un entorno de desarrollo orientado a la automatización de redes. Durante esta unidad, se abordaron herramientas fundamentales como Docker Engine, Docker Compose y Docker Swagger. Estas herramientas permiten la creación, gestión y despliegue de contenedores para servicios de red de forma automatizada y eficiente. Se incluye también el proceso de instalación de herramientas complementarias como Visual Studio Code, Git, así como extensiones necesarias para el trabajo en ambientes colaborativos.
El documento está estructurado para guiar al lector a través de cada etapa del proceso. Primero, se presenta un análisis detallado de las herramientas principales, explicando su arquitectura y cómo contribuyen a la automatización de redes. Luego, se proporciona una guía paso a paso para la instalación y configuración inicial, incluyendo soluciones a problemas comunes que pueden surgir durante este proceso.
Se mostrará evidencia clara de la instalación de cada herramienta y la verificación de su funcionamiento mediante la ejecución de pruebas prácticas, como la ejecución de imágenes de prueba y archivos .yml. Cada paso está respaldado con capturas de pantalla y fragmentos de código que demuestran el correcto funcionamiento del entorno.
Finalmente, se incluye una lista de recursos comunitarios consultados, y se reflexiona sobre los aprendizajes obtenidos. Este informe tiene como propósito consolidar las bases para continuar con la automatización de servicios más complejos, facilitando su implementación y monitoreo.

# Descripción de las herramientas utilizadas para automatización
## Docker Engine
Docker Engine es el motor central de la plataforma Docker que permite construir, ejecutar y gestionar contenedores en diferentes sistemas operativos como Linux, Windows y macOS. Es responsable de empaquetar aplicaciones y sus dependencias en contenedores ligeros y portables que facilitan la ejecución consistente en cualquier entorno.

### Características principales:
- Permite crear y ejecutar contenedores de forma rápida y eficiente.
- Gestiona imágenes de contenedores para construir y desplegar aplicaciones.
- Soporta la ejecución en modo daemon para correr en segundo plano.
- Facilita la comunicación y administración entre contenedores.
- Compatible con múltiples plataformas (Linux, Windows, macOS).
### Comandos básicos de Docker Engine

- Listar contenedores activos:
  ```shell
  docker ps 
  ```
- Listar todos los contenedores (activos y detenidos):
    ``` shell
    docker ps -a
    ```
- Iniciar un contenedor detenido
    ``` shell
    docker start [nombre o ID]
    ```
- Detener un contenedor en ejecución:
    ``` shell
    docker stop [nombre o ID]

    ```
- Eliminar un contenedor:
    ``` shell
    docker rm [nombre o ID]
    ```
- Listar imágenes disponibles en el sistema:
    ``` shell
    docker images
    ```
- Eliminar una imagen:
    ``` shell
    Eliminar una imagen:
    ```
- Construir una imagen desde un Dockerfile
    ``` shell
    docker build -t nombre_imagen:tag --no-cache .
    ```
- Ejecutar un contenedor desde una imagen:
    ``` shell
    docker run -d --name nombre_contenedor -p puerto_local:puerto_contenedor nombre_imagen:tag
    ```
- Ver logs de un contenedor:
    ``` shell
    docker logs [nombre o ID]
    ```
- Ver estadísticas en tiempo real de contenedores:
    ``` shell
    docker stats
    ```

## Docker Compose
Docker Compose es una herramienta que facilita la definición y ejecución de aplicaciones multicontenedor mediante un archivo de configuración YAML (docker-compose.yml). Permite orquestar múltiples contenedores, configurando redes, volúmenes y variables de entorno de forma sencilla, y gestionar todo el conjunto con comandos simples.
### Características principales:

   - Permite definir múltiples servicios, redes y volúmenes en un solo archivo.

   - Facilita el despliegue y la administración de aplicaciones multicontenedor.

   - Soporta ejecución en segundo plano (modo detached).

   - Facilita la escalabilidad de servicios.

   - Simplifica la gestión de configuraciones complejas.
### Comandos básicos de Docker Compose
- Levantar todos los servicios definidos en el archivo docker-compose.yml:
```shell
docker-compose up
```
- Levantar los servicios en segundo plano (modo detached):
```shell
docker-compose up -d
```
- Detener y eliminar todos los contenedores, redes y volúmenes creados por up:
```shell
docker-compose down
```
- Ver el estado de los servicios:
```shell
docker-compose ps
```
- Reiniciar uno o varios servicios:
```shell
docker-compose restart [servicio]
```
- Ver los logs de todos los servicios:
```shell
docker-compose logs
```
- Ver los logs de un servicio específico:
```shell
docker-compose logs [servicio]
```
- Construir o reconstruir los servicios definidos:
```shell
docker-compose build
```
## Docker Swagger.
## Docker Swagger

Docker Swagger no es una herramienta oficial de Docker, pero comúnmente se refiere al uso de Swagger (ahora conocido como OpenAPI) en contenedores Docker para documentar, probar y diseñar APIs RESTful. Swagger es un conjunto de herramientas que facilita la creación y visualización de documentación interactiva para APIs. Al ejecutarlo en Docker, se puede desplegar rápidamente un entorno para gestionar y probar APIs sin necesidad de instalación local compleja.

### Características principales:
- Proporciona una interfaz web interactiva para visualizar y probar APIs REST.
- Facilita la generación automática de documentación a partir de especificaciones OpenAPI.
- Permite diseñar y simular APIs en entornos controlados.
- Se puede desplegar fácilmente en contenedores Docker para entornos portables y consistentes.
- Compatible con múltiples lenguajes y frameworks para APIs.

### Comandos básicos para usar Swagger con Docker

- Descargar la imagen oficial de Swagger UI:
  ```shell
  docker pull swaggerapi/swagger-ui
    ```

- Permite diseñar y simular APIs en entornos controlados.
- Se puede desplegar fácilmente en contenedores Docker para entornos portables y consistentes.
- Compatible con múltiples lenguajes y frameworks para APIs.

### Comandos básicos para usar Swagger con Docker

- Descargar la imagen oficial de Swagger UI:
  ```shell
  docker pull swaggerapi/swagger-ui

- Ejecutar Swagger UI en un contenedor Docker (por ejemplo, montando un archivo de especificación OpenAPI local):
    ```shell
    docker run -p 8080:8080 -e SWAGGER_JSON=/foo/swagger.yaml -v /ruta/local/swagger.yaml:/foo/swagger.yaml swaggerapi/swagger-ui
    ```
- Ejecutar Swagger Editor para editar archivos OpenAPI en un contenedor:
    ```shell
    docker run -p 8080:8080 swaggerapi/swagger-editor
    ```
- Ver los contenedores en ejecución (para confirmar que Swagger está corriendo):
    ```shell
    docker ps
    ```
- Detener el contenedor de Swagger UI o Editor:
     ```shell   
    docker stop [nombre o ID]
    ```
- Eliminar el contenedor:
    ```shell 
     docker rm [nombre o ID]
    ```

# Procedimiento de Instalación de Visual Studio Code

### 1. Descargar Visual Studio Code

1. Abrir un navegador web (por ejemplo, Google Chrome, Microsoft Edge, Mozilla Firefox).
2. Acceder al sitio oficial de Visual Studio Code:  
<img src="./imagenes/Screenshot 2025-06-10 at 14-00-53 Visual Studio Code - Code Editing. Redefined.png" alt="Prueba local" width="500"/>

   `https://code.visualstudio.com/`
3. En la página principal, hacer clic en el botón **“Download for Windows”** para iniciar la descarga del instalador correspondiente.
<img src="./imagenes/Captura de pantalla 2025-06-10 140144.png" alt="Prueba local" width="500"/>


### 2. Ejecutar el instalador

1. Localizar el archivo descargado en la carpeta predeterminada de descargas del sistema operativo (normalmente `Descargas`).
    <img src="./imagenes/Captura de pantalla 2025-06-10 140320.png" alt="Prueba local" width="500"/>

2. Hacer doble clic sobre el archivo de instalación (`VSCodeSetup-x64-*.exe`) para iniciar el asistente de instalación.
<img src="./imagenes/Captura de pantalla 2025-06-10 140554.png" alt="Prueba local" width="500"/>

### 3. Inicio del asistente de instalación

1. En la ventana del instalador, leer y aceptar el acuerdo de licencia marcando la casilla “I accept the agreement”.
2. Hacer clic en el botón **siguiente** para continuar.
<img src="./imagenes/Captura de pantalla 2025-06-10 140630.png" alt="Prueba local" width="500"/>


### 4. Selección de directorio de instalación

1. Confirmar o modificar la carpeta de destino donde se instalará Visual Studio Code.  
   Por defecto: `C:\Program Files\Microsoft VS Code`.
2. Hacer clic en **siguiente** para avanzar.



### 5. Instalación

1. Confirmar las opciones seleccionadas.
2. Presionar el botón **Install** para comenzar la instalación.
3. Esperar a que finalice el proceso.
<img src="./imagenes/Captura de pantalla 2025-06-10 140820.png" alt="Prueba local" width="500"/>


### 6. Finalización

1. Dejar marcada la opción **Launch Visual Studio Code** para abrir la aplicación al terminar.
2. Hacer clic en **Finish** para cerrar el asistente de instalación.
<img src="./imagenes/Captura de pantalla 2025-06-10 140849.png" alt="Prueba local" width="500"/>

## 7. Verificación
1. Visual Studio Code debe abrirse automáticamente.
<img src="./imagenes/Captura de pantalla 2025-06-10 140955.png" alt="Prueba local" width="500"/>

# Procedimiento de Instalación y Configuración de Git

## 1. Descargar Git

1. Abrir un navegador web.
2. Ir al sitio oficial de Git:  
    https://git-scm.com/
    <img src="./imagenes/Captura de pantalla 2025-06-10 184145.png" alt="Prueba local" width="500"/>
3. Hacer clic en **Download for Windows**.
    <img src="./imagenes/Captura de pantalla 2025-06-10 184307.png" alt="Prueba local" width="500"/>
4. Esperar a que se descargue el instalador.

    <img src="./imagenes/Captura de pantalla 2025-06-10 184815.png" alt="Prueba local" width="500"/>

## 2. Instalar Git

1. Ejecutar el instalador descargado (`Git-*-64-bit.exe`).
     <img src="./imagenes/Captura de pantalla 2025-06-10 185026.png" alt="Prueba local" width="500"/>
2. En el asistente de instalación, aceptar los valores por defecto a menos que se tenga una configuración específica.


     <img src="./imagenes/Captura de pantalla 2025-06-10 190356.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 190406.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 190413.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 190420.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 190432.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 190536.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 191259.png" alt="Prueba local" width="500"/>

     <img src="./imagenes/Captura de pantalla 2025-06-10 191307.png" alt="Prueba local" width="500"/>

    <img src="./imagenes/Captura de pantalla 2025-06-10 191347.png" alt="Prueba local" width="500"/>

    <img src="./imagenes/Captura de pantalla 2025-06-10 191358.png" alt="Prueba local" width="500"/>

    <img src="./imagenes/Captura de pantalla 2025-06-10 191405.png" alt="Prueba local" width="500"/>

    <img src="./imagenes/Captura de pantalla 2025-06-10 191414.png" alt="Prueba local" width="500"/>


3. solo se hace una exepción en esta parte se selecciona la 3ra opción


    <img src="./imagenes/Captura de pantalla 2025-06-10 190521.png" alt="Prueba local" width="500"/>
4. Hacer clic en **Install** y esperar a que finalice.

  <img src="./imagenes/Captura de pantalla 2025-06-10 191420.png" alt="Prueba local" width="500"/>


<img src="./imagenes/Captura de pantalla 2025-06-10 191427.png" alt="Prueba local" width="500"/>

5. Al terminar, hacer clic en **Finish**.

<img src="./imagenes/Captura de pantalla 2025-06-10 192716.png" alt="Prueba local" width="500"/>



Durante el desarrollo de la Unidad I, se llevó a cabo la automatización de infraestructura digital empleando herramientas esenciales como Docker Engine, Docker Compose y Docker Swagger. Estas tecnologías permitieron crear entornos portables y automatizados, fundamentales para la administración moderna de sistemas. Docker Engine se utilizó como motor principal para crear contenedores, mientras que Docker Compose facilitó la definición y ejecución de servicios en múltiples contenedores mediante archivos .yml. Por su parte, Docker Swagger se exploró como herramienta de documentación y diseño de APIs, integrándose al ecosistema Docker.

El procedimiento de instalación inició con la configuración del entorno de trabajo en VSCode, agregando plugins útiles como el de Docker, YAML y Git. Posteriormente, se realizó la instalación técnica de Docker, siguiendo los pasos oficiales para sistemas Linux, asegurando el correcto funcionamiento del servicio. También se instaló Git, herramienta indispensable para la gestión de versiones y colaboración en el desarrollo.

Para verificar el funcionamiento de las herramientas, se ejecutó con éxito la imagen oficial “hello-world”, lo que confirmó que Docker estaba correctamente instalado y funcionando. Además, se creó un archivo docker-compose.yml básico para levantar un contenedor de prueba, evidenciando la correcta ejecución de servicios definidos por archivos YAML.

En conjunto, esta unidad permitió comprender a fondo los principios de la automatización de entornos de desarrollo e infraestructura, destacando la importancia de las herramientas mencionadas y consolidando habilidades prácticas para su implementación efectiva en contextos reales.







## 3. Verificar la instalación

Abrir la terminal o el símbolo del sistema (cmd) y escribir:

```shell
git --version

```
<img src="./imagenes/Captura de pantalla 2025-06-10 193045.png" alt="Prueba local" width="900"/>

## 4. Configuración de Git

Una vez instalado Git, es necesario configurarlo para poder utilizarlo correctamente con tus proyectos y servicios como GitHub.


1. Inicializar Git en tu proyecto
    ```shell
    git init
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203114.png" alt="Prueba local" width="900"/>
2. Cambiar el nombre de las ramas
    ```shell 
    git branch -m master main
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203352.png" alt="Prueba local" width="900"/>
3. Agregar todos los archivos al área de preparación
    ```shell
    git add .
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203600.png" alt="Prueba local" width="900"/>
4. Realizar un primer commit:
    ```shell
    git commit -m "Primer commit"
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203648.png" alt="Prueba local" width="900"/>
5. Este será el nombre que aparecerá en los commits de todos los repositorios del sistema.

    ```shell
    git config --global user.name "José Manuel Gutiérrez Pérez"
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203728.png" alt="Prueba local" width="900"/>
6. Configurar el correo electrónico global: Este correo debe coincidir con el que usas en tu cuenta de GitHub.
    ```shell
    git config --global user.email "josemanuelperez02082004@gmail.com"
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 203855.png" alt="Prueba local" width="900"/>
7.  Verificar la configuración actual: Puedes revisar que los datos se hayan configurado correctamente con el siguiente comando:

    ```shell
    git config --list
    ```
<img src="./imagenes/Captura de pantalla 2025-06-10 203931.png" alt="Prueba local" width="900"/>
8.  Ver historial de commits

```shell
    git log
```
<img src="./imagenes/Captura de pantalla 2025-06-10 204011.png" alt="Prueba local" width="900"/>
    
    
9.   Generar una clave SSH para autenticación con GitHub pero actualmente cuenta con una asi que no agrege otra 
```shell
    ssh-keygen -t ed25519 -C      "josemanuelperez02082004@gmail.com"
```
<img src="./imagenes/Captura de pantalla 2025-06-10 204206.png" alt="Prueba local" width="900"/>

10. Obtener la clave pública generada
    ```shell
    cat C:\Users\josem\.ssh\id_ed25519.pub
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 204257.png" alt="Prueba local" width="900"/>
11. Agregar la clave SSH a tu cuenta de GitHub 

    *  Iniciar sesión en https://github.com.
    <img src="./imagenes/Captura de pantalla 2025-06-10 204332.png" alt="Prueba local" width="900"/>

    * Ir a Settings > SSH and GPG keys.
    <img src="./imagenes/Captura de pantalla 2025-06-10 204501.png" alt="Prueba local" width="900"/>
    *  Hacer clic en New SSH key.
    * Pegar la clave pública generada.
    * Asignar un nombre a la clave ("instrumento") y guardar
    <img src="./imagenes/Captura de pantalla 2025-06-10 211214.png" alt="Prueba local" width="900"/>

12. Agregar el repositorio remoto(marca error ya que ya existe uno ):
    ```shell
    git remote add origin git@github.com
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 211406.png" alt="Prueba local" width="900"/>
13. Renombrar la rama principal: Git por defecto crea una rama llamada master, pero GitHub ahora utiliza main como estándar.
    ```shell
    git branch -M main
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 211421.png" alt="Prueba local" width="900"/>
14. Subir el contenido del repositorio(marca error ya que ya existe uno):
    ```shell
    git push -u origin main
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 211447.png" alt="Prueba local" width="900"/>

# Instalación y configuración de dockerfile 
## 1. Configurar el repositorio oficial de Docker
1. Actualizar el índice de paquetes e instalar dependencias:
    ```shell
        sudo apt-get update 
        sudo apt-get install ca-certificates curl
    ```
<img src="./imagenes/Captura de pantalla 2025-06-10 221752.png" alt="Prueba local" width="500"/>

2.  Añadir la clave GPG oficial de Docker:
    ```shell
    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 221933.png" alt="Prueba local" width="500"/>
    


3. Agregar el repositorio Docker al sistema:
    ```shell
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 222018.png" alt="Prueba local" width="500"/>

## 2. Instalar Docker Engine
```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
 ```
<img src="./imagenes/Captura de pantalla 2025-06-10 222126.png" alt="Prueba local" width="500"/>

## 3. Post-instalación
1. Crear el grupo docker si no existe:
    ```shell
    sudo groupadd docker
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 222204.png" alt="Prueba local" width="500"/>
2. Añadir a tu usuario al docker grupo.
    ```shell
    sudo usermod -aG docker $USER
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 222238.png" alt="Prueba local" width="500"/>
3. También puede ejecutar el siguiente comando para activar los cambios en los grupos:
    ```shell
    newgrp docker
    ```
    <img src="./imagenes/Captura de pantalla 2025-06-10 222306.png" alt="Prueba local" width="500"/>
# Ejecutar la imagen “hello-world” para verificar el funcionamiento de docker
```shell
    sudo docker run hello-world
```
# Ejecutar un archivo “.YML” para verificar el funcionamiento de contenedores
## Ejecutar un archivo PHP con Docker Compose
---

1. Estructura del proyecto

```bash
.
├── docker-compose.yml
└── html
    └── index.php

```
2. Contenido del archivo docker-compose.yml
```ymal
services:
  web:
    image: php:8.2-apache      
    ports:
      - "8080:80"              
    volumes:
      - ./html:/var/www/html 

```
3. Contenido de index.php
```php
   <?php
echo "<!DOCTYPE html>
<html lang='es'>
<head>
  <meta charset='UTF-8'>
  <title>Página PHP Docker</title>
</head>
<body>
  <h1>¡Hola desde PHP en Docker!</h1>
  <p>Esta página se sirve con <strong>php:8.2-apache</strong> via Docker Compose.</p>
</body>
</html>";
?>

```
4. Ejecutar los servicios
```shell
docker compose up
```
 <img src="./imagenes/Captura de pantalla 2025-06-10 232407.png" alt="Prueba local" width="500"/>
5. Verificar funcionamiento
Abre tu navegador en:
http://localhost:8080
<img src="./imagenes/Captura de pantalla 2025-06-10 233945.png" alt="Prueba local" width="500"/>

# Conclución
Durante el desarrollo de esta actividad  se llevaron a cabo diversas actividades enfocadas en la automatización de infraestructura digital. Se comenzó con la instalación de las herramientas necesarias para el entorno de trabajo, incluyendo Visual Studio Code, sus plugins, Git y Docker. Posteriormente, se instalaron y configuraron las herramientas principales: Docker Engine, Docker Compose y Docker Swagger.

Una vez completadas las instalaciones, se realizaron pruebas para verificar el correcto funcionamiento de las herramientas. Se ejecutó la imagen “hello-world” como prueba inicial para comprobar que Docker estaba instalado y funcionando correctamente. También se ejecutó un archivo con extensión “.YML” para verificar el funcionamiento de los contenedores mediante Docker Compose.

Estas actividades permitieron preparar y validar el entorno necesario para trabajar con automatización de infraestructura, logrando cumplir con los objetivos establecidos de este trabajo.

## bibliografias
* Docker, Inc. (2024). Install Docker Engine on Ubuntu. Docker Docs. https://docs.docker.com/engine/install/ubuntu/
* GitHub, Inc. (2024). GitHub. https://github.com
* Git-scm contributors. (2024). Git - Downloading Package. https://git-scm.com/
* Microsoft Corporation. (2024). Visual Studio Code. https://code.visualstudio.com/