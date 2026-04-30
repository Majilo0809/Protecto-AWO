
# AWO - Lenguaje de Programación

AWO es un lenguaje de programación interpretado desarrollado en Python usando ANTLR4.  
Permite ejecutar programas con variables, funciones, estructuras de control y librerías externas como **mate** y **paint**.

---

#  Características del lenguaje

-  Variables
-  Operaciones matemáticas básicas
-  Funciones con return
-  Condicionales (`if / else`)
-  Ciclos (`while`)
-  Importación de librerías
-  Sistema de memoria con scopes
-  Evaluación de expresiones
-  Librerías externas (matemática y dibujo)

---

#  Requisitos

- Python 3.10+
- antlr4-python3-runtime

Instalación:

```
pip install antlr4-python3-runtime
````

---

#  Estructura del proyecto

```
AWO/
│
├── principal.py        # Punto de entrada del intérprete
├── interprete.py       # Visitor que ejecuta el código
├── memoria.py          # Manejo de memoria por scopes
├── indentador.py       # Manejo de indentación tipo Python
├── AWO.g4              # Gramática del lenguaje
│
├── librerias/
│   ├── mate/           # Librería matemática
│   ├── paint/          # Librería gráfica en consola
│   └── base.py         # Sistema base de librerías
│
├── generado/           # Parser generado por ANTLR
└── programa.awo        # Archivo de pruebas
```

---

#  Cómo ejecutar

1. Escribe tu código en `programa.awo`
2. Ejecuta el intérprete:

```
python3 principal.py
```

3. Ingresa el archivo:

```
programa.awo
```

---

#  Sintaxis del lenguaje

---

##  Variables

```awo
x = 10
y = 20
```

---

##  Operaciones básicas

```awo
print(5 + 3)
print(10 - 2)
print(4 * 2)
print(8 / 2)
```

---

##  Condicionales

```awo
if x > 5:
    print("Mayor")
else:
    print("Menor")
```

---

##  Ciclos

```awo
while x > 0:
    print(x)
    x = x - 1
```
---

##  Funciones

```awo
func suma(a, b):
    return a + b

print(suma(2, 3))
```

---

#  Librerías

---

#  MATE (Matemáticas)

Funciones disponibles:

```awo
mate.sqrt(x)
mate.pow(x, y)
mate.abs(x)
mate.factorial(n)
mate.sin(x)
mate.cos(x)
mate.tan(x)
mate.log(x)
mate.exp(x)
mate.deg2rad(x)
mate.rad2deg(x)
```

Ejemplo:

```awo
import mate

print(mate.sqrt(16))
print(mate.factorial(5))
print(mate.exp(2))
```

---

---

#  Algoritmos implementados

##  Euclides (MCD)

Algoritmo iterativo usando módulo `%`.

##  Factorial

Multiplicación acumulativa desde 1 hasta n.

##  Potencia

Multiplicación repetida.

##  Fibonacci

Versión iterativa para evitar recursión infinita.

##  Serie de Taylor

Aproximación de `e^x` mediante suma de términos.

---

#  Diseño del intérprete

* Uso de **Visitor Pattern**
* Evaluación de AST generado por ANTLR
* Sistema de memoria tipo stack (scopes)
* Soporte para funciones con return mediante excepciones
* Evaluación de expresiones con precedencia

---

#  Notas importantes

* No existe `for`, solo `while`
* La indentación se maneja con `INDENT / DEDENT`
* El archivo principal siempre es `programa.awo`

---

#  Autores

AwoTeam
Proyecto académico de Lenguajes de Programación
Implementación de un intérprete completo en Python + ANTLR4
