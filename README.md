# To `join()` or not to `join()`...

En `dormilones.py` vimos tres ejemplos básicos de ejecución:

- Clásico secuencial,
- Con threads,
- Y con threads, pero esperando a que terminen usando `join()`.

Entonces responda:
- ¿Por qué los segundos que se imprimen que pasaron son 2, 0 y 1 (aprox.) respectivamente?
En el primer caso se ejecuta el codigo secuencialmente y cada uno dura 1seg, en el segundo caso hay hilos que se ejecutan fuera del main y en el tercer caso hay un join que espera que terminen los hilos para avanzar
- ¿Cuántos hilos o threads hay en cada caso?
En el primer caso hay 2 hilos y en los otros dos hay 3 hilos
- Los últimos dos ejemplos tienen la misma cantidad de threads cada uno, ¿cuál sería la diferencia entonces?
La diferecia es el join que espera a que termine de ejecutarse una linea para pasar a la otra
- En el último ejemplo, ¿qué desventaja o desventajas le ve al uso del `join()`?


# Muchos threads

En `muchosThreads.py` hay algunas cosas básicas de Python:
- `from tiempo import Contador` importa desde `tiempo.py` la clase `Contador`.
- Cómo crear una lista vacía.
- Cómo hacer un loop con cantidad de iteraciones fija.
- Cómo agregar elementos (al final) a una lista.
- Cómo hacer un loop que itere sobre una lista.

## Parte 1
Mirá el código y fijate de entender la sintaxis. 

## Parte 2
Ahora corré el script: ¿por qué tarda lo que tarda? 


# Intercalación en concurrencia

**Dos reglas importantes** para `contadorConcurrente.py`:
- Mirá el código pero _no lo ejecutes_,
- Mirá el código pero _no lo ejecutes_.

(Referencia [The First Rule of Fight Club (1999)](https://www.youtube.com/watch?v=dC1yHLp9bWA))

Mirando el código de `contadorConcurrente.py`, pero sin ejecutarlo:
- Al ejecutar la función `cuenta()`, ¿cuántas veces se ejecuta el `for` que tiene adentro, y qué hace cada iteración del `for`?
El 'for' se ejecuta 500000 veces y en cada iteracion suma 1 a la variable counter
- ¿Es verdad que cada thread lanza una ejecución de la función `cuenta()`?
Podria ser
- ¿Es verdad que se está esperando a que termine cada thread?
No
- ¿Cúal te parece que es el valor que se imprime de `counter`?
500000

Ahora corré `contadorConcurrente.py`:
- Correlo varias veces, ¿qué observás que pasa?
El valor cambia
- ¿Por qué está pasando eso que observás?
Al acceder a la misma variable las cuentas son distintas

# ¿Secuencial clásico, concurrente o paralelo?

Para cada una de las siguiente situaciones, decidí si es secuencial clásico, concurrente o paralelo. Intentá justificar señalando las ideas esenciales de cada caso.

- Cuál persona de un total de 50 corre más rápido una maratón.
    - opción 1) Cada persona corre secuencialmente en la pista, y medimos cada tiempo.
    Secuencial clásico, corren por turnos.
    - opción 2) Todas las personas corren en la misma pista, y la que llega primero listo.
    Concurrente.
		- Preguntas: ¿hay algún recurso compartido? ¿genera problemas?
    Se compartiria la pista, si es chica no entraria toda la gente.
    - opción 3) Cada persona corre en una pista distinta, todas al mismo tiempo.
    Paralelo
		- Pregunta: ¿hay un aumento de recursos respecto al anterior?
    Aumentaria el numero de pistas ya que se necesita una para cada competidor.
    - Pregunta: ¿pros y contras de cada opción?
    Opcion 1: Larga duracion pero no se usan tantos recursos.
    Opcion 2: Tendria una corta duracion y podrian surgir problemas al compartir recursos.
    Opcion 3: Corta duracion pero se usarian muchos recursos.

- Competencia de triples en basquet: quién mete más en 10 intentos.
    - opción 1) Cada persona secuencialmente realiza 10 intentos, y anotamos la cantidad de triples.
    Secuencial clásico, tiran por turnos.
    - opción 2) Todas las personas tiran los 10 intentos al mismo tiempo.
    Concurrente.
		- Preguntas: ¿hay algún recurso compartido? ¿genera problemas?
    "Todas las personas tiran los 10 intentos al mismo tiempo", no dice si en el mismo aro o 
    con la misma pelota. Si es asi, al compartir el aro seria casi imposible realizar la actividad.
    - opción 3) Cada persona tira en un aro distinto, todas al mismo tiempo.
    Paralelo.
    - Pregunta: ¿pros y contras de cada opción?
    Opcion 1: No se usaria muchos recuros pero tardaria en terminar.
    Opcion 2: Rapido pero con problemas si se comparten recursos.
    Opcion 3: Se usan muchos recursos pero tarda poco.
