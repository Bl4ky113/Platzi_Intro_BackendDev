# Introducción a el Desarrollo Backend

A aprender:
- Que es un framework o libreria
- Que es el proceso de HTTP?
- Que es un Servidor y que tipos de servidores

Con El TEACHER FACUNDO

## Ying Y el Yang

El frontend y el Backend

El frontend va ser lo principal que el usuario va ver y interactuar, siendo representado por:
- HTML5
- CSS3
- JavaScript
Pero estos representantes tienen diferentes derivados que pueden ser Frameworks o Librerias:

- CSS3
	- Tailwind
	- Bootstrap
	- ...
- JS
	- Angular
	- Vue
	- React
	- Svelte

Pero antes del frontend debe haber un diseño de User Interface y User Experience. Que son hechos por otros departamentos y herramientas.

Mientras que el Backend va a ser lo que va a mantener los servidores, dbs, entre otros. Son representados por casí todos los lenguajes modernos:
- Js
	- Node.js
		- Express.Js
- Java
	- Spring
- PHP
	- Laravel
- Go
- Rust
- Ruby
	- Ruby On Rails
- Python
	- Fast API
	- Flask 
	- Django

## Frame Work VS Librerias. Que son?

La libreria es un código hecho por otra persona que nos ayuda a realizar una actividad ya desarrollada en la comunidad, es decir no volver a 
inventar la rueda.

Mientras que los FrameWorks son la sintetización de estas librerias, código hecho por otras personas, agregandole recomendaciones, estandares y 
reglas en general de cómo usar el FrameWork

## Conectando Frontend con Backend

Estas conexiones se hacen mediante APIs o Aplication Program Interface. Estas tienen dos estandares de funcionamiento. 

- SOAP o Simple Object Access Protocol. 
	- SOAP movia la informacion entre back y front usando XML o Extensible Markup Lenguage. Pero este es casí código legacy y no se 
	usa tan a menudo hoy en día.
- REST o Representacional State Transfer.
	- REST mueve la información entre back y front usando JSON o JavaScript Object Notation. 

Estos estandares pasan la información en diferentes formatos, pero siguen usando el mismo metodo. HTTP.

## HTTP

HTTP HyperText Transfer Protocol. El HTTP funciona en la comunicación entre el cliente y el Servidor. El es el intermediario entre cada 
request del cliente, quiero ver X página web, y cada response del servidor, datos de X página web. 

HTTP tiene una estructura, veamos primero el request.

El request tiene cómo modelo un metodo para obtener o dar datos, siendo metodos de:
- GET
- POST
- PUT
- DELETE
- ...
Este request va a tener especificado la versión de HTTP, ejemplo HTTP/1.1

En este caso estamos haciendo un GET de una página web, estos se llaman headers o cabeceras. Los headers 
tienen la información del metodo del request, en este caso, el host de una dirección URL de developer.mozilla.org. Pero ademas tiene un 
header de el lenguaje que debería darle, frances o fr en este caso.

Despues de recibir el Request, y si no hay ningun error, el servidor nos va a dar la información del response con otros headers:

- Status del request HTTP, con su versión:
	Tiene un código de resultado, en el cual nos va a dar un breve resumen de la conexión:
	1xx: Mensajes de Información
	2xx: Mensaje de Finalizamiento
	3xx: Mensaje de Redirección
	4xx: Mensaje de Error (Cliente)
	5xx: Mensaje de Error (Servidor)

- Date: la fecha
- Server: El Servidor Apache
- Last-Modified: La Ultima Modificación de la información enviada
- ETag: Hash del cache
- Accept-Ranges: Cómo se va a entregar la información, generalmente bytes
- Content-Lenght: Que tanto de lo anterior
- Content-Type: El tipo de archivo del contenido enviado

El protocolo HTTP no es el unico por parte de una página web. Tambien hay otros desde el front y el backend. Siendo de abajo hacia arriba:

- Front:
	- HTML
		Cargar la Información base
	- CSS
		Aplicar Styles
	- Js / Web APIs
		Dar las diferentes funciones y recibir / hacer llamados a APIs para despues hacer uso de la información
- HTTP
	Lo que vimos

- Back
	- DNS 
		Convertir o afiliar la IP a un dominio
	- TLS
		Encriptación de la información
	- TCP / UDP
		Envió de la información
	- IP
		Protocolo que permite que nuestro servidor sea identificable y comunicable

## Flujo de Desarrollo de una App Web

1. Primero vamos a hacer el código, obviamente, usando nuestro editor de texto preferido. 
2. Vamos a tener un registro en commits de nuestro progreso usando un controlador de versiones cómo Git
3. Vamos a tener un browser para probar, ver y desarrollar la App Web
	Todo esto es un entorno local.
4. Despues de tener todo listo, puede haber sido hecho antes, pero vamos a hacer un push a un 
repositorio remoto, cómo GitLab o GitHub.
5. Despues de tener el código en el Repo, vamos a pasarlo a el servidor haciendo un ci / cd. Countinous Integration o Continous Delivery.
	Que hace un testing de tu código para despues pasarlo a Production.
6. Production es el entorno donde el usuario va a poder usar.
7. El servidor para poder ser usado por el usuario, va a guardar el contenido de Production en el sufijo de un dominio. 
	www.Coso.com


## El servidor

Una clase más de Cloud Computting. IaaS, PaaS y SaaS, pero lo bueno es que lo explico desde una perspectiva de programador.

## Diseño de la API del curso

La API del curso va a constar de un CRUD

- Create
- Read
- Update
- Delete

Vamos a usar las tecnologías disponibles de Python:

- FastAPI
- Djando + Rest Framework
- Flask

### Endpoint

El Endpoint, root o path es una URL de nuestro proyecto, en el cual vamos a acceder a nuestra API. 
Y en estos se van a tener diferentes funciones. Generalmente: dominio.me/api/endpoint

#### Endpoints para los Tweets

Estas funciones van a ser dirigidas por las siglas de nuestro CRUD. 

- tweets/: Vamos a hacer una funcion para READ o leer los tweets
- tweets/{tweet-id}: Function para hacer READ pero a un Tweet unico
- post/: Poder CREATE, Crear o postear un tweet
- tweets/{tweet-id}/update: Poder hacer un UPDATE a un tweet
- tweets/{tweet-id}/delete: Poder hacer un DELETE a un tweet

#### Endpoints para los Usuarios

Estas funciones van a ser dirigidas tambien en parte por las siglas de nuestro CRUD

- users/: Mostrar a los usuarios
- signup/: Registrar a los usuarios
- users/{user-id}: Ver un usuario en particular
- users/{user-id}/update: Actualizar info de un usuario
- users/{user-id}/delete: Eliminar a un usuario

## Fin

Sinceramente, pense que iba a haber más contenido, pero bueno...
