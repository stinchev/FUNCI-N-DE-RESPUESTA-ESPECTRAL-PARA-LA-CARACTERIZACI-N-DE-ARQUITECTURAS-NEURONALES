# Estabilidad de la SRF frente a la semilla — MNIST

## Setup
- Dataset: `MNIST`
- Arquitecturas: `['cnn', 'resnet18']`
- Semillas: `[42, 43, 44, 45, 46, 47, 48, 49, 50, 51]` (10 entrenamientos independientes por arquitectura)
- Puntos por curva: `150`

## Comparación entre arquitecturas (media ± desviación típica entre semillas)

| Arquitectura | Accuracy base | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|
| CNN (desde cero) | 99.33% ± 0.08pp | 0.1127 ± 0.0047 | 0.0617 ± 0.0032 | 0.1156 ± 0.0051 | 0.1313 ± 0.0243 | 0.8873 ± 0.0047 | -1.9029 ± 0.1127 | 0.5350 ± 0.1399 |
| ResNet-18 (preentrenada, congelada) | 97.76% ± 0.09pp | 0.4494 ± 0.0075 | 0.2417 ± 0.0025 | 0.5409 ± 0.0157 | 0.6576 ± 0.0000 | 0.5506 ± 0.0075 | -1.4509 ± 0.0270 | 1.4496 ± 0.0275 |

## Detalle por semilla — CNN (desde cero)

| Estadístico | Media | Desv. típica | Coef. de variación (|σ/media|) |
|---|---|---|---|
| E[R] | 0.1127 | 0.0047 | 0.041 |
| σ[R] | 0.0617 | 0.0032 | 0.051 |
| Mediana | 0.1156 | 0.0051 | 0.044 |
| Moda | 0.1313 | 0.0243 | 0.185 |
| AUC | 0.8873 | 0.0047 | 0.005 |
| H | -1.9029 | 0.1127 | 0.059 |
| ΔH (negentropía) | 0.5350 | 0.1399 | 0.262 |

| Semilla | Accuracy base | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|
| 42 | 99.39% | 0.1068 | 0.0657 | 0.1111 | 0.1070 | 0.8932 | -2.0009 | 0.6965 |
| 43 | 99.33% | 0.1098 | 0.0640 | 0.1139 | 0.1556 | 0.8902 | -1.7824 | 0.4528 |
| 44 | 99.23% | 0.1187 | 0.0660 | 0.1236 | 0.1070 | 0.8813 | -2.1631 | 0.8646 |
| 45 | 99.24% | 0.1063 | 0.0605 | 0.1097 | 0.1070 | 0.8937 | -1.7805 | 0.3935 |
| 46 | 99.21% | 0.1135 | 0.0570 | 0.1127 | 0.1070 | 0.8865 | -1.9666 | 0.5211 |
| 47 | 99.41% | 0.1078 | 0.0586 | 0.1096 | 0.1070 | 0.8922 | -1.8843 | 0.4658 |
| 48 | 99.34% | 0.1172 | 0.0610 | 0.1217 | 0.1556 | 0.8828 | -1.7822 | 0.4045 |
| 49 | 99.36% | 0.1161 | 0.0597 | 0.1139 | 0.1556 | 0.8839 | -1.8711 | 0.4723 |
| 50 | 99.44% | 0.1191 | 0.0589 | 0.1232 | 0.1556 | 0.8809 | -1.8882 | 0.4750 |
| 51 | 99.37% | 0.1123 | 0.0656 | 0.1166 | 0.1556 | 0.8877 | -1.9092 | 0.6041 |

## Detalle por semilla — ResNet-18 (preentrenada, congelada)

| Estadístico | Media | Desv. típica | Coef. de variación (|σ/media|) |
|---|---|---|---|
| E[R] | 0.4494 | 0.0075 | 0.017 |
| σ[R] | 0.2417 | 0.0025 | 0.010 |
| Mediana | 0.5409 | 0.0157 | 0.029 |
| Moda | 0.6576 | 0.0000 | 0.000 |
| AUC | 0.5506 | 0.0075 | 0.014 |
| H | -1.4509 | 0.0270 | 0.019 |
| ΔH (negentropía) | 1.4496 | 0.0275 | 0.019 |

| Semilla | Accuracy base | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|
| 42 | 97.81% | 0.4637 | 0.2422 | 0.5549 | 0.6576 | 0.5363 | -1.4337 | 1.4345 |
| 43 | 97.77% | 0.4474 | 0.2484 | 0.5440 | 0.6576 | 0.5526 | -1.4393 | 1.4657 |
| 44 | 97.70% | 0.4450 | 0.2406 | 0.5334 | 0.6576 | 0.5550 | -1.4766 | 1.4710 |
| 45 | 97.81% | 0.4545 | 0.2419 | 0.5556 | 0.6576 | 0.5455 | -1.4600 | 1.4596 |
| 46 | 97.79% | 0.4362 | 0.2409 | 0.5051 | 0.6576 | 0.5638 | -1.4308 | 1.4262 |
| 47 | 97.79% | 0.4582 | 0.2403 | 0.5559 | 0.6576 | 0.5418 | -1.4007 | 1.3939 |
| 48 | 97.85% | 0.4431 | 0.2406 | 0.5297 | 0.6576 | 0.5569 | -1.4698 | 1.4641 |
| 49 | 97.88% | 0.4483 | 0.2428 | 0.5560 | 0.6576 | 0.5517 | -1.4767 | 1.4801 |
| 50 | 97.65% | 0.4458 | 0.2391 | 0.5309 | 0.6576 | 0.5542 | -1.4920 | 1.4799 |
| 51 | 97.55% | 0.4516 | 0.2400 | 0.5440 | 0.6576 | 0.5484 | -1.4292 | 1.4212 |

Un coeficiente de variación bajo (desviación típica pequeña frente a la media) en todos los estadísticos indica que la SRF es una característica reproducible de la arquitectura entrenada bajo esta configuración fija, y no un artefacto de una inicialización concreta. Comparando las dos arquitecturas se puede además comprobar si esa reproducibilidad es distinta entre una red entrenada desde cero y una red preentrenada con el backbone congelado.
