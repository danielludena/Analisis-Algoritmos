# Analisis de Algoritmos
Repositorio para las clases de Análisis de Algoritmos del paralelo B 

### Que son los Algotirmos?

Algoritmo es un conjunto de reglas para efectuar algún cálculo, bien sea a mano o, más
frecuentemente, en una máquina 
![image](https://github.com/user-attachments/assets/5a13b2dc-3375-4a86-8355-f50faf0832c5)
Una instancia de un problema consiste en la entrada (que satisface las restricciones
impuestas en el enunciado del problema) necesaria para calcular una solución al problema.

### Que es la algoritmia?
- La algoritmia estudia las propiedades de los algoritmos y nos ayuda a elegir la solución más adecuada en cada situación.
- En muchos casos, una buena elección ahorra tiempo y dinero.
- En algunos casos, una buena elección marca la diferencia entre poder resolver un problema y no poder hacerlo.

### Eficiencia

Un algoritmo debe ser rápido y usar la menor cantidad de recursos. Es una relación entre los recursos consumidos, fundamentalmente tiempo y memoria versus los productos obtenidos.

### Tipos de Analisis

- **Peor caso:** indica el mayor tiempo obtenido, teniendo en consideración todas las entradas posibles.
- **Mejor caso:** indica el menor tiempo obtenido, teniendo en consideración todas las entradas posibles.
- **Media:** (Caso promedio), indica el tiempo medio obtenido, considerando todas las entradas posibles

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
