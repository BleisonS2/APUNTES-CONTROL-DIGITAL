# APUNTES-CONTROL-DIGITAL
## SEÑALES DIGITALES VS SEALES ANALOGAS
![images](https://github.com/user-attachments/assets/a53a33e2-0e26-4453-ba04-fa3709296e32)
Figura 1. Figura Comparativa de Señales
## ¿PORQUE CONTROL DIGITAL?
- Exactitud
- Errores de implementacion
- Flexibilidad
- Velocidad
- Costos
## ESTRUCTURA DEL CONTROLADOR ANALOGICO
![CONTROLADOR ANALOGICO](https://github.com/user-attachments/assets/cb18a982-eef9-4305-9508-b1d58dcdfcfc)
Figura 2. Figura Estructura Controlador Analogico
## ESTRUCTURA DEL CONTROLADOR DIGITAL
![CONTROLADOR DIGITAL](https://github.com/user-attachments/assets/9f89efa4-0a1c-4e6e-b771-5cbfaea9cd9e)
Figura 3. Figura Estructura Controlador Digital
## PROCEDIMIENTO DE CONVERSION
1. Muestreo:
- Medir valores de voltaje cada cierto tiempo
- Se mide como el numero de veces que se mide en 1 segundo por lo tanto la unidad es Hz
![MUESTREO](https://github.com/user-attachments/assets/95b46aad-ccb4-4e57-bcb7-cb5ea900af25)
Figura 4. Figura Ejemplo Muestreo
![muestreo2](https://github.com/user-attachments/assets/7ca14ac6-39c9-4a8b-ba93-5ffd58f31843)
Figura 5. Figura 2do Ejemplo Muestreo
- Entre mas alta la taza de muestreo mas informacion se esta procesando
2. Cuantizacion
  La señal analoga se convierte en una serie de valores que correspondesn a cada una de las medidas tomadas en el muestreo
![cuantizacion](https://github.com/user-attachments/assets/13cadef7-819e-490b-b624-7c938c6d7f8e)
Figura 5. Figura 2do Ejemplo Cuantizacion
3. Codificacion
  se asisgnan valores de tipo binario a cada uno de los valores de cuantizacion

  lo valores a usar los define el diseñador de acuerdo con el ipo de informacion obtenida en la cantizacion
- Cantidad de bits, a mayores bits mayor el costo

- Ta -> Tiempo de adquisicion
- Tp -> Tiempo de apertura
- Ts -> Tiempo e establesimiento
### Ejemplo
Señal analogica: [0.3]V
Bits de representacion: 2 bits
2^2 = 4 posibles simbolos
Rango analogico: 3-0=3V
Representacion: 3/4=0.75V

|     **V**     | **Binario** |
|---------------|-------------|
|       0       |     00      |
|---------------|-------------|
|     0.75      |     01      |
|---------------|-------------|
|      1,5      |     10      |
|---------------|-------------|
|     2.25      |     11      |
|---------------|-------------|
