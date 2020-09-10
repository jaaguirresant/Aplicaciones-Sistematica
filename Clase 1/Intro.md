# Taller 1. Lectura de datos y manipulación de árboles filogenéticos

_[Volver a inicio](/README.md)_

## Nociones básicas de R

1. Limpiar la memoria antes de comenzar

```
rm(list=ls())
```
2. Ubicarse en el respectivo directorio de trabajo. Usar el menú de R Studio o usar el siguiente comando:

```
setwd("/Users/home/Intro_R/")
getwd() # Esta función permite ver si estamos en la carpeta correcta
list.files() # Este comando permite ver que archivos hay en la carpeta.
```

3. Instalar y abrir los paquetes. Los paquetes son los programas escritos para que R haga operaciones complejas. Hay miles de programas. Para comenzar, usaremos el paquete "stats" para hacer operaciones estadísticas:

```
install.packages("stats") # este comando descarga el programa desde internet
library(stats) # este comando abre el programa.
```
4. R hace operaciones matemáticas sin problema:

```
2+2
3*4
15/3
((3+4)*5)/5
2^3
5 > 3
```

5. Las variables se pueden guardar como objetos, usando los símbolos "<-" o "->" "=":

```
x <- 2+2
y <- 3*4
z = ((3+4)*5)/5
M <- (x*y)^z

ls() # Este comando permite ver que objetos hay guardados en memoria.
```

6. Vectores. Un vector es la estructura de datos más sencilla en R. Un vector es una colección de uno o más datos del mismo tipo.

```
3
is.vector(3)
length(3)

1:10

# Vector numérico
c(1, 2, 3, 5, 8, 13)

# Vector de cadena de texto
c("arbol", "casa", "persona")

# Vector lógico
c(TRUE, TRUE, FALSE, FALSE, TRUE)

# Combinaciones de vectores:
mi_vector <- c(TRUE, FALSE, TRUE)
mi_vector <- c(mi_vector, FALSE)
mi_vector

mi_vector_1 <- c(1, 3, 5)
mi_vector_2 <- c(2, 4, 6)
mi_vector_3 <- c(mi_vector_1, mi_vector_2)
mi_vector_3

# vectorización de operaciones:

mi_vector <- c(2, 3, 6, 7, 8, 10, 11)
mi_vector + 2
mi_vector * 2
mi_vector > 7
mi_vector < 7
mi_vector == 7
```

7. Las funciones nos premiten hacer operaciones más complejas:

```
mean(medidas) -> promedio
sd(medidas) -> desviacion_estandar
```

8. Cuando no entendemos que hace una función o que variables debemos usar para que funcione, podemos usar la ayuda con "?" y "help()":

```
?mean
help("mean")
help(package = "stats") # o podemos ver toda la documentcaión de un paquete
```

9. Matrices (función "matrix")

```
# Creemos un vector numérico del uno al doce
1:12

# Pongámos los 12 números en una matriz sin especificar filas ni columnas
matrix(1:12)

# Tres filas y cuatro columnas
matrix(1:12, nrow = 3, ncol = 4)

# Cuatro filas y tres columnas
matrix(1:12, nrow = 4, ncol = 3)

# Propiedades de las matrices

mi_matriz <- matrix(1:12, nrow = 4, ncol = 3)
class(mi_matriz)

dim(mi_matriz) # me dice las dimensiones de mi matriz
mi_vector <- 1:12
dim(mi_vector) # la función dim no funciona si no hay más de una fila

# Podemos hacer operaciones con todos los valores de la matriz:

mi_matriz + 1
mi_matriz * 2
```

10. Data frames (tablas compuestas). Los data frames son estructuras de datos de dos dimensiones (rectangulares) que pueden contener datos de diferentes tipos, por lo tanto, son heterogéneas.

```
mi_df <- data.frame(
  "entero" = 1:4, 
  "factor" = c("a", "b", "c", "d"), 
  "numero" = c(1.2, 3.4, 4.5, 5.6),
  "cadena" = as.character(c("a", "b", "c", "d"))
)

mi_df
dim(mi_df)

# names() nos permite ver los nombres de las columnas
names(mi_df)

# Propiedades de un data frame

mi_df <- data.frame("nombre" = c("Armando", "Elsa", "Ignacio", "Olga"),
                    "edad" = c(20, 24, 22, 30),
                    "sexo" = c("H", "M", "M", "H"),
                    "grupo" = c(0, 1, 1, 0))

# Primero verifiquemos el resultado
mi_df
dim(mi_df)

# Podemos extraer columnas y filas usando corchetes y guardarlas en objetos
mi_df[1] -> nombres # Extrae la primer columna, incluyendo el nombre de la columna
nombres
mi_df[c(1, 3)]

mi_df[3,] # Extraer la fila 3
mi_df[ ,1] # Extraer columna 1 sin incluir el nombre del campo
mi_df[3, 3] # Extrae la información de la celda de la columna 3 y la fila 3.
mi_df[2:3, 3] # Extrae simultáneamente la información de las celdas de las filas 2 y 3 en la columna 3.
mi_df[1:2, c(2, 4)] # ????

# Podemos extraer información usando los nombres de las columnas:
mi_df["nombre"]
mi_df["grupo"]
mi_df[c("edad", "sexo")]
mi_df[c("sexo", "edad")]

# Podemos usar el signo de pesos "$" en vez del corchete:
mi_df$nombre
mi_df$"nombre"
class(mi_df$nombre)
```


