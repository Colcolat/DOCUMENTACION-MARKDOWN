# Portafolio de Evidencias: Álgebra Lineal

**Materia:** Álgebra   
**Alumno:** Juan José Zapata Buenfil  
**Grupo** 1B

---

## 📑 Introducción

En el presente reporte se documenta el procedimiento técnico para la resolución de sistemas de ecuaciones lineales. Se aplicarán cuatro metodologías fundamentales del álgebra matricial para verificar la consistencia de los resultados:

1.  **Eliminación Gaussiana**
2.  **Método de Gauss-Jordan**
3.  **Matriz Inversa**
4.  **Regla de Cramer**

Además, se incluye un análisis sobre la clasificación de sistemas (compatibles e incompatibles) y la resolución de un sistema de orden superior ($4 \times 4$).

---

## 1. Análisis de un Sistema de Ecuaciones $3 \times 3$

Para esta sección, trabajaremos con el siguiente sistema de ecuaciones lineales:

$$
\begin{cases}
x + y + z = 6\\
2x - y + z = 3\\
x + 2y - z = 2
\end{cases}
$$

Definimos los componentes matriciales $A$ (coeficientes), $\mathbf{x}$ (incógnitas) y $\mathbf{b}$ (términos independientes) de la forma $A\mathbf{x} = \mathbf{b}$:

$$
A =
\begin{pmatrix}
1 & 1 & 1\\
2 & -1 & 1\\
1 & 2 & -1
\end{pmatrix},
\qquad
\mathbf{x} =
\begin{pmatrix}
x\\y\\z
\end{pmatrix},
\qquad
\mathbf{b} =
\begin{pmatrix}
6\\3\\2
\end{pmatrix},
\qquad
A\mathbf{x} = \mathbf{b}.
$$

### 1.1 Resolución por Eliminación Gaussiana

El objetivo es triangular la matriz. Iniciamos con la matriz aumentada del sistema:

$$
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
2 & -1 & 1 & 3\\
1 & 2 & -1 & 2
\end{array}
\right]
$$

**Paso 1:** Generación de ceros en la primera columna (filas 2 y 3) mediante operaciones elementales:

$$
R_2 \leftarrow R_2 - 2R_1,\quad
R_3 \leftarrow R_3 - R_1
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
0 & -3 & -1 & -9\\
0 & 1 & -2 & -4
\end{array}
\right]
$$

**Paso 2:** Reordenamiento de filas para simplificar el pivote (intercambio $R_2$ y $R_3$):

$$
R_2 \leftrightarrow R_3
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
0 & 1 & -2 & -4\\
0 & -3 & -1 & -9
\end{array}
\right]
$$

**Paso 3:** Eliminación final en la segunda columna:

$$
R_3 \leftarrow R_3 + 3R_2
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
0 & 1 & -2 & -4\\
0 & 0 & -7 & -21
\end{array}
\right]
$$

**Sustitución hacia atrás:**
Una vez obtenida la forma escalonada, despejamos las variables comenzando desde $z$:

$$
-7z = -21 \Rightarrow z = 3,
$$

$$
y - 2z = -4 \Rightarrow y - 6 = -4 \Rightarrow y = 2,
$$

$$
x + y + z = 6 \Rightarrow x + 2 + 3 = 6 \Rightarrow x = 1.
$$

**Conjunto Solución:**

$$
(x,y,z) = (1,2,3).
$$

---

### 1.2 Resolución por Gauss-Jordan

Este método busca obtener la matriz identidad. Retomamos la matriz escalonada del paso anterior:

$$
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
0 & 1 & -2 & -4\\
0 & 0 & -7 & -21
\end{array}
\right]
$$

**Paso 1:** Convertimos el pivote de la fila 3 en 1:

$$
R_3 \leftarrow -\frac{1}{7} R_3
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6\\
0 & 1 & -2 & -4\\
0 & 0 & 1 & 3
\end{array}
\right]
$$

**Paso 2:** Eliminación de valores sobre el pivote $z$ (filas 1 y 2):

$$
R_2 \leftarrow R_2 + 2R_3,\quad
R_1 \leftarrow R_1 - R_3
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 0 & 3\\
0 & 1 & 0 & 2\\
0 & 0 & 1 & 3
\end{array}
\right]
$$

**Paso 3:** Eliminación final sobre el pivote $y$:

$$
R_1 \leftarrow R_1 - R_2
$$

$$
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 0 & 0 & 1\\
0 & 1 & 0 & 2\\
0 & 0 & 1 & 3
\end{array}
\right]
$$

El sistema queda resuelto directamente:

$$
x = 1,\quad y = 2,\quad z = 3.
$$

---

### 1.3 Método de la Matriz Inversa ($A^{-1}$)

Utilizamos la propiedad $X = A^{-1}B$.
Matriz de coeficientes:

$$
A =
\begin{pmatrix}
1 & 1 & 1\\
2 & -1 & 1\\
1 & 2 & -1
\end{pmatrix}.
$$

Calculamos el determinante ($\Delta$) usando Sarrus:

