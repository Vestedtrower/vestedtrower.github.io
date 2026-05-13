# Bucles. 
Bienbenidos [inicio](/README.md).

- [Materiales y Programas](#materiales-y-programas)
- [Usar Thonny]()
- [Conectar el sensor TCRT5000](#conectar-sensor-tcrt5000)
- [Bucles](#bucles)
- [Bucles while](#bucles-while)
- [Bucles for](#bucles-for)
- [Mejorando con la entrada del Usuario](#mejorando-con-la-entrada-del-usuario)
- [Mas sobre las listas](#mas-sobre-las-listas)
- [Longitud](#longitud)
- [Diccionarios](#diccionarios)
- [Mario](#mario)
- [Ejemplo sensor TCRT5000](#ejemplo-sensor-tcrt5000)

## Materiales y Programas
La lista de materiales es:
- Sensor TCRT5000
- Esp32
- Cableado Jumper Electrónica "F - F"
- Cable USB tipo A con entrada para micro puerto tipo B
- Computadora
- Aplicación Thonny 
- Instrucciones Git hub

## Usar Thonny
Para empezar a programar abrimos la aplicación Thonny que estara ubicada en el Escritorio.
Nos ubicamos en la interfaz del interprete para comenzar a escribir el código.

## Conectar sensor TCRT5000 a nuestro esp32
Para conectar nuestro sensor Utilizaremos los siguientes pines para depues conectarlos a nuestro esp32. 

- VCC
- GND
- DO

Procedemos a realizar las conecciones en nuestro protoboard mismo donde conectaremos nuestro esp32 alineandolos en los sigueintes pines. 

- 3V3
- GND
- D35

## Bucles.
Los **Bucles**, también conocidos como ciclos, permiten repetir bloques de código de manera automática. Estas estructuras son fundamentales en programación, ya que facilitan la ejecución de tareas repetitivas una o varias veces sin necesidad de escribir el mismo código continuamente, permitiendo así automatizar procesos de forma eficiente.

```Python 
print("meow")
print("meow")
print("meow")
```
![]()
```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

print("meow")
print("meow")
print("meow")
```
```console
MPY: soft reboot
meow
meow
meow
```

## Bucles While.
El bucle while es una estructura ampliamente utilizada en la mayoría de los lenguajes de programación. Este tipo de ciclo permite repetir un bloque de código continuamente mientras una condición determinada se mantenga verdadera. Si no se establece una condición de finalización adecuada, el bucle puede ejecutarse de manera ilimitada.

```Python
i = 3
while i != 0:
    print("meow")
```
```console
MPY: soft reboot
meow
meow
meow
meow
meow
meow
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

i = 3
while i != 0:
    print("meow")
```
el resultado seguira surgiendo indefinidamente.
```console
MPY: soft reboot
meow
meow
meow
meow
meow
meow
meow
meow
```

```Python 
i = 3
while i != 0:
  print("meow")
  i = i - 1
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

i = 3
while i != 0:
  print("meow")
  i = i - 1
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
  i = 1
  while i <= 3:
      print("meow")
      i = i + 1
```
```console
MPY: soft reboot
Traceback (most recent call last):
  File "<stdin>", line 1
IndentationError: unexpected indent
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

  i = 1
  while i <= 3:
      print("meow")
      i = i + 1
```
```console
MPY: soft reboot
Traceback (most recent call last):
  File "<stdin>", line 11
IndentationError: unexpected indent
```

```Python
i = 0
while i < 3:
    print("meow")
    i += 1
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

i = 0
while i < 3:
    print("meow")
    i += 1
```
```console
MPY: soft reboot
meow
meow
meow
```

## Bucles for.
El bucle for es un tipo de ciclo utilizado para recorrer conjuntos de datos de manera ordenada.

Para comprender mejor su funcionamiento, es importante conocer un tipo de variable llamado lista (list) en Python. Una lista permite almacenar múltiples elementos en una sola variable, de forma similar a una lista de compras o una lista de tareas en la vida cotidiana.

Un bucle for itera sobre una lista o conjunto de elementos, ejecutando un bloque de código una vez por cada elemento contenido en la colección.

```Python
for i in [0, 1, 2]:
    print("meow")
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

for i in [0, 1, 2]:
    print("meow")
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
for i in range(3):
    print("meow")
```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

for i in range(3):
    print("meow")

```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
for _ in range(3):
    print("meow")
```
```console 
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

for _ in range(3):
    print("meow")

```
```console
MPY: soft reboot
meow
meow
meow
```

```Python
print("meow" * 3)
```
```console
MPY: soft reboot
meowmeowmeow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

print("meow" * 3)

```
```console
MPY: soft reboot
meowmeowmeow
```

```Python
print("meow\n" * 3, end="")

```console
MPY: soft reboot
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

print("meow\n" * 3, end="")

```
```console
MPY: soft reboot
meow
meow
meow
```

## Mejorando con la entrada del Usuario.
En muchas ocasiones, es necesario obtener información proporcionada por el usuario. Para garantizar que los datos ingresados sean correctos, podemos utilizar bucles para validar la entrada.

Una práctica común en Python consiste en utilizar un bucle while para verificar que el usuario introduzca valores válidos antes de continuar con la ejecución del programa.

Por ejemplo, podemos solicitar al usuario que ingrese un número mayor o igual a 0 y repetir la petición hasta que la condición se cumpla correctamente.
```Python
while True:
    n = int(input("What's n? "))
    if n < 0:
        continue
    else:
        break
```
```console
MPY: soft reboot
What's n? 5
meow
meow
meow
meow
meow
```

```Python

```

```console

```

```Python
while True:
    n = int(input("What's n? "))
    if n > 0:
        break

for _ in range(n):
    print("meow")
```
```console
MPY: soft reboot
What's n? 5
meow
meow
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

while True:
    n = int(input("What's n? "))
    if n > 0:
        break

for _ in range(n):
    print("meow")
```
```console
MPY: soft reboot
What's n? 5
meow
meow
meow
meow
meow
```

```Python
def main():
    meow(get_number())


def get_number():
    while True:
        n = int(input("What's n? "))
        if n > 0:
            return n


def meow(n):
    for _ in range(n):
        print("meow")


main()
```
```console
MPY: soft reboot
What's n? 5
meow
meow
meow
meow
meow
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

def main():
    meow(get_number())


def get_number():
    while True:
        n = int(input("What's n? "))
        if n > 0:
            return n


def meow(n):
    for _ in range(n):
        print("meow")


main()
```
```console
MPY: soft reboot
What's n? 4
meow
meow
meow
meow
```

## Mas sobre las listas.
Consideremos el famoso universo de Harry Potter para nuestro siguiente ejemplo.

```Python
students = ["Hermione", "Harry", "Ron"]

print(students[0])
print(students[1])
print(students[2])
```
```console
MPY: soft reboot
Hermione
Harry
Ron
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

students = ["Hermione", "Harry", "Ron"]

print(students[0])
print(students[1])
print(students[2])

```
```console
MPY: soft reboot
Hermione
Harry
Ron
```

```Python
students = ["Hermione", "Harry", "Ron"]

for student in students:
    print(student)
```
```console
MPY: soft reboot
Hermione
Harry
Ron
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

students = ["Hermione", "Harry", "Ron"]

for student in students:
    print(student)
```
```console
MPY: soft reboot
Hermione
Harry
Ron
```

## Longitud.
Podemos utilizar la función len() como una forma de verificar la cantidad de elementos que contiene la lista llamada students.

Ahora bien, imagine que no solo desea imprimir el nombre de cada estudiante, sino también mostrar la posición que ocupa dentro de la lista.
```Python
students = ["Hermione", "Harry", "Ron"]

for i in range(len(students)):
    print(i + 1, students[i])
```
```console
MPY: soft reboot
1 Hermione
2 Harry
3 Ron
```
```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

students = ["Hermione", "Harry", "Ron"]

for i in range(len(students)):
    print(i + 1, students[i])
```
```console
MPY: soft reboot
1 Hermione
2 Harry
3 Ron
```

## Diccionarios.
Los diccionarios (dict) son una estructura de datos que permite asociar claves con valores.

Mientras que una lista (list) almacena múltiples elementos en una secuencia ordenada, un diccionario relaciona cada clave con un valor específico, facilitando la organización y búsqueda de información.

Por ejemplo, considerando las casas de Hogwarts, podríamos asociar a cada estudiante con la casa a la que pertenece mediante el uso de un diccionario.

```Pyhton
students = ["Hermione", "Harry", "Ron", "Draco"]
houses = ["Gryffindor", "Gryffindor", "Griffindor", "Slytherin"]
```
```console

```

```Python

```
```console

```

```Python
students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
print(students["Hermione"])
print(students["Harry"])
print(students["Ron"])
print(students["Draco"])
```
```console
MPY: soft reboot
Gryffindor
Gryffindor
Gryffindor
Slytherin
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
print(students["Hermione"])
print(students["Harry"])
print(students["Ron"])
print(students["Draco"])

```
```console
MPY: soft reboot
Gryffindor
Gryffindor
Gryffindor
Slytherin
```

## Mejorando el programa.
Podemos mejorar nuestro código utilizando lo dictsiguiente:
```Python
students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
for student in students:
    print(student)
```
```console
MPY: soft reboot
Draco
Harry
Hermione
Ron
```

```Python
```

```console
```

Observe cómo, al ejecutar este código, el bucle for solo itera todas las claves, lo que genera una lista con los nombres de los estudiantes. ¿Cómo podríamos imprimir tanto los valores como las claves?

Modifique su código de la siguiente manera:
```Python
students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
for student in students:
    print(student, students[student])
    
```
```console
MPY: soft reboot
Draco Slytherin
Harry Gryffindor
Hermione Gryffindor
Ron Gryffindor
```

```Python
```

```console
```

```Python
students = {
    "Hermione": "Gryffindor",
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
for student in students:
    print(student, students[student], sep=", ")
```
```console
MPY: soft reboot
Draco, Slytherin
Harry, Gryffindor
Hermione, Gryffindor
Ron, Gryffindor
```

```Python
```

```console
```

```Python
students = [
    {"name": "Hermione", "house": "Gryffindor", "patronus": "Otter"},
    {"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
    {"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]
```
```console

```

```Python
```
```console
```

```Python
students = [
    {"name": "Hermione", "house": "Gryffindor", "patronus": "Otter"},
    {"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
    {"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]

for student in students:
    print(student["name"], student["house"], student["patronus"], sep=", ")
```
```console
 MPY: soft reboot
Hermione, Gryffindor, Otter
Harry, Gryffindor, Stag
Ron, Gryffindor, Jack Russell terrier
Draco, Slytherin, None
```

```Python

```
```Python

```

## Mario.
Recuerda que en el clásico Mario, un héroe salta sobre ladrillos. Vamos a crear una representación textual de este juego.

```Python 
print("#")
print("#")
print("#")
```
```console
MPY: soft reboot
#
#
#
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

print("#")
print("#")
print("#")
```
```console
MPY: soft reboot
#
#
#
```

```Python
for _ in range(3):
    print("#")
```
```console
MPY: soft reboot
#
#
#
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

for _ in range(3):
    print("#")
```
```console
MPY: soft reboot
#
#
#
```

```Python
def main():
    print_column(3)


def print_column(height):
    for _ in range(height):
        print("#")


main()
```
```console
MPY: soft reboot
#
#
#
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

def main():
    print_column(3)


def print_column(height):
    for _ in range(height):
        print("#")


main()
```
```console
MPY: soft reboot
#
#
#
```

```Python
def main():
    print_row(4)


def print_row(width):
    print("?" * width)


main()
```
```console
MPY: soft reboot
????
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

def main():
    print_row(4)


def print_row(width):
    print("?" * width)


main()
```
```console
MPY: soft reboot
????
```

```Python
def main():
    print_square(3)


def print_square(size):

    # For each row in square
    for i in range(size):

        # For each brick in row
        for j in range(size):

            #  Print brick
            print("#", end="")

        # Print blank line
        print()


main()
```
```console
MPY: soft reboot
###
###
###
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

def main():
    print_square(3)


def print_square(size):

    # For each row in square
    for i in range(size):

        # For each brick in row
        for j in range(size):

            #  Print brick
            print("#", end="")

        # Print blank line
        print()


main()
```
```console
MPY: soft reboot
###
###
###
```

```Python
def main():
    print_square(3)


def print_square(size):
    for i in range(size):
        print_row(size)


def print_row(width):
    print("#" * width)


main()
```
```console
MPY: soft reboot
###
###
###
```

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095

def main():
    print_square(3)


def print_square(size):
    for i in range(size):
        print_row(size)


def print_row(width):
    print("#" * width)


main()
```
```console
MPY: soft reboot
###
###
###
```

## Ejemplo sensor TCRT5000

## ESTO ES EL PROGRAMA FINAL

```Python
from machine import Pin, ADC
import time

# TCRT5000 salida digital → GPIO4
sensor_ir = Pin(4, Pin.IN)

# LDR salida analógica → GPIO35 (ADC1 canal 7, solo entrada)
sensor_ldr = ADC(Pin(35))
sensor_ldr.atten(ADC.ATTN_11DB)   # rango completo 0 – 3.3 V → valor 0 – 4095


def leer_ldr(n=5):
    total = 0
    for _ in range(n):
        total += sensor_ldr.read()
        time.sleep_ms(10)
    return total // n


conteo = 0

while True:
    ir  = sensor_ir.value()   # 0 = objeto detectado, 1 = sin objeto
    luz = leer_ldr()          # 0 (muy oscuro) – 4095 (muy iluminado)

    if ir == 0:
        conteo += 1
        print("Objeto detectado! | Luz:", luz, "| Detecciones:", conteo)
    else:
        print("Sin objeto        | Luz:", luz)

    time.sleep(0.5)
```

```console
MPY: soft reboot
Objeto detectado! | Luz: 4095 | Detecciones: 1
Objeto detectado! | Luz: 4095 | Detecciones: 2
Objeto detectado! | Luz: 4095 | Detecciones: 3
Objeto detectado! | Luz: 4095 | Detecciones: 4
Objeto detectado! | Luz: 4095 | Detecciones: 5
Objeto detectado! | Luz: 4095 | Detecciones: 6
Objeto detectado! | Luz: 4095 | Detecciones: 7
Objeto detectado! | Luz: 4095 | Detecciones: 8
Objeto detectado! | Luz: 4095 | Detecciones: 9
```


```console
Objeto detectado! | Luz: 3931 | Detecciones: 39
Objeto detectado! | Luz: 3922 | Detecciones: 40
Objeto detectado! | Luz: 3921 | Detecciones: 41
Objeto detectado! | Luz: 3938 | Detecciones: 42
Objeto detectado! | Luz: 3924 | Detecciones: 43
Objeto detectado! | Luz: 3936 | Detecciones: 44

```


