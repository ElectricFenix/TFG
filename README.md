# TFG

# Trabajo de Fin de Grado: Sistema de Control de Acceso con Raspberry Pi y NFC

## Descripción general

Este Trabajo de Fin de Grado tiene como propósito el desarrollo de un sistema de control de acceso basado en la Raspberry Pi 4 y la tecnología NFC (Near Field Communication), utilizando el módulo PN532 como lector NFC.

El objetivo principal del proyecto es:

- Garantizar la identificación de usuarios mediante tarjetas NFC.
- Gestionar y registrar los accesos de manera segura.
- Ofrecer una solución cómoda y eficiente para la visualización de los accesos mediante una aplicación web intuitiva y segura.

La aplicación web también incluye una interfaz de administración, donde los usuarios administradores pueden registrar nuevos usuarios de forma sencilla, facilitando así la gestión del sistema.

## Estructura del proyecto

A continuación se detalla la estructura de carpetas y archivos relevantes incluidos en el proyecto:

### /gaiteapp
Contiene todos los archivos de la aplicación web:
- Backend y frontend de la interfaz de administración.
- Lógica de visualización y gestión de accesos.
- Requiere `requirements.txt` para instalar las dependencias necesarias.

### /dnsmasq
Contiene el archivo de configuración del servidor DNS:
- `dnsmasq.conf`: Configura el acceso local a la aplicación desde otros dispositivos de la red.

### /nginx
Incluye configuraciones para el servidor web inverso:
- `gaiteapp.txt`: Archivo de configuración para el servidor Nginx.

### /Pruebas Modulos
Contiene scripts para probar el hardware del sistema:
- `nfc.py`: Prueba básica de lectura de tarjetas NFC con el módulo PN532.
- `prueba_leds.py`: Prueba de funcionamiento de los LEDs.

### /systemd
Contiene archivos de configuración de servicios del sistema (systemd):
- `gunicorn.service`: Servicio para ejecutar el backend de la aplicación con Gunicorn.
- `nfc_reader.service`: Servicio para ejecutar el lector NFC al iniciar el sistema.

### /nfc/script_nfc.py
Script principal que gestiona la lectura de tarjetas NFC y la comunicación con el backend.

## Requisitos

Cada carpeta relevante contiene su propio archivo `requirements.txt` para instalar las dependencias necesarias. Para instalarlas, ejecutar:

- pip install -r requirements.txt


## Cómo ejecutar el sistema

1. Instalar todas las dependencias necesarias utilizando los archivos `requirements.txt`.
2. Asegurarse de que `dnsmasq` y `nginx` estén correctamente configurados y habilitados.
3. Configurar los servicios en systemd (`gunicorn.service` y `nfc_reader.service`) para que se inicien automáticamente al arrancar el sistema.
4. Acceder a la aplicación web desde otro dispositivo a través del navegador.

## Autor

José Manuel Romeral 
Grado en Administración de Sistemas Informaticos y Redes 
IES Carmén Martín Gaite – 2025

