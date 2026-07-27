# Anexo exploratorio: SRF de un autoencoder (clasificación en espacio latente)

**Aviso:** este experimento no forma parte del análisis comparativo riguroso de los Capítulos 2 y 3. Es un estudio exploratorio, a mano alzada, para comprobar si la SRF de una arquitectura de naturaleza distinta (con un objetivo de reconstrucción y una dimensión de espacio latente que no existen en la CNN ni en la ResNet-18) se comporta de forma distinta. Se deja como avance de trabajo futuro, no como una conclusión firme.

## Setup
- Semillas: `[42, 43]`
- Dimensión del espacio latente: `32`
- Puntos por curva: `100`

| Dataset | Accuracy base | MSE reconstrucción | E[R] | σ[R] | Mediana | Moda | AUC | H | ΔH |
|---|---|---|---|---|---|---|---|---|---|
| MNIST | 94.27% ± 0.00pp | 0.00280 ± 0.00002 | 0.1077 ± 0.0015 | 0.0673 ± 0.0016 | 0.1015 ± 0.0012 | 0.0922 ± 0.0000 | 0.8923 ± 0.0015 | -1.7920 ± 0.0296 | 0.5121 ± 0.0053 |
| Fashion-MNIST | 83.33% ± 0.06pp | 0.00627 ± 0.00001 | 0.1100 ± 0.0004 | 0.1014 ± 0.0029 | 0.0893 ± 0.0024 | 0.1717 ± 0.0204 | 0.8900 ± 0.0004 | -1.3025 ± 0.0056 | 0.4321 ± 0.0229 |
| KMNIST | 71.52% ± 0.08pp | 0.01834 ± 0.00007 | 0.0951 ± 0.0010 | 0.0851 ± 0.0040 | 0.0825 ± 0.0017 | 0.1513 ± 0.0000 | 0.9049 ± 0.0010 | -1.3118 ± 0.0257 | 0.2662 ± 0.0209 |
| CIFAR-10 (gris) | 29.82% ± 0.16pp | 0.00920 ± 0.00001 | 0.0423 ± 0.0003 | 0.0600 ± 0.0009 | 0.0083 ± 0.0008 | 0.0442 ± 0.0000 | 0.9577 ± 0.0003 | -1.7388 ± 0.0088 | 0.3446 ± 0.0069 |