$$
\det(A) = 1(-1)(-1) + 1(1)(1) + 1(2)(2)
          - 1(-1)(1) - 1(2)(-1) - 1(1)(2)
        = 7.
$$

Al ser $\det(A) \neq 0$, la matriz es invertible. Calculamos la adjunta y transpuesta para obtener:

$$
A^{-1} = \frac{1}{7}
\begin{pmatrix}
-1 & 3 & 2\\
3 & -2 & 1\\
5 & -1 & -3
\end{pmatrix}.
$$

Multiplicamos por el vector de términos independientes $\mathbf{b}$:

$$
A^{-1}\mathbf{b}
= \frac{1}{7}
\begin{pmatrix}
-1 & 3 & 2\\
3 & -2 & 1\\
5 & -1 & -3
\end{pmatrix}
\begin{pmatrix}
6\\3\\2
\end{pmatrix}.
$$

Operando el producto matricial:

$$
\begin{pmatrix}
7\\14\\21
\end{pmatrix}
$$

Dividiendo por el escalar (determinante):

$$
\mathbf{x}=
\begin{pmatrix}
1\\2\\3
\end{pmatrix}.
$$

---

### 1.4 Regla de Cramer

Calculamos los determinantes sustituyendo la columna de términos independientes en cada variable.

$$
A =
\begin{pmatrix}
1 & 1 & 1\\
2 & -1 & 1\\
1 & 2 & -1
\end{pmatrix},\quad
\mathbf{b} =
\begin{pmatrix}
6\\3\\2
\end{pmatrix},
$$

**Determinante del sistema:**

$$
D = 7
$$

**Matrices para $x, y, z$:**

$$
A_x =
\begin{pmatrix}
6 & 1 & 1\\
3 & -1 & 1\\
2 & 2 & -1
\end{pmatrix},
$$

$$
A_y =
\begin{pmatrix}
1 & 6 & 1\\
2 & 3 & 1\\
1 & 2 & -1
\end{pmatrix},
$$

$$
A_z =
\begin{pmatrix}
1 & 1 & 6\\
2 & -1 & 3\\
1 & 2 & 2
\end{pmatrix}.
$$

**Resultados de determinantes:**

$$
D_x=7,\quad D_y=14,\quad D_z=21
$$

**Cálculo final:**

$$
x=1,\quad y=2,\quad z=3.
$$

---

## 2. Clasificación de Tipos de Sistemas

A continuación analizamos el comportamiento de las soluciones en sistemas $2 \times 2$.

### Caso A: Sistema Compatible Indeterminado

$$
\begin{cases}
x + y = 3\\
2x + 2y = 6
\end{cases}
$$

Matriz aumentada:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
2 & 2 & 6
\end{array}
\right]
$$

Tras la reducción, obtenemos una fila de ceros:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
0 & 0 & 0
\end{array}
\right]
$$

**Conclusión:** Existen **infinitas soluciones** (las rectas son coincidentes).

---

### Caso B: Sistema Incompatible

$$
\begin{cases}
x + y = 3\\
2x + 2y = 7
\end{cases}
$$

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
2 & 2 & 7
\end{array}
\right]
$$

Reducción:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
0 & 0 & 1
\end{array}
\right]
$$

**Conclusión:** Se llega a una contradicción matemática ($0 = 1$). El sistema **no tiene solución** (rectas paralelas).

---

### Caso C: Sistema Compatible Determinado

$$
\begin{cases}
x + y = 3\\
x - y = 1
\end{cases}
$$

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
1 & -1 & 1
\end{array}
\right]
$$

Operación $R_2 - R_1$:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
0 & -2 & -2
\end{array}
\right]
$$

Normalización de fila 2:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3\\
0 & 1 & 1
\end{array}
\right]
$$

Sustitución final:

$$
\left[
\begin{array}{cc|c}
1 & 0 & 2\\
0 & 1 & 1
\end{array}
\right]
$$

**Conclusión:** Solución única en:

$$
x=2,\quad y=1.
$$

---

## 3. Resolución de Sistema de Orden Superior ($4 \times 4$)

Planteamiento del problema:

$$
\begin{cases}
x + y + z + w = 10\\
2x + y - z + w = 5\\
x - y + z - w = 1\\
x + y - z + 2w = 8
\end{cases}
$$

Matriz de coeficientes aumentada:

$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10\\
2 & 1 & -1 & 1 & 5\\
1 & -1 & 1 & -1 & 1\\
1 & 1 & -1 & 2 & 8
\end{array}
\right]
$$

Aplicando el método de Gauss obtenemos la forma escalonada:

$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10\\
0 & 1 & 3 & 1 & 15\\
0 & 0 & 1 & 0 & 7/2\\
0 & 0 & 0 & 1 & 5
\end{array}
\right]
$$

Despejando las variables desde la última fila hacia arriba:

$$
w=5,\quad z=\frac{7}{2},\quad y=-\frac{1}{2},\quad x=2
$$

**Resultado final:**

$$
(x,y,z,w)=\left(2,-\frac{1}{2},\frac{7}{2},5\right)
$$
