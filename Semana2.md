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
Para empesar a usar nuestro sensor tenemos que tener en mano lo antes mencionado en la lista de materiales

## Conectar sensor TCRT5000
Para conectar nuestro sensor contamos con las siguientes referencias.

## Bucles.
 Básicamente, los bucles son una forma de hacer algo una y otra vez.
Comience escribiendo code cat.pyen la ventana del terminal.
En el editor de texto, comience con el siguiente código:
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
El while bucle es casi universal en todos los lenguajes de codificación.
Un bucle de este tipo repetirá un bloque de código una y otra vez.
de manera ilimitada. 
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
Un for bucle es un tipo diferente de bucle.
Para comprender mejor un for bucle, conviene empezar hablando de un nuevo tipo de variable llamado a listen Python. Como en otras áreas de nuestra vida, podemos tener una lista de la compra, una lista de tareas, etc.
Un forbucle itera sobre un listconjunto de elementos. Por ejemplo, en la ventana del editor de texto, modifique su cat.pycódigo de la siguiente manera: 
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
Quizás queramos obtener información de nuestro usuario. Podemos usar bucles para validarla.
Un paradigma común dentro de Python es utilizar un whilebucle para validar la entrada del usuario.
Por ejemplo, intentemos solicitarle al usuario un número mayor o igual a 0:
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
Considere el mundo de Hogwarts del famoso universo de Harry Potter.
En la terminal, escriba code hogwarts.py.
En el editor de texto, escriba el código de la siguiente manera: 
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
Podemos utilizarlo lencomo una forma de comprobar la longitud del listllamado students.
Imagina que no solo quieres imprimir el nombre del estudiante, sino también su posición en la lista. Para ello, puedes editar tu código de la siguiente manera:
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
dictLos diccionarios o s son una estructura de datos que permite asociar claves con valores.
Donde a listes una lista de múltiples valores, a dictasocia una clave con un valor.
Considerando las casas de Hogwarts, podríamos asignar estudiantes específicos a casas específicas.

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
Mejorando el programa.
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


