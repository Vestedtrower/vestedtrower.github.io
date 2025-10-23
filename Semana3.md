# Excepciones.
Bienbenidos [inicio](/README.md).

- [Excepciones](#excepciones)
- [Errores de tiempo de ejecucion](#errores-de-tiempo-de-ejecucion)
- [try](#try)
- [else](#else)
- [Creacion de una funcion para obtener un entero](#creación-de-una-función-para-obtener-un-entero)
- [Pass](#pass)

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
Esta aún no es la mejor manera de implementar este código. Observe que estamos intentando ejecutar dos líneas de código. Para una mejor práctica, deberíamos usar solo tryla menor cantidad posible de líneas de código que nos preocupen que puedan fallar. Ajuste su código de la siguiente manera:
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
Tenga en cuenta que si no se produce ninguna excepción, se ejecutará el bloque de código dentro de [nombre de la excepción else]. Al ejecutar [nombre de la excepción python number.py] y proporcionar 50[nombre de la excepción], verá que se imprimirá el resultado. Si lo intenta de nuevo, esta vez proporcionando [nombre de la excepción] cat, notará que el programa detecta el error.

Al considerar mejorar nuestro código, tenga en cuenta que estamos siendo un poco groseros con el usuario. Si no coopera, simplemente finalizamos el programa. Considere cómo podemos usar un bucle para solicitarle al usuario que lo haga xy, si no, solicitarlo de nuevo.
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
Observe que estamos manifestando muchas propiedades excelentes. Primero, hemos abstraído la capacidad de obtener un entero. Ahora, todo el programa se reduce a las tres primeras líneas.

Aun así, podemos mejorar este programa. Piensa en qué más podrías hacer para mejorarlo. Modifica tu código de la siguiente manera:
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
Tenga en cuenta que esto returnno solo lo sacará de un bucle, sino que también devolverá un valor.

Algunas personas podrían argumentar que podría hacer lo siguiente:
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
## Pass 
Podemos hacer que nuestro código no advierta a nuestro usuario, sino que simplemente le vuelva a preguntar nuestra pregunta inicial modificando nuestro código de la siguiente manera:

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





