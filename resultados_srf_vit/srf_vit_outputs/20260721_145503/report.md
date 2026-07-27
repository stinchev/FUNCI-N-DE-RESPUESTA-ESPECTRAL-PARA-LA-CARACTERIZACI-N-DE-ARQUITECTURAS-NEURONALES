# Anexo exploratorio: SRF de un ViT-B/16 preentrenado y congelado (linear probe)

**Aviso:** este experimento no forma parte del análisis comparativo riguroso de los Capítulos 2 y 3. Es un estudio exploratorio, a mano alzada, motivado por la curiosidad de comprobar si una arquitectura basada en atención se comporta de forma distinta a la CNN y a la ResNet-18. No pretende ser un análisis exhaustivo de los muchos grados de libertad de diseño de un ViT (tamaño de parche, profundidad, número de cabezas, etc.); se deja como avance de trabajo futuro.

## Setup
- Semillas: `[42, 43]`
- Puntos por curva: `60`
- Subconjunto de test para el barrido: `1000`

| Dataset | Accuracy base | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|
| MNIST | 97.92% ± 0.04pp | 0.3781 ± 0.0008 | 0.2148 ± 0.0036 | 0.4211 ± 0.0107 | 0.4554 ± 0.0224 | 0.6219 ± 0.0008 | -0.8874 ± 0.0546 | 0.7680 ± 0.0377 |
| Fashion-MNIST | 90.78% ± 0.09pp | 0.3018 ± 0.0003 | 0.1826 ± 0.0030 | 0.3079 ± 0.0022 | 0.3669 ± 0.0661 | 0.6982 ± 0.0003 | -0.8760 ± 0.0288 | 0.5944 ± 0.0454 |
| KMNIST | 87.80% ± 0.15pp | 0.3563 ± 0.0141 | 0.2051 ± 0.0075 | 0.3190 ± 0.0043 | 0.3942 ± 0.0388 | 0.6437 ± 0.0141 | -0.7193 ± 0.0385 | 0.5533 ± 0.0749 |
| CIFAR-10 (gris) | 88.46% ± 0.13pp | 0.3391 ± 0.0044 | 0.1829 ± 0.0006 | 0.3496 ± 0.0008 | 0.2232 ± 0.0000 | 0.6609 ± 0.0044 | -0.8644 ± 0.0513 | 0.5847 ± 0.0478 |
