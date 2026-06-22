# Guía Completa de Strings en Python

Un **string** (o cadena de texto) es simplemente texto en Python. Puede ser una palabra, una frase, un párrafo, o incluso un solo carácter. Los strings son uno de los tipos de datos más usados en programación.

> 💡 En Python, cualquier texto entre comillas es un string: `"Hola"`, `'Python'`, `"123"` (sí, los números entre comillas también son texto).

---

## 1. Crear Strings

### Texto entre comillas

Para crear un string, solo escribe texto entre comillas simples o dobles.

```python
# Con comillas dobles
print("Hola, mundo")
# → Hola, mundo

# Con comillas simples
print('Bienvenido a Python')
# → Bienvenido a Python

# Un solo carácter también es un string
print("A")
# → A

# String vacío (sin caracteres)
print("")
# → (nada)
```

### Números como texto

Si pones números entre comillas, Python los trata como texto, no como números.

```python
# Esto es un número
print(42 + 8)
# → 50

# Esto es texto (no se puede sumar matemáticamente)
print("42" + "8")
# → 428 (los une como texto)
```

> ⚠️ **Error común:** poner números entre comillas sin querer. `"42" + "8"` da `"428"` (concatenación), no `50` (suma).

---

## 2. Comillas Simples vs Dobles

Ambas funcionan igual. La elección es tuya.

```python
print("Hola")
# → Hola

print('Hola')
# → Hola
```

### Cuando el texto tiene comillas

Si tu texto incluye un tipo de comillas, usa el otro tipo para encerrarlo.

```python
# El texto tiene comillas simples → usa dobles afuera
print("Él dijo 'hola' y se fue")
# → Él dijo 'hola' y se fue

# El texto tiene comillas dobles → usa simples afuera
print('Ella respondió "adiós"')
# → Ella respondió "adiós"

# O usa la barra invertida para "escapar" la comilla
print("Él dijo \"hola\" y se fue")
# → Él dijo "hola" y se fue
```

---

## 3. Strings Multilínea

### Comillas triples

Para texto que ocupa varias líneas, usa tres comillas al inicio y al final.

```python
print("""Este es un texto
que ocupa varias
líneas.""")

# → Este es un texto
# → que ocupa varias
# → líneas.
```

### Crear diseños con texto

Las comillas triples son perfectas para arte ASCII o menús.

```python
print("""
    *****
   *     *
  *  ^ ^  *
  *  (o)  *
   *     *
    *****
""")
```

---

## 4. Caracteres Especiales

### Secuencias de escape

Algunos caracteres no se pueden escribir directamente. Se usan secuencias que empiezan con `\`.

```python
# \n = Nueva línea
print("Primera\nSegunda")
# → Primera
# → Segunda

# \t = Tabulación
print("Nombre:\tJuan")
# → Nombre:    Juan

# \\ = Barra invertida
print("C:\\Usuarios\\Juan")
# → C:\Usuarios\Juan
```

### Tabla de secuencias de escape

| Secuencia | Resultado      | Uso común                          |
|-----------|----------------|------------------------------------|
| `\n`      | Nueva línea    | Saltar a la siguiente línea        |
| `\t`      | Tabulación     | Alinear texto en columnas          |
| `\\`      | Barra `\`      | Rutas de Windows                   |
| `\"`      | Comilla `"`    | Comillas dentro del texto          |
| `\'`      | Comilla `'`    | Apóstrofes dentro del texto        |

---

## 5. Unir Strings (Concatenación)

### Usar el signo `+`

Puedes unir dos o más strings usando el operador `+`.

```python
print("Hola" + "Mundo")
# → HolaMundo

# Agrega espacios si los necesitas
print("Hola" + " " + "Mundo")
# → Hola Mundo

# Puedes unir muchos strings
print("A" + "B" + "C" + "D")
# → ABCD
```

> ⚠️ **Cuidado:** No puedes concatenar strings con números directamente. `"Tengo " + 5` dará error. Más adelante aprenderás cómo resolver esto.

---

## 6. Repetir Strings

### Usar el signo `*`

Puedes repetir un string multiplicándolo por un número.

```python
print("Ja" * 3)
# → JaJaJa

