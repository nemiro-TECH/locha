# 6. Selección del Hardware

En esta sección se presenta los parámetros que se usaron para la selección de los dispositivos de transmisión y control que se están utilizando actualmente en el proyecto.

## 6.1 Selección del módulo de radio frecuencia

<img src="imple_pic/RF-selection.svg"  height="650" width="450" align="left"/>

Para la selección del módulo de radio el cual contiene el microcontrolador, la etapa de radio frecuencia y modulación y todo lo necesario para transmitir en la frecuencia de 915 MHz se establecieron algunos parámetros que se consideran importantes, los cuales son:
- Soporte del estándar IEEE 802.15.4.
- Al menos 2 puertos USART.
- De bajo costo.
- Fácil de utilizar.
- Soporte para la banda del Subgigahercio a 915 MHz.

La tabla de la imagen muestra 3 familias de micrcontroladores con interface de radio frecuencia con los cuales se aplicaron los criterios basados en la necesidad actual y se eligio el ```cc1312r1``` como el modulo mas económico, robusto,con un amplio rango de cobertura y de muy bajo consumo para desempeñar la tarea que el ```turpial``` requiere como dispositivo transceptor.

La familia de microcontroladores ```cc135x``` también es un dispositivo que cumple con la mayoría de requerimientos, provee más funciones de las que se necesitan, así que fue descartado, su precio también es elevado en consecuencia.

<br>
<br>

## 6.2 Selección de la fuente de voltaje

En esta sección se muestran algunas opciones a la hora de seleccionar el dispositivo que se encarga de regular la corriente proveniente de la batería y que provee la corriente necesaria al Turpial, para funcionar de una manera óptima, libre de ruidos y bajas de corriente que puedan afectar el funcionamiento del sistema en su totalidad.

<br>
<img src="imple_pic/powerSupply-selection.svg"  height="650" width="450" align="left"/>

Los parámetros más importantes a tener en cuenta a la hora de seleccionar el dispositvo que alimenta al circuito tenemos:
- Corriente: La corriente del circuito debe ser mayor o igual a 2 Amperios.
- Voltaje: El dispositivo seleccionado debe ser capaz de entregar un voltaje estable de salida de 3.3 Voltios, sin importar que la entrada que lo alimenta este por encima o por debajo del umbral requerido.
- ALta eficiencia: El dispositivo seleccionado debe ser eficiente en la transformación de la energía, lo que se traduce en libre de sobre calentamientos extremos.
- Ruido: Este parámetro es muy importante debido a que cualquier ruido en la señal de salida de voltaje, puede afectar todo el sistema.

Al realizar la ponderación de los diferentes dispositivos se observa que el ```LTC3113``` tiene muy buenas prestaciones, es full bridge y entrega corrientes por encima de los 2.5 Amperios, pero se ha decidido utilizar el ```TPS63802``` dada su amplia disponibilidad, precio económico y provee las prestaciones requeridas para cumplir los objetivos del proyecto; en cuanto al ```LTC3113```, es de muy buenas prestaciones pero su costo es realmente elevado para utilizarlo en este proyecto.

<br>
<br>
<br>

## 6.3 Selección del cargador de batería

<img src="imple_pic/BatteryChargerSelection.svg"  height="450" width="450" align="left"/>
<br>

Para la selección del chip encargado de cargar la batería de litio, existen diversas familias de integrados que tienen muy buenas prestaciones y precios accesibles, hemos decidido utilizar el chip de la familia ```BQ2407x```, el cual es de fácil adquisicion y se ajusta a los requerimientos de carga lineal y durabilidad en las baterías, el cual es el objetivo principal al tener un sistema de carga robusto, como el que se presenta en el diseño del Turpial.

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

## 6.4 Selección del control de energía de la batería

<img src="imple_pic/BatteryManagementSystem-selection.svg"  height="450" width="550" align="left"/>

El control de energía, es el sistema que se encarga de leer variables relacionadas con la batería, como energía disponible, tiempo de carga, corriente suministrada, etc.

A la hora de seleccionar el dispositivo que se encargará de dicha tarea, se tiene un requerimiento importante y es que tenga soporte para I2C, en la tabla se pueden apreciar dos diferentes dispositivos de dos fabricantes diferentes, los cuales tienen prestaciones similares, pero difieren mucho del costo por unidad, así que se utiliza el BQ27441-G1 como dispositivo para la recolección de datos relacionados con la batería, para ser enviada a la unidad principal de control. 

<br>
<br>

## 6.5 Selección del microcontrolador (Interface)

Para la seleccion del microcontrolador, existen una serie de requisitos que actualmente muchas familias de microcontroladores podría satisfacer, nos hemos centrado en la famila de microcontroladores de ```espressif```, debido a que esta es una marca que ofrece una gran variaded de dispositivos con increíbles características, como los es Bluetooth y WiFi a muy bajo costo, que difícilmente otra marca podría ofrecer.

Otra de las razones es la cantidad de información y ejemplos que se pueden encontrar en la web para este dispositivo.

Fácilmente se pueden listar algunas de las bondades de la familia ESP32:
- Económico.
- Amplia documentación disponible.
- Comunidad de desarrolladores en continuo crecimiento.
- Ejemplos en la plataforma de Arduino que se pueden portar al entorno de espressif sin mucha dificultad.
- Bajo consumo.
- Incorpora BLE, el cual deja  a la mano un abanico de posibilidades.

Para este trabajo específicamente se trabaja con el ESP32 WROVER, el cual consta de:
- 4Mb Flash SPI.
- 8MB PSRAM.
- Frecuencia de 80Mhz a 240Mhz.
- WiFi.
- BlueTooth.
- USART x3.
- Dual core.
Este dispositivo es perfecto para el diseño del turpial, ya que cuenta con varios puertos USART, para poder comunicarnos con el módulo de radio y el Pc a tráves del USB; También cuenta con un adaptador de red el cual permite implementar un servidor Web, para servir la aplicación de control y configuración del Turpial.

## 6.6 Diagrama en bloques del hardware del Turpial

<img src="imple_pic/Hardware-Block.svg" height="450" width="900" align="center"/>

## 6.7 Diagrama en bloques de la aplicación de control

## 6.8 Visión General del Turpial como dispositivo

<img src="imple_pic/turpial.svg" height="450" width="400" align="center"/>

La figura muestra el primer prototipo en desarrollo aun....
