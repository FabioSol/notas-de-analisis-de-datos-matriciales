---
title: "Operaciones de píxeles"
date: 2026-01-20T18:28:37-06:00
draft: false
type: "document"
description: "Operaciones básicas con píxeles en imágenes digitales"
showDescription: false
weight: 1
---

## Operaciones básicas con píxeles

### Contraste

Que haya mas contraste significa que los valores de los pixeles estan mas separados.

Se puede 'medir' el contraste con medidas de dispersion. 

La maestra menciona el rango de los valores:

$$C = I_{max} - I_{min}$$

El contraste se puede alterar utilicando un factor de contraste $f$:

- $f = 1$ : no hay cambio
- $f > 1$ : aumenta el contraste
- $0 < f < 1$ : disminuye el contraste

Lo que se hace con el factor de contraste es multiplicarlo por los pixeles. Si el resultado es mayor a 255, se asigna 255.

$$I'(x,y) = \min(255, f \cdot I(x,y))$$

Aplicando un factor de contraste de 0.5 y 2 a la imagen de ejemplo:

<div style="display: flex; flex-direction: row; gap: 10px;">
<p><img src="../img_contraste_50.png" alt="Imagen contraste 0.5"></p>
<p><img src="../img_contraste_200.png" alt="Imagen contraste 2"></p>
</div>

### Brillo

El brillo se puede alterar sumando un valor $b$ a los pixeles. Si el resultado es mayor a 255, se asigna 255. Si es menor a 0, se asigna 0.

$$I'(x,y) = \min(255, \max(0, I(x,y) + b))$$
Aplicando un valor de brillo de -70 y 70 a la imagen de ejemplo:
<div style="display: flex; flex-direction: row; gap: 10px;">
<p><img src="../img_brillo_neg_70.png" alt="Imagen brillo -70"></p>
<p><img src="../img_brillo_pos_70.png" alt="Imagen brillo 70"></p>
</div>



