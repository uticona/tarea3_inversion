---
title: " ![](C:/Users/ULISES/Downloads/colmex.png){width=6in} \\vspace{0.2in} Tarea III - Macroeconomía II\n \\  \ \ \n \n Inversión\n "
author: 
      - Josselyn Barranco ^[ cjbarranco@colmex.mx]
      - Héctor Deschamps ^[ hdeschamps@colmex.mx]
      - Ulises Ticona ^[ uticona@colmex.mx]
date: \today
output: 
  bookdown::pdf_document2:
  toc: true
  toc_depth: 2
  tables: true
  fig_caption: yes
  toc-title: Contenido
  urlcolor: blue

header-includes:
      - \usepackage{pdflscape}
      - \usepackage{multirow}
      - \usepackage[normalem]{ulem}
      - \useunder{\uline}{\ul}{}
      - \usepackage{float}
      - \floatplacement{figure}{H}
      - \usepackage[nottoc]{tocbibind}
      - \renewcommand{\listfigurename}{Lista de figuras}
      - \renewcommand{\listtablename}{Lista de tablas}
      - \usepackage[utf8]{inputenc}
      - \usepackage[spanish]{babel}
      - \usepackage{graphicx}
      - \usepackage{booktabs}
      - \usepackage{amsmath}
      - \usepackage{graphics}
      
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE, warning = FALSE, message = FALSE)
set.seed(47499)
macro <- "C:/Users/ULISES/OneDrive - El Colegio de México A.C/Documentos/COLMEX 2021/MAESTRIA EN ECONOMIA/Macroeconomia II/tarea3"
setwd(macro)

pacman::p_load(MASS, dplyr, tidyr, ggplot2, tidyverse, ,readxl, writexl, plm, seasonal, tempdisagg, dynlm, fUnitRoots, kableExtra, readr,foreign, msm,lubridate,zoo, janitor,hexbin, magrittr, broom,tinytext, fOptions, derivmkts, haven, growthrates, psych, stargazer)


