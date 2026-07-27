# Efecto de la función de activación sobre la SRF de la CNN, vs. ResNet-18 — MNIST

## Setup
- Dataset: `MNIST`
- Activaciones comparadas en la CNN: `['relu', 'gelu', 'tanh', 'sigmoid']` (capas ocultas; la capa de salida es siempre softmax)
- ResNet-18 de referencia incluida: `True` (backbone congelado, activación fija; no varía por diseño)
- Semillas: `[42, 43, 44]`
- Puntos por curva: `150`

## Estadísticos de la SRF por variante (media ± desviación típica entre semillas)

| Variante | Accuracy base | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|
| ReLU | 99.32% ± 0.07pp | 0.1118 ± 0.0051 | 0.0652 ± 0.0009 | 0.1162 ± 0.0053 | 0.1232 ± 0.0229 | 0.8882 ± 0.0051 | -1.9821 ± 0.1560 | 0.6713 ± 0.1691 |
| GELU | 99.33% ± 0.05pp | 0.1223 ± 0.0023 | 0.0657 ± 0.0026 | 0.1258 ± 0.0044 | 0.1232 ± 0.0229 | 0.8777 ± 0.0023 | -1.8543 ± 0.0382 | 0.5491 ± 0.0517 |
| tanh | 99.12% ± 0.03pp | 0.1231 ± 0.0021 | 0.0654 ± 0.0021 | 0.1287 ± 0.0053 | 0.1556 ± 0.0000 | 0.8769 ± 0.0021 | -1.7855 ± 0.0506 | 0.4762 ± 0.0273 |
| sigmoide | 98.56% ± 0.19pp | 0.1082 ± 0.0093 | 0.0599 ± 0.0007 | 0.1141 ± 0.0090 | 0.1070 ± 0.0000 | 0.8918 ± 0.0093 | -2.0776 ± 0.0590 | 0.6820 ± 0.0497 |
| ResNet-18 (referencia, backbone congelado) | 97.76% ± 0.05pp | 0.4520 ± 0.0083 | 0.2437 ± 0.0034 | 0.5441 ± 0.0088 | 0.6576 ± 0.0000 | 0.5480 ± 0.0083 | -1.4499 ± 0.0191 | 1.4571 ± 0.0161 |

Si la precisión base es similar entre las cuatro activaciones de la CNN pero E[R]/ΔH difieren claramente, la forma de la SRF no está determinada solo por el rendimiento final, sino también por la función de activación empleada en las capas ocultas. La fila de ResNet-18 es una referencia fija (backbone congelado, sin variar activación): sirve para ver si alguna variante de la CNN se acerca más a su comportamiento espectral, no para atribuir el efecto a su activación (que no se modifica).
