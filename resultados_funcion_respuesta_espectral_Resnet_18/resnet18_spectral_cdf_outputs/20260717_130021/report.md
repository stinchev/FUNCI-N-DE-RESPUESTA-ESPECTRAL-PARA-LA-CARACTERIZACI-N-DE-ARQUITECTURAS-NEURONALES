# Barrido espectral acumulativo + CDF — ResNet-18 preentrenada (backbone congelado, cabeza lineal)

## Setup
- Seeds: `[42, 43, 44]`
- Puntos por curva: `150`
- Tamaño del subconjunto de test usado en el barrido: `2000`

## Estadísticos de la distribución implícita (radio espectral normalizado, media ± desv. típica entre semillas)

| Dataset | Accuracy base (test completo) | E[r] (media) | Desv. típica | Mediana | Moda |
|---|---|---|---|---|---|
| MNIST | 97.76% ± 0.05pp | 0.4520 ± 0.0083 | 0.2437 ± 0.0034 | 0.5441 ± 0.0088 | 0.1967 ± 0.0206 |
| Fashion-MNIST | 89.18% ± 0.12pp | 0.3157 ± 0.0011 | 0.2538 ± 0.0015 | 0.2988 ± 0.0053 | 0.2259 ± 0.0000 |
| KMNIST | 83.87% ± 0.55pp | 0.3978 ± 0.0030 | 0.2312 ± 0.0046 | 0.3906 ± 0.0109 | 0.3638 ± 0.0793 |
| CIFAR-10 (gris) | 79.25% ± 0.18pp | 0.3828 ± 0.0021 | 0.2003 ± 0.0034 | 0.4121 ± 0.0028 | 0.3477 ± 0.1792 |

`E[r]`, `Desv. típica`, `Mediana` y `Moda` son estadísticos de la variable "radio espectral normalizado necesario para clasificar bien" (r ∈ [0,1]), calculados a partir de la CDF empírica (precisión normalizada vs. radio normalizado) tras ajustarla a monótona mediante regresión isotónica. Backbone ResNet-18 preentrenado en ImageNet y congelado; solo se entrena la cabeza lineal.