```

\pagebreak

# Ejercicio 1

**Resuelva los ejercicios 9.1, 9.4, 9.8 y 9.11 (5a edición). Realice estos con ayuda de su laboratorista y entregue las soluciones escritas a máquina, utilizando \LaTeX. [3 horas, 0.5 punto cada inciso].**

## Ejercicio 9.1., Romer (5ta edición) 
**Consider a firm that produces output using a Cobb-Douglas combination of capital and labor: $Y=K^{\alpha}L^{1-\alpha}$, $0<\alpha<1$. Suppose that the firm's price is fixed in the short run; thus it takes both the price of its product, $P$, and the quantity, $Y$, as given. Input markets are competitive; thus the firm takes the wage, $W$, and the rental price of capital, $r_{k}$, as given.**

### a) 
**What is the firm's choice of $L$ given $P, Y, W$, and $K$?**

Dado que el nivel de capital y de demanda del producto están fijos, la empresa contratará un nivel de trabajo dado el valor de esas variables. Despejamos L de la función de producción.

$$
Y=K^{\alpha}L^{1-\alpha}
$$
$$
L=Y^{\frac{1}{1-\alpha}}K^{\frac{-\alpha}{1-\alpha}}
$$

### b) 
**Given this choice of $L$, what are profits as a function of $P$, $Y$, $W$, and $K$?**

Sustituimos el valor de L en la función de beneficios de la empresa:

$$
\pi=PY-WL-r_{K}K
$$
$$
\pi=PY-W(Y^{\frac{1}{1-\alpha}}K^{\frac{-\alpha}{1-\alpha}})-r_{K}K
$$

### c) 
**Find the first-order condition for the profit maximizing choice of $K$. Is the second order condition satisfied?**

Condición de primer orden:

$$
\frac{\partial \pi}{\partial K}=\frac{\alpha}{1-\alpha}WY^{\frac{1}{1-\alpha}}K^{\frac{-\alpha}{1-\alpha}-1}-r_{k}=0
$$
$$
\frac{\alpha}{1-\alpha}WY^{\frac{1}{1-\alpha}}K^{\frac{-1}{1-\alpha}}=r_{k}
$$
Condición de segundo orden:

$$
\frac{\partial^{2}\pi}{\partial K^{2}}=(\frac{-1}{1-\alpha})\frac{\alpha}{1-\alpha}WY^{\frac{1}{1-\alpha}}K^{\frac{\alpha-2}{1-\alpha}}<0
$$
Se satisface la CSO de máximo, dado que $0<\alpha<1$.


### d) 
**Solve the first order condition in part (c) for $K$ as a function of $P, Y, W$, and $r_{k}$. How, if at all, do changes in each of these variables affect $K$?**

De CPO, tendremos que:

$$
\frac{\alpha}{1-\alpha}WY^{\frac{1}{1-\alpha}}K^{\frac{-1}{1-\alpha}}=r_{k}
$$
$$
K^{\frac{-1}{1-\alpha}}=\frac{1-\alpha}{\alpha}\frac{r_{K}}{WY^{\frac{1}{1-\alpha}}}
$$
$$
K=Y(\frac{\alpha}{1-\alpha})^{1-\alpha}(\frac{W}{r_{K}})^{1-\alpha}
$$
El valor óptimo de capital es independiente del precio del producto de manera directa. Respecto a las otras variables, se tiene que la elasticidad K-Y es unitaria y la elasticidad K-W positiva e igual a $1-\alpha$. Asimismo, la elasticidad K-precio de renta del capital es negativa e igual a $-(1-\alpha)$.

## Ejercicio 9.4., Romer (5ta edición) 

**BUILDING INTUITION CONCERNING THE TRANSVERSALITY CONDITION. Consider an individual choosing the path of $G$ to maximize $\int_{t=0}^{\infty}e^{-\rho t}[-\frac{a}{2} G(t)^{2}]dt$, $a>0$, $\rho>0$. Here $G(t)$ is the amount of garbage the individual creates at time t; for simplicity, we allow for the possibility that $G$ can be negative. The individual's creation of garbage affects his or her stock of trash. In particular, the stock of trash, $T$, evolves according to $T(0) = 0$, $\dot{T}(t) = G(t)$.**

### a) 
**Prove -using as little math as possible- that the utility-maximizing path is $G(t)=0$ for all $t$.**

Como todo el argumento de la integral es estrictamente negativo para todo $G(t) \neq 0$, el máxima de dicha función se alcanzará cuando $G(t)=0$ para toda $t$.

### b) 
**Suppose we want to analyze this problem using the calculus of variations. Let $G$ be the control variable and $T$ the state variable, and let $\mu$ denote the costate variable. What is the current-value Hamiltonian?**

$$
H[G(t),T(t),\lambda(t)]=e^{-\rho t}(-\frac{a}{2}G(t)^{2})+\lambda(t)G(t) \\ s.a. \dot{T}=G(t) \ con \ T(0)=0
$$

### c) 
**Find the conditions for optimality other than the transversality condition. Describe the paths of $G$ that satisfy those conditions.**

\begin{itemize}
\item $\frac{\partial H()}{\partial G(t)}=0$
\end{itemize}

$$
e^{-\rho t}(-aG(t))+\lambda(t)=0
$$
$$
\Rightarrow \lambda(t)=ae^{-\rho{t}}G(t)
$$
\begin{itemize}
\item $\frac{\partial H()}{\partial T(t)}=-\frac{d\lambda}{dt}$
\end{itemize}

$$
0=-\frac{d\lambda}{dt}
$$
\begin{itemize}
\item $\frac{\partial T(t)}{\partial t}=G(t) \ con \ T(0)=0$
\end{itemize}

De la segunda CPO:

$$
\frac{d\lambda}{dt}=0 \ \Rightarrow \lambda(t)=K
$$
Reemplazando en la primera CPO:

$$
\lambda(t)=ae^{-\rho t}G(t)
$$

$$
K=ae^{-\rho t}G(t)
$$
$$
\Rightarrow G(t)=\frac{K}{a}e^{\rho t}
$$

Reemplazando este resultado en la tercera CPO:

$$
\frac{\partial T(t)}{\partial t}=G(t)
$$
$$
\frac{\partial T(t)}{\partial t}=\frac{K}{a}e^{\rho t}
$$
$$
\Rightarrow T(t)=\int \frac{K}{a}e^{\rho t}dt
$$

$$
= \frac{K}{a} \Bigl[\frac{1}{\rho}\int \rho e^{\rho t}dt \Bigr]
$$
$$
\Rightarrow T(t)=\frac{K}{a\rho}e^{\rho t}+B
$$
Si $T(0)=0$:

$$
T(0)=0
$$

$$
\frac{K}{a\rho}e^{\rho(0)}+B=0
$$

$$
\frac{K}{a\rho}+B=0
$$
$$
\Rightarrow \frac{K}{a\rho}=-B
$$

### d) 
**What is the transversality condition? Show that it rules out all but one of the paths you found in part (c), and that the one remaining path is the one that you showed in part (a) to be optimal: $G(t)=0$ for all $t$.**

La condición de transversalidad viene definida por: $lim_{t\rightarrow \infty}T(t)=0$

$$
lim_{t\rightarrow \infty}T(t)=lim_{t\rightarrow \infty}\Bigl(\frac{K}{a\rho}e^{\rho t}+B \Bigr) = 0
$$
$$
=lim_{t\rightarrow \infty}\frac{K}{a\rho}e^{\rho t}+lim_{t\rightarrow \infty}B=0
$$
$$
=lim_{t\rightarrow \infty}-Be^{\rho t}+B=0
$$
$$
=lim_{t\rightarrow \infty}B(1-e^{\rho t})=0
$$


En esta última expresión tenemos que la condición de transversalidad se cumple en dos casos: $B=0$ o $1-e^{\rho t} \ cuando t=0$. Por tanto, $B=0$, $\frac{K}{\rho a}=0$, con $a>0$, $\rho>0$ y $A=0$. Entonces:

$$
G(t)=\frac{0}{a}e^{\rho t}=0 \ \ \ \forall t
$$


### e)
**Explain in a sentence or two why the solutions in (c) other than $G(t)=0$ for all $t$ look as if they are utility-maximizing if one does not consider the transversality condition, and why the transversality condition rules them out.**

Si omitimos la condición de transversalidad, la función $G(t)$ encontrada será mayor a cero para todo $t$, lo que quiere decir que siempre será óptimo acumular capital para siempre. Esta condición restringe este camino.

## Ejercicio 9.8., Romer (5ta edición) 
**Consider the model of investment in Sections 9.2-9.5. Suppose it becomes known at some date that there will be a one-time capital levy. Specifically, capital holders will be taxed an amount equal to fraction $f$ of the value of their capital holdings at some time in the future, time $T$. Assume the economy is initially in long-run equilibrium. What happens at the time of this news? How do $K$ and $q$ behave between the time of the news and the time the levy is imposed? What happens to $K$ and $q$ at the time of the levy? How do they behave thereafter? (Hint: Is $q$ anticipated to change discontinuosly at the time of the levy?)**

Supóngase que el anuncio del impuesto se hace en el tiempo $t$ y se cobra en el periodo $T$. Primero, hay que notar que que las pérdidas de capitales que sufren los inversionistas no pueden ocurrir después del tiempo t. Por ejemplo, si en el tiempo $T$ hubiera un salto de $K$ habría pérdidas de capital que los inversionistas pudieron haber evitado, por lo tanto, un salto no puede ocurrir después de la noticia. En el tiempo t ocurre un salto discontinuo en $q$ por la noticia del impuesto en el periodo $t$. Sin embargo, las curvas de $\dot{K}=0$ y $\dot{q}=0$ no se desplazan porque el cobro del impuesto ocurre en un solo instante.
	
Pensando en el diagrama de fase, en el tiempo $t$ ocurre un salto en $q$ hacia abajo, manteniéndose el stock de capital constante. Esto ocurre porque, dado que los inversionistas no tienen pérdidas de capital después de la noticia, el capital instantes antes y después de $T$ debe ser igual. Más formalmente, sea $\varepsilon>0$, con $\varepsilon\rightarrow0$ y sea $g\in(0,1)$ la tasa impositiva del impuesto (que se asume es una proporción del capital), entonces:
	
$$q(T-\varepsilon)=(1-g)q(T+\varepsilon)$$
	
Por lo tanto, $q$ se ajusta para satisfacer esta condición (que el valor del capital permanece ifual) y existe, también, un salto discontinuo de $q$ en el periodo $T$, mientras que $K$ permanece constante por los costos crecientes de cambiar el capital.
	
Después del salto de $q$ en el periodo de la noticia, nos encontramos fuera del equilibrio y fuera de la trayectoria silla (recuérdese que las nulclinas no se desplazaron). Nos encontramos en un punto debajo de las curvas $\dot{K}=0$ y $\dot{q}=0$, donde existe una trayectoria divergente hacia abajo y a la izquierda. Entre el periodo t y T este es el movimiento seguido por el sistema de ecuaciones diferenciales. En el periodo T, cuando ocurre y termina el impuesto, ocurre un salto discontinuo de $q$ hasta regresar a la misma trayectoria silla que existía antes de la noticia, para luego tender de nuevo al mismo equilibrio. El valor del capital sufrió solo una reducción temporal.

\begin{figure}
	\label{dfase2}
	\caption{Efectos de un impuesto al capital de una sola vez}
	\includegraphics{dfase2.png}
\end{figure}

En la Figura 1 se observa este proceso. Inicialmente se parte del equilibrio. Cuando se hace el anuncio del impuesto (tiempo $t$), $q$ salta de manera discontinua hasta la curva azul, la cual es la trayectoria divergente debajo del equilibrio. Entre el tiempo $t$ y $T$ se sigue dicha trayectoria y, cuando llega el cobro del impuesto, ocurre un salto discontinuo de $q$ hasta la línea verde, la cual es la trayectoria silla relevante, i.e. la que satisface las condiciones de transversalidad. A partir de esto, $q$ y $K$ siguen una trayectoria convergente hacia el mismo equilibrio incial.
	


## Ejercicio 9.11., Romer (5ta edición) 
**Suppose that $\pi(K)=a-bK$ and $C(I)=a\frac{I^{2}}{2}$.**

### a) 
**What is the $\dot{q}=0$ locus? What is the long-run equilibrium value of $K$?**

Partiendo del caso continuo del problema de maximización y partiendo de la ecuación $\int_{0}^{\infty}e^{-rt}[\pi(K(t))\kappa(t)-I-C(I(t))] dt$ (en lo que sigue se quitará la $t$ para facilitar la notación), tenemos que el Hamiltoniano es:
	
$$H=\pi(K)\kappa-I-C(I)+qI$$ 
	
Cuya condición de primer orden (respecto a $\kappa$) es:
	
$$\frac{\partial H}{\partial \kappa} = \dot{q}-rq+\pi(K)-\frac{\partial C}{\partial \kappa}=0$$
Sustituyendo $\pi(K)=a-bK(t)$, notando que $\frac{\partial C(I)}{\partial \kappa}=0$  y haciendo $\dot{q}=0$,
$$rq=a-bK$$
Despejando q, se puede observar que la curva $\dot{q}=0$ es
$$q=\frac{a-bK}{r}$$

### b) 
**What is the slope of the saddle path? (Hint: Use the approach in Section 2.6.)**

Empezamos notando que, como $I=\dot{\kappa}$, entonces $C(I)=\alpha\frac{I^{2}}{2}=\alpha\frac{\dot{\kappa}^{2}}{2}$ y, por lo tanto, $\frac{\partial C(\dot{\kappa})}{\partial \dot{\kappa}}=\alpha \dot{\kappa}$.
	
Sustituyendo en la primera condición de primer orden,
	
$$1+\alpha \dot{\kappa}=q$$
$$\Leftrightarrow\dot{\kappa}=\frac{q-1}{\alpha}$$ 
	
Como existen $N$ firmas idénticas, con la misma $\dot{\kappa}$, tenemos que
	
$$\dot{K}=N\left[\frac{q-1}{\alpha}\right]$$
	
Para obtener la ecuación de la trayectoria silla, hacemos uso de las condicones de equilibrio, $q^*$ y $K^*$, y de las ecuaciones de movimiento ya encontradas, de la siguiente forma:

\begin{equation}
	\label{eq1}
	\dot{(q-q^*)}=rq-a + bK
\end{equation}

\begin{equation}
	\label{eq2}
	\dot{(K-K^*)}=N\left[\frac{q-1}{\alpha}\right]
	\end{equation}

Nótese que el miembro izquierdo de las ecuaciones son las derivadas de la diferencia respecto al tiempo.
	
dividiendo \ref{eq1} entre $q-q^*$,
	
\begin{equation}
	\label{eq3}
	\frac{\dot{(q-q^*)}}{q-q^*}=\frac{rq-a + bK}{q-q^*}
\end{equation}
	
Luego, notando que $K^*=\frac{a-r}{b}$,
	
$$K-K^*=\frac{bK-a+r}{b}$$
	
sustituyendo la última ecuación en \ref{eq3} y notando que en equilibrio $q^*=1$
\begin{equation}
	\label{eq4}
	\frac{\dot{(q-q^*)}}{q-q^*}=r+b\frac{K-K^*}{q-q^*}
\end{equation}
	
Dividiendo ambos lados de la ecuación \ref{eq3} entre $K-K^*$ y notando de nuevo que $q^*=1$,
	
\begin{equation}
	\label{eq5}
	\frac{\dot{(K-K^*)}}{K-K^*}=\frac{N}{\alpha}\frac{q-q^*}{K-K^*}
\end{equation}
	
Ahora, sea $\mu=\frac{N}{\alpha}\frac{q-q^*}{K-K^*}$, 	tenemos que la ecuación \ref{eq5} se puede ver como
	
\begin{equation}
	\label{eq6}
\mu=\frac{N}{\alpha}\frac{q-q^*}{K-K^*}\Leftrightarrow\frac{q-q^*}{K-K^*}=\frac{\alpha\mu}{N}
\end{equation}
Sustituyendo en la ecuación \ref{eq4}, tenemos que
	
$$\mu=r+\frac{bN}{\alpha\mu}\Leftrightarrow\alpha\mu^2-\alpha r\mu-bN=0$$
	
Resolviendo la ecuación cuadrática mediante fórmula general,
	
$$\mu=\frac{r\pm\sqrt{\alpha^2r^2+4\alpha bN}}{2\alpha}$$
	
Sabemos que solo la trayectoria silla es convergente, esto es, se acerca a $(K^*, q^*)$. Para que esto ocurra, $\mu$ debe ser negativo, por lo tanto, solo se toma la solución que puede ser negativa con una r positiva (cuando se resta la raíz cuadrada).
	
Sustituyendo la solución relevante de $\mu$ en la ecuación \ref{eq6} y resolviendo por q se obtiene
	
$$q=q^*+\alpha\left[\frac{r\pm\sqrt{\alpha^2r^2+4\alpha bN}}{2\alpha}\right](K-K^*)$$
	
Por lo tanto, la pendiente de la trayectoria silla es:
	
$$\frac{\partial q}{\partial K}=\alpha\left[\frac{r\pm\sqrt{\alpha^2r^2+4\alpha bN}}{2\alpha}\right]$$
	
Que ya sabemos que es negativa por la solución elegida de la ecuación cuadrática.

\pagebreak

# Ejercicio 2
**Estudie los determinantes de la inversión agregada en México siguiendo estos pasos: [3 horas, 0.5 puntos cada inciso]**

## a)
**Obtenga, del Inegi, datos DESESTACIONALIZADOS para México del consumo "C", datos de "T", la inversión privada (inversión fija bruta), y de "Y", el PIB, entre 1980 y 2021/IV, A FRECUENCIA TRIMESTRAL, EN TÉRMINOS REALES y grafique las tres series. (Si encuentra varias series pero ninguna cubre el periodo completo, tome una decisión ejecutiva para "unir" las series.)**

La base de datos se construyó a partir del Banco de Información Económica del INEGI. Para la serie correspondiente al Producto Interno Bruto se encontraron datos de 1980 a 2021. Sin embargo, para las series de Consumo e Inversión Privada la disponibilidad de datos es distinta. Por esa razón, acotamos nuestro análisis al periodo de tiempo donde se disponga de datos para todas las variables; quedándonos así con los años de 1993-2021. Este tipo de ajuste es conveniente para eliminar los valores missing y garantizar buenas estimaciones; así mismo, este ajuste se repite a lo largo del ejercicio por limitaciones de datos. 

\begin{figure}[H]
      \centering
      \caption{Series de tiempo}
         \vspace{0.3cm}
        \includegraphics[width=0.7 \textwidth]{Cifrasreales_trim_1993a2019.png}
    \end{figure}

A partir de la gráfica anterior es posible observar una tendencia similar entre las tres series de tiempo. Destaca, sobretodo, la caída generada por la crisis sanitaria de Covid-19. No obstante, es posible ver que hay efectos suavizados en la serie de inversión privada; por ejemplo, si comparamos con la serie del producto interno bruto notaremos la diferencia en las pronunciadas caídas y en los ascensos. Así mismo, podemos ver que entre el consumo y la inversión, es el consumo agregado el que mayor aporta a los niveles de PIB y que esta diferencia se fue acrecentando con el paso de los años. 


## b)
**Grafique la relación entre los cambios de I y los de Y, es decir, grafique los puntos ($\% \Delta Y_{t}$, $\% \Delta I_{t}$) poniendo la inversión en el eje de las ordenadas.**

A partir de la gráfica notamos que hay una relación positiva entre las variaciones en el producto interno bruto y las variaciones de la inversión durante el periodo de 1993 a 2021. Esto quiere decir que a mayor variación en el PIB esperamos una variación positiva en la inversión bruta fija. Sin embargo, los resultados muestran que esta relación oscila normalmente alrededor del 0\%. Así mismo destacan algunos outliers dentro de los datos disponibles. 

\begin{figure}[H]
      \centering
      \caption{$\%\triangle Y_t$ vs. $\%\triangle I_t $}
         \vspace{0.3cm}
        \includegraphics[width=0.7 \textwidth]{VariacionGDPvsInv.png}
    \end{figure}

## c)
**Calcule la volatilidad de cada serie y la covarianza entre las tres series de crecimiento ($\% \Delta I$, $\% \Delta C$ y $\Delta Y$), describa cuál es más volátil y cuales cambios, si los de I o los de C están más relacionados con los de Y. **

Para calcular la volatilidad de las series se utiliza una medida de dispersión de la variable; en este caso puede utilizarse la desviación estándar y la varianza. También se puede medir a partir del error estándar de los residuos en un modelo univariante. Para este caso utilizaremos la desviación estándar bajo el entendimiento de que una mayor volatilidad significa que habrá una mayor desviación estándar en la serie de análisis. A partir de esto encontramos la siguiente información. 

\vspace{0.3cm}

\begin{table}[ht]
\centering
\caption{Estadísticos de las tasas de crecimiento.}
\vspace{0.3 cm}
\begin{tabular}{lcccccc} \hline
 & (1) & (2) & (3) & (4) & (5) & (6) \\
VARIABLES & N & mean & sd & Var & min & max \\ \hline
 &  &  &  &  &  &  \\
$\% \triangle Y$ & 116 & 0.523 & 2.465 & 6.076 & -17.85 & 13.49 \\
$\% \triangle I$ & 116 & 0.544 & 5.302 & 28.11 & -30.62 & 19.22 \\
$\% \triangle C$ & 116 & 0.615 & 2.629 & 6.914 & -20.35 & 12.47 \\
 &  &  &  &  &  &  \\ \hline
\end{tabular}
\end{table}


A partir de estos resultados vemos que la serie de inversión es la que presenta una volatilidad más alta dado que su relación estándar es de 5.30 y, por ende, tiene varianza menor. Contrariamente, la serie del consumo presenta una menor volatilidad con una desviación estándar de 2.62. 

Ahora bien, al observar las covarianzas entre las variables podemos observar el signo de la relación entre las variables aunque no es posible inferir la fuerza de esta. Por esa razón observamos, también, la correlación y observar que tan fuerte es la relación entre una tasa de crecimiento y otra. 

En el cuadro 1 es posible ver que la tasa de crecimiento del PIB tiene una relación positiva con las series de Consumo e Inversión. Es decir, si una de las variables incrementa la otra también lo hará dado que se mueven en la misma dirección. Esto mismo ocurre entre el consumo y la inversión. 

Por otra parte, cuando analizamos la matriz de correlación observamos que la tasa de crecimiento en el consumo tiene un mayor efecto sobre el PIB en comparación al efecto que tiene la inversión. No obstante, la diferencia no es muy grande pero si es significativa. 

## d)
**Obtenga, del Banco de México, datos sobre las tasas de interés reales ($r^{r}$) de la economía $r^{r}=r^{n}-\pi$, es decir, la tasa de interés nominal, menos la tasa de inflación esperada (en cuyo caso se trata de la tasa de interés real "ex-ante"), o menos la tasa de inflación observada (en cuyo caso se trata de la ex-post") y grafíquelas.**

Para obtener la tasa de interés real utilizamos datos del Sistema de Información Económica del Banco de México. Dentro de los datos disponibles encontramos series de 1995 a 2021 tanto para inflación anual como para la TIEE a 28 días. Teniendo en cuenta lo anterior realizamos, para fines prácticos, un acotamiento de los años de estudio eliminando los años anteriores a 1995. Así mismo, se realizo un procesamiento de los datos para tomar como medida trimestral de inflación el promedio de la inflación mensual observada y se realizó un procedimiento análogo para la tasa de interés nominal. Posteriormente se realizó una operación simple para obtener los datos de la tasa de interés real. 

\begin{figure}[H]
      \centering
      \caption{Inflación y tasas de interés}
         \vspace{0.3cm}
        \includegraphics[width=0.7 \textwidth]{interestrates.png}
    \end{figure}

Mediante la gráfica es posible ver una tendencia descendente tanto de la tasa de interés nominal como de la tasa de inflación observada y por ende de la tasa de interés real. Así mismo, dado los niveles de la tasa de interés nominal y de inflación tenemos una serie de interés real que presenta cierta volatilidad al inicio del periodo. Eventualmente las tres series convergen hacia un nivel de estabilidad donde vemos curvas con variaciones más suaves. 

## e)
**Estime una serie de modelos lineales con el objetivo de averiguar qué variables predicen la tasa de crecimiento de la inversión $\Delta \% I_{t}$. Utilice valores corrientes y rezagados del crecimiento en el producto, de la tasa de interés real, valores rezagados de la propia tasa de cambio en la inversión y combinaciones de estas variables.**

## f)
**Estime otra serie de modelos lineales con el objetivo de averiguar qué variables predicen la tasa de crecimiento de la inversión $\Delta \% I_{t}$: a las especificaciones del inciso anterior, agregue valores corrientes y/o rezagados de la *confianza empresarial* del Inegi y de la *confianza del consumidor* elaborado por el Inegi y el Banco de México.**

## g)
**Interprete los resultados.**

A continuación se presentan los resultados de los incisos e), f) y g).

Con el objetivo de averiguar las variables que predicen la tasa de crecimiento de la Inversión. se sugiere la estimación de los siguientes modelos lineales:

\begin{equation}
\triangle \% I_t = \beta_0 + \beta_1 \triangle \% Y_t + \beta_2 r_t + u_1    
\end{equation}

\begin{equation}
    \triangle \% I_t = \beta_0 + \beta_1 \triangle \% Y_{t-1} + \beta_2 r_{t-1} + u_2
\end{equation}


\begin{equation}
\triangle \% I_t = \beta_0 + \beta_1 \triangle  \% Y_{t-1} + \beta_2 r_{t-1} + \beta_3 \triangle \% I_{t-1} + u_3    
\end{equation}

\begin{equation}
 \triangle \% I_t = \beta_0 + \beta_1 \triangle \% Y_t + \beta_2 \triangle  \% Y_{t-1} + \beta_3 r_t + \beta_4 r_{t-1} + \beta_5 \triangle \% I_{t-1} + u_4   
\end{equation}

\begin{equation}
 \triangle \% I_t = \beta_0 + \beta_1 \triangle  \% Y_{t-1} + \beta_2  r_{t-1} + \beta_3 \triangle \% Y_t + u_5   
\end{equation}


\begin{table}[ht]
\centering
\caption{Estimación de Modelos Lineales sugeridos}
\vspace{0.3 cm}
\begin{tabular}{lccccc} \hline
 & (1) & (2) & (3) & (4) & (5) \\
Variables & Modelo 1 & Modelo 2 & Modelo 3 & Modelo 4 & Modelo 5 \\ \hline
 &  &  &  &  &  \\
$\triangle \%Y$ & 1.610*** &  &  & 1.643*** & 1.659*** \\
 & (0.0639) &  &  & (0.0620) & (0.0732) \\
Real interest rate (r) & -0.0729 &  &  & -0.0554 &  \\
 & (0.0445) &  &  & (0.0503) &  \\
$\triangle \% Y_{t-1}$ &  & -0.236 & -0.570 & 0.179 & 0.123* \\
 &  & (0.460) & (0.561) & (0.190) & (0.0704) \\
Lag ($r_{t-1}$) &  & -0.131 & -0.116 & -0.0383 & -0.0556 \\
 &  & (0.0933) & (0.0954) & (0.0448) & (0.0417) \\
$\triangle \% I_{t-1}$ &  &  & 0.207 & -0.0331 &  \\
 &  &  & (0.169) & (0.103) &  \\
Constant & 0.0578 & 1.247* & 1.234* & 0.0278 & -0.0868 \\
 & (0.235) & (0.735) & (0.740) & (0.277) & (0.268) \\
 &  &  &  &  &  \\
Observations & 107 & 107 & 107 & 107 & 107 \\
 R-squared & 0.818 & 0.026 & 0.033 & 0.825 & 0.822 \\ \hline
\multicolumn{6}{c}{ Robust standard errors in parentheses} \\
\multicolumn{6}{c}{ *** p$<$0.01, ** p$<$0.05, * p$<$0.1} \\
\end{tabular}
\end{table}

Al realizar las estimaciones anteriores, teniendo en cuenta un periodo de 1995 a 2021, encontramos los resultados que muestra el Cuadro 2. 

Dado que el objetivo es encontrar las variables que predicen la tasa de crecimiento de la inversión, es importante contemplar variables que pueden ser de utilidad aunque estás no se encontrasen en nuestro análisis. Por esa razón agregamos a las estimaciones valores corrientes y rezagados del indicador de confianza empresarial y del indicador de la confianza del consumidor elaborados por INEGI y el Banco de México. Es importante decir que la disponibilidad de estos datos es a partir de 2017. Acotando el periodo de análisis, de 2017 a 2021, nos quedamos solo con 20 observaciones lo que puede subestimar los resultados obtenidos en las estimaciones. Finalmente, los resultados que obtenemos son:

\begin{table}[ht]
\centering
\caption{Estimación de Modelos Lineales con indicadores de confianza}
\vspace{0.3 cm}
\begin{tabular}{lccccc} \hline
 & (1) & (2) & (3) & (4) & (5) \\
Variables & Modelo 1 & Modelo 2 & Modelo 3 & Modelo 4 & Modelo 5 \\ \hline
 &  &  &  &  &  \\
$ \triangle\% Y$ & 1.494*** &  &  & 1.505*** & 1.508*** \\
 & (0.0356) &  &  & (0.0442) & (0.0369) \\
Real interest rate (r) & -0.353 &  &  & 0.399 &  \\
 & (0.204) &  &  & (0.395) &  \\
Confianza del consumidor & 0.128 & 0.454 & 0.520 & 0.224* & 0.174 \\
 & (0.128) & (0.334) & (0.371) & (0.120) & (0.124) \\
Confianza empresarial & -0.0615 & -0.0895 & -0.105 & -0.194 & -0.141 \\
 & (0.106) & (0.782) & (0.793) & (0.140) & (0.112) \\
$\triangle \% Y_{t-1}$ &  & -0.603 & 0.576 & 0.414 & 0.0218 \\
 &  & (0.611) & (0.897) & (0.282) & (0.0522) \\
Lag ($r_{t-1}$) &  & -1.627* & -1.933* & -1.123** & -0.559** \\
 &  & (0.901) & (1.053) & (0.445) & (0.206) \\
$\triangle \% I_{t-1}$ &  &  & -0.790 & -0.285 &  \\
 &  &  & (0.462) & (0.179) &  \\
Constant & -1.958 & -10.46 & -12.15 & 1.412 & 0.540 \\
 & (3.948) & (40.50) & (41.25) & (4.453) & (4.116) \\
 &  &  &  &  &  \\
Observations & 20 & 20 & 20 & 20 & 20 \\
 R-squared & 0.960 & 0.230 & 0.256 & 0.975 & 0.968 \\ \hline
\multicolumn{6}{c}{ Robust standard errors in parentheses} \\
\multicolumn{6}{c}{ *** p$<$0.01, ** p$<$0.05, * p$<$0.1} \\
\end{tabular}
\end{table}

En cuanto a las interpretaciones, las estimaciones de modelos lineales sugeridos (Cuadro 2) nos permiten ver que la tasa de interés real y su rezago presentan efectos marginales negativos sobre la tasa de crecimiento de la inversión. Al analizar el rezago de la propia tasa de crecimiento de la inversión, vemos que en uno de los modelos tiene un efecto positivo mientras que en el otro es negativo; no obstante, estos efectos no son significativos a ningún nivel. Lo más importante de éstos modelos simples es que una variación en la tasa de crecimiento del producto interno bruto tiene efectos positivos en la tasa de crecimiento de inversión para los tres modelos donde se contemplan y que hay que resaltar que son estimaciones significativas al más alto nivel. Por último, los modelos en donde incluimos a la variación del PIB son modelos con R-cuadrada más alta y que explican un mayor porcentaje de la muestra. 

Ahora bien, cuando añadimos a los indicadores de confianza tanto del consumidor como del nivel empresarial hay variaciones importantes pero no drásticas. Los modelos que incluyen a las variaciones en el PIB siguen siendo los modelos que explican mayor porcentaje de los casos. Así mismo, cuando vemos los efectos del indicador de confianza del consumidor podemos observar que una variación en el indicador tiene un efecto marginal positivo sobre la tasa de crecimiento de la inversión. Pero cuando vemos el indicador de confianza empresarial destaca el hecho de que un crecimiento positivo en este indicador repercute de manera negativa al crecimiento en la inversión. Si analizamos esto con la lógica macroeconómica, es congruente que si los consumidores confían más en los mercados tendrán mayor apertura a realizar inversiones. En cambio, si las empresas confían más veremos que tomarán la decisión de invertir menos. 

Algunas otras distinciones de estas estimaciones en contraste a las estimaciones anteriores es que, en este caso, el rezago de la tasa de interés real presenta efectos negativos con nivel de significancia. Mientras tanto, se mantiene el hecho de que variaciones en el PIB tienen un efecto marginal positivo sobre la variación en el crecimiento de la inversión y que estos resultados son significativos al más alto nivel. 



\pagebreak

# Ejercicio 3
**Estudie la habilidad de modelo de la q de Tobin para explicar las tasas de inversión de empresas individuales, siguiendo estos pasos [3 horas, 0.5 puntos cada inciso]:**

## a)
**Con el propósito de desarrollar intuición sobre la existencia y fuente de los datos corporativos, vaya al sitio de internet de algún corporativo mexicano y obtenga su reporte anual. De ahí, obtenga el valor de los activos menos los pasivos (excepto el capital) y con ello construya el "valor en libros" de la empresa. Posteriormente, de dicho reporte, o del sitio de la BMV o de la BIVA, obtenga el "valor de capitalización" de mercado de la misma empresa y finalmente construya la variable "Q" como la razón de dichos valores.**

Para realizar este ejercicio, se eligió a la empresa mexicana CEMEX S.A.B. de C.V. Se obtuvo la información sobre la capitalización de la empresa mediante su reporte anual de 2021. Al 20 de abril de 2021, CEMEX tenía un valor de capitalización de $10,845 millones de pesos. Para obtener información sobre los activos y los pasivos, se utilizó el estado financiero del 31 de marzo de 2021. A continuación se muestra un cuadro resumiendo la información obtenida.

\begin{table}[H]
\centering
\begin{tabular}{@{}ccc@{}}
\toprule
Activo     & Pasivo     & Capitalización \\ \midrule
27,562,367 & 17,987,728 & 10,845,000     \\ \bottomrule
\multicolumn{3}{l}{\footnotesize Nota: las cifras están en miles de pesos.}
\end{tabular}
\end{table}


```{r,include=FALSE, echo=FALSE}
activos21 <- 27562367 ### en miles
pasivos21 <- 17987728 ### en miles
v_libros21 <- activos21-pasivos21
v_cap21 <- 10845000 ### en miles
Q21 <- v_libros21/v_cap21
```

Para obtener la "Q" se utilizó la siguiente fórmula:

$$Q=\frac{valor\ de\ capitalización}{activos-pasivos}=\frac{valor\ de\ capitalización}{valor\ en\ libros} $$

Por lo tanto, la Q para 2021 de CEMEX fue de
$$Q=\frac{10845000}{9574639}\approx1.1327$$

También se ilustra una serie histórica del precio de las acciones de la firma.

\begin{figure}[H]
      \centering
      \caption{Precio histórico acción CEMEX}
         \vspace{0.01cm}
        \includegraphics[width=0.7 \textwidth]{accioncemex.png}
    \end{figure}
    
## b)
**Construya una medida (no necesariamente una buena) de "q" de la empresa utilizando DOS reportes corporativos, idealmente el de un trimestre y el el mismo trimestre del año anterior, y comparando el cambio del valor en libros vs el cambio del valor de capitalización.**

La "q" utilizada fue la misma que en el inciso anterior, la relación entre el valor en libros y el valor de capitalización. Para este inciso se parte de la información obtenida de los activos y pasivos de 2021 y se agregan los activos y pasivos del 31 de marzo de 2020 y el valor de capitalización del 20 de abril de 2020. A continuación se resume la información.

\begin{table}[H]
\centering
\begin{tabular}{@{}ccccc@{}}
\toprule
Año  & Activos    & Pasivos    & Capitalización & Q      \\ \midrule
2020 & 28,597,946 & 18,423,280 & 3,032,000      & 0.2980 \\
2021 & 27,562,367 & 17,987,728 & 10,845,000     & 1.1327 \\ \bottomrule
\end{tabular}
\end{table}

```{r,include=FALSE, echo=FALSE}
activos20 <- 28597946
pasivos20 <- 18423280
v_libros20 <- activos20-pasivos20
v_cap20 <- 3032000
Q20 <- v_libros20/v_cap20
```

Es notable la diferencia en el valor de capitalización de un año al otro. Esto tiene que ver con la caída de las acciones de CEMEX durante el inicio de la pandemia, mientras que el valor en libros se mantuvo relativamente constante. Esto también ocasiona que la "Q" disminuya una vez que se recuperó el precio de las acciones en 2021. Esto se puede observar en la gráfica, hubo un valle aproximadamente en marzo y abril de 2020 en el precio de su acción, esto explica la gran diferencia en las "q" de ambos años. Además, este dato parece apoyar la teoría, ya que el movimiento del valor de capitalización se movió a favor de acercar la q de Tobin a uno.

El cambio porcentual del valor en libros fue de 
$$\Delta\%valor\ en\ libros=-5.89\%$$
Mientras que el cambio porcentual del valor de capitalización fue de
$$\Delta\% valor\ de\ capitalización=257.68\%$$

```{r,include=FALSE, echo=FALSE}
d.libros <- (activos21-pasivos21-(activos20-pasivos20))/(activos20-pasivos20)
d.cap <- (v_cap21/v_cap20)-1
```

## c)
**Utilice su cuenta de GitHub.com para entrar al repositorio fisionmail, Colmex\_Macro\_2\_2022 y bajar el archivo de datos que está ahí, está en formato de stata,  ".dta". Cree una medida de la tasa de inversión y una medida de q de Tobin: la medida de la tasa de inversión puede ser el gasto en capital (capx) sobre el capital (ppen), o la tasa de cambio en el capital (\%$\Delta$ ppen), o la tasa de cambio de los activos (\%$\Delta$ta).**

```{r}
ej3dta<-read_stata("emisorasGAM.dta")
```

```{r, echo=FALSE}
ej3dta <- read_stata("emisorasGAM.dta")
ej3dta$Fecha <- ydm(ej3dta$fecha2)
ej3dta$Activos <- (ej3dta$econ_activotot)
ej3dta$Inventarios <- (ej3dta$econ_inventario)
```

Utilizaremos la medida de tasa de cambio de los activos ($\% \Delta Activos$) como proxy de la inversión.

$$
I_{i,t}=\% \Delta Activos=\frac{Activos_{t}-Activos_{t-1}}{Activos_{t-1}}
$$

donde $i$ es la empresa y $t$ es el trimestre en cuestión. 

Asimismo, para el cálculo de la q de Tobin, tomamos la metodología propuesta por Chung y Pruitt (1994):

$$
q=\frac{MarketCap-Deuda}{Activos}
$$
Con los datos obtenidos de la base .dta, obtenemos para la empresa CEMEX los siguientes resultados:

```{r, echo=FALSE}
cemex <- read_xlsx("ej3_cemex.xlsx")
cemex <- ts(cemex, frequency=4, start=c(1989,1))
```

```{r, include=TRUE}
Inv <- headTail(read_xlsx("ej3_cemex.xlsx", sheet=2), top=0, bottom=10)

