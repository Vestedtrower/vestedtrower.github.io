# E\S de archivos

Bienbenidos [inicio](/README.md).

- [E/S de archivos](#es-de-archivos)
- [open](#open)
- [with](#with)
- [CSV](#csv)
- [Archivos binarios y PIL](#archivos-binarios-y-pil)

## E\S de archivos
Hasta ahora, todo lo que hemos programado almacena información en la memoria. Es decir, al finalizar el programa, se pierde toda la información recopilada del usuario o generada por el programa.
La E/S de archivos es la capacidad de un programa de tomar un archivo como entrada o crear un archivo como salida.
Para comenzar, en la ventana de terminal escriba code names.pyy codifique lo siguiente:
```Python
name = input("What's your name?" )
print(f"hello, {name}")
```

```Python
names = []

for _ in range(3):
    name = input("What's your name?" )
    names.append(name)
```

```Python
names = []

for _ in range(3):
    names.append(input("What's your name?" ))
```

```Python
names = []

for _ in range(3):
    names.append(input("What's your name?" ))

for name in sorted(names):
    print(f"hello, {name}")
```

## open
openEs una funcionalidad integrada en Python que permite abrir un archivo y utilizarlo en un programa. Esta openfunción permite abrir un archivo para poder leerlo o escribir en él.

```Python
name = input("What's your name? ")

file = open("names.txt", "w")
file.write(name)
file.close()
```

```Python
name = input("What's your name? ")

file = open("names.txt", "a")
file.write(name)
file.close()
```

```Python
name = input("What's your name? ")

file = open("names.txt", "a")
file.write(f"{name}\n")
file.close()
```

## with
La palabra clave withpermite automatizar el cierre de un archivo.

```Python
name = input("What's your name? ")

with open("names.txt", "a") as file:
    file.write(f"{name}\n")
```

```Python
with open("names.txt", "r") as file:
    lines = file.readlines()

for line in lines:
    print("hello,", line)
```

```Python
with open("names.txt", "r") as file:
    lines = file.readlines()

for line in lines:
    print("hello,", line.rstrip())
```

```Python
with open("names.txt", "r") as file:
    for line in file:
        print("hello,", line.rstrip())
```

```Python
names = []

with open("names.txt") as file:
    for line in file:
        names.append(line.rstrip())

for name in sorted(names):
    print(f"hello, {name}")
```

## CSV
CSV significa “valores separados por comas”.
En la ventana de tu terminal, escribe code students.csv. Asegúrate de que tu nuevo archivo CSV tenga el siguiente aspecto:

```Python
Hermione,Gryffindor
Harry,Gryffindor
Ron,Gryffindor
Draco,Slytherin
```

```Python
with open("students.csv") as file:
    for line in file:
        row = line.rstrip().split(",")
        print(f"{row[0]} is in {row[1]}")
```

```Python
with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        print(f"{name} is in {house}")
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        students.append(f"{name} is in {house}")

for student in sorted(students):
    print(student)
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        student = {}
        student["name"] = name
        student["house"] = house
        students.append(student)

for student in students:
    print(f"{student['name']} is in {student['house']}")
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        student = {"name": name, "house": house}
        students.append(student)

for student in students:
    print(f"{student['name']} is in {student['house']}")
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        students.append({"name": name, "house": house})


def get_name(student):
    return student["name"]


for student in sorted(students, key=get_name):
    print(f"{student['name']} is in {student['house']}")
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, house = line.rstrip().split(",")
        students.append({"name": name, "house": house})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is in {student['house']}")
```

```Python
Harry,"Number Four, Privet Drive"
Ron,The Burrow
Draco,Malfoy Manor
```

```Python
students = []

with open("students.csv") as file:
    for line in file:
        name, home = line.rstrip().split(",")
        students.append({"name": name, "home": home})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is in {student['home']}")
```

```Python
import csv

students = []

with open("students.csv") as file:
    reader = csv.reader(file)
    for row in reader:
        students.append({"name": row[0], "home": row[1]})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is from {student['home']}")
```

```Python
name,home
Harry,"Number Four, Privet Drive"
Ron,The Burrow
Draco,Malfoy Manor
```

```Python
import csv

students = []

with open("students.csv") as file:
    reader = csv.DictReader(file)
    for row in reader:
        students.append({"name": row["name"], "home": row["home"]})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is in {student['home']}")
```

```Python
import csv

name = input("What's your name? ")
home = input("Where's your home? ")

with open("students.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames=["name", "home"])
    writer.writerow({"name": name, "home": home})
```


## Archivos binarios y PIL
Otro tipo de archivo que analizaremos hoy es el binario. Un archivo binario es simplemente una colección de unos y ceros. Este tipo de archivo puede almacenar cualquier cosa, incluyendo música e imágenes.
Existe una biblioteca de Python popular llamada PILque funciona bien con archivos de imagen.
Los GIF animados son un tipo popular de archivo de imagen que contiene muchos archivos de imagen que se reproducen en secuencia una y otra vez, creando una animación o un efecto de video simplista.
Imaginemos que tenemos una serie de disfraces, como se ilustra a continuación.
Aquí está costume1.gif.

```Python
import sys

from PIL import Image

images = []

for arg in sys.argv[1:]:
    image = Image.open(arg)
    images.append(image)

images[0].save(
    "costumes.gif", save_all=True, append_images=[images[1]], duration=200, loop=0
)

```

