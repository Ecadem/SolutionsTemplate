# Crear ambiente de desarrollo Angular

### Requisitos
* **Docker**
    - _En Windows:_ Leer guia de instalación [aqui](https://docs.docker.com/desktop/install/windows-install/)
    - _En linux:_ Leer guia de instalación [aqui](https://docs.docker.com/desktop/install/linux-install/)
    - _En Mac:_ Leer guia de instalación [aqui](https://docs.docker.com/desktop/install/mac-install/)


## Guia de uso
### Levantar ambiente de desarrollo
1. Clonar el repositorio o copiar el `Dockerfile_Desarrollo` dentro de la carpeta del proyacto.
2. Abrir una terminal en el directorio del proyecto
3. Correr los siguientes comandos:
    - ` docker build --build-arg NG_VERSION=14.0.4 --build-arg NODE_VERSION=v14.16.1 -t angular -f .\Dokerfile_Desarrollo . `
    - ` docker run -p 4200:4200 -v ${pwd}/:/ng-app -it angular bash `

#### _Build_

El `build` de la imagen consta de dos argumenos obligatorios:
- `NG_VERSION`: es la versión del Angular CLI que se instalará en la imagen. _Ej: 14.0.4_
- `NODE_VERSION`: es la versión de Nodejs que se instalará  en la imagen. _Ej: v14.16.1_

### Configurar ambiente de desarrollo en VSC
Nuestro entorno de trabajo en VSC debe contar con las dos siguientes extenciones:
1. La extención de [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
2. La extención de [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

### Ahora si...
Despues de asegurarnos que el contenedor este corriendo _(se puede confirmar con un `docker ps`)_. Una vez dentro de VSC en la parte inferior izquierda
![Captura desde 2023-01-21 02-37-14](https://user-images.githubusercontent.com/62354692/213857852-819e2b76-954b-43de-aba3-d564b72b333f.png)

Seleccionar la opción *Attach to running container* y seleccionar el contenedor de *Angular*.
![Captura desde 2023-01-21 02-38-51](https://user-images.githubusercontent.com/62354692/213858149-4b5160c9-9c8d-42f7-9ae2-9f22cea64fcb.png)

Por ultimo, se abrira otra ventana de VSC que estará dentro del entorno de la imagen y podremos programar con todas las dependencias que tenga el contenedor.

![Captura desde 2023-01-21 03-20-39](https://user-images.githubusercontent.com/62354692/213858591-822c20f1-5184-44dc-9a00-728085ff7298.png)

