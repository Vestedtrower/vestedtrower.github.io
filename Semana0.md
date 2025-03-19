# Funciones y variables con Micropython.
- [Materiales](#materiales)
- [Instalar Thonny](#instalar-thonny)
- [Usar Thonny](#usar-thonny)
- [Variables](#variables)
- [Comentarios](#comentarios)
- [Pseudocodigo](#pseudocodigo)
- [Mejorando](#mejorando-el-primer-programa)
- [Comas](#comas)
- [Cadenas_y_parametros](#cadenas-y-parametros)
- [Modificaciones](#modificaciones)
- [Formato_cadenas](#formato-cadenas)
- [Mas_sobre_cuerdas](#mas-sobre-cuerdas)
- [Uso_de_title](#uso-de-tilte)
- [Conentar el sensor DHT11 a nuestro esp32](#conentar-el-sensor-dht11-a-nuestro-esp32)
- [Numeros_enteros_o_int](#numeros-enteros-o-int)
- [Conceptos_basicos_de_flotacion](#conceptos-basicos-de-flotacion)
- [Mas_sobre_los_flotadores](#mas-sobre-los-flotadores)
- [Definicion](#Definicion)
- [Devolviendo_valores](#Devolviendo_valores)
- [Aplicasion_thonny_con_el_sensor_Dht11](#aplicasion-thonny-con-el-sensor-dht11)
  
## Materiales
La lista de materiales es:
- Sensor DHT11
- Esp32
- Cableado Jumper Electronica "F - F"
- Cable USB tipo A con entrada para micro puerto tipo B
- Computadora
- Aplicacion Thonny 

## Instalar Thonny
Descarga Thonny. Para descargar a Thonny nos dirigimos a la pagina oficial al apartado de [descargas](https://github.com/thonny/thonny/releases/download/v4.1.6/thonny-4.1.6.exe).
Busca tu archivo descargado y lo ejecutas dandole doble click.
Dale al boton <kbd>Next</kbd> y despues acepta los términos.
![Aceptar términos](./imagen/thony_aceptar_acuerdo.png).

Activa la casilla para que te ponga un icono en el escritorio.
Con esto podras tener un acceso rapido en tu escritorio.
![Crear icono](./imagen/thony_acceso_directo.png).

Da click en <kbd>Install</kbd> para que inicie el proceso de instalación.
Este proceso puede tomar tiempo, dependerá de el procesador de tu computadora. 

![Iniciar instalación](./imagen/iniciar_instalacion.png)

Para finalizar la instalación hay que dar click en el boton <kbd>Finish</kbd>.
O simplemente puedes cerrar la ventana.
![Finalizar instalacion](./imagen/finalizar_instalacion.png)
 
## Usar Thonny
Para empezar a programar abrimos la aplicación Thonny que estara ubicada en el Escritorio.
Nos ubicamos en la interfaz del interprete para comenzar a escribir el codigo.
Al abrir el programa te abrira tambien un archivo en el que podras empezar a programar.
![Inicio Thonny](./imagen/Inicio_Thonny.png)
En la siguiente imagen esta señalado con un cadro amarillo donde podras editar este archivo. 
![Ubicamos la interfaz para escribir](./imagen/thony_ubicar_interfaz.png)

Notarás que en la consola, señalada en el recuadro amarillo de la siguiente imagen, no indica que no esta conectado el puerto COM 3.
Esto quiere decir que tienes que conectar tu esp32 con el cable USB a tu compuadora.
Duespues de esto, ve al menú **Ejecutar** y despues de click en **Detener/Reinicia back end**.
![Ubicamos la consola para interactuar](./imagen/Ubicar_Consola.png)


## Conectar el sensor DHT11 a nuestro esp32
Asegurate que los datos del DHT11 estan conectados al pin 15
![]()

Ahora comenzaremos a escribir el siguiente código.
Partiendo por poner a prueba lo primero que aprendemos en Python sera imprimir una simple etiqueta de texto en Python utlizando la función **print**.
Para ejecutarlo ve al menú **Ejecutar** y da click en **Ejecutar el script actual**.
De igual forma puedes presionar en tu teclado al tecla <kbd>F5</kbd>.
```python
print("Hola esp32")
```
El resultado de este programa es el siguiente:
```console
Hola esp32
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

## Variables

A continuacion vamos a nombrar una variable.
Para esto utilizaremos el signo **=** para asignar el valor a la variable.
Colocaremos a la derecha de este simbolo el valor que le quermos dar a nuestra variable que estara del lado izquierdo del simbolo.
```python
temperatura = input("Cual es la temperatura? ")
print("La temperatura es: temperatura")
```
Al obsevar el resultado notarás que no nos dará la temperatura y solo esta imprimiendo **La temperatura es: temperatura**.
Pero si esta asignando un valor a la variable **temperatura**, no obstante no lo esta imprimiendo:
```console
MPY: soft reboot
Cual es la temperatura? 32
La temperatura es: temperatura
```
En este ejemplo podemos solucionar que si nos imprima la temperatura que hemos ingresado de la siguiente forma.
```python
temperatura = input("Cual es la temperatura? ")
print("La temperatura es: ")
print(temperatura)
```
El resultado obtenido es el siguiente:
```console
MPY: soft reboot
Cual es la temperatura? 32
La temperatura es: 
32
```

## Comentarios

En python utilizamos **#**  para comentar una linea mediante los bloques de codigo podemos informar al programador sobre la lo que trata el bloque de código. 
```python 
# Preguntamos al usuario que ingrese la temperatura
temperatura = input("Cual es la temperatura? ")
print("La temperatura es: ")
print(temperatura)
```
Resultado obtenido.
```console
MPY: soft reboot
Cual es la temperatura? 32
La temperatura es: 
32
```

## Pseudocodigo

El pseudocódigo es una herramienta utilizada para describir la lógica de un programa de manera estructurada, sin depender de un lenguaje de programación específico. En Python, podemos representar un pseudocódigo utilizando comentarios, los cuales no afectan la ejecución del código, pero sirven para documentar y mejorar su comprensión.
A continuación, se presenta un ejemplo en el que solicitamos al usuario ingresar una temperatura y luego la mostramos en pantalla.
```python
# Solicitamos al usuario que ingrese la temperatura
temperatura = input("¿Cuál es la temperatura? ")

# Mostramos un mensaje en pantalla
print("La temperatura es: ")

# Imprimimos la temperatura ingresada
print(temperatura)
```
Salida esperada. 
```console
MPY: soft reboot
¿Cuál es la temperatura? 32
La temperatura es: 
32
```

## Mejorando el programa anterior

En este ejemplo, optimizaremos el código anterior combinando las dos llamadas a print() en una sola línea. Esto mejora la eficiencia y mantiene el código más limpio y legible. 
Se optimiza la impresión en pantalla concatenando el texto "La temperatura es: " con la variable temperatura dentro de una única instrucción print().
```python
# Solicitamos al usuario que ingrese la temperatura
temperatura = input("¿Cuál es la temperatura? ")

# Mostramos el mensaje y la temperatura en una sola línea
print("La temperatura es: " + temperatura)
```
El resultado obtenido es. 
```console
MPY: soft reboot
¿Cuál es la temperatura? 32
La temperatura es: 32
```

## Comas 

Las comas **,**  se utilizan para pasar multiples argumentos. 
En este caso estamos ingresando dos argumentos a print, lo sabemos por que pudes ver que dice "Hola Ambiente," **,** temperatura.
```python
# Le preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")

# Impriminmos Hola Ambiente y ingresamos la temperatura
print("Hola Ambiente,", temperatura)
```
El resultado del programa es. 
```console
MPY: soft reboot
Cual es la temperatura? 32
Hola Ambiente, 32
```

## Cadenas y parametros

Para representar una cadena utilizamos **str** nos sirven para realizar secuencias de texto. 
En Python, el tipo de dato str se utiliza para representar cadenas de texto. Estas cadenas permiten almacenar y manipular secuencias de caracteres, lo que resulta útil para diversas aplicaciones, como la comunicación con interfaces de usuario, el procesamiento de datos y la interacción con sistemas embebidos.
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print("hola ambiente,")
print(temperatura)
```

## Modificaciones 

En el siguiente ejemplo podemos modificar nuestro codigo de la siguiente forma.
Para no crear una linea nueva, Usamos **end=""**.  
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print("hola ambiente,", end="")
print(temperatura)
```

## Formato cadenas 

Para usar las cadenas en el ejemplo que se muestra a continuacion probablemente sea una forma mas elegente para programar en python. Utilizamos **f** un indicador especial para que Python trate la cadena de un modo distinto a los enfoques anteriores.  
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print(f"hola ambiente, {temperatura}")
```

## Mas sobre cuerdas 


```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")

# Eliminamos los espacios en blanco de la cadena 
temperatura = temperatura.strip()

# Imprimimos la salida
print(f"hola ambiente, {temperatura}")

```

## Uso de tilte

Si colocamos title en nuestro codigo nos va a servir para poner en mayuscula el nombre del Usuario.
En consola obserbaremos los resultados en donde se muestra 
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")

# Eliminamos los espacios en blanco de la cadena 
temperatura = temperatura.strip()

# Escribimos con mayuscula la primera letra de cada palabra 
temperatura = temperatura.title()

# Imprimimos la salida
print(f"hola ambiente, {temperatura}")
```
Mejoramos mas el codigo para que obtengamos una mayor eficiencia.
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")

# Eliminamos los espacios en blanco de la cadena y escribimos con mayuscula la primera letra de cada palabra
temperatura = temperatura   

# Imprimimos la salida
print(f"hola ambiente, {temperatura}")
```
El siguiente codigo es para que mejorermos mas el programa.
obteniendo los mismos resultados. 
```python
# Preguntamos al usuario por la temperatura, Eliminamos los espacios en blanco de la cadena y escribimos con mayuscula la primera letra de cada palabra
temperatura = input("Cual es la temperatura? ").strip().title()

# Imprimimos la salida
print(f"hola ambiente, {temperatura}")
```

## Numeros enteros o int
En python a los numeros enteros se les denomina **int**. 
Al estar familiarizados con las matematcicas podemos hacer uso de los operadores logicos como lo son.
**+**, **-**, **/** y **%**. 
Notaras que te estoy agregando 4 lineas.
Quiero que por el momento solo las incluyas en tu sccript y mas adelante te explicare de que se tratan.
Por ahora basta que entiendas la temperatura de tu sensor se esta asignando a la variable **x**.

```python 
from machine import Pin
import dht
sensor = dht.DHT11(Pin(15))
sensor.measure()
x = s.temperature()
y = 2

z = x + y

print(z)
```


## Conceptos basicos de flotante
Los valores flotantes son numeros reales con puntos decimales, Por ejemplo **0.22** dando asi una aproximacion a los enteros o int.
Para utilizar los valores flotantes recordemos el comando de los numeros enteros, pero en su lugar utlizaremos **float**.

```python 
x = float(input("What's x? "))
y = float(input("What's y? "))

print(x + y)
```
```python 
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Create a rounded result
z = round(x + y)

# Print the result
print(z)
```
```python 
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Create a rounded result
z = round(x + y)

# Print the formatted result
print(f"{z:,}")
```

## Mas sobre los flotadores 
Si deseamos redondear nuestros valores de punto flotante obtenemos un resultado que aparenta llegar hasta el infinito.

```python 
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result
z = x / y

# Print the result
print(z)
```

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result and round
z = round(x / y, 2)

# Print the result
print(z)
```

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result
z = x / y

# Print the result
print(f"{z:.2f}")

```

## Definicion
las definiciones en python son mejor conocidas como funciones. 

```python
# Ask the user for their name, remove whitespace from the str and capitalize the first letter of each word
name = input("What's your name? ").strip().title()

# Print the output
print(f"hello, {name}")
```

```python
name = input("What's your name? ")
hello()
print(name)
```

```python
def hello():
    print("hello")


name = input("What's your name? ")
hello()
print(name)
```

```python
# Create our own function
def hello(to):
    print("hello,", to)


# Output using our own function
name = input("What's your name? ")
hello(name)
```

```python
# Create our own function
def hello(to="world"):
    print("hello,", to)


# Output using our own function
name = input("What's your name? ")
hello(name)

# Output without passing the expected arguments
hello()
```

```python
def main():

    # Output using our own function
    name = input("What's your name? ")
    hello(name)

    # Output without passing the expected arguments
    hello()


# Create our own function
def hello(to="world"):
    print("hello,", to)
```

```python
def main():

    # Output using our own function
    name = input("What's your name? ")
    hello(name)

    # Output without passing the expected arguments
    hello()


# Create our own function
def hello(to="world"):
    print("hello,", to)


main()
```
Devolviendo valores 

```python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n * n


main()
```

## Aplicasion thonny con el sensor Dht11

## ESTO ES EL PROGRAMA FINAL

A continuacion se muestra un ejemplo con lo que anteriormente hemos visto.
Para que apliquemos lo visto con un sensor DHT11 mismo que nos servira para capturar la temperatura en tiempo real.  
```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
temp = s.temperature()
hum = s.humidity()

# IMPRIMEREMOS
print("Temperatura ",temp)
print("Humedad: " + hum)
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

temp = s.temperature()
hum = s.humidity()

# IMPRIMIMOS 
print("Temperatura {temp}" )
print("Humedad: {hum}")
```
El resultado de este programa es:
```console

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

```