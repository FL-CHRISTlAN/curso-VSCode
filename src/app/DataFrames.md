---
noteId: "27b87080a8fa11e998bcd37a20b305d8"
tags: []
title: "DataFramesEnR"
author: "CH!!"
date: "8 de mayo de 2019"
output:
  html_document:
    fig_caption: "yes"
    highlight: "pygments"
    number_sections: "yes"
    theme: "lumen"
    toc: "yes"
  pdf_document:
    fig_caption: "yes"
    highlight: "tango"
    number_sections: "yes"
    toc: "yes"
    toc_depth: 5

---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# Dataframes (o DataSets) en R

## Ejemplo de carga de un dataset desde internet. 

```{r message=TRUE, warning=TRUE, paged.print=TRUE}
#asigno a la variable olive el dataset olive.dat desde internet
olive = read.table("https://maitra.public.iastate.edu/stat501/datasets/olive.dat")

#leo la dimension de olive, siendo esta una tabla de 573 filas por 9 col.
dim(olive)

#puedo acceder a los nombres de las columnas con las funcion names()
names(olive)

# o a todo su contenido simplemente llamando a la variable que contiene el dataset
# por fines practicos solo se visualizará su head y tail, ya que de caso contrario
# Al exportar a PDF, representaria absolutamente todos los datos.
head(olive, 5)
tail(olive, 5)
```

## Usando Bulls.dat desde 501 DataSets
El valor header de los datasets viene por defecto en false, con lo cual muchas veces y según la fuente, habra que cargarle las cabeceras con valores descriptivos.

de forma que nos quede la tabla de datos como

| nombre_Col-01 | nombre_Col-02 | .... | nombre_Col-n  |
|---------------|---------------|------|---------------|
| fila-01-col-01| fila-01-col-02| .... | fila-01-col-n |
| fila-02-col-01| fila-02-col-02| .... | fila-02-col-n |
| fila-03-col-01| fila-03-col-02| .... | fila-03-col-n |

__Nota:__ no voy a utilizar archivos locales, ya que los mismos se puede acceder desde su path relativo o su path absoluto; Pero en cambio voy a usar la carga via URL.
Por lo tanto, no tendra sentido la modificacion de este documento sin acceso a internet.

Para este caso, usaremos nombres de columas aproximados en base a la descripción provista por la página.

### Datos descriptivos de bulls.dat

> Breed (1/5/8), Sale Price, Yearling height at shoulder (in.), Fat Free Body (lbs.), Percent Fat-free body, Frame -- scale from 1 (small) to 8 (large), Back fat (in.), sale height at shoulder (in.) and sale weight (lbs.) of three breeds of bulls. (Table 1.10)

Por lo tanto podemos decir que:

>
- Breed
- SalePrice
- YearlingHeight
- Weight
- Weight_percent
- Scale_1-8
- BackFat
- SaleHeight
- SaleWeight

Pueden inicialmente ser los nombres referenciales de cada una de las columnas.


```{r}
## Carga de datos con sus nombres de cabecera.
bulls = read.table("https://maitra.public.iastate.edu/stat501/datasets/bulls.dat",
                   header = FALSE,
                   col.names = c("Breed",
                             "SalePrc",
                             "YearHgt",
                             "WgtLbs",
                             "WgtPrc",
                             "Scale_1-8",
                             "BkFat",
                             "SaleHgt",
                             "SaleWgt"
                             )
                   )
head(bulls, 5)

#Una buena practica es usar str() para verificar la estructura de datos.
str(bulls)
```

## Creando DataFrames a partir de Vectores

---------------

## Funsiones en DataFrames