## Ejercicio 1

Escriba al frente de cada comando que operación realizó. Para el ejercicio, vamos a usar datos florales de plantas del género Iris. Estos datos están guardados en la tabla llamada "Iris", la cual viene incluida en el paquete "stats":

```
iris
class(iris)
iris$Sepal.Length
mean(iris$Sepal.Length)
log(iris[1:4])
mean(log(iris$Sepal.Length))
iris[1:2]
iris[1:2, ]
iris[,1:2]
iris[4:5, c("Sepal.Width","Species")]
iris$Sepal.Length > 7.5
iris[iris$Sepal.Length > 7.5, ]
iris[iris$Sepal.Length > 7.5, 5]
iris[iris$Sepal.Length > 7.5, "Species"]
iris[iris$Sepal.Width < 3 & iris$Species == "setosa", ]
iris[iris$Petal.Width >= 5]

?subset
subset(x = iris, subset = Sepal.Length > 7.5)
subset(x = iris, subset = Sepal.Length > 7.5, select = c("Sepal.Length", "Species"))
subset(x = iris, subset = Sepal.Length > 7.5 & Sepal.Width == 3)
```

#

## Árboles filogenéticos en R

_Ejercicio basado en los ejemplos de Liam Revell y Luke Harmon https://lukejharmon.github.io/ilhabela/instruction/2015/07/02/introduction-phylogenies-in-R/_

Para este ejercicio usaremos los paquetes ape y phytools. Este último paquete es excelente para crear visualizaciones y hacer análisis complejos con datos filogenéticos. Para explorar todo el potencial de este paquete, recomiendo visitar el blog de Liam Revel, creador del paquete: http://blog.phytools.org/

```
setwd("working directory") 
library(ape)
library(phangorn)
library(phytools)
```

1. Generar un árbol manual.

Primero, crear la base del árbol con dos taxones para poder enraizar los otros taxones.

```
tree<-pbtree(n=2,tip.label=c("Salamandra","humano"))
```

Con la función bind.tip podemos agregar interactivamente nuevas especies a la rama que queramos:

```
tips<-c("Rana","Serpiente","Ave")
for(i in 1:length(tips)) tree<-bind.tip(tree,tips[i],interactive=TRUE)
```

También podemos hacer el árbol manualmente usando el formato Newick (parentético) y la función "read.tree":

```
tt="(((((((vaca, cerdo),ballena),(murciélago,(lemur,humano))),(cardenal,iguana)),coelacanto),bagre),tiburón);"
vert.tree<-read.tree(text=tt)
plot(vert.tree)
```

Finalmente, podemos exportar el árbol con la función "write.tree"

```
write.tree(tree, file = "Árbol_tetrapodos.tre")
```

**Tarea:** Dibujar un árbol filogenético de los animales usando únicamente 8 terminales y exportarlo a un archivo.

2. Manipulación de árboles filogenéticos.

La función "plot" y "plot.phylo" de ape permite hacer variaciones visuales al árbol filogenético. Por ejemplo:

```
plot(vert.tree,type="cladogram") # 
plot(unroot(vert.tree),type="unrooted")
plot(vert.tree,type="fan")
roundPhylogram(vert.tree)
```
**Tarea:** Explore que otros argumentos tiene la función "plot" y genere una imagen de un árbol filogenético diferente a los mostrados en el ejemplo.

Para realmente tener control del sinnúmero de ediciones que se pueden hacer con árboles filogenéticos, es muy importante entender que estos árboles son elementos de clase "phylo". Un objeto de clase "phylo" está compuesto de cuatro listas: (1) los nombres de los terminales del árbol "$tip.label"; (2)los nodos a los dos extremos de cada rama "$edge"; (3) el número de nodos internos "$Nnode"; y (4) la longitud de las ramas "$edge.length".

Para ver estos valores en nuestro árbol podemos usar la función "str"

```
vert.tree
str(vert.tree)
```

Para entender mejor un objeto de clase "phylo", generemos el siguiente árbol:

```
tree<-read.tree(text="(((A,B),(C,D)),E);")
plot(tree,type="cladogram",edge.width=2)
tree$edge # ¿Que significa esta matriz?
tree$tip.label
tree$Nnode
```

