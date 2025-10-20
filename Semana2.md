# Bucles. 
Bienbenidos [inicio](/README.md).

- [Bucles](#bucles)
- [Bucles while](#bucles-while)
- [Bucles for](#bucles-for)
- [Mejorando con la entrada del Usuario](#mejorando-con-la-entrada-del-usuario)
- [Mas sobre las listas](#mas-sobre-las-listas)
- [Longitud](#longitud)
- [Diccionarios](#diccionarios)
- [Mario](#mario)
- [Resumiendo](#resumiendo)

## Bucles.
 Básicamente, los bucles son una forma de hacer algo una y otra vez.
Comience escribiendo code cat.pyen la ventana del terminal.
En el editor de texto, comience con el siguiente código:
```Python 
print("meow")
print("meow")
print("meow")
```
## Bucles While.
El whilebucle es casi universal en todos los lenguajes de codificación.
Un bucle de este tipo repetirá un bloque de código una y otra vez.
En la ventana del editor de texto, edite su código de la siguiente manera:
```Python
i = 3
while i != 0:
    print("meow")
```
```Python 
i = 3
while i != 0:
  print("meow")
  i = i - 1
```
```Python
  i = 1
  while i <= 3:
      print("meow")
      i = i + 1
```
```Python
i = 0
while i < 3:
    print("meow")
    i += 1
```
## Bucles for.

Un forbucle es un tipo diferente de bucle.
Para comprender mejor un forbucle, conviene empezar hablando de un nuevo tipo de variable llamado a listen Python. Como en otras áreas de nuestra vida, podemos tener una lista de la compra, una lista de tareas, etc.
Un forbucle itera sobre un listconjunto de elementos. Por ejemplo, en la ventana del editor de texto, modifique su cat.pycódigo de la siguiente manera: 

```Python
for i in [0, 1, 2]:
    print("meow")
```
```Python
for i in range(3):
    print("meow")
```
```Python
for _ in range(3):
    print("meow")
```
```Python
print("meow" * 3)
``` 
```Python
print("meow\n" * 3, end="")
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
```Python
while True:
    n = int(input("What's n? "))
    if n > 0:
        break

for _ in range(n):
    print("meow")
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
```Python
students = ["Hermione", "Harry", "Ron"]

for student in students:
    print(student)
```

## Longitud.
Podemos utilizarlo lencomo una forma de comprobar la longitud del listllamado students.
Imagina que no solo quieres imprimir el nombre del estudiante, sino también su posición en la lista. Para ello, puedes editar tu código de la siguiente manera:

```
students = ["Hermione", "Harry", "Ron"]

for i in range(len(students)):
    print(i + 1, students[i])
```

## Diccionarios.
dictLos diccionarios o s son una estructura de datos que permite asociar claves con valores.
Donde a listes una lista de múltiples valores, a dictasocia una clave con un valor.
Considerando las casas de Hogwarts, podríamos asignar estudiantes específicos a casas específicas.
```Pyhton
students = ["Hermione", "Harry", "Ron", "Draco"]
houses = ["Gryffindor", "Gryffindor", "Griffindor", "Slytherin"]
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
```Python
$ python hogwarts.py
Gryffindor
Gryffindor
Gryffindor
Slytherin
```
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
```Python
students = [
    {"name": "Hermione", "house": "Gryffindor", "patronus": "Otter"},
    {"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
    {"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]
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
```Python
for _ in range(3):
    print("#")

```
```Python
def main():
    print_column(3)


def print_column(height):
    for _ in range(height):
        print("#")


main()
```
```Python
def main():
    print_row(4)


def print_row(width):
    print("?" * width)


main()
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
## Resumiendo


