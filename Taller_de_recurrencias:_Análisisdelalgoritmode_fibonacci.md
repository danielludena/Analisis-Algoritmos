# Análisis del algoritmo de fibonacci

def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

# Prueba
for i in range(10):
    print(f"f({i}) = {fibonacci(i)}")



Tarea: Análisis del algoritmo de Fibonacci
1. Codificación del algoritmo
Se implementó una función recursiva en Python para calcular el n-ésimo término de la sucesión de Fibonacci, definida por las siguientes condiciones:


f(0) = 0  
f(1) = 1  
f(n) = f(n-1) + f(n-2)  para n ≥ 2

El algoritmo sigue directamente la definición matemática de la sucesión.

2. Identificación de la recurrencia
La complejidad del algoritmo recursivo se modela mediante la siguiente ecuación de recurrencia:


T(n) = T(n-1) + T(n-2) + c
Donde T(n) representa el tiempo para calcular f(n), y c representa el tiempo constante de la suma. Esta recurrencia crece de manera exponencial.


3. Ecuación general de la sucesión

La forma cerrada (fórmula de Binet) para calcular el n-ésimo término es:

f(n)= 51
​
(ϕ n− ϕ^n)

Donde:

𝜙=1+52ϕ= 21+ 5 

  es la razón áurea

𝜙^=1−52ϕ^=21−5
​
​4. Demostración formal
Se puede demostrar por inducción matemática que:

𝑓(0)=0f(0)=0, 𝑓(1)=1
f(1)=1

Si se asume que 
𝑓(𝑘)=𝑓(𝑘−1)+𝑓(𝑘−2)
f(k)=f(k−1)+f(k−2) para algún 𝑘≥2
k≥2, entonces también se cumple para 𝑘+1
k+1, lo que completa la demostración por inducción.

Además, se puede demostrar que la fórmula cerrada satisface la misma recurrencia, utilizando álgebra.

5. Complejidad
La versión recursiva sin optimización tiene una complejidad exponencial:

𝑇(𝑛)∈𝑂(2𝑛)
T(n)∈O(2 n)
Esto se debe a que se repiten múltiples llamadas a los mismos subproblemas. Una forma eficiente de resolver el problema es utilizar programación dinámica, lo que reduce la complejidad a:

𝑇(𝑛)∈𝑂(𝑛)
T(n)∈O(n)

