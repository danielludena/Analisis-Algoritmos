# Codificación de algoritmo



def merge(A, p, q, r):
    nL = q - p + 1  # Longitud de A[p : q]
    nR = r - q      # Longitud de A[q + 1 : r]

    # Crear subarreglos temporales
    L = [0] * nL
    R = [0] * nR

    # Copiar datos a los subarreglos L y R
    for i in range(nL):
        L[i] = A[p + i]
    for j in range(nR):
        R[j] = A[q + 1 + j]

    # Fusionar los subarreglos L y R de nuevo en A[p..r]
    i = 0  # Índice inicial para L
    j = 0  # Índice inicial para R
    k = p  # Índice inicial para A

    # Comparar elementos de L y R y fusionar ordenadamente
    while i < nL and j < nR:
        if L[i] <= R[j]:
            A[k] = L[i]
            i += 1
        else:
            A[k] = R[j]
            j += 1
        k += 1

    # Copiar los elementos restantes de L (si hay)
    while i < nL:
        A[k] = L[i]
        i += 1
        k += 1

    # Copiar los elementos restantes de R (si hay)
    while j < nR:
        A[k] = R[j]
        j += 1
        k += 1




En este taller implementé el algoritmo de fusión (merge) como parte del método de ordenamiento Merge Sort. El algoritmo toma un arreglo A y tres índices p, q y r, donde A[p..q] y A[q+1..r] ya están ordenados. El objetivo es fusionarlos en un solo segmento ordenado A[p..r].
Dividí el arreglo original en dos subarreglos temporales L y R, comparé sus elementos y los coloqué nuevamente en el arreglo original ordenadamente.
El resultado es que el segmento A[p..r] queda completamente ordenado.



if __name__ == "__main__":
    A = [2, 4, 5, 7, 1, 2, 3, 6]
    merge(A, 0, 3, 7)
    print("Resultado:", A)
    # Salida esperada: [1, 2, 2, 3, 4, 5, 6, 7]
