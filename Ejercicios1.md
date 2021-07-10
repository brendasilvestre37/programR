Ejercicios1
================
Brenda\_Silvestre
10/7/2021

# Ejercicios

## Parte 1

Cargar las variables almacenadas en el siguiente archivo
[Rdata](https://goo.gl/uDzU8v)

**1. Calcula los valores numéricos aproximados de **

1.  $\\frac{0.3 \\cdot 0.15}{0.3 \\cdot 0.15 + 0.2 \\cdot 0.8 + 0.5 \\cdot 0.12}$

``` r
v1 <- c(0.3,0.15,0.2,0.8,0.5,0.12)
v1
```

    ## [1] 0.30 0.15 0.20 0.80 0.50 0.12

``` r
r1 <- (v1[1]*v1[2])
r1
```

    ## [1] 0.045

``` r
r2 <- (v1[3]*v1[4])
r3 <- (v1[5]*v1[6])
r4 <- ((r1)/(r1+r2+r3))
r4
```

    ## [1] 0.1698113

2.  $\\frac{5^6}{6!} e^{-5}$

``` r
a <- 5**6
b <- factorial(6)
c <- a/b
c
```

    ## [1] 21.70139

``` r
d <- exp(-5)
c*d
```

    ## [1] 0.1462228

3.  $\\begin{pmatrix} 20 \\\\ 7 \\end{pmatrix} 0.4^7 0.6^{13}$

``` r
num1 <- 20
num2 <- 7
num3 <- 0.4
num4 <- 0.6
a <- factorial(num1)
b <- factorial(num2)
c <- a/((num1-num2)*b)
d <- c*num3**7*num4**13
d
```

    ## [1] 79457871

**2. Realizar la siguiente suma**

1.  1 + 2 + 3 + ... + 1000

``` r
a <- 1:100
b <- sum(a)
b
```

    ## [1] 5050

2.  1 + 2 + 4 + 8 + 16 + ... + 1024

``` r
a1 <- 1
an <- 1024
r <- 2
c <- log(an/a1)
d <- log(r)
e <- (c/d) + 1
e
```

    ## [1] 11

``` r
Sn <- function(a1, r, n) {
  a1 * (r^n - 1) / (r - 1)
}

Sn(a1 = 1, r = 2, n = 11)
```

    ## [1] 2047

**3. El vector `grupo` representa el grupo al que pertenece una serie de
alumnos**

1.  ¿Cuántos elementos tiene?

``` r
load ("ei1012-1516-la-s1-datos (1).RData")
length(grupo)
```

    ## [1] 192

``` r
grupo
```

    ##   [1] "B" "A" "E" "D" "B" "D" "D" "A" "D" "C" "D" "E" "B" "E" "E" "E" "A" "B"
    ##  [19] "C" "C" "A" "C" "C" "D" "D" "E" "E" "A" "B" "C" "C" "E" "D" "C" "E" "E"
    ##  [37] "E" "E" "D" "D" "D" "E" "E" "E" "D" "E" "B" "E" "D" "C" "E" "D" "E" "E"
    ##  [55] "C" "B" "D" "C" "E" "D" "E" "B" "D" "B" "B" "C" "D" "C" "C" "C" "E" "D"
    ##  [73] "E" "D" "C" "D" "E" "E" "C" "D" "C" "E" "D" "A" "B" "B" "E" "E" "C" "D"
    ##  [91] "C" "E" "E" "C" "E" "D" "D" "D" "E" "D" "A" "D" "B" "B" "C" "D" "E" "A"
    ## [109] "E" "E" "A" "C" "E" "D" "A" "D" "D" "C" "E" "E" "E" "D" "A" "E" "E" "E"
    ## [127] "C" "C" "B" "C" "C" "D" "C" "B" "C" "A" "D" "E" "D" "E" "E" "B" "E" "E"
    ## [145] "E" "E" "C" "B" "D" "D" "E" "E" "D" "D" "E" "D" "E" "D" "D" "C" "D" "D"
    ## [163] "D" "C" "E" "D" "E" "C" "E" "B" "C" "C" "C" "D" "D" "B" "D" "B" "E" "C"
    ## [181] "E" "D" "D" "E" "D" "B" "B" "E" "E" "A" "C" "A"

2.  ¿En qué posiciones del vector está la letra “A”?

``` r
which(grupo=="A")
```

    ##  [1]   2   8  17  21  28  84 101 108 111 115 123 136 190 192

**4. El vector `nota` representa la nota de un examen de los alumnos que
están en los grupos del vector `grupo`.**

1.  ¿Cuanto suman todas las notas?

``` r
nota
```

    ##   [1] 4.9 5.4 5.2 6.8 5.0 6.2 4.4 4.1 4.3 5.5 5.5 4.8 6.4 6.8 5.5 4.7 5.2 6.4
    ##  [19] 4.8 3.4 4.7 6.0 5.9 5.4 5.3 5.6 6.9 5.6 4.2 4.4 5.8 4.8 6.1 6.2 6.6 5.2
    ##  [37] 4.6 5.0 2.5 4.0 5.6 4.9 5.4 3.9 4.2 4.7 4.2 5.4 3.7 6.2 5.9 3.7 5.8 2.7
    ##  [55] 5.6 5.0 2.6 5.0 4.9 3.4 5.9 4.3 6.1 4.5 5.5 3.2 3.2 6.4 4.4 6.0 5.0 5.4
    ##  [73] 7.0 3.8 4.2 4.7 4.7 5.3 6.8 4.0 7.2 4.8 6.0 4.1 4.5 5.8 2.9 5.0 4.6 4.9
    ##  [91] 6.8 4.2 6.9 5.7 5.7 6.4 4.4 4.2 4.5 5.8 4.3 3.7 7.4 3.9 5.2 4.9 3.6 5.5
    ## [109] 6.0 5.0 4.1 4.5 3.1 5.4 4.5 5.3 4.7 6.1 5.2 7.7 5.3 5.0 4.0 5.2 4.0 5.5
    ## [127] 4.0 5.4 4.6 3.4 6.2 5.7 3.8 4.8 4.0 4.4 5.5 5.9 5.9 5.7 4.9 1.7 5.5 5.9
    ## [145] 5.5 3.8 5.5 6.0 3.5 5.5 7.5 3.4 5.8 4.7 3.6 4.1 5.0 4.6 3.6 4.7 4.1 5.7
    ## [163] 5.9 4.7 3.2 5.5 3.0 4.5 5.5 5.9 5.6 6.0 4.4 3.7 4.4 6.8 6.1 4.7 4.2 6.2
    ## [181] 5.2 5.1 2.9 6.5 4.2 5.4 5.9 6.2 6.3 4.8 5.6 2.9

``` r
sum(nota)
```

    ## [1] 962

2.  ¿Cual es la media aritmética de todas las notas?

``` r
mean(nota)
```

    ## [1] 5.010417

3.  ¿En qué posiciones están las notas mayores de *7.0*?

``` r
a <- nota>7
which(a)
```

    ## [1]  81 103 120 151

4.  Visualiza las notas ordenadas de mayor a menor

``` r
nota[order(-nota)] 
```

    ##   [1] 7.7 7.5 7.4 7.2 7.0 6.9 6.9 6.8 6.8 6.8 6.8 6.8 6.6 6.5 6.4 6.4 6.4 6.4
    ##  [19] 6.3 6.2 6.2 6.2 6.2 6.2 6.2 6.1 6.1 6.1 6.1 6.0 6.0 6.0 6.0 6.0 6.0 5.9
    ##  [37] 5.9 5.9 5.9 5.9 5.9 5.9 5.9 5.9 5.8 5.8 5.8 5.8 5.8 5.7 5.7 5.7 5.7 5.7
    ##  [55] 5.6 5.6 5.6 5.6 5.6 5.6 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5
    ##  [73] 5.5 5.4 5.4 5.4 5.4 5.4 5.4 5.4 5.4 5.3 5.3 5.3 5.3 5.2 5.2 5.2 5.2 5.2
    ##  [91] 5.2 5.2 5.1 5.0 5.0 5.0 5.0 5.0 5.0 5.0 5.0 5.0 4.9 4.9 4.9 4.9 4.9 4.9
    ## [109] 4.8 4.8 4.8 4.8 4.8 4.8 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.6 4.6
    ## [127] 4.6 4.6 4.5 4.5 4.5 4.5 4.5 4.5 4.4 4.4 4.4 4.4 4.4 4.4 4.4 4.3 4.3 4.3
    ## [145] 4.2 4.2 4.2 4.2 4.2 4.2 4.2 4.2 4.1 4.1 4.1 4.1 4.1 4.0 4.0 4.0 4.0 4.0
    ## [163] 4.0 3.9 3.9 3.8 3.8 3.8 3.7 3.7 3.7 3.7 3.6 3.6 3.6 3.5 3.4 3.4 3.4 3.4
    ## [181] 3.2 3.2 3.2 3.1 3.0 2.9 2.9 2.9 2.7 2.6 2.5 1.7

``` r
a<- max(nota)
which(nota==a) 
```

    ## [1] 120

5.  ¿En qué posición está la nota máxima?

``` r
a<- max(nota)
which(nota==a) 
```

    ## [1] 120

**5. A partir de los vectores `grupo` y `nota` definidos.**

1.  Suma las notas de los 10 primeros alumnos del vector

``` r
def <- data.frame(grupo, nota)
def
```

    ##     grupo nota
    ## 1       B  4.9
    ## 2       A  5.4
    ## 3       E  5.2
    ## 4       D  6.8
    ## 5       B  5.0
    ## 6       D  6.2
    ## 7       D  4.4
    ## 8       A  4.1
    ## 9       D  4.3
    ## 10      C  5.5
    ## 11      D  5.5
    ## 12      E  4.8
    ## 13      B  6.4
    ## 14      E  6.8
    ## 15      E  5.5
    ## 16      E  4.7
    ## 17      A  5.2
    ## 18      B  6.4
    ## 19      C  4.8
    ## 20      C  3.4
    ## 21      A  4.7
    ## 22      C  6.0
    ## 23      C  5.9
    ## 24      D  5.4
    ## 25      D  5.3
    ## 26      E  5.6
    ## 27      E  6.9
    ## 28      A  5.6
    ## 29      B  4.2
    ## 30      C  4.4
    ## 31      C  5.8
    ## 32      E  4.8
    ## 33      D  6.1
    ## 34      C  6.2
    ## 35      E  6.6
    ## 36      E  5.2
    ## 37      E  4.6
    ## 38      E  5.0
    ## 39      D  2.5
    ## 40      D  4.0
    ## 41      D  5.6
    ## 42      E  4.9
    ## 43      E  5.4
    ## 44      E  3.9
    ## 45      D  4.2
    ## 46      E  4.7
    ## 47      B  4.2
    ## 48      E  5.4
    ## 49      D  3.7
    ## 50      C  6.2
    ## 51      E  5.9
    ## 52      D  3.7
    ## 53      E  5.8
    ## 54      E  2.7
    ## 55      C  5.6
    ## 56      B  5.0
    ## 57      D  2.6
    ## 58      C  5.0
    ## 59      E  4.9
    ## 60      D  3.4
    ## 61      E  5.9
    ## 62      B  4.3
    ## 63      D  6.1
    ## 64      B  4.5
    ## 65      B  5.5
    ## 66      C  3.2
    ## 67      D  3.2
    ## 68      C  6.4
    ## 69      C  4.4
    ## 70      C  6.0
    ## 71      E  5.0
    ## 72      D  5.4
    ## 73      E  7.0
    ## 74      D  3.8
    ## 75      C  4.2
    ## 76      D  4.7
    ## 77      E  4.7
    ## 78      E  5.3
    ## 79      C  6.8
    ## 80      D  4.0
    ## 81      C  7.2
    ## 82      E  4.8
    ## 83      D  6.0
    ## 84      A  4.1
    ## 85      B  4.5
    ## 86      B  5.8
    ## 87      E  2.9
    ## 88      E  5.0
    ## 89      C  4.6
    ## 90      D  4.9
    ## 91      C  6.8
    ## 92      E  4.2
    ## 93      E  6.9
    ## 94      C  5.7
    ## 95      E  5.7
    ## 96      D  6.4
    ## 97      D  4.4
    ## 98      D  4.2
    ## 99      E  4.5
    ## 100     D  5.8
    ## 101     A  4.3
    ## 102     D  3.7
    ## 103     B  7.4
    ## 104     B  3.9
    ## 105     C  5.2
    ## 106     D  4.9
    ## 107     E  3.6
    ## 108     A  5.5
    ## 109     E  6.0
    ## 110     E  5.0
    ## 111     A  4.1
    ## 112     C  4.5
    ## 113     E  3.1
    ## 114     D  5.4
    ## 115     A  4.5
    ## 116     D  5.3
    ## 117     D  4.7
    ## 118     C  6.1
    ## 119     E  5.2
    ## 120     E  7.7
    ## 121     E  5.3
    ## 122     D  5.0
    ## 123     A  4.0
    ## 124     E  5.2
    ## 125     E  4.0
    ## 126     E  5.5
    ## 127     C  4.0
    ## 128     C  5.4
    ## 129     B  4.6
    ## 130     C  3.4
    ## 131     C  6.2
    ## 132     D  5.7
    ## 133     C  3.8
    ## 134     B  4.8
    ## 135     C  4.0
    ## 136     A  4.4
    ## 137     D  5.5
    ## 138     E  5.9
    ## 139     D  5.9
    ## 140     E  5.7
    ## 141     E  4.9
    ## 142     B  1.7
    ## 143     E  5.5
    ## 144     E  5.9
    ## 145     E  5.5
    ## 146     E  3.8
    ## 147     C  5.5
    ## 148     B  6.0
    ## 149     D  3.5
    ## 150     D  5.5
    ## 151     E  7.5
    ## 152     E  3.4
    ## 153     D  5.8
    ## 154     D  4.7
    ## 155     E  3.6
    ## 156     D  4.1
    ## 157     E  5.0
    ## 158     D  4.6
    ## 159     D  3.6
    ## 160     C  4.7
    ## 161     D  4.1
    ## 162     D  5.7
    ## 163     D  5.9
    ## 164     C  4.7
    ## 165     E  3.2
    ## 166     D  5.5
    ## 167     E  3.0
    ## 168     C  4.5
    ## 169     E  5.5
    ## 170     B  5.9
    ## 171     C  5.6
    ## 172     C  6.0
    ## 173     C  4.4
    ## 174     D  3.7
    ## 175     D  4.4
    ## 176     B  6.8
    ## 177     D  6.1
    ## 178     B  4.7
    ## 179     E  4.2
    ## 180     C  6.2
    ## 181     E  5.2
    ## 182     D  5.1
    ## 183     D  2.9
    ## 184     E  6.5
    ## 185     D  4.2
    ## 186     B  5.4
    ## 187     B  5.9
    ## 188     E  6.2
    ## 189     E  6.3
    ## 190     A  4.8
    ## 191     C  5.6
    ## 192     A  2.9

``` r
notes <- def$nota[1:10]
sum(notes)
```

    ## [1] 51.8

2.  ¿Cuántos alumnos hay del grupo *C*?

``` r
library(tidyverse)
```

    ## Warning in (function (kind = NULL, normal.kind = NULL, sample.kind = NULL) :
    ## non-uniform 'Rounding' sampler used

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.4     v purrr   0.3.4
    ## v tibble  3.1.2     v dplyr   1.0.7
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   1.4.0     v forcats 0.5.1

    ## Warning in (function (kind = NULL, normal.kind = NULL, sample.kind = NULL) :
    ## non-uniform 'Rounding' sampler used

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
dplyr::filter(def,grupo=="C") %>% count()
```

    ##    n
    ## 1 39

3.  ¿Cuántos alumnos han aprobado?

``` r
b <- nota[nota>= 11 ]
b
```

    ## numeric(0)

``` r
length(b)
```

    ## [1] 0

4.  ¿Cuántos alumnos del grupo *B* han aprobado?

``` r
d <- grupo=="B"
d
```

    ##   [1]  TRUE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [13]  TRUE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [25] FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [37] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE
    ##  [49] FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
    ##  [61] FALSE  TRUE FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [73] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [85]  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [97] FALSE FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE
    ## [109] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ## [121] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE
    ## [133] FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE
    ## [145] FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ## [157] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ## [169] FALSE  TRUE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE  TRUE FALSE FALSE
    ## [181] FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE

``` r
c <- d[nota > 11 ]
c
```

    ## logical(0)

5.  ¿Qué porcentaje de alumnos del grupo *C* han aprobado?
6.  ¿De qué grupos son la máxima y mínima notas de toda la muestra?
7.  Nota media de los alumnos de grupo *A* y *B*, juntos, considerando
    sólo a los que han aprobado.

**6. Calcula el percentil 66 de las notas de todos los alumnos, y
también de los alumnos del grupo C.**

**7. Un alumno tiene una nota de 4.9. ¿Qué porcentaje, del total de
alumnos, tiene una nota menor o igual que la suya? ¿Y qué porcentaje
tiene una nota mayor o igual que la suya?**

**8. Realiza el gráfico de diagramas de caja de las notas de cada grupo,
para poder comparar el nivel de cada uno de ellos.**

**9. Si la variable `conc` recoge la concentración de plomo (en ppm) en
el aire de cierta zona durante un día completo**

1.  ¿Cuál ha sido la concentración máxima?
2.  ¿En cuántos de los muestreos se ha superado la concentración de 40.0
    ppm?
3.  ¿Cuál ha sido la concentración media del día?
4.  ¿Cuáles fueron las 10 mediciones más bajas del día?
5.  Si la primera medida fue a las 00:00. ¿A qué hora del día se alcanzó
    la concentración máxima?

## Parte 2

**1. 1.Graficar los puntos
(1, 1), (2, 4), (3, 6), (4, 8), (5, 25), (6, 36), (7, 49), (8, 61), (9, 81), (10, 100)
en un plano utilizando RStudio.**

``` r
a <- c(1:10)
b <- c(1,4,6,8,25,36,49,61,81,100)
plot(x= a, y = b)
```

![](Ejercicios1_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

**2. Ingresar la matriz A en RStudio**
$A = \\begin{pmatrix} 1 & 2 & 3 \\\\ 2 & 4 & 6 \\\\ 3 & 6 & 9 \\\\ 4 & 8 & 12 \\end{pmatrix}$

``` r
a <- c(1:4)
b <- c(a*2)
c <- c(a*3)


matrix <- cbind(a,b,c) # rbind o juntar por columnas
A <- matrix
A
```

    ##      a b  c
    ## [1,] 1 2  3
    ## [2,] 2 4  6
    ## [3,] 3 6  9
    ## [4,] 4 8 12

**3. Ingresar la matriz identidad de tamaño 3**
$I = \\begin{pmatrix} 1 & 0 & 0 \\\\ 0 & 1 & 0 \\\\ 0 & 0 & 1 \\end{pmatrix}$

``` r
d <- diag(1,3,3) #en la diagonal "1" y matriz 3*3
d
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    0    0
    ## [2,]    0    1    0
    ## [3,]    0    0    1

``` r
3*d
```

    ##      [,1] [,2] [,3]
    ## [1,]    3    0    0
    ## [2,]    0    3    0
    ## [3,]    0    0    3

**4. Crea una función que cree una matriz nula ingresando las
dimensiones**

``` r
d <- diag(0,4,4)
d
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    0    0    0
    ## [3,]    0    0    0    0
    ## [4,]    0    0    0    0

**5. Modificar la matriz `diag(4)`, para que se parezca a la matriz B**
$B = \\begin{pmatrix} 0 & 0 & 0 & 0 \\\\ 0 & 2 & 0 & 0 \\\\ 0 & 0 & 3 & 0 \\\\ 0 & 0 & 0 & 4 \\end{pmatrix}$

``` r
B<-d
B[1,1]=0
B[2,2]=2
B[3,3]=3
B[4,4]=4
B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    2    0    0
    ## [3,]    0    0    3    0
    ## [4,]    0    0    0    4

**6. Obtener la matriz transpuesta de A (ejercicio 2)**

``` r
t(A)
```

    ##   [,1] [,2] [,3] [,4]
    ## a    1    2    3    4
    ## b    2    4    6    8
    ## c    3    6    9   12

**7. Realizar las siguientes operaciones *A* + *B*, *A* − *B*, 3*B* y
*A**B***

``` r
#A+B  #dimensiones incompatibles
#A-B  #dimensiones incompatibles
3*B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    6    0    0
    ## [3,]    0    0    9    0
    ## [4,]    0    0    0   12

``` r
#A%*%B  #dimensiones incompatibles
```

**8. Crea una función para calcular *P*<sup>6</sup>**
$P = \\begin{pmatrix} 1 & 2 & 3 \\\\ -2 & 4 & -2 \\\\ 1 & 0 & 1 \\end{pmatrix}$

``` r
P <- matrix(c(1,-2,1,2,4,0,3,-2,1), nrow=3, ncol=3)
  # %*% este es el multiplicador de matrices

potencia <- function(X,n){M=X;
for (i in 2:n){M=M%*%X};
print(M)}

potencia(P,6)
```

    ##       [,1]  [,2]  [,3]
    ## [1,] -1792    24 -2824
    ## [2,]  -464 -2416 -1344
    ## [3,]  -648   440  -912

**9. Resolver el sistema de ecuaciones**
$3x - y + z = -1\\\\9x - 2y + z = -9\\\\3x + y - 2z = -9$

``` r
A =matrix(c(3,9,3,-1,-2,1,1,1,-2), ncol=3,nrow=3)
A
```

    ##      [,1] [,2] [,3]
    ## [1,]    3   -1    1
    ## [2,]    9   -2    1
    ## [3,]    3    1   -2

``` r
L <-c(-1,-9,-9)
solve(A,L)
```

    ## [1] -1  2  4

**10. Utilizando la ayuda de R, investigue para qué sirven las funciones
`eigen()` y `det()`**

``` r
eigen(A)
```

    ## eigen() decomposition
    ## $values
    ## [1]  1.732051 -1.732051 -1.000000
    ## 
    ## $vectors
    ##           [,1]        [,2]          [,3]
    ## [1,] 0.2955268 -0.08260515  5.441136e-16
    ## [2,] 0.8363784  0.48159851 -7.071068e-01
    ## [3,] 0.4616655  0.87249027 -7.071068e-01

``` r
det(A)
```

    ## [1] 3

**11. Considerando las matrices**

$$

B=
A =
$$

Calcular *A* ⋅ *B* − *A**B*<sup>*t*</sup>

``` r
b <- c(1:10)
c <- c(b*2)
d <- c(b*3)
e <- c(b*4)
f <- c(b*5)

B <- cbind(b,c,d,e,f)
B
```

    ##        b  c  d  e  f
    ##  [1,]  1  2  3  4  5
    ##  [2,]  2  4  6  8 10
    ##  [3,]  3  6  9 12 15
    ##  [4,]  4  8 12 16 20
    ##  [5,]  5 10 15 20 25
    ##  [6,]  6 12 18 24 30
    ##  [7,]  7 14 21 28 35
    ##  [8,]  8 16 24 32 40
    ##  [9,]  9 18 27 36 45
    ## [10,] 10 20 30 40 50

``` r
x <- c(0,1) 
x1 <- rep(x,7)


y <- c(0,0,1) 
y1 <- rep(y,2)

z <- c(1,0,1,1,0)

A <- matrix(c(x1,y1,z), nrow =5, ncol =5, by=TRUE)
A
```

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    0    1    0    1    0
    ## [2,]    1    0    1    0    1
    ## [3,]    0    1    0    1    0
    ## [4,]    0    1    0    0    1
    ## [5,]    1    0    1    1    0

``` r
#A%*%B #no cumple 
primero <-B%*%A 
primero
```

    ##       [,1] [,2] [,3] [,4] [,5]
    ##  [1,]    7    8    7    9    6
    ##  [2,]   14   16   14   18   12
    ##  [3,]   21   24   21   27   18
    ##  [4,]   28   32   28   36   24
    ##  [5,]   35   40   35   45   30
    ##  [6,]   42   48   42   54   36
    ##  [7,]   49   56   49   63   42
    ##  [8,]   56   64   56   72   48
    ##  [9,]   63   72   63   81   54
    ## [10,]   70   80   70   90   60

``` r
trans <- t(B)
segundo <- A%*%trans
segundo
```

    ##      [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
    ## [1,]    6   12   18   24   30   36   42   48   54    60
    ## [2,]    9   18   27   36   45   54   63   72   81    90
    ## [3,]    6   12   18   24   30   36   42   48   54    60
    ## [4,]    7   14   21   28   35   42   49   56   63    70
    ## [5,]    8   16   24   32   40   48   56   64   72    80

``` r
#primero-segundo  #no sale
```

**12. Considere**
*β̂* = (*X*<sup>*t*</sup> ⋅ *X*)<sup> − 1</sup> ⋅ *X*<sup>*t*</sup> ⋅ *Y*

Determine la matriz *β̂*

$$

x=
y =
$$

``` r
a <- rep(1,5)
a
```

    ## [1] 1 1 1 1 1

``` r
b <- c(1,-1,0,1,2)

x <- cbind(a,b)
x
```

    ##      a  b
    ## [1,] 1  1
    ## [2,] 1 -1
    ## [3,] 1  0
    ## [4,] 1  1
    ## [5,] 1  2

``` r
y <- rbind(0,0,1,1,3)
y
```

    ##      [,1]
    ## [1,]    0
    ## [2,]    0
    ## [3,]    1
    ## [4,]    1
    ## [5,]    3

``` r
m <- t(x)
n <- m%*%x
s <- solve(n)
t <- s%*%m
u <- t%*%y
u  
```

    ##        [,1]
    ## a 0.5384615
    ## b 0.7692308

``` r
t(x)%*%x %>% solve() %*% t(x) %*% y 
```

    ##        [,1]
    ## a 0.5384615
    ## b 0.7692308

**13. Corre el siguiente código para cargar los vectores `year` y
`co2`** en memoria

``` r
data(co2)
means = aggregate(co2, FUN=mean)
year = as.vector(time(means))
co2 = as.vector(means)
```

-   El vector `co2` contiene medidas de *C**O*<sub>2</sub> en la
    atmósfera, en unidades de *ppm*, durante el periodo 1959-1997. El
    vector `year` contiene sus años correspondientes.
-   Calcular un vector de diferencias de *C**O*<sub>2</sub> entre años
    consecutivos, que sería:
    -   *C**O*<sub>2</sub> en 1960 menos *C**O*<sub>2</sub> en 1959
    -   *C**O*<sub>2</sub> en 1961 menos *C**O*<sub>2</sub> en 1960
    -   y así sucesivamente…
-   Crear un **plot** con lineas y puntos mostrando las diferencias
    consecutivas de *C**O*<sub>2</sub> en función del tiempo (1960,
    1961, etc…), en **negrita**
-   La diferencia de concentración de *C**O*<sub>2</sub> entre 2020 y
    2019 fue igual a 2.64. Agregar un punto rojo representando esa
    diferencia al plot ya creado (usar una forma diferente, como
    `pch=4`)

**14. **

-   Lee el archivo `rainfall.csv` como un `data.frame`
-   Calcula e imprime un vector con los nombres de las estaciones donde
    al menos uno de los meses tiene una precipitación superior a 180mm.

## Parte 3

**15. Manipule los dataframe según se solicite**

Se tiene el conjuntos de datos de precipitación diaria (período 1980 -
2013) de ciertas estaciones meteorológicas (**raingaugeDataset.csv**),
donde cada una de estas están asociadas a un código único (**p.e.
qc00000208**). Asimismo, se tiene una lista con los nombres, códigos,
coordenadas y elevación de cada una de las estaciones
(**listRaingauge.csv**).

A cada grupo le corresponde la siguiente estación:

-   **Grupo 01**: MALLARES
-   **Grupo 02**: TABACONAS
-   **Grupo 03**: PUERTO PIZARRO
-   **Grupo 04**: MORROPON
-   **Grupo 05**: SAN MIGUEL
-   **Grupo 06**: CHULUCANAS
-   **Grupo 07**: LAMBAYEQUE
-   **Grupo 08**: EL LIMON
-   **Grupo 09**: EL SALTO
-   **Grupo 10**: CHUSIS

``` r
data2 <- as_tibble(read.csv("ProgramacionR-master/data/raingaugeDataset.csv"))
names(data2)
```

    ##  [1] "date"       "qc00000132" "qc00000135" "qc00000207" "qc00000208"
    ##  [6] "qc00000211" "qc00000219" "qc00000230" "qc00000231" "qc00000235"
    ## [11] "qc00000237" "qc00000238" "qc00000240" "qc00000241" "qc00000247"
    ## [16] "qc00000248" "qc00000250" "qc00000255" "qc00000278" "qc00000281"
    ## [21] "qc00000301" "qc00000304"

``` r
data3 <- as_tibble(read.csv("ProgramacionR-master/data/listRaingauge.csv"))
names(data3)
```

    ## [1] "DEPARTAMENTO" "NOM_EST"      "CODIGO"       "LON"          "LAT"         
    ## [6] "ALT"

``` r
est <- dplyr::select(data3, NOM_EST, CODIGO) %>% 
  dplyr::filter(NOM_EST == "MORROPON")
```

De lo descrito anteriormente, se solicita:

1.  Determine la cantidad de **missing values** de la serie de tiempo a
    paso diario.

``` r
data2 %>% dplyr::mutate(date = as.Date(date, format = "%d/%m/%Y")) %>%
  rename(pp = qc00000235) %>% 
  dplyr::select(date, pp) %>%
  group_by(date) %>% 
  mutate(missVal = sum(is.na(pp)))
```

    ## # A tibble: 12,419 x 3
    ## # Groups:   date [12,419]
    ##    date          pp missVal
    ##    <date>     <dbl>   <int>
    ##  1 1980-01-01     0       0
    ##  2 1980-01-02     0       0
    ##  3 1980-01-03     0       0
    ##  4 1980-01-04     0       0
    ##  5 1980-01-05     0       0
    ##  6 1980-01-06     0       0
    ##  7 1980-01-07     0       0
    ##  8 1980-01-08     0       0
    ##  9 1980-01-09     0       0
    ## 10 1980-01-10     0       0
    ## # ... with 12,409 more rows

2.  Calcule la serie de tiempo de precipitación **acumulada mensual**
    (si el \# de días con missing values, en un mes, supera el 10%, la
    precipitación acumulada mensual será considerado como un **`NA`**).

``` r
ejerc2 <- data2 %>% dplyr::mutate(date = as.Date(date, format = "%d/%m/%Y")) %>% 
  rename(pp = qc00000235) %>%
  dplyr::select(date, pp) %>%
  group_by(date = str_sub(date, 1, 7)) %>% 
  mutate(missVal = sum(is.na(pp)) * 100 / n()) %>%   
  summarize(
    pp = sum(pp , na.rm = T),
    missVal = unique(missVal)
  ) %>% 
  mutate(
    pp = ifelse(missVal >= 10 , NA, pp),
    date = as.Date(sprintf("%1$s-01", date)), #Para agregar el 01 a la fecha
    month= str_sub(date, 6, 7)
  )
```

3.  Determine la cantidad de **missing values** de la serie de tiempo a
    paso mensual.

``` r
sum(is.na(ejerc2$pp))
```

    ## [1] 15

``` r
max(ejerc2$pp, na.rm = T)
```

    ## [1] 1030.7

``` r
min(ejerc2$pp, na.rm = T)
```

    ## [1] 0

4.  Cree una función que calcule, a partir de los datos de preicpitación
    mensual, la **climatología (Ene-Dic)** para el **período
    1980-2010**.

``` r
#ejerc4 <- ejerc2 %>%
#  group_by(pp) %>% 
#  na.rm = T

for (pp1 in ejerc2$pp){
  if (pp1 %in% 0:250) {
    print("desertico")
  } else if (pp1 %in% 251:500) {
    print("arido")
  } else if (pp1 %in% 501: 1030.7) {
    print("moderadamente lluvioso")
  } else {
    print("NA")
  }
}
```

    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "arido"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "arido"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"
    ## [1] "NA"
    ## [1] "desertico"
    ## [1] "desertico"

5.  Poltear (boxplot) la variabilidad de los valores mensuales (Ene-Dic)
    para el período 1980-2013.

``` r
view(ejerc2)

length(levels(data3$NOM_EST))
```

    ## [1] 0

``` r
table(data3$NOM_EST)
```

    ## 
    ##                   ACOBAMBA                    ACOMAYO 
    ##                          1                          1 
    ##                       ALAO               ALCANTARILLA 
    ##                          1                          1 
    ##                     ANANEA                    ANDAHUA 
    ##                          1                          1 
    ##                    ANDAJES                  ANTIOQUIA 
    ##                          1                          1 
    ##                      APLAO                    ARAHUAY 
    ##                          1                          1 
    ##                      ARAPA                   ASUNCION 
    ##                          1                          1 
    ##         AUGUSTO WEBERBAUER                    AUTISHA 
    ##                          1                          1 
    ##                    AYABACA                    AYAVIRI 
    ##                          1                          2 
    ##                        AYO                   AZANGARO 
    ##                          1                          1 
    ##                    BAGAZAN                     BERNAL 
    ##                          1                          1 
    ##                    BRETANA                BUENA VISTA 
    ##                          1                          1 
    ##                 CABANILLAS                   CACHACHI 
    ##                          1                          1 
    ##                 CACHICADAN                  CAJABAMBA 
    ##                          1                          1 
    ##                    CALACOA                     CALANA 
    ##                          1                          1 
    ##                  CALLANCAS                     CANETE 
    ##                          1                          1 
    ##                      CANTA                  CAPACHICA 
    ##                          1                          1 
    ##                     CAPAZO                  CARAMPOMA 
    ##                          1                          1 
    ##                    CARANIA                   CARAVELI 
    ##                          1                          1 
    ##                CARHUACAYAN                    CAY CAY 
    ##                          1                          1 
    ##                    CAYALTI                    CCATCCA 
    ##                          1                          1 
    ##                   CHACCHAN                    CHACHAS 
    ##                          1                          1 
    ##                CHALLAPALCA                    CHAZUTA 
    ##                          1                          1 
    ##                    CHICHAS                   CHIGUATA 
    ##                          1                          1 
    ##                  CHILCAYOC                    CHILETE 
    ##                          1                          1 
    ##                     CHIVAY                CHOCLOCOCHA 
    ##                          1                          1 
    ##                      CHOCO                   CHONTALI 
    ##                          1                          1 
    ##                  CHUAPALCA                     CHUGUR 
    ##                          1                          1 
    ##                 CHULUCANAS             CHUQUIBAMBILLA 
    ##                          1                          1 
    ##                     CHUSIS                 COCHABAMBA 
    ##                          1                          1 
    ##                     COJATA                 COLQUEPATA 
    ##                          1                          1 
    ##                     COPARA                   CORACORA 
    ##                          1                          1 
    ##                    CORDOVA                  COTAHUASI 
    ##                          1                          1 
    ##                    CRUCERO               CRUCERO ALTO 
    ##                          1                          1 
    ##               CUEVA BLANCA                 CUNUMBUQUE 
    ##                          1                          1 
    ##                  CURAHUASI                    CUTERVO 
    ##                          1                          1 
    ##                  CUYO CUYO                DESAGUADERO 
    ##                          1                          1 
    ##     DOS DE MAYO (J. OLAYA)                 EL ESPINAL 
    ##                          1                          1 
    ##                  EL FRAYLE                   EL LIMON 
    ##                          1                          1 
    ##                EL PORVENIR                   EL SALTO 
    ##                          1                          1 
    ##                   EL TIGRE         FRANCISCO ORELLANA 
    ##                          1                          1 
    ##             GENARO HERRERA                     GORGOR 
    ##                          1                          1 
    ##              GRANJA KCAYRA          HACIENDA BERNALES 
    ##                          1                          1 
    ##            HACIENDA BIGOTE            HACIENDA PUCARA 
    ##                          1                          1 
    ##           HACIENDA SHUMAYA              HUACAMARCANGA 
    ##                          1                          1 
    ##                    HUACHOS                 HUAMACHUCO 
    ##                          1                          1 
    ##                    HUAMANI                HUAMANTANGA 
    ##                          1                          1 
    ##                     HUAMBO                  HUANCALPI 
    ##                          1                          1 
    ##                   HUANCANE                   HUANCATA 
    ##                          1                          1 
    ##                     HUANEC                HUANGACOCHA 
    ##                          1                          1 
    ##                    HUANUCO               HUARAYA MOHO 
    ##                          1                          1 
    ##                   HUARMACA                     HUAROS 
    ##                          1                          1 
    ##                     HUAYAN                     HUAYAO 
    ##                          1                          1 
    ##                     ICHUNA                      ILAVE 
    ##                          1                          1 
    ##                        ILO                      IMATA 
    ##                          1                          1 
    ##                    INGENIO               ISLA TAQUILE 
    ##                          1                          1 
    ##                      JAUJA          JAYANCA (LA VINA) 
    ##                          1                          1 
    ##                  JEPELACIO                   JUANCITO 
    ##                          1                          1 
    ##                     JULCAN                       JULI 
    ##                          1                          1 
    ##               LA ANGOSTURA               LA ESPERANZA 
    ##                          1                          1 
    ##                    LA JOYA                LA PAMPILLA 
    ##                          1                          1 
    ##                   LACHAQUI                      LAMAS 
    ##                          1                          1 
    ##                 LAMBAYEQUE                      LAMPA 
    ##                          1                          2 
    ##                   LANCONES                      LANGA 
    ##                          1                          1 
    ##                LAS SALINAS                     LIRCAY 
    ##                          1                          1 
    ##                      LIVES                      LLAMA 
    ##                          1                          1 
    ##                     LLAUTA                    LOCUMBA 
    ##                          1                          1 
    ##            LOMAS DE LACHAY                    LUCANAS 
    ##                          1                          1 
    ##                  MACHAHUAY                   MADRIGAL 
    ##                          1                          1 
    ##                   MALLARES                   MATUCANA 
    ##                          1                          1 
    ##                  MAZO CRUZ                      MILPO 
    ##                          1                          1 
    ##                 MIRAFLORES                  MOLLEPATA 
    ##                          1                          1 
    ##                   MOQUEGUA                   MORROPON 
    ##                          1                          1 
    ##                     MUNANI                       NANA 
    ##                          1                          1 
    ##                 NARANJILLO                 NUEVO LIMA 
    ##                          1                          1 
    ##                      OCROS                    OCUCAJE 
    ##                          1                          1 
    ##                  ORCOPAMPA                       OYON 
    ##                          1                          1 
    ##                    PACARAN                     PACCHO 
    ##                          1                          1 
    ##                      PALCA                     PALLAC 
    ##                          1                          1 
    ##               PAMPA BLANCA             PAMPA DE MAJES 
    ##                          2                          1 
    ##                PAMPA LIBRE                  PAMPAHUTA 
    ##                          1                          1 
    ##                    PANANGA                PARIACANCHA 
    ##                          1                          1 
    ##                    PARQUIN                     PARURO 
    ##                          1                          1 
    ##                  PAUCARANI                      PAUZA 
    ##                          1                          1 
    ##                     PELEJO                     PICOTA 
    ##                          1                          1 
    ##                      PICOY                   PILLONES 
    ##                          1                          1 
    ##                   PILLUANA                       PIRA 
    ##                          1                          1 
    ##                      PIRCA                      PISAC 
    ##                          1                          1 
    ##                   PIZACOMA        PONGO DE CAYNARACHI 
    ##                          1                          1 
    ##                   PORCULLA                    PORPERA 
    ##                          1                          1 
    ##                   PROGRESO       PUCALLPA - HUIMBAYOC 
    ##                          1                          1 
    ##                     PUCARA                    PUCHACA 
    ##                          1                          1 
    ##             PUERTO PIZARRO        PULLHUAY (AYAHUASI) 
    ##                          1                          1 
    ##                       PUNO                PUNTA ATICO 
    ##                          1                          1 
    ##                PUNTA COLES                     PUQUIO 
    ##                          1                          1 
    ##                     PUTINA            QUEBRADA SHUGAR 
    ##                          1                          1 
    ##               QUEROCOTILLO            QUINISTAQUILLAS 
    ##                          1                          1 
    ##                 QUIRUVILCA                     RECUAY 
    ##                          1                          1 
    ##                      REQUE                     RICRAN 
    ##                          1                          1 
    ##                  SALAMANCA                 SALCABAMBA 
    ##                          1                          1 
    ##                   SALLIQUE                SAMA GRANDE 
    ##                          1                          1 
    ##                SAN ANTONIO                 SAN BENITO 
    ##                          1                          1 
    ##                 SAN CAMILO                   SAN JUAN 
    ##                          1                          1 
    ## SAN JUAN DE CASTROVIRREYNA          SAN JUAN DE YANAC 
    ##                          1                          1 
    ##    SAN LAZARO DE ESCOMARCA                 SAN MARCOS 
    ##                          1                          1 
    ##                 SAN MIGUEL                  SAN PABLO 
    ##                          1                          1 
    ##                  SAN PEDRO                 SAN RAFAEL 
    ##                          1                          1 
    ##                  SAN RAMON                 SANTA CRUZ 
    ##                          1                          1 
    ##              SANTA EULALIA       SANTA MARIA DE NANAY 
    ##                          1                          1 
    ##     SANTA RITA DE CASTILLA                 SANTA ROSA 
    ##                          1                          2 
    ##      SANTIAGO DE CHOCORVOS           SANTIAGO DE TUNA 
    ##                          1                          1 
    ##                  SAPILLICA                    SAPOSOA 
    ##                          1                          1 
    ##                      SAUCE          SAUSAL DE CULUCAN 
    ##                          1                          1 
    ##                    SHANUSI                     SIBAYO 
    ##                          1                          1 
    ##                     SIHUAS                   SINSICAP 
    ##                          1                          1 
    ##                   SITAJARA                 SONDORILLO 
    ##                          1                          1 
    ##                    SORITOR                   SUSAPAYA 
    ##                          1                          1 
    ##                  TABACONAS                  TABALOSOS 
    ##                          1                          1 
    ##          TAHUACO - YUNGUYO                   TALABAYA 
    ##                          1                          1 
    ##          TALLA (GUADALUPE)                      TAMBO 
    ##                          1                          1 
    ##                      TANTA                     TARATA 
    ##                          1                          1 
    ##                TINGO MARIA                   TOCMOCHE 
    ##                          1                          1 
    ##                    TOQUELA                     TULUCE 
    ##                          1                          1 
    ##                   TULUMAYO                 TUNEL CERO 
    ##                          1                          1 
    ##                     UBINAS                      UDIMA 
    ##                          1                          1 
    ##                      VILCA               VILCASHUAMAN 
    ##                          1                          1 
    ##                     VIQUES                     VIRREY 
    ##                          1                          1 
    ##                 YANAQUIHUA                     YANTAC 
    ##                          1                          1
