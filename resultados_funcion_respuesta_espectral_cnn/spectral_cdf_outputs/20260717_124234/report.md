# Barrido espectral acumulativo + CDF (MNIST / Fashion-MNIST / KMNIST / CIFAR-10 gris)

## Setup
- Seeds: `[42, 43, 44]`
- Puntos por curva: `150`

## Estadísticos de la distribución implícita (radio espectral normalizado, media ± desv. típica entre semillas)

| Dataset | Accuracy base | E[r] (media) | Desv. típica | Mediana | Moda |
|---|---|---|---|---|---|
| MNIST | 99.36% ± 0.08pp | 0.1164 ± 0.0021 | 0.0649 ± 0.0041 | 0.1223 ± 0.0038 | 0.3510 ± 0.0086 |
| Fashion-MNIST | 92.35% ± 0.16pp | 0.1432 ± 0.0022 | 0.1202 ± 0.0040 | 0.1080 ± 0.0010 | 0.4061 ± 0.0510 |
| KMNIST | 96.73% ± 0.14pp | 0.1291 ± 0.0015 | 0.0720 ± 0.0030 | 0.1331 ± 0.0053 | 0.3602 ± 0.0188 |
| CIFAR-10 (gris) | 71.01% ± 0.85pp | 0.2192 ± 0.0056 | 0.1493 ± 0.0094 | 0.2281 ± 0.0044 | 0.4747 ± 0.0233 |

`E[r]`, `Desv. típica`, `Mediana` y `Moda` son estadísticos de la variable "radio espectral normalizado necesario para clasificar bien" (r ∈ [0,1]), calculados a partir de la CDF empírica (precisión normalizada vs. radio normalizado) tras ajustarla a monótona mediante regresión isotónica.
