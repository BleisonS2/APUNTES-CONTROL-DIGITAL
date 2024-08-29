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

![siscontr](https://github.com/user-attachments/assets/d014033f-3c47-44e4-abfd-c0c2037bfbca)

Figura 2. Figura Estructura Controlador Analogico

## ESTRUCTURA DEL CONTROLADOR DIGITAL

![img6](https://github.com/user-attachments/assets/1af20061-d710-475c-bc8e-df8d045ceef5)

Figura 3. Figura Estructura Controlador Digital

## PROCEDIMIENTO DE CONVERSION
### 1. Muestreo:
- Medir valores de voltaje cada cierto tiempo
- Se mide como el numero de veces que se mide en 1 segundo por lo tanto la unidad es Hz

![senoidal muestreada](https://github.com/user-attachments/assets/4235a67b-3905-4eb4-83f4-bdf1596b61d6)

Figura 4. Figura 2do Ejemplo Muestreo

- Entre mas alta la taza de muestreo mas informacion se esta procesando

### 2. Cuantizacion
  La señal analoga se convierte en una serie de valores que correspondesn a cada una de las medidas tomadas en el muestreo

![5figura7](https://github.com/user-attachments/assets/ad3ca95e-40c8-41d8-b7d3-c499dcedadfe)

Figura 5. Figura 2do Ejemplo Cuantizacion

### 3. Codificacion
-se asisgnan valores de tipo binario a cada uno de los valores de cuantizacion

- lo valores a usar los define el diseñador de acuerdo con el tipo de informacion obtenida en la cantizacion

- Cantidad de bits, a mayores bits mayor el costo

- Ta -> Tiempo de adquisicion
- Tp -> Tiempo de apertura
- Ts -> Tiempo e establesimiento
  
**Ejemplo**

- Señal analogica: [0.3]V
- Bits de representacion: 2 bits
- $2^2 = 4$ posibles simbolos
- Rango analogico: 3-0=3V
- Representacion: $\frac{3}{4}=0.75V$

|     **V**     | **Binario** |
|---------------|-------------|
|       0       |     00      |
|     0.75      |     01      |
|      1,5      |     10      |
|     2.25      |     11      |

## CONVERSOR DIGITAL ANALOGO

Es un dispositivo que genera una correspondencia uno a uno entre valores digitales y valores analogicos

## RESOLUCION DAC

- Depende de bits de representacion
- se entiende en voltaje o en fondo de escala (FS)

## METODOS

- Resistores ponderados -> No es tan exacto
- Red en escalera R-2R -> Es mas complicado pero mas exacto
- $$𝑉𝑜 =-\frac{𝑅𝑓}{𝑅}$$
- $$𝑉𝑜 =− \frac{(𝑅𝑓*𝑉𝑟𝑒𝑓)}{𝑅}$$


## MODELO MATEMATICO

- Operaciones inversas -> Utilizan los mismos componentes 
- Muestreador -> Se modela idealmente con una señal de reloj y un interruptor
- Retenedor -> Se modela atraves de una funcion de transferencia

## MODELO MATEMATICO CONVERSORES A/D y D/A (CONCIDERACIONES)

- Asumiendo que el conversor digital-análogo DAC tienelas siguientes características:
- Las entradas y las salidas del conversor son iguales enmagnitud
- La conversión se produce de manera instantánea
- Las salidas son constantes sobre el periodo demuestreo

## Zero order Hold (ZOH)

![contro10](https://github.com/user-attachments/assets/f485448d-73f6-4736-adf5-ed1425ed0100)

Figura 6. Figura Ejemplo ZOH

![3 1+Zero-order-hold+(ZOH)](https://github.com/user-attachments/assets/2ef22e17-bd7f-4c84-a0c3-be61341a0163)

Figura 7. Figura Funcion de tranferencia de ZOH

## DAC de orden superior

- First order hold es un DAC que considera un modelo lineal durante el intervalo de muestreo
- Second order hold es un DAC que considera un modelo parabólico durante el intervalo de tiempo de muestreo

## MUESTREO EN TERMINOS MATEMATICOS

![mat muestreo](https://github.com/user-attachments/assets/1cb83f90-8e92-48f9-95d9-dd74c86561fd)

Figura 8. Figura Funcion de tranferencia de ZOH
### Metodos iterativos
**Ejemplo**

- $Y(k)=1/3(-2y(k-1)+y(k-2)+2u(k-1)-3u(k-2)$

- Condiciones iniciales-> $y(-2)=1, y(-1)=-2;u(k){1;k=0,1,2...  0; k<0}$
- $$k=0$$
- $$Y(0)=(\frac{1}{3})*(-2(-2)+1+2(0)-3(0)) = \frac{5}{3}$$

### Transformada Z
> Es la contraparte de la Tranformada de Laplace, el espacio z tiene caracteristicas diferentes al espacio de Laplace

La transformada de Laplace de una función $\( f(t) \)$ se denota como $\( \mathcal{L}\{f(t)\} \)$ y se define por la siguiente integral:

- $$\[\mathcal{L}\{f(t)\}  = \int_{0}^{\infty} e^{-st} f(t) \, dt\]$$
- $$\[\mathcal{L}\{y(s)\}  = \sum_{k=0}^{\infty} Y(kT) \cdot e^{-kTs}\]$$

> La transformada Z de una secuencia $\( x[n] \)$ se denota como $\( \mathcal{Z}\{x[n]\} \)$ y se define por la siguiente suma:

- $$\[\mathcal{Z}\{f(k)\} = \sum_{k=0}^{\infty} f(k) \cdot z^{-k}\]$$
- $$\[\mathcal{Z}\{F(k)\} = \sum_{k=0}^{\infty} F[k] \cdot z^{-k}\]$$
- $$ Z=e^{Ts}

### Solucion de ecuacion de diferencias
 - F(k+n) en adelanto
 - F(k-n) en atraso

### Metodo de la invarianza al inpulso
> se usa respuesta al impulso de c(s) para obtener C(z)
*a transdormada de Laplace del impulso*
$$(e(t)=\(\sigma\)t) =  (e(s)=1)$$
  
