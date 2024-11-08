# Tarea 11
## Distribucion Normal
**Probabilidad en un Rango Específico en R**
````
media <- 40
desviacion_estandar <- 5

probabilidad <- pnorm(45, mean = media, sd = desviacion_estandar) - pnorm(35, mean = media, sd = desviacion_estandar)
probabilidad

curve(dnorm(x, mean=media, sd=desviacion_estandar), from=20, to=60, col="purple", lwd=2, main="Distribución Normal y Rango de Probabilidad", xlab="Valores", ylab="Densidad")
abline(v=35, col="red", lty=2)
abline(v=45, col="red", lty=2)

````
