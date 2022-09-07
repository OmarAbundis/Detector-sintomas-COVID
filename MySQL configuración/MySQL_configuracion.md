# Configuración de MySQL en terminal de Ubuntu

1. Instalar mysql server
+ `sudo apt update`
+ `sudo apt install mysql-server`

2. Entrar a mysql con la instrucción:
   
   `sudo mysql`

3. Crear una nueva base de datos
   
    `CREATE DATABASE DetectorSintomas;`

4. Seleccionar base de datos 
   
    `use DetectorSintomas;`

5. Crear una tabla llamada **registro** que contenga todos los campos necesarios
    
    `CREATE TABLE registro (id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, fecha TIMESTAMP DEFAULT CURRENT_TIMESTAMP, nombre CHAR (248) NOT NULL, crreo CHAR (248) NOT NULL, temp FLOAT(4,2) NOT NULL, bpm INT(1) UNSIGNED NOT NULL, sp02 INT(1) UNSIGNED NOT NULL, protodiagnostico CHAR (248) NOT NULL);`

6. Crear un nuevo usuario de MySQL

    `CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON *.* TO 'OmarAb'@'localhost';`


7. Para salir de los comandos de MySQL, usar el comando
   
    `exit;`

Notas

Puedes consultar todas las bases de datos con el comando
    
`show databases;` Ver figura 1.

**Figura 1.** *Muestra de base datos en MySQL.*

!()[https://github.com/OmarAbundis/Detector-sintomas-COVID/blob/main/MySQL%20configuraci%C3%B3n/Show%20databases.PNG]


Puedes consultar las tablas en el interior de una base de datos selecccionada con el comando 
    
`show tables;`

Puedes consultar la forma de la tabla con el comando 

`describe registro;`

Para agregar información a la base de datos con NodeRed se requiere poner en un nodo Function la siguiente información:

msg.topic = "INSERT INTO registro (nombre,correo,temp,bpm,sp02,protodiagnostico) VALUES ('" + global.get ("paciente") + "','" + global.get ("correo") + "'," + global.get ("temp") + "," + global.get ("hr") + "," + global.get ("spo2") + ",'" + global.get("protodiagnostico") + "');"; return msg;

Puedes consultar todos los datos de una tabla con el siguiente comando 

`SELECT * FROM clima;`
