# Condicionales. 

Bienbenidos [inicio](/README.md).

- [Condicionales](#condicionales)
- [Declaraciones if]()
- [Flujo de control elif else]()
- [Or]()
- [And]()
- [Módulo]()
- [Creando tu propia función de paridad ]() 
- [Codificación pitónica]()
- [y match]()

## Condicionales.
Un condicional 
Los condicionales le permiten a usted, el programador, permitir que su programa tome decisiones: como si su programa tuviera la opción de tomar el camino de la izquierda o el de la derecha en función de ciertas condiciones.
Los condicionales permiten que su programa tome decisiones y elija un camino sobre otro dependiendo de condiciones específicas.
Dentro de Python hay un conjunto de “operadores” que se utilizan para plantear preguntas matemáticas.

>y <los símbolos probablemente te resulten bastante familiares.
>=denota “mayor o igual a”.
<=denota “menor o igual a”.
==denota “igual”. Nótese el doble signo igual: un solo signo igual asigna un valor, mientras que dos signos iguales comparan valores.
!=denota “no igual a”.
Las declaraciones condicionales comparan un término de la izquierda con un término de la derecha.

## Declaraciones If.
En la ventana de tu terminal, escribe code compare.py. Esto creará un nuevo archivo llamado "comparar".
En la ventana del editor de texto, comience con lo siguiente:
```Python 
x = ldr1
y = ldr2

if x < y:
    print("x is less than y")

```
Observe cómo su programa toma la entrada del usuario para x e y, convirtiéndolas en enteros y guardándolas en sus respectivas variables x e y. Luego, la instrucción compara x e y. Si se cumple ifla condición de , se ejecuta la instrucción.x < yprint

ifLas sentencias utilizan boolvalores booleanos ( Trueo False) para decidir si se ejecuta el código. Si la comparación x > yes True, el intérprete ejecuta el bloque con sangría.

## Flujo de control elif, else.
Revise aún más su código de la siguiente manera:
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
```Python

Observe cómo proporciona una serie de ifinstrucciones. Primero, ifse evalúa la primera instrucción. Luego, la segunda ifinstrucción ejecuta su evaluación. Finalmente, la última ifinstrucción ejecuta su evaluación. 

## Or.
orPermite que su programa decida entre una o más alternativas. Por ejemplo, podríamos editar nuestro programa de la siguiente manera:
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y or x > y:
    print("x is not equal to y")
else:
    print("x is equal to y")
```
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x != y:
    print("x is not equal to y")
else:
    print("x is equal to y")
```
```Python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x == y:
    print("x is equal to y")
else:
    print("x is not equal to y")
```

## And.
Similar a or, andse puede utilizar dentro de declaraciones condicionales.
Ejecútalo en la ventana de terminal code grade.py. Inicia tu nuevo programa como se indica a continuación:
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

## Codificación Pitónica.
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
## Pythonic

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
```Python
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
## Match

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

```Python
 name = input("What's your name? ")

  if name == "Harry" or name == "Hermione" or name == "Ron": 
      print("Gryffindor")
  elif name == "Draco":
      print("Slytherin")
  else:
      print("Who?")
```
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
