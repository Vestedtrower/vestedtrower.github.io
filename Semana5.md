# Pruebas Unitarias

Bienbenidos [inicio](/README.md).

- [Pruebas unitarias](#pruebas-unitarias)
- [assert](#assert)
- [pytest](#pytest)
- [Prueba de cadenas](#prueba-de-cadenas)
- [Organizar pruebas en carpetas](#organizar-pruebas-en-carpetas)

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

```Python
from calculator import square


def main():
    test_square()


def test_square():
    if square(2) != 4:
        print("2 squared was not 4")
    if square(3) != 9:
        print("3 squared was not 9")


if __name__ == "__main__":
    main()
```

## assert
El comando de Python assertnos permite indicar al intérprete que una afirmación es verdadera. Podemos aplicar esto a nuestro código de prueba de la siguiente manera:

```Python
from calculator import square


def main():
    test_square()


def test_square():
    assert square(2) == 4
    assert square(3) == 9


if __name__ == "__main__":
    main()
```

```Python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n + n


if __name__ == "__main__":
    main()
```

```Python
from calculator import square


def main():
    test_square()


def test_square():
    try:
        assert square(2) == 4
    except AssertionError:
        print("2 squared is not 4")
    try:
        assert square(3) == 9
    except AssertionError:
        print("3 squared is not 9")
    try:
        assert square(-2) == 4
    except AssertionError:
        print("-2 squared is not 4")
    try:
        assert square(-3) == 9
    except AssertionError:
        print("-3 squared is not 9")
    try:
        assert square(0) == 0
    except AssertionError:
        print("0 squared is not 0")


if __name__ == "__main__":
    main()
```
## pytest
pytestEs una biblioteca de terceros que permite realizar pruebas unitarias en el programa. Es decir, permite probar las funciones dentro del programa.
Para utilizarlo pytest, escriba pip install pytesten la ventana de su consola.
Antes de aplicar pytesta nuestro propio programa, modifique su test_squarefunción de la siguiente manera:

```Python
from calculator import square


def main():
    test_square()


def test_square():
    assert square(2) == 4
    assert square(3) == 9
    assert square(-2) == 4
    assert square(-3) == 9
    assert square(0) == 0
```

```Python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n * n


if __name__ == "__main__":
    main()
```

```Python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n + n


if __name__ == "__main__":
    main()
```

```Python
from calculator import square


def test_positive():
    assert square(2) == 4
    assert square(3) == 9


def test_negative():
    assert square(-2) == 4
    assert square(-3) == 9


def test_zero():
    assert square(0) == 0
```

```Python
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))


def square(n):
    return n * n


if __name__ == "__main__":
    main()
```

```Python
 import pytest

  from calculator import square


  def test_positive():
      assert square(2) == 4
      assert square(3) == 9


  def test_negative():
      assert square(-2) == 4
      assert square(-3) == 9


  def test_zero():
      assert square(0) == 0


  def test_str():
      with pytest.raises(TypeError):
          square("cat")
```

## Prueba de cadenas
Retrocediendo en el tiempo, considere el siguiente código hello.py:

```Python
def main():
    name = input("What's your name? ")
    hello(name)


def hello(to="world"):
    print("hello,", to)


if __name__ == "__main__":
    main()
```
```Python 
from hello import hello


def test_hello():
    assert hello("David") == "hello, David"
    assert hello() == "hello, world"
```
```Python
from hello import hello


def test_default():
    assert hello() == "hello, world"


def test_argument():
    assert hello("David") == "hello, David"
```

## Organizar pruebas en carpetas
Las pruebas unitarias de código que utilizan múltiples pruebas son tan comunes que es posible ejecutar una carpeta completa de pruebas con un solo comando.
Primero, en la ventana del terminal, ejecute mkdir testpara crear una carpeta llamada test.
Luego, para crear una prueba dentro de esa carpeta, escriba en la ventana de terminal code test/test_hello.py. Observe que test/indica a la terminal que cree test_hello.pyen la carpeta llamada test.

```Python
from hello import hello
  
  
def test_default():
    assert hello() == "hello, world"
  
  
def test_argument():
    assert hello("David") == "hello, David"
```


