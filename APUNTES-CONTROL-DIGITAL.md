- **Danilo Stiben Rodriguez Malagon Cod 119238**
- **Bleison Bley Ruiz Gutierrez Cod 112589**
- **Sergio Fabian Guzman Pulido Cod 119753**

# APUNTES CONTROL DIGITAL
## SEÑALES DIGITALES VS SEÑALES ANALOGAS

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

si C(s) es estrictamente propia y se asume a un tiempo de muestreo T lo suficientemente pequeño

$$C(z)=z(L^{-1}(c(s))t=kt)$$

- Teniendo en cuenta el tiempo de muestreo 

$$C(z)=Tz(l^{-1}(C(s))t=kt)$$

- Dando valores

$$C(s)=\frac{((5cs)+2)}{((5+1)(5+10))}$$

- fracciones parciales

$$C(s)=(\frac{5/9}{5+1})+(\frac{40/9}{5+10})$$

- inversa de Laplace obtenemos la funcion en tiempo continuo

$$\mathcal{L^{-1}}\{C(s)\}  = (\frac{5}{9} e^{-t}) + (\frac{40}{9} e^{-10t})$$

- Reemplazamos t->KT

$$\mathcal{L^{-1}}\{C(s)\} t =KT= (\frac{5}{9} e^{-KT}) + (\frac{40}{9} e^{-10KT})$$

- Por lo tanto

$$C(z)=Tz((\frac{5}{9} e^{-KT})+(\frac{40}{9} e^{-10KT}))$$

- De las tablas se obtiene

$$C(z)=T((\frac{5}{9})(\frac{z}{z-e^{-t}})+((\frac{40}{9})(\frac{z}{z-e^{-10T}}))$$

- Obtenemos

$$C(z)=0.5(\frac{405z^2-216.27z}{81z^2-49.08z+0.29})$$

- luego

$$(U(z))(81z^{2}-49.08z+0.29) = (E(z))(200.25z^{2}-108.13z)$$

- Tranzformada inversa Z

$$(81U)(k+2)-(49.08U)(k+1)+(0.29U)(k)= (200,25E)(k+2)-108.13E(k+1)$$

- Movemos las muestras para dejar la ecuacion en atrasos ya que se encuentra en forma de adelantos (k+n))

$$(81U)(k)-(49.08U)(k-1)+(0.29U)(k-2)= (200,25E)(k)-108.13E(k-1)$$

## TRANSFORMADA Z DE UNA FUNSION PASO

$$Z[E(t)]= \frac{z}{z-1}$$

- se pueden igualar las transfomadas inversas

$$Z^{-1} [C(z)\frac{z}{z-1}]= L^{-1}[C(s)\frac{1}{s}]$$

- se despeja la transformada z

$$C(z)=\frac{z-1}{z}z[L^{-1}[C(s)\frac{1}{s}]]$$

- se divide por s

$$\frac{C(s)}{s}=\frac{2(5-2)}{5(5+1)(5+3)}$$

- fracciones parciales

$$\frac{C(s)}{s}=\frac{-\frac{4}{3}}{5}-\frac{3}{5+1}-\frac{\frac{5}{3}}{5+3})$$

- Obtenemos

