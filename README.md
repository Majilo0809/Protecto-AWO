# Protecto-AWO
# Lenguaje de Programación AWO

## Descripción

**AWO** es un lenguaje de programación.
El objetivo del lenguaje es demostrar el funcionamiento de un **intérprete**, incluyendo:

* Análisis léxico
* Análisis sintáctico
* Recorrido del árbol de sintaxis (Visitor)
* Manejo de memoria para variables
* Evaluación de expresiones aritméticas

El lenguaje permite declarar variables y realizar operaciones matemáticas básicas entre números y variables.
El intérprete fue desarrollado en **Python** utilizando **ANTLR4** para la generación del lexer y parser.

---

# Estructura del Proyecto

El proyecto está compuesto por los siguientes archivos:

```
.
│
├── AWO.g4
├── interprete.py
├── memoria.py
├── principal.py
├── programa.awo
└── generado/
```

### AWO.g4

Archivo de gramática de **ANTLR4** que define:

* Las reglas léxicas del lenguaje
* Las reglas sintácticas
* La estructura del programa

A partir de este archivo se generan automáticamente:

* `AWOLexer`
* `AWOParser`
* `AWOVisitor`

---

### interprete.py

Contiene la clase `InterpreteAWO`, encargada de **recorrer el árbol sintáctico** y ejecutar el programa.

Funciones principales:

* **visitSentencia**

  * Procesa asignaciones de variables.
  * Evalúa la expresión y guarda el resultado en memoria.

* **visitExpresion**

  * Evalúa expresiones matemáticas.
  * Soporta:

    * números
    * variables
    * operaciones aritméticas

Operaciones soportadas:

```
+
-
*
/
```

Ejemplo interno:

```
a = 5 + 3
b = a * 2
```

---

### memoria.py

Implementa la clase **Memoria**, encargada de almacenar las variables del programa.

Funcionalidades:

* Guardar variables
* Obtener valores de variables
* Detectar variables no definidas

La memoria utiliza un diccionario de Python:

```
self.variables = {}
```

Ejemplo conceptual:

```
a = 10
b = 20
```

Memoria:

```
{
  "a": 10,
  "b": 20
}
```

---

### principal.py

Es el **punto de entrada del programa**.

Se encarga de:

1. Leer el archivo del programa.
2. Crear el lexer.
3. Crear el parser.
4. Construir el árbol sintáctico.
5. Ejecutar el intérprete.

Flujo del programa:

```
Archivo .awo
     ↓
Lexer
     ↓
Parser
     ↓
Árbol Sintáctico
     ↓
Visitor (Interprete)
     ↓
Ejecución
```

El usuario debe ingresar el nombre del archivo a ejecutar:

```
Ingrese el nombre del archivo a ejecutar:
```

---

### programa.awo

Archivo de ejemplo escrito en el lenguaje **AWO**.

Ejemplo de programa:

```
a = 5
b = 10
c = a + b
d = c * 2
```

Salida esperada:

```
a = 5
b = 10
c = 15
d = 30
```

---

# Características del Lenguaje

El lenguaje AWO actualmente soporta:

* Variables
* Números enteros
* Operaciones aritméticas
* Expresiones con variables

Operadores disponibles:

```
+  suma
-  resta
*  multiplicación
/  división
```

---

# Requisitos

Para ejecutar el proyecto se requiere:

* Python 
* ANTLR4

Instalar dependencia:

```
pip install antlr4-python3-runtime
```

---

# Ejecución del Proyecto

1. Abrir una terminal en la carpeta del proyecto.

2. Ejecutar el programa principal:

```
python principal.py
```

3. Ingresar el nombre del archivo `.awo`:

```
Ingrese el nombre del archivo a ejecutar: programa.awo
```

4. El intérprete procesará el archivo y mostrará los resultados.

---

# Manejo de Errores

El intérprete detecta errores cuando:

* Se usa una variable que no ha sido definida.

Ejemplo:

```
a = b + 5
```

Salida:

```
Exception: Variable 'b' no definida
```

---

# Objetivo del Proyecto

Este lenguaje fue desarrollado para comprender:

* Construcción de lenguajes de programación
* Uso de ANTLR
* Interpretación mediante árboles sintácticos
* Manejo de variables y memoria

---

# Autores

Proyecto desarrollado por:

* AWO TEAM

