# RabbitMQ Docker Lab

![Docker](https://img.shields.io/badge/Docker-2496ED?&style=flat&logo=docker&logoColor=ffffff)&nbsp;
![SonarQube](https://img.shields.io/badge/rabbitmq-%23FF6600.svg?&style=flat&logo=rabbitmq&logoColor=white)&nbsp;

Más ejemplos de Badges en [markdown-badges](https://ileriayo.github.io/markdown-badges/), [Badges 4 README.md Profile](https://github.com/alexandresanlim/Badges4-README.md-Profile) y [Awesome Badges](https://github.com/Envoy-VC/awesome-badges)

## Introducción

Este repo se ha creado para complementar los Posts sobre [RabbitMQ](https://elwillie.es/tag/rabbitmq/) del Blog [El Willie - The Geeks invaders](https://elwillie.es/), y comparte un pequeño laboratorio en formato de Docker Compose, con el que podemos arrancar los siguientes componentes:

* **RabbitMQ**, utilizando volúmenes Docker, y escuchando en los puertos por defecto (tcp-5672 y tcp-15672).

De esta forma, podemos arrancar este laboratorio y trastear con RabbitMQ de forma rápida y sencilla gracias a Docker, pero con volúmenes que nos ofrezcan persistencia.

Algunos de los Posts de Sonar en los que se basa este Docker Compose son:

* [RabbitMQ - Introducción e instalación de RabbitMQ]()

**Puedes apoyar mi trabajo siguiéndome, haciendo "☆ Star" en el repo, o nominarme a "GitHub Star"**. Muchas gracias :-) 

[![GitHub Star](https://img.shields.io/badge/GitHub-Nominar_a_star-yellow?style=for-the-badge&logo=github&logoColor=white&labelColor=101010)](https://stars.github.com/nominate/)

En mi Blog personal ([El Willie - The Geeks invaders](https://elwillie.es)) y en mi perfil de GitHub, encontrarás más información sobre mi, y sobre los contenidos de tecnología que comparto con la comunidad.

[![Web](https://img.shields.io/badge/GitHub-ElWillieES-14a1f0?style=for-the-badge&logo=github&logoColor=white&labelColor=101010)](https://github.com/ElWillieES)

# Docker - Ejecución en local con Docker Compose

Lo primero, en la raíz del repo, debemos **editar el fichero .env** donde se establecen variables que podemos utilizar en los contenedores definidos en el Docker Compose, como sería la Zona Horaria. 

Por ejemplo, para usar Madrid deberíamos dejar así la variable TZ en el ficher .env

```shell
TZ=Europe/Madrid
```

Los siguientes comandos ejecutados en la raíz del Proyecto, muestra cómo arrancar todos los contenedores con Docker Compose, como comprobar su estado, así como la forma de poder comprobar los logs de su ejecución.

```shell
docker-compose up -d
docker-compose ps
docker-compose logs
```

Podemos abrir una sesión bash en cualquiera de los contenedores ejecutando con comando como el siguiente:

```shell
docker exec -it rabbitmq-docker-lab-rabbitmq-1 bash
```

En caso necesario, podemos parar (sin eliminar) y volver a arrancar todos los contenedores Docker con los siguientes comandos:

```shell
docker-compose stop
docker-compose start
```

Si deseamos parar y/o arrancar un único contenedor (ej: RabbitMQ), podemos utilizar comandos como los siguientes:

```shell
docker-compose stop rabbitmq
docker-compose start rabbitmq
```

Podemos parar y eliminar todos los contenedores con el siguiente comando:

```shell
docker-compose down
```
