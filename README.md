# MyTasks 📝
By Micaela Gordillo 🌸

MyTasks es un gestor de tareas desarrollado utilizando el framework serverless y las tecnologías de la nube de Amazon Web Services (AWS). Se utilizó el Serverless Framework para crear y desplegar fácilmente los AWS Lambda, la base de datos DynamoDB y la API Gateway necesarios para la funcionalidad del gestor de tareas. El frontend está desarrollado con el framework Angular, proporcionando una interfaz intuitiva para que los usuarios puedan crear, actualizar y eliminar tareas de manera eficiente.
## Tecnologías utilizadas
- AWS Lambda: Servicio de computación sin servidor que permite ejecutar código sin aprovisionar ni administrar servidores.
- DynamoDB: Base de datos NoSQL altamente escalable de Amazon Web Services (AWS).
- AWS API Gateway: Servicio que facilita la creación, publicación, mantenimiento, monitoreo y protección de APIs.
- Serverless Framework: Framework open source que simplifica el desarrollo, despliegue y administración de aplicaciones serverless.
- Angular: Framework de desarrollo de aplicaciones web de código abierto desarrollado por Google.
## Instalación y configuración
### Configuración del entorno de desarrollo para Angular
Antes de poder ejecutar el proyecto Angular, asegúrate de tener lo siguiente instalado en tu computadora:
- Node.js y npm (Node Package Manager): Puedes descargar e instalar Node.js desde nodejs.org.
- Angular CLI: Instala el Angular Command Line Interface (CLI) globalmente mediante el siguiente comando en la terminal: npm install -g @angular/cli
### Configuración del entorno de desarrollo para Serverless Framework
Para ejecutar el proyecto utilizando el framework serverless, necesitarás lo siguiente:
- Node.js y npm: Asegúrate de tener Node.js y npm instalados en tu computadora.
- Serverless Framework: Instala el Serverless Framework globalmente mediante el siguiente comando en la terminal:
```shell
npm install -g serverless
```
### Clonar el repositorio
Para obtener el código fuente de MyTasks, puedes clonar este repositorio utilizando el siguiente comando:
```shell
git clone <URL_DEL_REPOSITORIO>
```
Reemplaza <URL_DEL_REPOSITORIO> con la URL del repositorio de tu proyecto en GitHub. Esto creará una copia local del proyecto en tu computadora.
### Instalar las dependencias del proyecto
Una vez que hayas clonado el repositorio, navega hasta la carpeta del proyecto en tu terminal. Normalmente, esto se haría con el comando cd seguido del nombre de la carpeta del proyecto.
Una vez que te encuentres dentro de la carpeta del proyecto, ejecuta el siguiente comando para instalar las dependencias:
```shell
npm install
```
Esto instalará todas las dependencias especificadas en el archivo package.json del proyecto.
### Configurar las credenciales de AWS
Para utilizar los servicios de AWS, necesitarás configurar las credenciales de acceso. Puedes seguir estos pasos:
- Inicia sesión en la Consola de AWS utilizando tu cuenta de AWS.
- Navega hasta la sección de IAM (Identity and Access Management).
- Crea un nuevo usuario IAM o utiliza uno existente. Asegúrate de que el usuario tenga los permisos necesarios para acceder a los servicios que utilizarás en tu proyecto, como AWS Lambda, DynamoDB y API Gateway.
- Genera las credenciales de acceso para el usuario IAM. Obtendrás una clave de acceso (Access Key ID) y una clave de acceso secreta (Secret Access Key).
- Configura las credenciales en tu entorno local. Puedes hacer esto de varias formas, pero una forma común es utilizando el AWS CLI (Command Line Interface) en tu terminal. Ejecuta el siguiente comando y reemplaza <ACCESS_KEY> y <SECRET_KEY> con tus propias credenciales:
```shell
aws configure
```
- Se te solicitará ingresar el Access Key ID y Secret Access Key. También puedes especificar la región predeterminada y el formato de salida preferido.
- Una vez configuradas las credenciales de AWS, podrás utilizar los servicios de AWS en tu proyecto sin problemas.
### Ejecución del Backend con Serverless Framework
Asegúrate de estar en la carpeta raíz de tu proyecto (donde se encuentra el archivo serverless.yml).

Ejecuta el siguiente comando en tu terminal para desplegar el backend en AWS Lambda y API Gateway: 
```shell
serverless deploy --verbose
```
Esto desplegará tu aplicación backend en AWS utilizando la configuración definida en el archivo serverless.yml. Verás los logs y recibirás la URL de la API generada una vez que el despliegue se complete.
### Ejecución del Frontend con Angular
Navega hasta la carpeta del proyecto frontend en tu terminal. Normalmente, esto se haría con el comando cd seguido del nombre de la carpeta del proyecto frontend.

Ejecuta el siguiente comando para iniciar la aplicación Angular en modo de desarrollo: 
```shell
ng serve
```
Esto iniciará el servidor de desarrollo de Angular y comenzará a compilar y ejecutar la aplicación en tu máquina local.
Abre un navegador web y navega a http://localhost:4200 para ver y utilizar la aplicación frontend.
## Funcionamiento
1. Desde la aplicación Angular, los usuarios interactúan con la interfaz de usuario para realizar acciones como crear una nueva tarea, actualizar una tarea existente o eliminar una tarea.
2. Cuando se realiza una acción, la aplicación Angular se conecta al API Gateway, que se ha configurado previamente.
3. El API Gateway actúa como un punto de entrada y enruta la solicitud al AWS Lambda correspondiente. Dependiendo de la acción requerida (crear, actualizar o eliminar), se invocará una función Lambda específica.
4. El AWS Lambda ejecuta la función correspondiente a la acción solicitada. Por ejemplo, si se solicita crear una nueva tarea, se ejecutará la función Lambda de creación.
5. La función Lambda procesa la solicitud y actualiza los datos en la base de datos DynamoDB. Si es necesario, puede realizar validaciones adicionales o ejecutar otras operaciones lógicas antes de actualizar los datos.
6. Una vez que los datos se han actualizado en DynamoDB, el AWS Lambda devuelve una respuesta al API Gateway, indicando el resultado de la operación.
7. El API Gateway reenvía la respuesta al frontend de la aplicación Angular, donde se muestran los cambios realizados en la interfaz de usuario.

<p align="center">
  <img src="https://github.com/Arquitectura-de-Software-01-2023/mytasks/assets/88464906/d15b4aa1-7410-49b5-ae60-4fd429fa6824" alt="Diagrama" width="700">
</p>
<p align="center">
  <img src="https://github.com/Arquitectura-de-Software-01-2023/mytasks/assets/88464906/b03dcac0-736c-4788-8fa4-7f12703be6db" alt="Diagrama" width="450">
</p>
