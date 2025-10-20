# Bibliotecas.
Bienbenidos [inicio](/README.md).

- [Bibliotecas](#bibliotecas)
- [Aleatorio](#aleatorio)
- [Estadistica](#estadistica)
- [Argumentos de linea de comandos](#argumentos-de-linea-de-comandos)
- [Slice](#slice)
- [Paquetes](#paquetes)
- [API](#api)
- [Creando tus propias bibliotecas](#creando-tus-propias-bibliotecas)
- [Resumiendo](#resumiendo)

## Bibliotecas.
Generalmente, las bibliotecas son fragmentos de código escritos por usted u otros y que puede utilizar en su programa.
Python le permite compartir funciones o características con otros como “módulos”.
Si copia y pega código de un proyecto antiguo, es posible que pueda crear un módulo o biblioteca que pueda incorporar a su nuevo proyecto.

## Aleatorio.
randomEs una biblioteca que viene con Python y que puedes importar a tu propio proyecto.
Para un programador es más fácil apoyarse en los hombros de los programadores anteriores.
Entonces, ¿cómo se carga un módulo en el programa? Puedes usar la palabra importen el programa.
Dentro del randommódulo, hay una función integrada llamada random.choice(seq). randomque es el módulo que estás importando. Dentro de ese módulo, se encuentra la choicefunción . Esta función acepta una seqsecuencia o una lista.

```Python
import random

coin = random.choice(["heads", "tails"])
print(coin)
```
## Estadistica.
Python incluye una biblioteca integrada statistics. ¿Cómo podríamos usar este módulo?
meanEs una función de esta biblioteca muy útil. En la ventana de terminal, escribe code average.py. En el editor de texto, modifica tu código de la siguiente manera:
```Python
import statistics

print(statistics.mean([100, 90]))
```

## Argumentos de linea de comandos.
Hasta ahora, hemos proporcionado todos los valores dentro del programa que hemos creado. ¿Qué sucedería si quisiéramos obtener información desde la línea de comandos? Por ejemplo, en lugar de escribir python average.pyen la terminal, ¿qué sucedería si quisiéramos escribir python average.py 100 90y obtener el promedio entre 100y 90?
syses un módulo que nos permite tomar argumentos en la línea de comando.
argves una lista dentro del sysmódulo que registra lo que el usuario escribió en la línea de comando.
Observa cómo se sys.argvutiliza en el código a continuación. En la ventana de terminal, escribe code name.py. En el editor de texto, escribe lo siguiente:
```Python
import sys

print("hello, my name is", sys.argv[1])
```
## Slice.
sliceEs un comando que nos permite tomar un `a` liste indicarle al intérprete dónde queremos que considere el inicio listy el final de ` list. Por ejemplo, modifique su código de la siguiente manera:

## Paquetes.
Una de las razones por las que Python es tan popular es la existencia de numerosas y potentes bibliotecas de terceros que añaden funcionalidad. Estas bibliotecas, implementadas como una carpeta, se denominan «paquetes».
PyPI es un repositorio o directorio de todos los paquetes de terceros disponibles actualmente.
cowsayEs un paquete conocido que permite a una vaca hablar con el usuario.
Python tiene un administrador de paquetes llamado pipque le permite instalar paquetes rápidamente en su sistema.
En la ventana de terminal, puedes instalar el cowsaypaquete escribiendo pip install cowsay. Tras un breve resultado, ya puedes usar este paquete en tu código.
En la ventana de terminal, escribe code say.py. En el editor de texto, escribe el código de la siguiente manera:

## API.
Las API o “interfaces de programación de aplicaciones” le permiten conectarse al código de otros.
requestses un paquete que permite que su programa se comporte como lo haría un navegador web.
En tu terminal, escribe pip install requests. Luego, escribe code itunes.py.
Resulta que Apple iTunes tiene su propia API a la que puedes acceder desde tus programas. En tu navegador, puedes visitar https://itunes.apple.com/search?entity=song&limit=1&term=weezer y se descargará un archivo de texto. David creó esta URL consultando la documentación de la API de Apple. Observa cómo esta consulta busca un [nombre de la consulta] song, con un [ nombre de la consulta limit] de un resultado, relacionado con el [ nombre de la termconsulta] llamado weezer. Al observar este archivo de texto descargado, es posible que el formato sea similar al que programamos previamente en Python.
El formato del archivo de texto descargado se llama JSON, un formato basado en texto que se utiliza para intercambiar datos textuales entre aplicaciones. Literalmente, Apple proporciona un archivo JSON que podemos interpretar en nuestro propio programa Python.
En la ventana de terminal, escribe code itunes.py. Código:
```Python
import requests
import sys

if len(sys.argv) != 2:
    sys.exit()

response = requests.get("https://itunes.apple.com/search?entity=song&limit=1&term=" + sys.argv[1])
print(response.json())
```

## Creando tus propias bibliotecas.
¡Como programador Python tienes la capacidad de crear tu propia biblioteca!
¡Imagina situaciones en las que quizás quieras reutilizar fragmentos de código una y otra vez o incluso compartirlos con otros!
Hemos escrito mucho código para decir "hola" en este curso. Vamos a crear un paquete que nos permita decir "hola" y "adiós". En la ventana de tu terminal, escribe code sayings.py. En el editor de texto, escribe lo siguiente:
```Python
def hello(name):
    print(f"hello, {name}")


def goodbye(name):
    print(f"goodbye, {name}")
```

## Resumiendo

