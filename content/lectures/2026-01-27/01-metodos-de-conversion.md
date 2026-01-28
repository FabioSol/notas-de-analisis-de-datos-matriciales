---
title: "Métodos de conversión"
date: 2026-01-20T18:28:37-06:00
draft: false
type: "document"
description: "métodos de conversión de unidades"
showDescription: false
weight: 1
---

## Métodos de conversión

Estaremos trabajando con la siguiente imagen:

![Imagen de ejemplo](../img.png)

### Extraccion de plano

Vimos la clase pasada que el color que mas informacion tiene es el canal verde. por lo tanto podemos extraer un plano de color verde y trabajar con el.

```python
image = cv2.imread('imagen.jpg')
# Extraer el canal verde
green_channel = image[:, :, 1]
# Mostrar la imagen del canal verde
cv2.imshow('Canal Verde', green_channel)
```

![Imagen plano verde](../img_green_channel.png)

### Promedio de canales

Otra forma de convertir una imagen a escala de grises es promediando los valores de los tres canales (rojo, verde y azul).

```python
image = cv2.imread('imagen.jpg')
# Convertir a escala de grises promediando los canales
gray_image = image.mean(axis=2).astype(np.uint8)
```

![Imagen promedio de canales](../img_average_channels.png)

### Comparacion

<div style="display: flex; flex-direction: row; gap: 10px;">
<p><img src="../img.png" alt="Imagen de ejemplo"></p>
<p><img src="../img_green_channel.png" alt="Imagen plano verde"></p>
<p><img src="../img_average_channels.png" alt="Imagen promedio de canales"></p>
</div>


### Metodo Luma: ponderacion de canales

El método Luma utiliza una ponderación específica para cada canal de color, reflejando la sensibilidad del ojo humano a diferentes colores. Las fórmulas comúnmente utilizada es:

| Estándar | Ponderacion R  | Ponderacion G  | Ponderacion B | uso común             |
|----------|----------------|----------------|---------------|-----------------------|
| BT.601   | 0.299          | 0.587          | 0.114         | Televisión estándar   |
| BT.709   | 0.2126         | 0.7152         | 0.0722        | Alta definición       |
| BT.2020  | 0.2627         | 0.6780         | 0.0593        | Ultra alta definición |


<div style="display: flex; flex-direction: row; gap: 10px;">
<p><img src="../img_601.png" alt="Imagen de ejemplo"></p>
<p><img src="../img_709.png" alt="Imagen plano verde"></p>
<p><img src="../img_2020.png" alt="Imagen promedio de canales"></p>
</div>