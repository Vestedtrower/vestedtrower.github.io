# Funciones y variables con Micropython.
- [Materiales](#materiales)
- [Instrucciones](#instrucciones)
  - [Instalar Thonny](#instalar-thonny)
  - [Usar Thonny](#usar-thonny)
  - [Variables](#variables)
  

## Materiales
- Sensor DHT11
- Esp32
- Cableado Jumper Electronica "F - F"
- Cable USB tipo A con entrada para micro puerto tipo B
- Computadora
- Aplicacion Thonny 

## Instrucciones
### Instalar Thonny
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
 
### Usar Thonny
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

### Variables

A continuacion vamos a nombrar una variable.
Para esto utilizaremos el signo **=** para asignar el valor a la variable.
Colocaremos a la derecha de este simbolo el valor que le quermos dar a nuestra variable que estara del lado izquierdo del simbolo.
```python
temperatura = input("Cual es la temperatura? ")
print("Hola Ambiente : temperatura")
```
Al obsevar el resultado nos dará la temperatura pero si esta asignando un valor a la variable temperatura:
```console
MPY: soft reboot
Cual es la temperatura? 32
Temperatura: temperatura
```
En este ejemplo podemos solucionar la asignacion antes mencionada, agragendo un print con la variable a la que le hemos asignado el valor.
```python
temperatura = input("Cual es la temperatura? ")
print("temperatura,")
print(temperatura)
```
El resultado obtenido es el siguiente:
```console
MPY: soft reboot
Cual es la temperatura? 32
temperatura,
32
```

### Comentarios

En python utilizamos **#**  para comentar una linea mediante los bloques de codigo podemos informar al programador sobre la informacion que se desea compartir. 
```python 
# Preguntamos al usuario que ingrese la temperatura
temperatura = input("Cual es la temperatura? ")
print("temperatura,")
print(temperatura)
```
Resultado obtenido.
```console
MPY: soft reboot
Cual es la temperatura? 32
temperatura,
32
```

### Pseudocodigo

Para crear un Pseudocodigo, hacemos uso de la misma manera que un comentario.
No afecta al codigo funcional nos sirve para dar instrucciones, dejando notas de seguimiento por asi decirlo. 
```python
# Preguntamos al usuario cual es la temperatura 
temperatura = input("Cual es la temperatura? ")

# Print Hola Ambiente
print("Hola Ambiente,")

# Utilizamos print para ingresar la temperatura en numeros por ejemplo 32 
print(temperatura)
```
Resultado obtenido. 
```console
MPY: soft reboot
Cual es la temperatura? 32
Hola Ambiente,
32
```

### Mejorando el primer programa 

Para el siguiente ejemplo podemos editar el anterior programa. 
Donde podemos sumar los dos print de una manera mas optimizada.   
```python
# Le pedimos al usuario la temperatura 
temperatura = input("Cual es la temperatura? ")

# Imprimimos Hola ambiente con la temperatura ingresada
print("Hola Ambiente, " + temperatura)
```
El resultado obtenido es. 

```console
MPY: soft reboot
Cual es la temperatura? 32
Hola Ambiente, 32
```

### Comas 

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

### Cadenas y parametros

Para representar una cadena utilizamos **str** nos sirven para realizar secuencias de texto. 
```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print("hola ambiente,")
print(temperatura)
```

### Modificaciones 

```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print("hola ambiente,", end="")
print(temperatura)
```

### Formato cadenas 

```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")
print(f"hola ambiente, {temperatura}")
```

### Mas sobre cuerdas 

```python
# Preguntamos al usuario por la temperatura
temperatura = input("Cual es la temperatura? ")

# Eliminamos los espacios en blanco de la cadena 
temperatura = temperatura.strip()

# Imprimimos la salida
print(f"hola ambiente, {temperatura}")

```

### Uso de tilte

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
temperatura = temperatura.strip().title()

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

### Numeros enteros o int

```python 
x = 1
y = 2

z = x + y

print(z)
```

### Interacion con input

```python
x = input("What's x? ")
y = input("What's y? ")

z = x + y

print(z)
```

### Concatenamos dos cadenas mediante signos 

```python
x = input("What's x? ")
y = input("What's y? ")

z = int(x) + int(y)

print(z)
```
El uso de int(x).

```python 
x = int(input("What's x? "))
y = int(input("What's y? "))

print(x + y)
```

### Conceptos basicos de flotacion

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

### Mas sobre los flotadores 

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

### Definicion

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

### Aplicasion thonny con el sensor Dht11

### ESTO ES EL PROGRAMA FINAL

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
