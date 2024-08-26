# Documentación del Proyecto

## Descripción del Proyecto

Este proyecto utiliza un ESP32 para capturar datos de un sensor MAX30102 y un sensor analógico, visualizando la información en una pantalla OLED de 1.3 pulgadas. Los datos se envían a un servidor a través de una conexión HTTP y se almacenan en una base de datos MySQL. La visualización de datos en tiempo real se realiza mediante Grafana.

### Sensores Utilizados

1. **MAX30102**: Sensor de frecuencia cardíaca y oxígeno en sangre.
2. **Sensor Analógico**: Este sensor mide señales fisiológicas que son convertidas a voltaje a través de un circuito con un **convertidor de corriente a voltaje**, un **filtro pasa-bajo**, un **filtro pasa-alto**, y un **amplificador** implementado con el **TL084**. La señal resultante es capturada por el ESP32 a través de un pin analógico.

## Componentes Utilizados

1. **ESP32**: Microcontrolador encargado de la recolección de datos y la comunicación con otros componentes.
2. **MAX30102**: Sensor de frecuencia cardíaca y oxígeno en sangre.
3. **Sensor Analógico con Circuito TL084**: Captura y procesa señales fisiológicas.
4. **Pantalla OLED 1.3 pulgadas**: Pantalla para la visualización de datos en tiempo real.

## Archivos del Proyecto

1. **`Analog_Esp32.ino.ino`**:
   - Ubicación: `code_esp32.ino`
   - Descripción: Archivo de código para el ESP32. Debe ser cargado en el microcontrolador. Asegúrate de ajustar los datos necesarios en el archivo.

2. **`post1.php`**:
   - Ubicación: Carpeta de XAMPP
   - Descripción: Script PHP que se encarga de la conexión con la base de datos y el envío de datos. Debe ser configurado para conectar con la base de datos y manejar las solicitudes HTTP desde el ESP32.

3. **`base_de_datos.sql`**:
   - Ubicación: Archivo de base de datos
   - Descripción: Archivo SQL que contiene el código para la creación de la base de datos y la tabla donde se almacenarán los datos.

## Conexiones de Hardware

1. **Conexión MAX30102 con ESP32**:
   - **SCL** del MAX30102 a **GPIO22** del ESP32
   - **SDA** del MAX30102 a **GPIO21** del ESP32
   - **VCC** del MAX30102 a **3.3V/5V** del ESP32
   - **GND** del MAX30102 a **GND** del ESP32

2. **Conexión Pantalla OLED con ESP32**:
   - **SCL** de la pantalla OLED a **GPIO22** del ESP32
   - **SDA** de la pantalla OLED a **GPIO21** del ESP32
   - **VCC** de la pantalla OLED a **3.3V/5V** del ESP32
   - **GND** de la pantalla OLED a **GND** del ESP32

3. **Conexión Sensor Analógico con ESP32**:
   - **Salida del circuito TL084** al **Pin Analógico (GPIO34)** del ESP32.

## Programas Necesarios

1. **XAMPP**:
   - Descripción: Paquete que incluye Apache, MySQL, y PHP para el desarrollo local.
   - [Descargar XAMPP](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/8.2.12/xampp-windows-x64-8.2.12-0-VS16-installer.exe/download)

2. **Composer**:
   - Descripción: Herramienta para la gestión de dependencias en PHP.
   - [Descargar Composer](https://getcomposer.org/Composer-Setup.exe)

3. **Arduino IDE**:
   - Descripción: Entorno de desarrollo para programar el ESP32.
   - [Descargar Arduino IDE](https://www.arduino.cc/en/software)

4. **Grafana**:
   - Descripción: Plataforma para la visualización y análisis de datos en tiempo real.
   - [Descargar Grafana](https://grafana.com/grafana/download?pg=get&plcmt=selfmanaged-box1-cta1)

## Instrucciones de Configuración

1. **Configurar el ESP32**:
   - Carga el archivo `Analog_Esp32.ino.ino` en el Arduino IDE y ajusta los parámetros según sea necesario.
   - Conecta el ESP32 a tu computadora y carga el código.

2. **Configurar XAMPP**:
   - Instala y configura XAMPP en tu máquina local.
   - Coloca el archivo `post1.php` en la carpeta `htdocs` de XAMPP.

3. **Configurar la Base de Datos**:
   - Importa el archivo `base_de_datos.sql` en tu base de datos MySQL utilizando phpMyAdmin o una herramienta similar.

4. **Configurar Grafana**:
   - Instala y configura Grafana para conectar con tu base de datos y visualizar los datos en tiempo real.

## Ariel Moreta - Adrian Vera
