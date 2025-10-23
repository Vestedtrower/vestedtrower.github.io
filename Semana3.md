# Excepciones.
Bienbenidos [inicio](/README.md).

- [Excepciones](#excepciones)
- [Errores de tiempo de ejecucion](#errores-de-tiempo-de-ejecucion)
- [try](#try)
- [else](#else)
- [Creacion de una funcion para obtener un entero](#creación-de-una-función-para-obtener-un-entero)

## Excepciones.
Las excepciones son cosas que salen mal dentro de nuestra codificación.
Las excepciones son problemas que surgen mientras el programa se está ejecutando.
En nuestro editor de texto, escriba code hello.pypara crear un nuevo archivo. Escriba lo siguiente (con los errores intencionales incluidos).

```Python
print("hello, world)
```

## Errores de tiempo de ejecucion.
Los errores de ejecución se refieren a aquellos generados por un comportamiento inesperado en el código. Por ejemplo, quizás se pretendía que un usuario ingresara un número, pero en su lugar se ingresa un carácter. El programa podría generar un error debido a esta entrada inesperada del usuario.
En la ventana de terminal, ejecute code number.py. Codifique de la siguiente manera en su editor de texto:
```Python
x = int(input("What's x? "))
print(f"x is {x}")
```
```console
MPY: soft reboot
What's x? 2
x is 2
```
## Try.
En Python try, y exceptson formas de probar la entrada del usuario antes de que algo falle. Modifique su código de la siguiente manera:
```Python
try:
    x = int(input("What's x?"))
    print(f"x is {x}")
except ValueError:
    print("x is not an integer")
```
Posibles respuestas:

```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
```
```Python
try:
    x = int(input("What's x?"))
except ValueError:
    print("x is not an integer")

print(f"x is {x}")
```
Posibles respuestas:
```console
MPY: soft reboot
What's x? 22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
```

## Else.
Resulta que hay otra forma de implementar tryque podría detectar errores de esta naturaleza.

Ajuste su código de la siguiente manera:
```Python
try:
    x = int(input("What's x?"))
except ValueError:
    print("x is not an integer")
else:
    print(f"x is {x}")
```
Posibles respuestas:

```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
```

```Python
while True:
    try:
        x = int(input("What's x?"))
    except ValueError:
        print("x is not an integer")
    else:
        break

print(f"x is {x}")
```
```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
What's x?
```

## Creación de una función para obtener un entero.
Seguramente, muchas veces querríamos obtener un entero de nuestro usuario. Modifique su código de la siguiente manera:

```Python
def main():
    x = get_int()
    print(f"x is {x}")


def get_int():
    while True:
        try:
            x = int(input("What's x?"))
        except ValueError:
            print("x is not an integer")
        else:
            break
    return x


main()
```
```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
What's x?
```

```Python
def main():
    x = get_int()
    print(f"x is {x}")


def get_int():
    while True:
        try:
            x = int(input("What's x?"))
        except ValueError:
            print("x is not an integer")
        else:
            return x


main()
```
```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
What's x?
```
```Python
def main():
    x = get_int()
    print(f"x is {x}")


def get_int():
    while True:
        try:
            return int(input("What's x?"))
        except ValueError:
            print("x is not an integer")


main()
```
```console
MPY: soft reboot
What's x?22
x is 22
```
```console
MPY: soft reboot
What's x?cat
x is not an integer
What's x?
```

```Python
def main():
    x = get_int()
    print(f"x is {x}")


def get_int():
    while True:
        try:
            return int(input("What's x?"))
        except ValueError:
            pass


main()
```
```console
MPY: soft reboot
What's x?22
x is 22
```
```console

```

```Python
def main():
    x = get_int("What's x? ")
    print(f"x is {x}")


def get_int(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            pass


main()
```
```console
MPY: soft reboot
What's x? 22
x is 22
```