$$C(z)=\frac{z-1}{z}(\frac{-\frac{3}{4}z}{z-1}-\frac{3z}{z-e^{-t}}-\frac{5z}{3(z-e^{-3t}})$$

## METODO EULER ADELANTE

$$\frac{d}{dKT}(KT)=\frac{x(k+1)-x(k)}{T}$$

- Luego de Aplicar transfomada z obtenemos

$$S=\frac{z-1}{T}$$

## METODO EULER ATRAS

$$\frac{d}{dKT}(KT)=X\frac{x(k)-x(k-1)}{T}$$

- Luego de Aplicar transfomada z obtenemos

$$S=\frac{z-1}{TZ}$$

## METODO TRAPEZOIAL

- La equivalencia es

$$S=(\frac{2}{T})(\frac{z-1}{z+1}$$

- o tambien

$$Z=\frac{1+\frac{Ts}{2}}{1-\frac{Ts}{2}}$$

## ESTABILIDAD ABSOLUTA

Un sistema es considerado estable cuando, ante una entrada limitada, produce una salida limitada.

![Sitema estable](https://github.com/user-attachments/assets/5e17785f-4079-4c4d-b5bd-790d401fa962)

Figura 9. Ejemplo sistema Estable

## CLASIFICACION DE LA ESTABILIDAD

1. *Estabilidad Absoluta*: Todos los polos del sistema están ubicados en el semiplano izquierdo (parte real negativa) del plano complejo \(s\).
2. *Marginalmente Estable*: Algunos polos están en el eje imaginario, pero no en el semiplano derecho.
3. *Inestable*: Cualquier polo en el semiplano derecho (parte real positiva) del plano complejo \(s\).


![estabilidad_ejemplos](https://github.com/user-attachments/assets/e3746461-ff1e-4a9a-8a9d-6d4feae569b9)

Figura 10. Ejemplos de estabilidad de sistemas. 

Los polos del sistema en el espacio de Laplace tienen una equivalencia en la Transformada Z, lo que permite analizar la estabilidad en sistemas discretos. Esta equivalencia se expresa como:

 $$ Z = e^{Ts} $$

Donde:

- \( T \) es el período de muestreo.
- \( s = \sigma + j\omega \) es el polo en el plano \(s\), con \(\sigma\) representando la parte real y \(j\omega\) la parte imaginaria.

**Ejemplos:**

*a)* 

$$ s = σ + j w > Z=e^{Ts} $$

- decimos que

$$ σ > 0 $$ 

- es inestable
- 
## Métodos de Euler

Los métodos de Euler son técnicas numéricas básicas utilizadas para resolver ecuaciones diferenciales ordinarias (EDOs). Son métodos de integración explícitos (Euler hacia adelante) e implícitos (Euler hacia atrás) que aproximan soluciones de EDOs en intervalos discretos.

## 1. Método de Euler Hacia Adelante

> *Definición:* El método de Euler hacia adelante es un método explícito que utiliza la pendiente en el punto actual para estimar el valor de la función en el siguiente paso.

### 1.1 Fórmula

$$y_{n+1} = y_n + h \cdot f(t_n, y_n)$$

donde:
- \( y_{n+1} \) es el valor aproximado en el siguiente paso.
- \( y_n \) es el valor actual de la función.
- \( h \) es el tamaño del paso.
- \( f(t_n, y_n) \) es la derivada de \( y \) en el tiempo \( t_n \).

### 1.2 Características

- *Simplicidad:* Fácil de implementar y computacionalmente eficiente.
- *Estabilidad:* Es condicionalmente estable, lo que significa que requiere un tamaño de paso pequeño para mantener la precisión.
- *Aplicación:* Adecuado para problemas donde se requiere una solución rápida y aproximada.

## 2. Método de Euler Hacia Atrás

> *Definición:* El método de Euler hacia atrás es un método implícito que utiliza la pendiente en el punto futuro para estimar el valor de la función, lo que suele requerir la solución de una ecuación no lineal en cada paso.

### 2.1 Fórmula

$$y_{n+1} = y_n + h \cdot f(t_{n+1}, y_{n+1})$$

donde:
- \( y_{n+1} \) debe ser calculado resolviendo la ecuación, ya que aparece en ambos lados de la misma.

### 2.2 Características

- *Estabilidad:* Es incondicionalmente estable, lo que permite el uso de pasos más grandes sin perder estabilidad.
- *Complejidad:* Más complicado de implementar debido a la necesidad de resolver una ecuación en cada paso.
- *Aplicación:* Adecuado para problemas donde la estabilidad es crítica, como en la simulación de sistemas rígidos.

## Test de Jury

El Test de Jury es un proceso algebraico utilizado en sistemas de control para determinar la estabilidad de un sistema discreto. Este método es una extensión del criterio de Routh-Hurwitz aplicado a sistemas de tiempo continuo, adaptado para sistemas de tiempo discreto. Funciona para analizar la estabilidad de polinomios.

## 1. Procedimiento del Test de Jury

![Captura de pantalla 2024-09-01 110105](https://github.com/user-attachments/assets/7f635fc7-c181-4dcf-bdec-117af5e671fd)

1. *Formar la Tabla de Jury:*
   - Se construye una tabla utilizando los coeficientes del polinomio característico, organizados en filas con un proceso iterativo.
  
 ![tabla-criterio-de-estabilidad-de-jury](https://github.com/user-attachments/assets/c02d1278-01fb-40ea-8418-2973cea8ccf5)
  - 
  
2. *Condiciones de Estabilidad:*
   - El sistema es estable si se cumplen las condiciones de signo y magnitud para cada fila generada en la tabla.

3. *Interpretación de Resultados:*
   - Si todas las condiciones de estabilidad son satisfechas, entonces todas las raíces del polinomio característico están dentro del círculo unitario y, por lo tanto, el sistema es estable.

## 2. Conclusión

> El Test de Jury es una herramienta eficaz para evaluar la estabilidad de sistemas discretos mediante el análisis algebraico de su polinomio característico. Es especialmente útil en el diseño de controladores digitales y en la verificación de la estabilidad de sistemas en tiempo discreto.