kbl(Inv, booktabs = T, format="latex",  caption = "Inversión y q de Tobin") %>%
kable_styling(position = "center",latex_options = c("striped", "hold_position"))
```

```{r, echo=FALSE, fig.cap="Inversión", fig.pos='H'}

ts.plot(cemex[,7], title = "Inversión", 
                   ylab = "Inversión, %", 
                   xlab = "Trimestre",
                   xgrid = TRUE,
                   ygrid = TRUE,
                   legend = "Inversión")

```

```{r, echo=FALSE, fig.cap="q Tobin", fig.pos='H'}

ts.plot(cemex[,8], title = "q Tobin", 
                   ylab = "q Tobin", 
                   xlab = "Trimestre",
                   xgrid = TRUE,
                   ygrid = TRUE,
                   legend = "q Tobin")

```


## d)
**Cree una medida de la "Q": el  valor de mercado de la empresa sobre el valor en libros de la empresa, en donde el valor de mercado es es número de acciones por el precio de la acción.**

Calculamos, según el enunciado, una medida de Q con los datos proporcionados.

```{r, include=TRUE}
Q <- headTail(read_xlsx("ej3_cemex.xlsx", sheet=3), top=0, bottom=10)

kbl(Q, booktabs = T, format="latex",  caption = "Q estimada") %>%
kable_styling(position = "center",latex_options = c("striped", "hold_position"))
```


```{r, echo=FALSE, fig.cap="Q estimada", fig.pos='H'}

