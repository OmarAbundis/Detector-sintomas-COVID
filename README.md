# Detector-sintomas-COVID
## Introducción

Como parte de las actividades de aprendizaje del taller de IoT, se ha solicitado realizar una aplicación que sirva de apoyo, en la detección de los sintomas más frecuentes que se presentan en las personas al manifestarse contagio del virus del COVID-19, las cuales son: nivel de oxigenación, pulso cardíaco y temperatura corporal.

Para su realización práctica primeramente se arma un circuito electrónico capaz de detectar y procesar las variables indicadas, después se intercomunicaran los datos obtenidos usando el protocolo MQTT, luego se mostran los valores de manera gráfica usando un CANVAS en NodeRed, se notificará en caso del alto riesgo por correo electrónico al solicitante y se almacenarán los datos en una base de datos.

## Material necesario

- [ESP32CAM](https://docs.ai-thinker.com/en/esp32-cam), tarjeta de desarrollo.
- [FTDI](https://microcontrollerslab.com/ftdi-usb-to-serial-converter-cable-use-linux-windows/), trjeta controladora USB.
- [MLX90614](https://www.sparkfun.com/datasheets/Sensors/Temperature/MLX90614_rev001.pdf), sensor de temperatura infrarrojo.
- [MAX30100](https://datasheets.maximintegrated.com/en/ds/MAX30100.pdf), sensor de ritmo cardíaco y porsentaje de oxigenación en la sangre.
- 2 resistores de 10Kohms. (Cáfe, negro, naranja, dorado).
- 1 cable USB a USB mini.
- Jumpers MM.

## Software necesario

En la experimentación de está práctica se debe de contar con el siguiente software libre:

- Ubuntu 20.04
- Arduino IDE
- Mosquitto MQTT Broker, Listener en puerto 1883 para 0.0.0.0 y conexiones autentificadas activadas.
- NodeJS. NPM, NodeRed y Node Dashboard.
- MySQL

## Material de referencia

Previamente a la realización de está práctica, ha sido necesario el estudio de distitos temas, que se encuentran en la plataforma edu.codigoiot.com, en donde se explican conceptos y configuraciones necesarias, tales como:

- Instalación de virtual Box y Ubuntu 20.04
- Configuración de Arduino IDE para ESP32CAM
- Instalación de NodeRed
- Introducción a NodeRed
- Instalación de Mosquitto MQTT

## Servicios

## Instrucciones para la realización de la práctica

Para una experimentación satisfactoria es necesario cumplir lo siguiente:

1. Realizar el armado del circuito mostrado en la figura 1.

**Figura 1.** *Circuito electrónico*
![](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/ESP32CAM/CTO_ESP32CAM_FTDI_MAX30100_MLX90614.png)



## Instrucciones de operación


## Resultados


## Evidencia


## Preguntas frecuentes

## Compatibilidad

## Créditos