print("=" * 20)
# → ====================

print("-*" * 10)
# → -*-*-*-*-*-*-*-*-*-*

# Útil para crear separadores
print("TÍTULO")
print("─" * 15)
# → TÍTULO
# → ───────────────
```

---

## 7. Acceder a Caracteres

### Índices (posiciones)

Cada carácter en un string tiene una posición llamada **índice**. El primer carácter está en la posición `0`.

```
P  y  t  h  o  n
0  1  2  3  4  5
```

```python
# Acceder al primer carácter (índice 0)
print("Python"[0])
# → P

# Acceder al segundo carácter (índice 1)
print("Python"[1])
# → y

# Acceder al último carácter (índice 5)
print("Python"[5])
# → n
```

### Índices negativos

También puedes contar desde el final usando números negativos. `-1` es el último carácter.

```
P   y   t   h   o   n
-6  -5  -4  -3  -2  -1
```

```python
# Último carácter
print("Python"[-1])
# → n

# Penúltimo carácter
print("Python"[-2])
# → o

# Primer carácter (desde el final)
print("Python"[-6])
# → P
```

> 💡 **¿Por qué empieza en 0?** En programación, los índices suelen empezar en 0, no en 1. Es una convención que viene de cómo las computadoras manejan la memoria.

---

## 8. Extraer Partes (Slicing)

### Cortar un pedazo del string

Puedes extraer una porción del string usando `[inicio:fin]`. El carácter en `fin` **NO** se incluye.

```python
# Desde índice 0 hasta índice 3 (sin incluir el 3)
print("Python"[0:3])
# → Pyt

# Desde índice 2 hasta índice 5
print("Python"[2:5])
# → tho

# Desde el inicio hasta índice 4
print("Python"[:4])
# → Pyth

# Desde índice 2 hasta el final
print("Python"[2:])
# → thon
```

### Ejemplos prácticos

```python
# Extraer extensión de archivo
print("documento.pdf"[-3:])
# → pdf

# Extraer código de país
print("+54 11 1234-5678"[:3])
# → +54

# Extraer las primeras 5 letras
print("Bienvenidos al curso"[:5])
# → Bienv
```

### Tabla de sintaxis de slicing

| Sintaxis | Significado                       | Ejemplo con `"Python"` |
|----------|-----------------------------------|------------------------|
| `[n]`    | Carácter en posición n            | `[2]` → `"t"`          |
| `[a:b]`  | Desde a hasta b (sin incluir b)   | `[1:4]` → `"yth"`      |
| `[:b]`   | Desde el inicio hasta b           | `[:3]` → `"Pyt"`       |
| `[a:]`   | Desde a hasta el final            | `[3:]` → `"hon"`       |
| `[-n]`   | n-ésimo carácter desde el final   | `[-1]` → `"n"`         |

---

## 9. Longitud de un String

### Contar caracteres con `len()`

`len()` te dice cuántos caracteres tiene un string (incluyendo espacios).

```python
print(len("Hola"))
# → 4

print(len("Python"))
# → 6

# Los espacios también cuentan
print(len("Hola Mundo"))
# → 10

# String vacío tiene longitud 0
print(len(""))
# → 0
```

> 💡 **Relación entre `len()` e índices:** Si un string tiene longitud 6, sus índices van de `0` a `5` (no de 1 a 6). El último índice siempre es `len() - 1`.

---

## Resumen General

| Operación           | Sintaxis                  | Ejemplo                          |
|---------------------|---------------------------|----------------------------------|
| Crear string        | `"texto"` o `'texto'`     | `"Hola"`                         |
| Multilínea          | `"""texto"""`             | `"""línea1\nlínea2"""`           |
| Concatenar          | `str1 + str2`             | `"Hola" + " Mundo"`              |
| Repetir             | `str * n`                 | `"=" * 10`                       |
| Acceder carácter    | `str[i]`                  | `"Python"[0]` → `"P"`           |
| Índice negativo     | `str[-i]`                 | `"Python"[-1]` → `"n"`          |
| Slicing             | `str[a:b]`                | `"Python"[1:4]` → `"yth"`       |
| Longitud            | `len(str)`                | `len("Hola")` → `4`             |