ts.plot(cemex[,9], title = "Q estimada", 
                   ylab = "Q estimada", 
                   xlab = "Trimestre",
                   xgrid = TRUE,
                   ygrid = TRUE,
                   legend = "Q estimada")

```

## e)
**Estime los coeficientes de una relación lineal entre la tasa de inversión en un periodo y la "Q"" en el mismo y también de una relación utilizando la "Q" del periodo inmediato anterior.** 

```{r}
tres_e <- read_xlsx("ej3_cemex.xlsx")

modelo_1 <- lm(tres_e$inversion ~ tres_e$Q)
modelo_2 <- lm(tres_e$inversion ~ tres_e$Q_1)
```                                                             

```{r results='asis',echo=F}
stargazer(modelo_1, modelo_2, header=FALSE, type='latex',title="Inversión en función de Q",dep.var.labels = "Inversión",column.labels = c("Q contemporáneo", "Q rezagado"))
```

En ambos modelos el coeficiente $\beta$ estimado es mayor a 0. Mientras más alta es la Q, mayor la inversión efectiva. Nótese que este resultado es consistente con la condición de optimalidad de la firma: $1+C'(I(t))=q(t)$.

## f)
**Produzca un estimado del coeficiente del costo de ajuste a partir de las regresiones anteriores.**

Bajo el supuesto que los modelos del inciso anterior son significativos, el stock de capital de la firma CEMEX tiene una relación directa con la Q. Introduciendo una función de costos de ajuste cuadrática, siguiendo la propuesta de Summers:

$$
C(I(t),K(t))=\frac{1}{2}a\Bigl[\frac{I(t)}{K(t)}\Bigr]^{2}K(t), \ a>0
$$
Tomando la primera derivada:

$$
C'(I(t))=aI(t)
$$
Entonces $\hat{a}=\frac{1}{\hat{\beta}}$

\begin{table}[H]
\centering
\begin{tabular}{@{}ccc@{}}
\toprule
     & Modelo 1    & Modelo 2      \\ \midrule
$\hat{\beta}$ & 0.152 & 0.210   \\
$a$           & 6.579 & 4.762   \\ \bottomrule
\end{tabular}
\end{table}

Los valores de $a$ estimados indican un proceso gradual y coherente de convergencia del capital al estado estacionario. Esto se debe a que el coeficiente $\beta$ estimado no es demasiado pequeño, como para que la convergencia sea lenta ante perturbaciones.

## g)
**Explique, suponiendo que la función de costo de ajuste es cuadrática (es decir $C_{t}=b(I_t/K_t)^2K_{t}$), qué implican los resultados de sus regresiones sobre el costo de ajuste relativo al capital total para una inversión de 50\% del capital total y qué implican los resultados para el tiempo que le tomaría a una empresa recorrer la mitad mitad del camino entre el capital que tiene, $K$, y el que quisiera tener $K^{*}$.**

Con esta forma funcional, se tendrá un costo marginal de ajuste de la forma:

$$
C'(t)=2b\frac{I(t)}{K(t)}
$$
Por lo que la expresión $1+C'(I_{t})=q_{t}$ se puede expresar como:

$$
1+2b\frac{I(t)}{K(t)}=q_{t}
$$
Reordenando:

$$
\frac{I(t)}{K(t)}=\frac{1}{2b}(q(t)-1)
$$
Sea $\frac{I_{t}}{K_{t}}=i_{t}$ como la tasa de inversión usada en el ejercicio y $\beta=\frac{1}{b}$, se puede reexpresar el coeficiente de costo de ajuste como $b=\frac{1}{2}a$, entonces:

\begin{table}[H]
\centering
\begin{tabular}{@{}ccc@{}}
\toprule
     & Modelo 1    & Modelo 2      \\ \midrule
$b$           & 3.290  &  2.381    \\ \bottomrule
\end{tabular}
\end{table}

Sea $K$ es el monto del capital y se tiene una inversión del 50% del capital total, entonces los costos de ajuste vienen dados por:

\begin{table}[H]
\centering
\begin{tabular}{@{}ccc@{}}
\toprule
     & Modelo 1    & Modelo 2      \\ \midrule
Costo de ajuste           & 0.822K  &  0.595K    \\ \bottomrule
\end{tabular}
\end{table}

Para Cemex, los costos de ajustes estimados son bajos. El $a$ estimado para los modelos son menores a los encontrados por summers, por lo que la trayectoria de K a K* (el nuevo estado estacionario) tomará mucho menos que 10 años, ante shocks (por ejemplo aumento del precio del capital o un cambio en el impuesto al uso del capital).

## h)
**Simule una relación lineal $Y=a+bX+\epsilon$ y cree tres variables con error de medición $\tilde{X}=X+\epsilon^x$, $\tilde{\tilde{X}}=X-c  \cdot {\epsilon}$ y  $\tilde{Y}=Y+\epsilon^y$. (Es decir, primero invéntese una variable, X, genere una variable $\epsilon$ aleatoria y con esas dos genere una variable Y. Luego genere dos nuevas X's, una afectada aleatoriamente por otro error diferente, $\epsilon^x$, y otra afectada, de manera NEGATIVA, por el mismo error que incluyó en la simulación de la Y original, y tercero, genere una nueva Y que esté afectada por una tercera variable aleatoria $\epsilon^Y$.  Finalmente, estime varias relaciones lineales:  la de la $Y$ original, con la $X$ original, la de $Y$ original, pero contra $\tilde{X}$ y $\tilde{\tilde{X}}$ y la de $\tilde{Y}$ con la $X$ original, explicando como cambia el coeficiente $\hat{b}$ en cada caso, y relacionándo sus hallazgos con el coeficiente $b$ del inciso anterior.**

```{r, include=FALSE}

