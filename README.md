# Tecnológico de Software
## Materia: Fundamentos de álgebra
## Alumno: Juan José Zapata Buenfil
## Actividad \#16 - Matrices doc

---

## Objetivo de la Documentación
El propósito de este documento es registrar y explicar los ejercicios realizados en la Actividad que nos marcó el profesor, enfocada en la identificación, clasificación y operaciones básicas con matrices.

---

## Ejercicios Realizados

### Ejercicio 1: Identificación de matrices

* **Enunciado del Problema :**
    Identifica el tipo de cada matriz.
  
--- 

#### Matriz A
$$
A = \begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
$$

* **Procedimiento:**
    1. Es una matriz de 2x2 (originalmente pensaba que era solo cuadrada).
    2. Los elementos de la diagonal principal son 1.
    3. Los elementos fuera de la diagonal principal son 0.
          
* **Respuesta:**
        La matriz A es una Matriz Identidad de tamaño 2x2.  
    
---

#### Matriz B
$$
B = \begin{pmatrix}
3 & 0 & 0 \\
0 & -2 & 0 \\
0 & 0 & 5 \\
\end{pmatrix}
$$

* **Procedimiento:**.
    1.  Se ve que todos los elementos fuera de la diagonal principal (arriba y abajo) son 0.
    2.  Los elementos en la diagonal principal (3, -2, 5) son distintos de 0.
    3.  Como solo los valores de la diagonal son algo diferente a 0 se le denomina a esta matriz el tipo diagonal.

* **Respuesta:**
    La matriz B es una Matriz Diagonal.

---

#### Matriz C
$$
C = \begin{pmatrix}
2 & 1 & 4 \\
1 & 3 & 5 \\
4 & 5 & 6 \\
\end{pmatrix}
$$

* **Procedimiento:**.
    1.  Es una matriz de 3x3, por lo tanto es una matriz cuadrada (sin embargo hay algo mas).
    2.  Se puede notar que todos los elementos tienen un mismo valor en la parte inferior de la tabla
        * El elemento 1,2 (1) es igual al 2,1 (1).
        * El elemento 1,3 (4) es igual al 3,1 (4).
        * El elemento 2,3 (5) es igual al 3,2 (5).
    3.  Dado que los elementos inferiores de la matriz son iguales a los superiores se clasifica como simetrica.

* **Respuesta:**
    La matriz C es una Matriz Simétrica.

---

#### Matriz D
$$
D = \begin{pmatrix}
1 & 2 & 3 \\
0 & 4 & 5 \\
0 & 0 & 6 \\
\end{pmatrix}
$$

* **Procedimiento:**.
    1.  Se puede ver que es una matriz cuadrada 3x3.
    2.  Se ve que todos los elementos situados por debajo de la diagonal principal son 0.
    3.  Los elementos sobre la diagonal principal no son 0.
    4.  La estructura corresponde a una matriz triangular superior.

* **Respuesta:**
    La matriz D es una Matriz Triangular Superior.


### Ejercicio 2: Operaciones básicas

* **Enunciado del Problema:**
    Dadas las matrices, calcula.

---


#### a) A + B

* **Proceso/Procedimiento:**
    Se suman los elementos correspondientes de cada matriz (elemento por elemento).
  
$$
A + B = \left(\begin{array}{cc}
2+5 & -1+2 \\
3+(-1) & 4+3 \\
\end{array}\right)
= \left(\begin{array}{cc}
7 & 1 \\
2 & 7 \\
\end{array}\right)
$$

* **Respuesta:**
  
$$
\left(\begin{array}{cc}
7 & 1 \\
2 & 7 \\
\end{array}\right)
$$

---

#### b) 2A - B 

$$
2A = 2 \times \begin{pmatrix} 2 & -1 \\ 3 & 4 \end{pmatrix} = \begin{pmatrix} 4 & -2 \\ 6 & 8 \end{pmatrix}
$$

$$
2A - B = \begin{pmatrix} 4 & -2 \\ 6 & 8 \end{pmatrix} - \begin{pmatrix} 5 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 4-5 & -2-2 \\ 6-(-1) & 8-3 \end{pmatrix}
$$

* **Respuesta:**
  
$$
\begin{pmatrix} -1 & -4 \\ 7 & 5 \end{pmatrix}
$$


