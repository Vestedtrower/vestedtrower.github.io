# Pruebas Unitarias

Bienbenidos [inicio](/README.md).

- [Pruebas unitarias](#pruebas-unitarias)
- [assert](#assert)
- [pytest](#pytest)
- [Prueba de cadenas](#prueba-de-cadenas)
- [Organizar pruebas en carpetas](#organizar-pruebas-en-carpetas)
- [Resumiendo](#resumiendo)

## Pruebas Unitarias
Hasta ahora, probablemente has estado probando tu propio código usando printdeclaraciones.
¡Alternativamente, es posible que hayas estado confiando en CS50 para probar tu código por ti!
Lo más común en la industria es escribir código para probar sus propios programas.
En la ventana de la consola, escribe code calculator.py. Ten en cuenta que es posible que ya hayas codificado este archivo en una lección anterior. En el editor de texto, asegúrate de que tu código aparezca así:

```Python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n * n


if __name__ == "__main__":
    main()

```


## assert
El comando de Python assertnos permite indicar al intérprete que una afirmación es verdadera. Podemos aplicar esto a nuestro código de prueba de la siguiente manera:

## pytest
pytestEs una biblioteca de terceros que permite realizar pruebas unitarias en el programa. Es decir, permite probar las funciones dentro del programa.
Para utilizarlo pytest, escriba pip install pytesten la ventana de su consola.
Antes de aplicar pytesta nuestro propio programa, modifique su test_squarefunción de la siguiente manera:

## Prueba de cadenas
Retrocediendo en el tiempo, considere el siguiente código hello.py:

## Organizar pruebas en carpetas
Las pruebas unitarias de código que utilizan múltiples pruebas son tan comunes que es posible ejecutar una carpeta completa de pruebas con un solo comando.
Primero, en la ventana del terminal, ejecute mkdir testpara crear una carpeta llamada test.
Luego, para crear una prueba dentro de esa carpeta, escriba en la ventana de terminal code test/test_hello.py. Observe que test/indica a la terminal que cree test_hello.pyen la carpeta llamada test.

## Resumiendo