##Generamos la muestra aleatoria de la variable X. Para este caso, generamos una muestra de distribución normal con una media 1000 y varianza 2.6.: 
rnorm(1000,mean=40,sd=80)
set.seed(1)
x<-rnorm(1000,mean=40,sd=80)
mean(x)
sd(x)
View(x)

## Generaremos a Y como una normal con media 1500 y una varianza 1.5.
y<-50+5*x
View(y)

## Generaremos a ex como una normal estándar
rnorm(100,mean=0,sd=1)
ex<-rnorm(100,mean=0,sd=1)
mean(ex)
sd(ex)

## Generamos a e como una normal estándar:
rnorm(1000,mean=0,sd=1)
e<-rnorm(1000,mean=0,sd=1)
mean(e)
sd(e)

## Generamos a ey como una normal estándar:
rnorm(1000,mean=0,sd=1)
ey<-rnorm(1000,mean=0,sd=1)
mean(ey)
sd(ey)

## Generamos a x orlada, dada por x2=x+ex
x2<-x+ex
plot(x2)
View(x2)

## Generamos a x2, dada por x3=x-c*e, donde c es cualquier constante, que será igual a 5.
x3<-x-5*e
plot(x3)
View(x3)

## Generamos a y1, dada por y1=y+ey
y1<-y+ey
plot(y1)

