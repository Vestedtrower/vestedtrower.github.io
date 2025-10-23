# Tutorial mejorado de MicroPython para estudiantes de Mecatrónica
_Versión revisada: 2025-05-27_

Bienbenidos [inicio](/README.md).

# Funciónes y variables con Micropython.
- [Materiales](#materiales)
- [Instalar Thonny](#instalar-thonny)
- [Instalar firmware Micropython en ESP32](#instalar-firmware-micropython-en-esp32)
- [Usar Thonny](#usar-thonny)
- [Conectar el sensor DHT11 a nuestro esp32](#conectar-el-sensor-dht11-a-nuestro-esp32)
- [Bugs](#Bugs)
- [Variables](#variables)
- [Comentarios](#comentarios)
- [Pseudocodigo](#pseudocodigo)
- [Mejorando el programa anterior](#mejorando-el-programa-anterior)
- [Comas](#comas)
- [Cadenas_y_parametros](#cadenas-y-parametros)
- [Modificaciones](#modificaciones)
- [Formato_cadenas](#formato-cadenas)
- [Mas_sobre_cuerdas](#mas-sobre-cuerdas)
- [Numeros_enteros_o_int](#numeros-enteros-o-int)
- [Conceptos_basicos_de_flotacion](#conceptos-basicos-de-flotacion)
- [Mas_sobre_los_flotadores](#mas-sobre-los-flotadores)
- [Definicion](#definicion)
- [Devolviendo valores](#devolviendo-valores)
- [Aplicasion_thonny_con_el_sensor_Dht11](#aplicasion-thonny-con-el-sensor-dht11)
  
## Materiales
La lista de materiales es:
- Sensor DHT11
- Esp32
- Cableado Jumper Electrónica "F - F"
- Cable USB tipo A con entrada para micro puerto tipo B
- Computadora
- Aplicación Thonny 

## Instalar Thonny
Descarga Thonny. Para descargar a Thonny nos dirigimos a la página oficial al apartado de [descargas](https://github.com/thonny/thonny/releases/download/v4.1.6/thonny-4.1.6.exe).
Busca tu archivo descargado y lo ejecutas dandole doble click.
Dale al boton <kbd>Next</kbd> y despues acepta los términos.
![Aceptar términos](./imagen/thony_aceptar_acuerdo.png)

Activa la casilla para que te ponga un icono en el escritorio.
Con esto podrás tener un acceso rápido en tu escritorio.
![Crear icono](./imagen/thony_acceso_directo.png)

Da click en <kbd>Install</kbd> para que inicie el proceso de instalación.
Este proceso puede tomar tiempo, dependerá de el procesador de tu computadora. 

![Iniciar instalación](./imagen/iniciar_instalacion.png)

Para finalizar la instalación hay que dar click en el boton <kbd>Finish</kbd>.
O simplemente puedes cerrar la ventana.
![Finalizar instalacion](./imagen/finalizar_instalacion.png)

## Instalar firmware Micropython en ESP32
Un firmware es el lenguaje que le vamos a instalar a nuestro esp32 para despues poder interpretarlo mediante una interfaz como lo es en nuestro caso la aplicacion de Thonny. 
Descarga firmware. Para descargar firmware Micropython en ESP32
nos dirigimos a la pagina oficial al apartado de [descargas](https://micropython.org/download/esp32/). 
si damos click en el enlace de descagas nos dirigira a la pagina en google. ![paginaMicropython](./imagen/paginaMicropython.png) 
ya una vez ubicados en la pagina oficial de micropython Buscamos Firmware al recorrer la pagina. ![firmwareThonnyESP32](./imagen/firmwareThonnyESP32.png) 
Seleccionamos la Ultima version de firmware, Siempre nos aparecera al comienzo de la lista de versiones
por cualquier duda de todas formas la señalamos adentro de el recuadro amarillo.Al cual damos click derecho para que iniciemos la descarga  
![seleccionarVersion](./imagen/seleccionarVersion.png)
Al finalizar la descarga nos dirigimos a la aplicación de thonny seleccionamos ''**Ejecutar**'' al dar click nos dirigimos a la primera opción ''**configurar interprete**''.  ![Ejecutar](./imagen/Ejecutar.png)
Enseguida nos aparecera una ventanilla llamada **Opciones de Thonny**, enseguida seleccionamos las opciones enmarcadas en los recuadros amarillos. **Interprete**, **Micropython(ESP32)** y el puerto **COM3** en mi caso es donde tengo conectado mi ESP32. la deteccion de puertos es completamente automatica asi que les aparecera el puerto al que su ordenador este conectado con su ESP32.  
![SELECTport](./imagen/SELECTport.png)
Enseguida nos ubicamos en **Isntalar o actualizar Micropython**. se señala adentro del recuadro en la imagen y damos click para instalar o actualizar.
![ActualizarFMW](./imagen/ActualizarFMW.png)
Una vez seguidos los pasos anteriores nos abrira una nueva ventana que se llama  **Install Micro Python (esptool)** en las casillas para seleccion algunas ya vendran seleccionadas por defecto como lo es el puerto COM3 y en las tres casillas restantes ESP32, WROOM Y la version que descargamos v1.25.0 **Para empezar a Instalar o actualizar el firmware** Primero hay que formatear presionando el botón de nuestro esp32 el botón BOOT señalado en la imagen con un circulo rojo al mismo tiempo que damos click en <kbd>Instalar</kbd> tambien señalado de color rojo pero en un recuadro. hay que mantener Oprimido el botón de EBOOT hasta que empieze el porcentaje de la instalación. 
![ResetearFMW2](./imagen/ResetearFMW2.png)

para finalizar ya solo restaria dar click en el botón <kbd>OK</kbd>.
![FinalFWM](./imagen/FinalFMW.png)

Solo para confirmar la ultima version de nuestro firmware del esp32 podemos checar en la parte inferior.
![Confirmacion](./imagen/ConfirmarFWM.png)

## Usar Thonny
Para empezar a programar abrimos la aplicación Thonny que estara ubicada en el Escritorio.
Nos ubicamos en la interfaz del interprete para comenzar a escribir el código.
Al abrir el programa te abrira también un archivo en el que podrás empezar a programar.
![Inicio Thonny](./imagen/Inicio_Thonny.png)
En la siguiente imagen esta señalado con un cuadro amarillo donde podrás editar este archivo. 
![Ubicamos la interfaz para escribir](./imagen/thony_ubicar_interfaz.png)

Notarás que en la consola, señalada en el recuadro amarillo de la siguiente imagen, no indica que no esta conectado el puerto COM 3.
Esto quiere decir que tienes que conectar tu esp32 con el cable USB a tu compuadora.
Duespués de esto, ve al menú **Ejecutar** y enseguida da click en **Detener/Reinicia back end**.
![Ubicamos la consola para interactuar](./imagen/Ubicar_Consola.png)

## Conectar el sensor DHT11 a nuestro esp32
Asegúrate que los datos del DHT11 estan conectados al pin 15, vcc DHT11 en 3v3 del ESP32 y GND de DHT11 al GND de nuestro ESP32.
![conexion](./imagen/conexionESPDHT11.png)

Ahora comenzaremos a escribir el siguiente código.
Partiendo por poner a prueba lo primero que aprendemos en Python sera imprimir una simple etiqueta de texto en Python utlizando la función **print**.
Para ejecutarlo ve al menú **Ejecutar** y da click en **Ejecutar el script actual**.
De igual forma puedes presionar en tu teclado al tecla <kbd>F5</kbd>.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

print(s.temperature())
```
El resultado de este programa es el siguiente:
```console
MPY: soft reboot
29
```
Para el siguiente ejemplo queremos solicitarle al usuario que ingrese algo escrito en la consola que se encuentra en la parte inferior de nuestra interfaz de Thonny. 
Para hacer esto utilizaremos la funcion **input**.
```python
input("Cual es la temperatura? ")
print("Hola, ambiente")
```
El resultado del programa en la consola es el siguiente: 
```console
MPY: soft reboot
Cual es la temperatura? 32
Hola, ambiente
```

## Bugs
En programacion independientemente de cualquier lenguaje usualmente podemos cometer errores no te preocupes, es parte de covertirse en un gran programador a estos errores en programacion se les llama bugs.
 
Imaginemos que en nuestro programa escribimos accidentalmente print("hola, mundo", olvidando la función final **)**. print Si cometemos este error, el intérprete mostrará un error en la ventana de terminal.
```python
print("Hola mundo"
```
Los mensajes de error suelen informarle de sus errores y ofrecerle pistas sobre cómo solucionarlos. Sin embargo, en muchas ocasiones el intérprete no será tan útil.
```console
MPY: soft reboot
Traceback (most recent call last):
  File "<stdin>", line 2
SyntaxError: invalid syntax
```
## Variables
A continuacion vamos a nombrar una variable.
Para esto utilizaremos el signo **=** para asignar el valor a la variable.
Colocaremos a la derecha de este simbolo el valor que le quermos dar a nuestra variable que estara del lado izquierdo del simbolo.



```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temperatura = s.temperature()

print("La temperatura es: temperatura")
```
Al obsevar el resultado notarás que no nos dará la temperatura y solo esta imprimiendo **La temperatura es: temperatura**.
Pero si esta asignando un valor a la variable **temperatura**, no obstante no lo esta imprimiendo.
```console
MPY: soft reboot
La temperatura es: temperatura
```
En este ejemplo podemos solucionar que si nos imprima la temperatura que hemos ingresado de la siguiente forma.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temperatura = s.temperature()

print("La temperatura es: ")
print(temperatura)
```
El resultado obtenido es el siguiente:
```console
MPY: soft reboot
La temperatura es: 
29
```

## Comentarios
En python utilizamos **#**  para comentar una linea mediante los bloques de código podemos informar al programador sobre la lo que trata el bloque de código. 
En Python, utilizamos el símbolo # para escribir comentarios en una sola línea. Estos comentarios son útiles para explicar qué hace una parte específica del código o para dejar notas importantes al programador.
Además, es una buena práctica incluir comentarios al inicio de cada bloque de código para describir brevemente su propósito. Esto facilita la comprensión del programa, especialmente cuando se trabaja en equipo o se revisa el código después de un tiempo.
```python 
# la medicion nos entregara la temperatura 
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temperatura = s.temperature()

print("La temperatura es: ")
print(temperatura)
```
Resultado obtenido.
```console
MPY: soft reboot
La temperatura es: 
30
```

## Pseudocodigo
El pseudocódigo es una herramienta utilizada para describir la lógica de un programa de manera estructurada, sin depender de un lenguaje de programación específico. En Python, podemos representar un pseudocódigo utilizando comentarios, los cuales no afectan la ejecución del código, pero sirven para documentar y mejorar su comprensión.
A continuación, se presenta un ejemplo en el que solicitamos al usuario ingresar una temperatura y luego la mostramos en pantalla.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# Solicitamos al usuario que ingrese la temperatura en este caso al no manejar "input" solo usaremos la medicion. "s.temperature"
temperatura = s.temperature()

# Mostramos un mensaje en pantalla
print("La temperatura es: ")

# Imprimimos la temperatura obtenida por el sensor
print(temperatura)
```
Salida esperada. 
```console
MPY: soft reboot
La temperatura es: 
30
```

## Mejorando el programa anterior
En este ejemplo, optimizaremos el código anterior combinando las dos llamadas a print() en una sola línea. Esto mejora la eficiencia y mantiene el código más limpio y legible. 
Se optimiza la impresión en pantalla concatenando el texto "La temperatura es: " con la variable temperatura dentro de una única instrucción print().
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# Solicitamos la medicion dando play en el programa
temperatura = s.temperature()

# Mostramos el mensaje y la temperatura en una sola línea
print("La temperatura es: " + str(temperatura))
```
El resultado obtenido es. 
```console
MPY: soft reboot
La temperatura es: 30
```

## Comas 
Las comas **,**  se utilizan para pasar multiples argumentos. 
En este caso estamos ingresando dos argumentos a print, lo sabemos por que pudes ver que dice "Hola Ambiente," **,** temperatura.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# Le preguntamos al usuario por la medicion
temperatura = s.temperature()

# Impriminmos la temperatura es y la medicion
print("la temperatura es,", temperatura)
```
El resultado del programa es. 
```console
MPY: soft reboot
la temperatura es, 30
```

## Cadenas y parametros
Para representar una cadena utilizamos **str** nos sirven para realizar secuencias de texto. 
En Python, el tipo de dato str se utiliza para representar cadenas de texto. Estas cadenas permiten almacenar y manipular secuencias de caracteres, lo que resulta útil para diversas aplicaciones, como la comunicación con interfaces de usuario, el procesamiento de datos y la interacción con sistemas embebidos.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# Solicitamos la medicion dando play en el programa
temperatura = s.temperature()
print("la temperatura es,")
print(temperatura)
```
El resultado obtenido es 
```console
MPY: soft reboot
la temperatura es,
30
```

## Modificaciones 
En el siguiente ejemplo podemos modificar nuestro codigo de la siguiente forma.
Para no crear una linea nueva, Usamos **end=""**.  
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# damos play a nuestro codigo para obtener la medicion de la temperatura 
temperatura = s.temperature()
print("la temperatura es,", end="")
print(temperatura)
```
El resultado obtenido es 
```console
MPY: soft reboot
la temperatura es,30
```

## Formato cadenas 
Para trabajar con cadenas en Python, existe una forma más elegante y eficiente que los métodos tradicionales: las f-strings (cadenas formateadas). Este enfoque utiliza un prefijo especial **f** antes de la cadena, lo que permite insertar variables o expresiones directamente dentro del texto, haciendo el código más legible y conciso.
```python

from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# damos play a nuestro codigo para obtener la medicion de la temperatura 
temperatura = s.temperature()
print(f"la temperatura es, {temperatura}")
```
El resultado obtenido es 
```console
MPY: soft reboot
la temperatura es, 30
```
Mejoramos mas el código para que obtengamos una mayor eficiencia.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

# damos play a nuestro codigo para obtener la medicion de la temperatura 
temperatura = s.temperature()

# Eliminamos los espacios en blanco de la cadena y escribimos con mayuscula la primera letra de cada palabra
temperatura = temperatura   

# Imprimimos la salida
print(f"la temperatura es, {temperatura}")
```
El resultado obtenido es 
```console
MPY: soft reboot
la temperatura es, 29
```

## Numeros enteros o int
En python a los números enteros se les denomina **int**. 
Al estar familiarizados con las matemátcicas podemos hacer uso de los operadores lógicos como lo son.
**+**, **-**, **/** y **%**. 
Notarás que te estoy agregando 4 líneas.
Quiero que por el momento solo las incluyas en tu sccript y mas adelante te explicare de que se tratan.
Por ahora basta que entiendas la temperatura de tu sensor se esta asignando a la variable **x**.

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

temp = 1
hum = 2

z = temp + hum

print(z)
```
El resultado obtenido es.
```console
MPY: soft reboot
3
```
```python 
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

x = s.temperature()  
y = s.humidity()  

z = x + y  

print(z)
```
El resultado obtenido es.
```console
MPY: soft reboot
91
```
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

x = s.temperature()  
y = s.humidity()  

z = int(x) + int(y)

print(z)
```
El resultado de este programa es. 
```console
MPY: soft reboot
90
```

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

temp = int (s.temperature())
hum = int(s.humidity())

print(temp + hum)
```
```console
MPY: soft reboot
91
```
## Flotantes
Los valores flotantes son números reales con puntos décimales, Por ejemplo **0.22** dando asi una aproximación a los enteros o int.
Para utilizar los valores flotantes recordemos el comando de los números enteros, pero en su lugar utlizaremos **float**.

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = float(s.temperature())
hum = float(s.humidity())

print(temp + hum)
```
```Console
MPY: soft reboot
92.0
```

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()


temp = s.temperature()
hum = s.humidity()
# Damos play al programa para obtener la medicion 
x = float(s.temperature())
y = float(s.humidity())

# Calculamos el resultado y redondeamos
z = round(x + y)

# Imprimos el resultado
print(z)
```
El resultado obtenido es. 
```console
MPY: soft reboot
96
```

```python 
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()
hum = s.humidity()
#Obtener la entrada del usuario
x = float(s.temperature())
y = float(s.humidity())

#Crear un resultado redondeado
z = x/y

#Imprimir el resultado formateado
print(f"{z:.2f}")
```
El resultado obtenido es 
```console
MPY: soft reboot
95
```
Division
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()
hum = s.humidity()
#Obtener la entrada del usuario
x = float(s.temperature())
y = float(s.humidity())

#Calcular el resultado y redondear
z = round(x / y, 2)

#imprimir el resultado
print(z)
```
El resultado obtenido es 
```console
MPY: soft reboot
0.43
```


## Definicion
las definiciones en python son mejor conocidas como funciones. 
Definición.
En Python, una definición se refiere comúnmente a la creación de una función. Las funciones permiten encapsular un bloque de código que puede reutilizarse en diferentes partes del programa, facilitando la organización, mantenimiento y legibilidad del código.

```python
#Pídale al usuario su nombre, elimine los espacios en blanco de la cadena y escriba en mayúscula la primera letra de cada palabra.
temperatura = input("Cual es la temperatura? ")

#Imprimir la salida
print(f"temperatura, {temperatura}")
```
En este ejemplo es muy importante definir la funcion por lo cual generaremos un error a proposito. 
```python
temperatura = input("What's your name? ")
Ambiente()
print(temperatura)
```
El resultado obtenido es
```console
MPY: soft reboot
What's your name? jerry
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
NameError: name 'Ambiente' isn't defined
```
En este ejemplo hemos defininido nuestra funcion mediante las dos primeras lineas de codigo por lo cual ya no tendremos el mismo error.
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()


def Ambiente():
    print("Temperatura")


temp = s.temperature()
Ambiente()
print(temp)
```
El resultado obtenido es
```console
MPY: soft reboot
Temperatura
30
```
Actualizado
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()

def Temperature():
        print("La temperatura es")


Temperature()
print(temp)
```
El resultado obtenido es
```console
MPY: soft reboot
La temperatura es
29
```

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()

# Create our own function
def temperatura(to):
    print("Temperatura,", to)


# Output using our own function
name = temp = s.temperature()
temperatura(name)
```
El resultado obtenido es 
```console
MPY: soft reboot
Temperatura, 29
```
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()


# Create our own function
def temperatura(to="Ambiente"):
    print("temperatura,", to)


# Output using our own function
name = s.temperature()
temperatura(name)

# Output without passing the expected arguments
temperatura()
```
El resultado obtenido es 
```console
MPY: soft reboot
temperatura, 31
temperatura, Ambiente
```
```python
def main():

    #Salida usando nuestra propia función
    name = input("Cual es la temperatura? ")
    temperatura(name)

    #Salida sin pasar los argumentos esperados
    temperatura()


#Crear nuestra propia función
def temperatura(to="ambiente"):
    print("temperatura,", to)
```
El resultado obtenido es 
```console
MPY: soft reboot
```

```python
def main():

    #Salida usando nuestra propia función
    ambiente = input("Cual es la temperatura? ")
    temperatura(ambiente)

    #Salida sin pasar los argumentos esperados
    temperatura()


#Crear nuestra propia función
def temperatura(to="ambiente"):
    print("temperatura,", to)


main()
```
El resultado obtenido es 
```console
MPY: soft reboot
Cual es la temperatura? 32
temperatura, 32
temperatura, ambiente
```

## Devolviendo valores 
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

temp = s.temperature()

def main():
    x = int(s.temperature())
    print("x squared is", square(x))


def square(n):
    return n * n


main()
```
El resultado obtenido es 
```console
MPY: soft reboot
x squared is 1024
```

## Aplicasion thonny con el sensor Dht11

## ESTO ES EL PROGRAMA FINAL

A continuacion se muestra un ejemplo con lo que anteriormente hemos visto.
Para que apliquemos lo visto con un sensor DHT11 mismo que nos servira para capturar la temperatura en tiempo real.  
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

# IMPRIMEREMOS
print("Temperatura: ",temp)
print("Humedad: " + str(hum))
```
El resultado de este programa es:
```console
Temperatura 34
Humedad: 68
```
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()
temp = s.temperature()
hum = s.humidity()

# IMPRIMIMOS 
print("Temperatura {temp}", temp)
print("Humedad: {hum}"+ str(hum))
```
El resultado de este programa es:
```console
Temperatura {temp} 24
Humedad: {hum}56
```
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))

temp = s.temperature()
hum = s.humidity()

suma = int(temp) + int(hum)

# IMPRIMEREMOS
print("Suma {sum}" )
```
El resultado de este programa es:
```console
MPY: soft reboot
Suma {sum}
>>> 32+12
44
>>> 
```