Conocer los valores de estos elementos nos permiten tener control absoluto de todas las partes del árbol y modificarlo de la manera que queramos. Una forma visual de identificar específicamente cada nodo y su ubicación en el árbol es usar las funciones "nodelables" y "tiplabels":

```
plot(tree,edge.width=2,label.offset=0.1,type="cladogram")
tree$Nnode
nodelabels()
tiplabels()
```

3. Exportar árboles filogenéticos en diferentes formatos.

Los dos formatos más populares para almacenar árboles filogenéticos son NEWICK y NEXUS. Para guardar nuestros áboles en estos formatos, usamos las funciones "write.tree" y "writeNexus":

```
write.tree(tree,"example.tre")
cat(readLines("example.tre"))

writeNexus(tree,"example.nex")
cat(readLines("example.nex"),sep="\n")
```
**Tarea:** describa estos dos formatos.

4. Simulación, visualización, extracción de clados y eliminación de terminales.

La función "pbtree" permite simular un árbol usando el módelo de nacimiento-muerte. La simulacion de arboles es extremadamente importante en la evaluación de hipótesis evolutivas de diversificación y evolución de carateres. Como ejemplo, simularemos un árbol de 40 terminales con una tasa de especiación de 1 y una tasa de extinción de 0.2:

```
set.seed(1) # Este comando lo pongo solo para poder repetir los análisis con el mismo árbol.
tree<-pbtree(b=1,d=0.2,n=40) # los 40 terminales son todos existentes (p.e. no extintos). Sin embargo, como hay extinción, la función generará terminales extintos.
plotTree(tree)
```

Digamos que solo me interesa investigar el clado cuyo ancestro es el nodo número 62. Para esto, es posible extraer el clado usando la función "extract.clade". Primero debemos visualizar donde se ubica el nodo 62 y despues ejecutar la funcion:

```
nodelabels()
tt62<-extract.clade(tree,62)
plotTree(tt62)
```
También es posible queramos quitar algunos terminales del árbol (p.e. si tenemos varias accesiones por especie). Con la función "drop.tip" vamos a extraer 10 terminales aleatoriamente del árbol simulado:

```
dtips<-sample(tree$tip.label,10)
dt<-drop.tip(tree,dtips)
plotTree(dt)
```
También podemos seleccionar cuales especies eliminar (p.e. las especies extintas):

```
plotTree(et<-drop.tip(tree,getExtinct(tree)),cex=0.7)
```

**Tarea:** Repita el ejercicio del punto 4 simulando un árbol de 50 terminales.

5. Árboles binarios y politómicos

Muchas veces los programa de filogenética resultan en árboles de consenso que contienen politomías o a veces en un solo árbol perfectamente bifurcado. El paquete "ape" lee ambos tipos de árboles; sin embargo, para análisis posteriores es importante estar seguro de que el árbol es bifucardo. Para esto, la función "is.binary.tree" es muy útil. Construyamos un árbol politómico y verificamos que nos dice la función "is.binary.tree":

```
t1<-read.tree(text="((A,B,C),D);")
plot(t1,type="cladogram")
is.binary.tree(t1)
```

Si el árbol no es binario, podemos resolver las politomias de forma aleatoria usando la función "multi2di":

```
t2<-multi2di(t1)
plot(t2,type="cladogram")
is.binary.tree(t2)
```

6. Otros rearreglos del árbol.

Además de las funciones explicadas arriba, podemos manipular los árboles de otras maneras. Por ejemplo:
 
   - Podemos rotar los nodos con función "rotate" y "rotateNodes":

```
plotTree(tree,node.numbers=T)
rt.50<-rotate(tree,50) ## primero, rotemos el nodo #50
plotTree(rt.50)

## o podemos rotar todos los nodos:

rt.all<-rotateNodes(tree,"all")
plotTree(rt.all)
```

   - Podemos enraizar el árbol con las funciones "root" y "reroot":

```
rr.67<-root(tree,node=67) # Enraizamos en el nodo 67.
plotTree(rr.67)

# Esto crea una trifurcación en la raiz. Para evitar esto, podríamos enraizar a lo largo de una rama usando la función "reroot":

rr.62<-reroot(tree,62,position=0.5*tree$edge.length[which(tree$edge[,2]==62)])
plotTree(rr.62)

# o podemos enraizar escogiendo un grupo externo:

tree_outgroup <-root(tree,outgroup="t33")
plotTree(tree_outgroup)
```

   - Podemos comparar dos árboles filogenéticos:

```

# Vamos a comparar el árbol original con el árbol rotado. Para ello, es necesario asegurarse que los dos árboles son idénticos con la función "all.equal":

all.equal(tree,rt.all)

## Se puede hacer lo mismo comparando el árbol original con rr.62:

all.equal(tree,rr.62) # En este caso, ¿son iguales o no?

## Ahora intentemos lo mismo pero con el árbol rr.62 sin enraizar:

all.equal(unroot(tree),unroot(rr.62)) #¿son iguales?
```
#
