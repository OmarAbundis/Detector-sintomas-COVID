# Detector-sintomas-COVID
## Introducción

Como parte de las actividades de aprendizaje del taller de IoT, se ha solicitado realizar una aplicación que sirva de apoyo, en la detección de los sintomas más frecuentes que se presentan en las personas al manifestarse contagio del virus del COVID-19, las cuales son: nivel de oxigenación, pulso cardíaco y temperatura corporal.

Para su realización práctica primeramente se arma un circuito electrónico capaz de detectar y procesar las variables indicadas, después se intercomunicarán los datos obtenidos usando el protocolo MQTT, luego se mostrán los valores de manera gráfica usando un CANVAS en NodeRed, se notificará en caso del alto riesgo por correo electrónico al solicitante y se almacenarán los datos en una base de datos.

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

## Instrucciones para la realización de la práctica

Para una experimentación satisfactoria es necesario cumplir lo siguiente:

1. Realizar el armado del circuito mostrado en la figura 1.

**Figura 1.** *Circuito electrónico*
![](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/Figuras/CTO_ESP32CAM_FTDI_MAX30100_MLX90614.png)

2. Cargar el [programa](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/ESP32CAM/ESPCAM-MQTT-MLX90614-MAX30100-JSON/ESPCAM-MQTT-MLX90614-MAX30100-JSON.ino) de control que permite la detección, procesado y tranformación de las variables a **JSON**, para que sean enviadas a través **MQTT** al flow en NodeRed.

3. Armar y configurar cada uno de los elementos que integran al flow. Ver figura 2.

**Figura 2.** *Flow de control.*
![](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/Figuras/Flow%20Detector%20sintomas%20COVID.PNG)

4. Ya seleccionado el *dashboard*, se introducen los datos solicitados correo electrónico y nombre del paciente, posteriormente se toman las medidas de la temperatura, oxigenación y pulsos por minuto, cabe destacar que se debe de tener mucho cuidado de la colocación de los sensores en el paciente, porque de lo contrario, se obtendrán mediciones incorrectas.

## Instrucciones de operación

Los pasos que se deben de serguir para la adquisición de los valores de la forma más correcta posible son los siguientes:

- Abrir el dashboard creado para interactuar con el circuito elecrónico, desde la computadora en que se ejecuta NodeRed.
- Introducir el nombre y correo electrónico del paciente.
- Colocar el dedo índice sobre el sensor MLX90614 y el sensor de temperatura MAX30100.
- Esperar a que el sistema tome las mediciones, entre 30 y 60 segundos.
- Presionar el botón **REALIZAR DIAGNÓSTICO**.


## Resultados

En la figura 3, se muestra el dashboard realizado para interactuar con el circuito electrónico.

**Figura 3.** *Dashboard para tomar medidas.*

![](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/Figuras/Dashboard.PNG)

En la figura 4, se muestra el respaldo de los datos en MySQL, del paciente.

**Figura 4.** *Datos en MySQL.*

![](https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/Figuras/SELECT%20FROM%20registro.PNG)


## Evidencia

En el siguiente enlace se puede ver el vídeo de su funcionamiento en YouTube.



## Preguntas frecuentes

**¿Por qué no se conecta el ESP32CAM a la red por WiFi?**
 - **R:** Verificar que en el programa de control hayas colocado correctamente el SSID y la contraseña de tu router.
 - **R:** Verificar que tú red tenga una conexión AES-WPA2.
 - **R:** El ESP32CAM debe de estar en un rango de no más de tres metros al router y no debe de haber piezas metálicas cercanas.

**¿Por qué no se pueden observar en el dashboar la información de los sensores?**

  - **R:** Verifivar que se hayan escrito los mismos temas en los suscriptores y en los publicadores tanto en el flow como en el programa.
  - **R:** Asegurarse de tener una regla que permita conexiones con el puerto 1883 y tener correctamente configurado el archivo **mosquitto.conf**.
  - **R:** Asegurarse que se tenga la IP más reciente del broker público, ya que cambia con frecuencia.
  - **R:** Esperar entre 30 y 60 segundos para que el senso MAX30100 realice las primeras 100 lecturas.

## Créditos

Al profesor Hugo Vargas, instructor del curso de IoT.
