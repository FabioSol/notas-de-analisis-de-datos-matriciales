---
title: "Fundamentos"
date: 2026-01-20T18:28:37-06:00
draft: false
type: "document"
description: "Fundamentos del curso de Análisis de Datos Matriciales" 
weight: 2
---

## Objetivo del curso

Este no es un curso de Deep Learning.

Conocer las bases y fundamentos del procesamiento de imagenes

## Definición de imagen digital

Una imagen digital es una funcion bidimensional discreta $I(x,y)$  donde $x$ y $y$ son las coordenadas espaciales y el valor de la función en cualquier par de coordenadas  $(x,y)$ va de $0$ a $255$.

Se le llama resolucion espacial al número de pixeles en la imagen.

A cada par de coordenadas $(x,y)$ se le llama píxel (picture element).

$$
I(x,y) =
\begin{bmatrix}
I(1,1) & I(1,2) & I(1,3) & \cdots & I(1,n) \\\\
I(2,1) & I(2,2) & I(2,3) & \cdots & I(2,n) \\\\
I(3,1) & I(3,2) & I(3,3) & \cdots & I(3,n) \\\\
\vdots & \vdots & \vdots & \ddots & \vdots \\\\
I(m,1) & I(m,2) & I(m,3) & \cdots & I(m,n) \\\\
\end{bmatrix}
$$

### Formatos


#### RGB

Una imagen a color se representa con tres matrices, una para cada canal de color: rojo, verde y azul.

$$
I_R(x,y), I_G(x,y), I_B(x,y)
$$

en python, en OpenCV, el orden es BGR.

![imagen RGB](../rgb-example.png)

#### Escala de grises

A diferencia de las imagenes a color, las imagenes en escala de grises solo tienen una matriz. lo que las hace mas faciles de procesar.

#### Binarias

También conocidas como imágenes en blanco y negro, solo tienen dos valores posibles: 0 y 1 (o 0 y 255).


### conversion de RGB a Escala de grises

podemos visualizar cada canal de color por separado.

por ejemplo con `lennacolor.png`

![lennacolor](../lennacolor.png)

descomponemos la imagen en sus canales:

![lenna channels](../lennachannels.png)

Podemos identificar que el color mas claro (facil de visualizar) es el canal verde.

Esta es la razon por la cual cuando requerimos trabajar con un solo canal, se suele elegir el canal verde.

aqui tenemos los tres canales por separado en escala de grises

![lenna gray channels](../lennagraychannels.png)

confirmamos que el canal verde sigue siendo el mas claro.