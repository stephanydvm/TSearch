# Taboo Search
> Taboo Search Algorithm with a complete matrix.


## Install

`pip install TSearch`

## How to use

Aquí el algoritmo.

Recibes el número de ciudades:

```
N = int(input("Numero de ciudades: "))
```

Recibes el número máximo de iteraciones

```
I_max = int(input("Maximo de iteraciones: "))
```

Recibes la matriz de costos de una ciudad a otra

```
mat_cost = entrada(N)
```

Encuentras una solución inicial con el método _Greedy_

```
CT, best_sol = greedy(N,mat_cost)
```

Inicializas el contador de iteraciones, la lista Taboo como conjunto vacío, y el nuevo elemento a insertar en la lista Taboo.

```
k = 0
Taboo = {}
new_T = None
```

Y mientras las iteraciones no lleguen al máximo:

```
while k < I_max:
    # Determinar el vecindario
    new_T, V = vecindario(N,best_sol,Taboo.keys())
    # Determinar la nueva mejor solución
    best_sol = new_best(best_sol,V)
    # Actualizar k
    k += 1
    # Actualizar la lista Taboo
    Taboo = update_T(Taboo)
```

```
print(f(best_sol), best_sol)
```

Ejemplo:

Con la siguiente entrada:

10 <br>
100 <br>
49 30 53 72 19 76 87 45 48<br>
19 38 32 31 75 69 61 25<br>
41 98 56 6 6 45 53<br>
52 29 46 90 23 98<br>
63 90 69 50 82<br>
60 88 41 95<br>
61 92 10<br>
82 73<br>
5<br>

Debe obtener el siguiente resultado:<br>
248 [0, 5, 3, 8, 9, 6, 2, 7, 4, 1]
