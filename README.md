## Tarea 12
## Distribucion Normal
**Ejercicio 1: Generación de la Distribución Normal en Python**
````
import numpy as np
import matplotlib.pyplot as plt

media = 60
desviacion_estandar = 15
muestra = np.random.normal(media, desviacion_estandar, 1000)

plt.hist(muestra, bins=30, color="purple", edgecolor="black")
plt.title("Distribución Normal")
plt.xlabel("Valores")
plt.ylabel("Frecuencia")
plt.show()

media_muestra = np.mean(muestra)
desviacion_estandar_muestra = np.std(muestra)

media_muestra, desviacion_estandar_muestra
````
**Ejercicio 2: Probabilidad en un Rango Específico en R**
````
media <- 40
desviacion_estandar <- 5

probabilidad <- pnorm(45, mean = media, sd = desviacion_estandar) - pnorm(35, mean = media, sd = desviacion_estandar)
probabilidad

curve(dnorm(x, mean=media, sd=desviacion_estandar), from=20, to=60, col="purple", lwd=2, main="Distribución Normal y Rango de Probabilidad", xlab="Valores", ylab="Densidad")
abline(v=35, col="red", lty=2)
abline(v=45, col="red", lty=2)

````
**Ejercicio 3: Simulación de una Muestra en Python**
````
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

media = 75
desviacion_estandar = 8
muestra = np.random.normal(media, desviacion_estandar, 500)

confianza = 0.95
limite_inferior, limite_superior = stats.norm.interval(confianza, loc=np.mean(muestra), scale=np.std(muestra, ddof=1))

plt.hist(muestra, bins=30, color="purple", edgecolor="black", alpha=0.7)
plt.axvline(limite_inferior, color="red", linestyle="--", label="Límite Inferior")
plt.axvline(limite_superior, color="blue", linestyle="--", label="Límite Superior")
plt.title("Intervalo de Confianza al 95%")
plt.xlabel("Valores")
plt.ylabel("Frecuencia")
plt.legend()
plt.show()

limite_inferior, limite_superior
````
**Ejercicio 4: Comparación de dos Distribuciones en R**
````
set.seed(123)
muestra_A <- rnorm(1000, mean = 55, sd = 10)
muestra_B <- rnorm(1000, mean = 65, sd = 15)

hist(muestra_A, col=rgb(0.2,0.6,0.5,0.7), xlim=c(20,100), main="Comparación de Distribuciones", xlab="Valores", ylab="Frecuencia")
hist(muestra_B, col=rgb(0.7,0.2,0.4,0.6), add=TRUE)
legend("topright", legend=c("Muestra A", "Muestra B"), fill=c(rgb(0.2,0.6,0.5,0.7), rgb(0.7,0.2,0.4,0.6)))

media_A <- mean(muestra_A)
sd_A <- sd(muestra_A)
media_B <- mean(muestra_B)
sd_B <- sd(muestra_B)

media_A
sd_A
media_B
sd_B

````
**Ejercicio 5: Cálculo de Percentiles en Python**
````
import numpy as np
import matplotlib.pyplot as plt

media = 100
desviacion_estandar = 20
muestra = np.random.normal(media, desviacion_estandar, 100)

percentil_90 = np.percentile(muestra, 90)

plt.hist(muestra, bins=30, color="purple", edgecolor="black", alpha=0.7)
plt.axvline(percentil_90, color="orange", linestyle="--", label=f"Percentil 90: {percentil_90:.2f}")
plt.title("Distribución Percentil 90")
plt.xlabel("Valores")
plt.ylabel("Frecuencia")
plt.legend()
plt.show()

percentil_90
````
**Ejercicio 6: Probabilidad de Exceder un Valor en R**
````
media <- 50
desviacion_estandar <- 12

probabilidad_exceder_70 <- 1 - pnorm(70, mean = media, sd = desviacion_estandar)
probabilidad_exceder_70

curve(dnorm(x, mean=media, sd=desviacion_estandar), from=20, to=80, col="purple", lwd=2, main="Distribución Normal y Probabilidad", xlab="Valores", ylab="Densidad")
abline(v=70, col="red", lty=2)

````
**Ejercicio 7: Simulación de Distribución Normal Estándar en Python**
````
import numpy as np
import matplotlib.pyplot as plt

muestra = np.random.normal(0, 1, 1000)

porcentaje = np.mean((muestra > -1) & (muestra < 1)) * 100

plt.hist(muestra, bins=30, color="purple", edgecolor="black", alpha=0.7)
plt.axvline(-1, color="red", linestyle="--", label="-1")
plt.axvline(1, color="blue", linestyle="--", label="1")
plt.title("Distribución Normal Estándar de la Muestra")
plt.xlabel("Valores")
plt.ylabel("Frecuencia")
plt.legend()
plt.show()

porcentaje
````
**Ejercicio 8: Prueba de Normalidad en R**
````
set.seed(123)
muestra <- rnorm(200, mean = 30, sd = 5)

resultado <- shapiro.test(muestra)
resultado

hist(muestra, col="purple", main="Prueba de Normalidad", xlab="Valores", ylab="Frecuencia")

````
**Ejercicio 9: Transformación de una Muestra a una Distribución Normal Estándar en Python**
````
import numpy as np
import matplotlib.pyplot as plt

media = 60
desviacion_estandar = 10
muestra = np.random.normal(media, desviacion_estandar, 150)

muestra_estandarizada = (muestra - np.mean(muestra)) / np.std(muestra)

plt.hist(muestra_estandarizada, bins=30, color="purple", edgecolor="black", alpha=0.7)
plt.title("Distribución Normal Estándar")
plt.xlabel("Valores Estandarizados")
plt.ylabel("Frecuencia")
plt.show()

media_transformada = np.mean(muestra_estandarizada)
desviacion_estandar_transformada = np.std(muestra_estandarizada)

media_transformada, desviacion_estandar_transformada
````
**Ejercicio 10: Análisis de la Suma de Dos Variables Normales en R**
````
set.seed(123)
muestra_X <- rnorm(100, mean = 10, sd = 3)
muestra_Y <- rnorm(100, mean = 15, sd = 4)

muestra_Z <- muestra_X + muestra_Y

media_Z <- mean(muestra_Z)
desviacion_estandar_Z <- sd(muestra_Z)

media_teorica <- 10 + 15
desviacion_estandar_teorica <- sqrt(3^2 + 4^2)

cat("Media observada de Z:", media_Z, "\n")
cat("Desviación estándar observada de Z:", desviacion_estandar_Z, "\n")
cat("Media teórica de Z:", media_teorica, "\n")
cat("Desviación estándar teórica de Z:", desviacion_estandar_teorica, "\n")

hist(muestra_Z, breaks=20, col="pink", border="black",
     main="Distribución de la Suma de Valores",
     xlab="Valores de Z", ylab="Frecuencia")

abline(v=media_Z, col="purple", lwd=2, lty=2)  # Media observada
abline(v=media_teorica, col="red", lwd=2, lty=3)  # Media teórica

legend("topright", legend=c("Media Observada", "Media Teórica"),
       col=c("purple", "red"), lty=c(2, 3), lwd=2)

````
