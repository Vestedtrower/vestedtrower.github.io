# Condicionales. 

Bienbenidos [inicio](/README.md).

- [Materiales](#materiales)
- [Coneccion de componentes](#coneccion-de-componentes)
- [Usar Thonny](#usar-thonny)
- [Condicionales](#condicionales)
- [Declaraciones if](#declaraciones-if)
- [Flujo de control elif else](#flujo-de-control-elif-else)
- [Or](#)
- [And](#and)
- [Módulo](#módulo)
- [Creando tu propia función de paridad ](#creando-tu-propia-función-de-paridad) 
- [Codificación pitónica](#codificación-pitónica)
- [Pythonic](#pythonic)
- [Match](#match)

## Materiales 
La lista de materiales es:
- 2 protoboard 
- 2 Sensores para deteccion de Luz Ldr
- 2 resistencias
- Esp32
- Cableado Jumper Electrónica "F - F"
- Cable USB tipo A con entrada para micro puerto tipo B
- Computadora
- Aplicación Thonny 

## Coneccion de componentes
Para empezar nesecitaremos conectar nuestro esp32 de manera que conecte las dos ptoboards solicitadas en la lista de materiales. despues utilizaremos nuestro cable de aimentacion para conectar el Esp32 a nuestro computadora. enseguida colocaremos nuestros sensores y resistencias siguiendo el diagrama de la imagen. 

## Usar Thonny
Para empezar a usar Thonny nos ubicamos en la ventana del editor. al ya tener nuestros componentes especificados y conectados empezamos a redactor nuetro codigo.

## Condicionales.
Los condicionales permiten que su programa tome decisiones y elija un camino sobre otro dependiendo de condiciones específicas.

En Python tenemos un conjunto de “operadores” que se utilizan para plantear preguntas matemáticas.

los símbolos probablemente te resulten bastante familiares.
- **>=** denota “mayor o igual a”.
- **<=** denota “menor o igual a”.
- **\==** denota “igual”. Nótese el doble signo igual: un solo signo igual **=** asigna un valor, mientras que dos signos iguales **==** comparan valores.
- **\!\=** denota “no igual a”.

Las declaraciones condicionales comparan un término de la izquierda con un término de la derecha.

## Declaraciones If
En Python, las sentencias **if** se utilizan para tomar decisiones dentro del programa. Estas permiten ejecutar un bloque de código solo cuando una condición se evalúa como verdadera; de lo contrario, el programa puede ejecutar instrucciones alternativas o simplemente continuar su flujo normal.

En la ventana del editor de thonny comenzamos a redactar nuestro ejemplo para empesar a usar **if**. 

![DHT11](/imegen/)

```python
from machine import Pin
import dht
s = dht.DHT11(Pin(15))
s.measure()

x = s.temperature()
y = s.humidity()

print(x)
print(y)

if x < y:
   print("x es menor que y")
   
```
```console
MPY: soft reboot
27
72
x es menor que y
```
Solo especificamos el codigo para que el codigo indique que **"X"** es menor a **"Y"** por lo tanto solo la respuesta señalara lo antes mencionado siendo **Y** mayor que **X**. 

## Ejemplo sensor LDR
```Python 
x = ldr1
y = ldr2

if x < y:
    print("x is less than y")
```

Observe cómo su programa toma la entrada del usuario para x e y, convirtiéndolas en enteros y guardándolas en sus respectivas variables x e y. Luego, la instrucción compara x e y. Si se cumple ifla condición de , se ejecuta la instrucción.x < yprint

ifLas sentencias utilizan boolvalores booleanos ( Trueo False) para decidir si se ejecuta el código. Si la comparación x > yes True, el intérprete ejecuta el bloque con sangría.

## Flujo de control elif, else.
Observe cómo proporciona una serie de <kbd>if</kbd> instrucciones. Primero, <kbd>if</kbd>se evalúa la primera instrucción. Luego, la segunda ifinstrucción ejecuta su evaluación. Finalmente, la última ifinstrucción ejecuta su evaluación. Este flujo de decisiones se denomina "flujo de control".
```Python 
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
if x > y:
    print("x is greater than y")
if x == y:
    print("x is equal to y")
```
Posibles respuestas para los tres casos **if**.

Caso **1** donde **"X"** es menor que **"Y"**. 
```console 
MPY: soft reboot
What's x? 2
What's y? 4
x is less than y
```
Caso **2** donde **"X"** es mayor que **"Y"**.
```console
MPY: soft reboot
What's x? 4
What's y? 2
x is greater than y
```
Caso **3** donde **"X"** y **"Y"** son iguales. 
```console
MPY: soft reboot
What's x? 2
What's y? 2
x is equal to y
```
## Aplicaion de elif
Observe comp el uso de **elif** permite que el programa tome menos decisiones, Primero **if** se evalua la condicion es verdadera, ninguna de las **elif** demas se ejecutara, sin embargo si la **if** se evalua y es falsa, **elif** se evaluara la primera condicion si esta es verdadera, no se ejecutara la evaluacion final.
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
elif x == y:
    print("x is equal to y")
```
Posibles repuestas para los tres casos. **menor**, **mayor** y **igual que**.

```console
MPY: soft reboot
What's x? 4
What's y? 6
x is less than y
```

```console
MPY: soft reboot
What's x? 6
What's y? 2
x is greater than y
```
```console
MPY: soft reboot
What's x? 2
What's y? 2
x is equal to y
```
## Aplicasion de else.
Podemos crear un resultado predeterminado general usando una declarasion else. Podemos revisarlo de la siguiente forma. 
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")
```
Posibles resultados para los tres casos **menor**, **mayor** y **igual** que.
```console
MPY: soft reboot
What's x? 2
What's y? 4
x is less than y
```
```console
MPY: soft reboot
What's x? 4
What's y? 2
x is greater than y
```
```console 
MPY: soft reboot
What's x? 2
What's y? 2
x is equal to y
```
Observe cómo proporciona una serie de ifinstrucciones. Primero, if se evalúa la primera instrucción. Luego, la segunda if instrucción ejecuta su evaluación. Finalmente, la última ifinstrucción ejecuta su evaluación. 

## Aplicasion de Or.
Or Permite que su programa decida entre una o más alternativas. Por ejemplo, podríamos editar nuestro programa de la siguiente manera.
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y or x > y:
    print("x is not equal to y")
else:
    print("x is equal to y")
```
Posibles resultados para los dos casos es **igual** y **no es igual que**.

```consola 
MPY: soft reboot
What's x? 2
What's y? 4
x is not equal to y
```

```consola
MPY: soft reboot
What's x? 3
What's y? 3
x is equal to y
```
en el siguiente ejemplo mejoramos mas aun nuestro programa eliminando el operadr **or**.
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x != y:
    print("x is not equal to y")
else:
    print("x is equal to y")
```
Posibles respuestas para los dos casos es **igual** o **no es igual** que.
```console
MPY: soft reboot
What's x? 4
What's y? 2
x is not equal to y
```
```console
MPY: soft reboot
What's x? 3
What's y? 3
x is equal to y
```
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x == y:
    print("x is equal to y")
else:
    print("x is not equal to y")
```
Posibles  respuestas para los dos casos **no es igual** y es **igual que**. 
```console
MPY: soft reboot
What's x? 2
What's y? 4
x is not equal to y
```
```console 
MPY: soft reboot
What's x? 3
What's y? 3
x is equal to y
```
## And.
Similar a or, and se puede utilizar dentro de declaraciones condicionales.
Ejecútalo en la ventana de terminal, Inicia tu nuevo programa como se indica a continuación:
```Python 
score = int(input("Score: "))

if score >= 90 and score <= 100:
    print("Grade: A")
elif score >=80 and score < 90:
    print("Grade: B")
elif score >=70 and score < 80:
    print("Grade: C")
elif score >=60 and score < 70:
    print("Grade: D")
else:
    print("Grade: F")
```
Posibles resultados 
```consola
MPY: soft reboot
Score: 97
Grade: A
```
Ejemplo Jerry
```python
from machine import ADC, Pin
import time

ldr = ADC(Pin(34))
ldr.atten(ADC.ATTN_11DB)   
ldr.width(ADC.WIDTH_10BIT) 

valor = ldr.read()
print(valor)
score = ldr.read()

if score >= 900 and score <= 1000:
    print("Grade: A")
elif score >=800 and score < 900:
    print("Grade: B")
elif score >=700 and score < 800:
    print("Grade: C")
elif score >=60 and score < 700:
    print("Grade: D")
```
```
MPY: soft reboot
833
Grade: B
```
Observa como en Python pueden encadenarse operadores y condiciones de una manera bastante inusual en otros lenguajes de programacion. 
```Python
score = int(input("Score: "))

  if 90 <= score <= 100:
      print("Grade: A")
  elif 80 <= score < 90:
      print("Grade: B")
  elif 70 <= score < 80:
      print("Grade: C")
  elif 60 <= score < 70:
      print("Grade: D")
  else:
      print("Grade: F")
```
```console

```
```Python
score = int(input("Score: "))

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```
```console
MPY: soft reboot
Score: 97
Grade: A
```

## Módulo.
En matemáticas, la paridad se refiere a si un número es par o impar.
El operador módulo %en programación permite ver si dos números se dividen exactamente o se dividen y tienen resto.
Por ejemplo, 4 % 2 resultaría en cero, ya que es un divisor exacto. Sin embargo, 3 % 2 no es un divisor exacto y resultaría en un número distinto de cero.
En la ventana de terminal, crea un nuevo programa escribiendo code parity.py. En el editor de texto, escribe el código como se indica a continuación:
```Python
x = int(input("What's x? "))

if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```
Posibles respuestas para los dos casos par e impar Even, Odd. 
```console 
MPY: soft reboot
What's x? 4
Even
```
```console
MPY: soft reboot
What's x? 5
Odd
```

## Creando tu propia función de paridad.
Como se discutió en la lección 0, ¡te resultará útil crear una función propia!
Podemos crear nuestra propia función para comprobar si un número es par o impar. Ajusta tu código como sigue:
```Python
def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")


def is_even(n):
    if n % 2 == 0:
        return True
    else:
        return False


main()
```
Posibles respuestas para los dos casos par e impar Even y Odd 
```console
MPY: soft reboot
What's x? 2
Even
```
```console
MPY: soft reboot
What's x? 3
Odd
```

## Pythonic
En el mundo de la programación, existen tipos de programación que se denominan "Pythonic". Es decir, existen formas de programar que a veces solo se ven en la programación Python. Considere la siguiente revisión de nuestro programa:
```Python
def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")


def is_even(n):
    return True if n % 2 == 0 else False


main()
```
Posibles respuestas para los dos casos par e impar Even, Odd. 
```console
MPY: soft reboot
What's x? 2
Even
```
```console
MPY: soft reboot
What's x? 3
Odd
```
Observe que esta declaración de retorno en nuestro código es casi como una oración en inglés. Esta es una forma única de codificar que solo se ve en Python.

Podemos revisar aún más nuestro código y hacerlo cada vez más legible:
```python
def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")


def is_even(n):
    return n % 2 == 0


main()
```
Posibles respuestas para los dos casos par e impar Even, Odd. 
```console
MPY: soft reboot
What's x? 2
Even
```
```console
MPY: soft reboot
What's x? 3
Odd
```
## Match
De manera similar a las declaraciones if, elif, y else, matchlas declaraciones se pueden usar para ejecutar código condicional que coincida con ciertos valores.

```Python 
 name = input("What's your name? ")

  if name == "Harry":
      print("Gryffindor")
  elif name == "Hermione":
      print("Gryffindor")
  elif name == "Ron": 
      print("Gryffindor")
  elif name == "Draco":
      print("Slytherin")
  else:
      print("Who?")
```
Posibles respuestas para los 4 Nombres definidos en nuestro codigo. **Harry**, **Hermione**, **Ron** y **Draco**. En caso de ser otro Nombre la respuesta sera, Who?
```console
MPY: soft reboot
What's your name? Harry
Gryffindor
```
```console
MPY: soft reboot
What's your name? Hermione
Gryffindor
```
```console
MPY: soft reboot
What's your name? Ron
Gryffindor
```
```console
MPY: soft reboot
What's your name? Draco
Slytherin
```
```console
MPY: soft reboot
What's your name? Lovegood 
Who?
```
En nuestro suguiente ejemplo implementaremos **Or**.para que asi mejoremos un poco nuestro codigo.
```Python
 name = input("What's your name? ")

  if name == "Harry" or name == "Hermione" or name == "Ron": 
      print("Gryffindor")
  elif name == "Draco":
      print("Slytherin")
  else:
      print("Who?")
```

```console
MPY: soft reboot
What's your name? Harry
Gryffindor
```
```console
MPY: soft reboot
What's your name? Herione
Gryffindor
```
```console
MPY: soft reboot
What's your name? Ron
Gryffindor
```
```console
MPY: soft reboot
What's your name? Draco
Slytherin
```
```console
MPY: soft reboot
What's your name? Lovegood
Who?
```
EJEMPLOS MATH DAN ERROR, en Thonny.

```Python
name = input("What's your name? ")

match name: 
      case "Harry":
          print("Gryffindor")
      case "Hermione":
          print("Gryffindor")
      case "Ron": 
          print("Gryffindor")
      case "Draco":
          print("Slytherin")
      case _:
          print("Who?")
```
```console

```
```Python
 name = input("What's your name? ")

  match name: 
      case "Harry" | "Hermione" | "Ron":
          print("Gryffindor")
      case "Draco":
          print("Slytherin")
      case _:
          print("Who?")
```
```console

```