## Estimamos los modelos: 
## Modelo 1 : Y normal con X normal
yts=ts(y,start=1022,end=2022,frequency=1)
xts=ts(x,start=1022,end=2022,frequency=1)
regresion1<-lm(yts~xts,data=yts)
#Graficamos
plot(y,x,xlab="x",ylab="y")
#Ploteamos la regresió

## Modelo 2: Y normal con X2
x2ts=ts(x2,start=1022,end=2022,frequency=1)
regresion2<-lm(yts~x2ts,data=yts)
#Graficamos
plot(y,x2,xlab="x2",ylab="y")

## Modelo 3: Y normal con X3
x3ts=ts(x3,start=1022,end=2022,frequency=1)
regresion3<-lm(yts~x3ts,data=yts)
#Graficamos
plot(y,x3,xlab="x3",ylab="y")
```

Generamos una muestra aleatoria de la variable X. Para ello, asumimos que X es una variable aleatoria distribuida normal con media $\mu_x$ y varianza $\sigma_x^2$. 

$$
y=a+bx+\epsilon
$$
Por lo que el valor de $Y$ está en función de $X$. De esta forma, $X$ se define como sigue:

$$
X_{i=1}^{1000} \sim N_1(\mu_x,\sigma_x)
$$
donde $\mu_x=40$ y $\sigma_x=80$, y donde $X_i$ toma valores de $i\in(1,1000)$, es decir, generamos una muestra de 1,000 observaciones.

En la siguiente tabla se muestran 10 valores aleatorios de la variable aleatoria $X_i$. 

| **Observación**  	| **X** 	|
|---	|---	|
| **1** 	| 45.99 	|
| **2** 	| 76.01 	|
| **3** 	| 27.15 	|
| **4** 	| 107.73 	|
| **5** 	| 38.04 	|
| **6** 	| 72.72 	|
| **7** 	| 28.36 	|
| **8** 	| 85.44 	|
| **9** 	| 29.09 	|
| **10** 	| 44.37 	|

Table: Observaciones aleatorias para X

Dando valores fijos a los parámetros, $Y_i$ viene dada por la siguiente ecuación: 
$$
Y_i=50+5*X_i
$$
En la siguiente tabla se muestran las primeras 10 observaciones de las 1000 generadas para $Y_i$:

| **Observación**  	| **Y** 	|
|---	|---	|
| **1** 	| 240.28 	|
| **2** 	| 307.33 	|
| **3** 	| 38.10 	|
| **4** 	| 385.05 	|
| **5** 	| 293.87 	|
| **6** 	| 854.71 	|
| **7** 	| 253.83 	|
| **8** 	| 184.72 	|
| **9** 	| 536.27 	|
| **10** 	| 523.96 	|

Table: Observaciones aleatorias para Y

Ahora, generamos las siguientes variables definidas como siguen:
$$
\tilde{X}=X+\epsilon_x
$$
Y, 
$$
\tilde{\tilde{X}}=X-C\epsilon
$$
donde $C\in(\mathcal{R})$, es decir, como hicimos con los valores para $\hat{a}$ y $\hat{b}$, asignamos un valor aleatorio a la constante $C$. Para este caso, $\tilde{\tilde{X}}$ se determinará¡ para un valor de $C=5$. 

Los valores para $\tilde{X}$ y $\tilde{\tilde{X}}$ están dados en la siguiente tabla:

| **Observación**  	| **X1** 	| **X2** 	|
|---	|---	|---	|
| **1** 	| -30.43 	| 13.27 	|
| **2** 	| 6.014 	| -35.56 	|
| **3** 	| -80.25 	| 3.70 	|
| **4** 	| -16.42 	| -85.82 	|
| **5** 	| 14.62 	| -15.41 	|
| **6** 	| 47.88 	| 58.92 	|
| **7** 	| 47.88 	| 118.73 	|
| **8** 	| 125.13 	| 80.59 	|
| **9** 	| 80.00 	| -17.11 	|
| **10** 	| -13.95 	| 4.36 	|

Table: Observaciones aleatorias para $\tilde{X}$ y $\tilde{\tilde{X}}$. 

Nótese que las variables $\epsilon_x$, $\epsilon_y$ y $\epsilon$ son variables aleatorias con distribución normal estándar, es decir, $\mu_{\epsilon_x}=\mu_{\epsilon_y}=\mu_{\epsilon}=0$, mientras que la varianza, $\sigma_{\epsilon_x}=\sigma_{\epsilon_y}=\sigma_{\epsilon}=1$. 

Se proponen los siguientes modelos de regresión: 
$$
a) Y=\hat{a}+\hat{b}X+\epsilon
$$
$$
b) Y=\hat{a}+\hat{b}\tilde{X}+\epsilon
$$
y, 
$$
c)Y=\hat{a}+\hat{b}\tilde{\tilde{X}}+\epsilon
$$
Los resultados para los modelos se muestran en el Cuadro 10:

```{r, results='asis', echo =FALSE}
##Generamos los cuadros de resultados
stargazer(regresion1, regresion2,regresion3, header=FALSE,title="Comparación de modelos",omit.stat="f")
```

Las variaciones entre los modelos son pequeñas pero se cumple que al introducir errores aleatorios, el modelo pierde poder de explicación. Esto se debe, presuntamente a errores de medición, tal como Summers criticó a los modelos de determinación de $q$. Asimismo, se presume simultaneidad, también criticada por el autor, que causaría que el residuo y la variable explicativa estén correlacionados, ociasionando sesgo en el estimador

## i)
**Estime los coeficientes de una relación lineal entre la tasa de inversión en un periodo, la $q$ de Tobin en el mismo o en el periodo inmediato anterior, y el flujo de efectivo o las ganancias netas. Interprete los resultados contrastándolos con los resultados que obtuvo anteriormente.**

Agregamos la variable ganancias netas para verificar cómo cambia el coeficiente de la q de Tobin y analizar si al introducir esta variable como otra determinante, se captura otros efectos sobre la inversión.


```{r}
tres_i <- read_xlsx("ej3_cemex.xlsx")

