# Ejecutar playbook de Ansible desde Pipelines de IBM Cloud

En este tutorial usaremos un Playbook Ansible ejecutado desde el servicio IBM Cloud Continuous Delivery para implementar una aplicación PHP de muestra. Crearemos automáticamente un delivery pipeline a partir de una tool chain. Luego usaremos Ansible para desplegarla en Cloud Foundry. Ansible Playbooks se pueden usar para entregar aplicaciones simples, como en este hands-on, así como una infraestructura de aplicaciones compleja.

## Requisitos

- Cuenta en [github](https://github.com)
- Cuenta en [IBM Cloud](https://cloud.ibm.com)
- Conocimientos básicos de php
- Conocimientos básicos de shell scripting

## Setup

Para hacer la instalación del entorno de trabajo del taller, debes realizar los siguientes pasos en tu estación de trabajo:

1. Instalar [PHP](http://php.net/downloads.php). Puedes instalar cualquier versión de PHP 5.X.X. o superior
```
$ php --version
PHP 5.4.16 (cli) (built: Oct 30 2018 19:30:51)
Copyright (c) 1997-2013 The PHP Group
Zend Engine v2.4.0, Copyright (c) 1998-2013 Zend Technologies
```
2. Instalar la [CLI de Cloud Foundry](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html). La versión puede ser 6.X.X o superior
```
cf --version
cf version 6.46.0+29d6257f1.2019-07-09
```
3. Instalar cliente de [git](https://git-scm.com/downloads). Puede usarse la versión 1.8.X.X o superior.
```
$ git --version
git version 1.8.3.1
```
4. Crear un directorio de trabajo en la estación de trabajo. P.e. en Linux ```/home/mcuevas/lab```
5. Clonar este repositorio en el directorio creado en el paso 4
```
$ git clone https://github.com/surasiterix/bluemix-php-sample.git
Cloning into 'bluemix-php-sample'...
remote: Enumerating objects: 74, done.
remote: Total 74 (delta 0), reused 0 (delta 0), pack-reused 74
Unpacking objects: 100% (74/74), done.
```
6. Ahora levantaremos nuestra aplicación web de prueba usando el web server de desarrollo que viene en php. Entremos en el directorio ```bluemix-php-sample``` y ejecutemos el siguiente comando
```
$ php -S localhost:8000
PHP 5.4.16 Development Server started at Wed Aug  7 16:32:53 2019
Listening on http://localhost:8000
Document root is /home/mcuevas/lab/bluemix-php-sample
Press Ctrl-C to quit.
```
7. Desde un browser, accedemos a nuestra aplicación web en http://localhost:8000
8. Creamos nuestro toolchain en IBM Cloud para automatizar el despliegue de nuestra aplicación Web en los servicios de Cloud Foundry.

[![Crear Toolchain](https://console.ng.bluemix.net/devops/graphics/create_toolchain_button.png)](https://console.ng.bluemix.net/devops/setup/deploy/?repository=https://github.com/abgutierrez/bluemix-php-sample)

## Agradecimientos

Este laboratorio fue adaptado del original (https://github.com/IBMCloudDevOps/bluemix-php-sample) para el IBM Code Day 2019 en Montevideo (https://www.ibm.com/events/uy/es/ibm-code-mvd/montevideo/)
