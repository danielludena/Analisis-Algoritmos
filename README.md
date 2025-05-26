# Analisis de Algoritmos
Repositorio para las clases de Análisis de Algoritmos del paralelo B 

---

# Fundamentos

### Que son los Algotirmos?

Algoritmo es un conjunto de reglas para efectuar algún cálculo, bien sea a mano o, más
frecuentemente, en una máquina 
![image](https://github.com/user-attachments/assets/5a13b2dc-3375-4a86-8355-f50faf0832c5)
Una instancia de un problema consiste en la entrada (que satisface las restricciones
impuestas en el enunciado del problema) necesaria para calcular una solución al problema.

---

### Que es la algoritmia?
- La algoritmia estudia las propiedades de los algoritmos y nos ayuda a elegir la solución más adecuada en cada situación.
- En muchos casos, una buena elección ahorra tiempo y dinero.
- En algunos casos, una buena elección marca la diferencia entre poder resolver un problema y no poder hacerlo.

---

### Eficiencia

Un algoritmo debe ser rápido y usar la menor cantidad de recursos. Es una relación entre los recursos consumidos, fundamentalmente tiempo y memoria versus los productos obtenidos.

### Tipos de Analisis

- **Peor caso:** indica el mayor tiempo obtenido, teniendo en consideración todas las entradas posibles.
- **Mejor caso:** indica el menor tiempo obtenido, teniendo en consideración todas las entradas posibles.
- **Media:** (Caso promedio), indica el tiempo medio obtenido, considerando todas las entradas posibles

---
---

## Notación Asintótica

### ¿Qué es la notación asintótica?
Forma de describir la eficiencia de un algoritmo cuando el tamaño de la entrada tiende a infinito. Se enfoca en la *tasa de crecimiento*.

---

### Notación O (Big-O)
Representa una **cota superior** del tiempo de ejecución.

- Se usa para describir el **peor caso**.
- Se descartan constantes y términos no dominantes.
- Ejemplo: si T(n) = 3n² + 5n + 2, entonces T(n) ∈ O(n²)

Formulación:
T(n) ∈ O(f(n)) ⟺ ∃ c > 0, n₀ ∈ ℕ tal que ∀n ≥ n₀: T(n) ≤ c·f(n)

---

### Notación Ω (Omega)
Representa una **cota inferior** del tiempo de ejecución.

- Describe el **mejor caso**.
- Sirve para saber qué tan rápido *no puede* correr un algoritmo.

Formulación:
T(n) ∈ Ω(f(n)) ⟺ ∃ d > 0, n₀ ∈ ℕ tal que ∀n ≥ n₀: T(n) ≥ d·f(n)

---

### Notación Θ (Theta)
Representa una **cota exacta** del tiempo de ejecución.

- Se usa cuando un algoritmo tiene una tasa de crecimiento que está *acotada por arriba y por abajo* por la misma función.

Formulación:
T(n) ∈ Θ(f(n)) ⟺ ∃ c,d > 0, n₀ ∈ ℕ tal que ∀n ≥ n₀: d·f(n) ≤ T(n) ≤ c·f(n)

---

### Reglas útiles

- **Regla del máximo**:  
  T(n) = O(max(f(n), g(n)))

- **Regla del umbral**:  
  Se evalúa el comportamiento para valores grandes de n.

- **Regla del límite**:  
  Si lim[n→∞] f(n)/g(n) = 0 → f ∈ O(g)  
  Si = ∞ → f ∈ Ω(g)  
  Si = c (0 < c < ∞) → f ∈ Θ(g)

---

### Ordenes comunes de complejidad

| Orden             | Ejemplo de función   |
|------------------|----------------------|
| Constante        | O(1)                 |
| Logarítmica      | O(log n)             |
| Lineal           | O(n)                 |
| Lineal-logarítmica | O(n log n)         |
| Cuadrática       | O(n²)                |
| Exponencial      | O(2ⁿ)                |
| Factorial        | O(n!)                |

---

### Ejemplo práctico

T(n) = 6n² + 100n + 300  
→ Descartando constantes y términos menores:  
T(n) ∈ O(n²)

---

### Cómo demostrar formalmente

- Usa la definición matemática (con constantes y umbral n₀).
- O aplica la regla del límite comparando dos funciones.
- En algoritmos: enfócate en el **paso más costoso**.

---
---

### Tarea 1:

Dadas las funciones:

- \( f(n) = n^3 + 9n^2 \log(n) \)
- \( g(n) = n^2 \log(n) \)

Se solicita:

1. Comprobar si \( f(n) \in O(g(n)) \)
2. Comprobar si \( f(n) \notin O(n^2) \)
3. Analizar formalmente la relación entre:
   - \( f(n) = 2^n \) y \( g(n) = 2^{2n} \)
   - Ver si \( f(n) \in O(g(n)) \) y si \( g(n) \in O(f(n)) \)


### Solución

### 1. ¿\( f(n) \in O(g(n)) \)?

Sea:  
- \( f(n) = n^3 + 9n^2 \log(n) \)
- \( g(n) = n^2 \log(n) \)

Analizamos el comportamiento asintótico:

- \( n^3 \gg n^2 \log(n) \), por lo tanto:
  \[
  f(n) \sim n^3
  \]

Ahora comparamos \( f(n) \sim n^3 \) con \( g(n) = n^2 \log(n) \):

\[
\lim_{n \to \infty} \frac{f(n)}{g(n)} = \lim_{n \to \infty} \frac{n^3}{n^2 \log(n)} = \lim_{n \to \infty} \frac{n}{\log(n)} = \infty
\]

**Conclusión**:  
\( f(n) \notin O(g(n)) \)


### 2. ¿\( f(n) \notin O(n^2) \)?

Ya sabemos que:
\[
f(n) = n^3 + 9n^2 \log(n) \sim n^3
\]

Comparación con \( n^2 \):

\[
\lim_{n \to \infty} \frac{f(n)}{n^2} = \lim_{n \to \infty} \frac{n^3}{n^2} = n \to \infty
\]

**Conclusión**:  
\( f(n) \notin O(n^2) \) SI


### 3. Análisis con funciones exponenciales

Sean:

- \( f(n) = 2^n \)
- \( g(n) = 2^{2n} = (2^n)^2 \)

#### 3.1. ¿\( f(n) \in O(g(n)) \)?

\[
\lim_{n \to \infty} \frac{f(n)}{g(n)} = \frac{2^n}{2^{2n}} = \frac{1}{2^n} \to 0
\]

**Conclusión**:  
\( f(n) \in O(g(n)) \)   SI

#### 3.2. ¿\( g(n) \in O(f(n)) \)?

\[
\lim_{n \to \infty} \frac{g(n)}{f(n)} = \frac{2^{2n}}{2^n} = 2^n \to \infty
\]

**Conclusión**:  
\( g(n) \notin O(f(n)) \)   NO


### Conclusión general

| Relación                         | Resultado        |
|----------------------------------|------------------|
| \( f(n) = n^3 + 9n^2 \log(n) \in O(g(n)) \)     | NO |
| \( f(n) \notin O(n^2) \)                     | SI |
| \( f(n) = 2^n \in O(2^{2n}) \)              | SI |
| \( 2^{2n} \notin O(2^n) \)                  | SI |

---


### Tarea 2:

- Obtenga t(n) del siguiente algoritmo:

```  
procedure misterio(n: integer)
var
  contador, i, j, k: integer
begin
  contador := 0
  for i := 1 to n - 1 do
    for j := i + 1 to n do
      for k := 1 to j do
        contador := contador + 1
end
```

El número total de veces que se ejecuta contador := contador + 1 es:

![image](https://github.com/user-attachments/assets/0317bf69-ac19-4cc8-ac3b-5ae841d42225)

La prueba de escritorio seria de la siguiente manera:

```
n = 3
contador := 0

i = 1:
  j = 2 → k = 1,2 → contador += 2 → contador = 2
  j = 3 → k = 1,2,3 → contador += 3 → contador = 5

i = 2:
  j = 3 → k = 1,2,3 → contador += 3 → contador = 8

Resultado final: contador = 8
```