modelo_3 <- lm(tres_i$inversion ~ tres_i$Q)
modelo_4 <- lm(tres_i$inversion ~ tres_i$Q+tres_i$g_ganancias_netas)
```                                                             

```{r results='asis',echo=F}
stargazer(modelo_3, modelo_4, header=FALSE, type='latex',title="Modelo de inversión con ganancias netas",dep.var.labels = "Inversión",column.labels = c("Sin ganancias netas", "Con ganancias netas"))
```
Se puede observar que la Inversión de Cemex es ligeramente sensible al crecimiento de las ganancias netas. Es decir una fuente de financiamiento y determinante de la inversión de la empresa es las ganancias netas del ejercicio. El coeficiente de determinación del nuevo modelo es más grande (mayor bondad de ajuste), aunque el nuevo coeficiente de ganancias netas es poco significativo. Sin embargo, podrían también afectar otras variables al modelo.

\pagebreak

# Ejercicio 4
**Proponga una mejora al archivo Diccionario de Economía utilizando github.**


Se sugieren los siguientes conceptos:

\begin{itemize}
    \item Inflationary Spiral: Es un fenómeno económico consistente en un incremento de precios y salarios. Se produce si a un aumento inicial de los salarios en la economía le sigue un aumento en el nivel de los precios, que a su vez va seguido de un aumento en los salarios y así sucesivamente. También puede comenzar con un aumento inicial en el nivel de precios. 
    \item Efficiency-wage: Salario que paga la empresa y que corresponde al nivel de salario de reserva más alto del empleado. El objetivo es que el salario funcione como un incentivo que aumente el esfuerzo del trabajador.
    \item Hysteresis: Caso extremo en el que un choque adverso a la demanda de trabajo que ocurre una sola vez, genera una caída persistente en el nivel de empleo y cuyos efectos son permanentes. 
    \item Real Interest Rate: Es la tasa de interés que está corregida dado que toma en cuenta los niveles de inflación. Es la tasa de interés nominal menos la tasa de inflación. Mide el poder adquisitivo porque representa cuantos bienes se obtienen en el futuro por los que no se consumen en este momento.
\end{itemize}
