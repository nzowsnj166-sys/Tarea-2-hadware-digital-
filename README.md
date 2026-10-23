# Tarea-2-hadware-digital-
Proyecto completo en C/C++ (Arduino IDE o PlatformIO)  modular, comentado y alojado en repositorio Git. URL  informada en el reporte técnico.


# Theremin Digital sin Contacto con Arduino UNO

## 1. Descripcion del proyecto

Instrumento musical digital que utiliza un sensor ultrasonico HC-SR04
para detectar la distancia de la mano y modificar la frecuencia de
un buzzer pasivo sin necesidad de contacto fisico.

## 2. Componentes

- Arduino UNO R3
- Sensor ultrasonico HC-SR04
- Buzzer pasivo
- 3 pulsadores
- Cables de conexion
- Protoboard

## 3. Tabla de conexiones

| Componente | Pin Arduino |
|---|---|
| Pulsador rango grave | D2 |
| Pulsador rango medio | D3 |
| Pulsador rango agudo | D4 |
| HC-SR04 Echo | D6 |
| HC-SR04 Trigger | D7 |
| Buzzer positivo | D8 |
| VCC del HC-SR04 | 5V |
| GND comun | GND |

Los pulsadores se conectan entre su pin digital y GND,
utilizando INPUT_PULLUP.

## 4. Rangos tonales

- Grave: Do3 a Do4 (131-262 Hz)
- Medio: Do4 a Do5 (262-523 Hz)
- Agudo: Do5 a Do6 (523-1047 Hz)

## 5. Funcionamiento

1. El sensor HC-SR04 mide la distancia de la mano.
2. El programa calcula la distancia en centimetros.
3. Un filtro de promedio movil de cinco muestras ayuda
   a reducir las variaciones de las lecturas.
4. Los pulsadores permiten seleccionar el rango tonal.
5. La funcion map() relaciona la distancia con la frecuencia.
6. La funcion tone() genera el sonido en el buzzer.
7. Fuera del rango de 5 a 30 cm, el buzzer se silencia.

## 6. Tecnicas implementadas

- Lectura del sensor ultrasonico.
- Seleccion de rangos mediante pulsadores.
- Antirrebote por software utilizando millis().
- Filtro de promedio movil.
- Generacion de tonos mediante tone().
- Silencio automatico mediante noTone().

## 7. Archivo principal

El firmware se encuentra en:

theremin_digital.ino

## 8. Placa utilizada

Arduino UNO R3 con microcontrolador ATmega328P.

## 9. Asignatura

Hardware Digital (CIN-212)
Universidad de Valparaiso
Carrera: Ingenieria Civil Informatica
