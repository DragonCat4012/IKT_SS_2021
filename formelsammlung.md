# Formelsammlung für IKT Prüfung



### 1. Diskrete Informationsquellen



mittlerer Informationsgehalt: $H_{m} = \sum_{i} p(x_{i}) \cdot \log_{2}{\frac{1}{p(x_{i})}} = \frac{bit}{Zustand}$ 

Informationsgehalt bei gleichwahrscheinlichen N Zuständen: $H_{0} = \lceil log_{2}{N} \rceil = \frac{bit}{Zustand}$

Unbestimmtheit eines Ereignisses : $H_{i} = log_{2}{\frac{1}{p(x_{i})}} = \frac{bit}{Ereignis}$

Einsparung durch bessere Kodierung: $(1- \frac {l_m}{l}) \cdot 100$



Markov-Kette: $p(x_{j}) = \sum p(x_{i}) \cdot p(x_{j},x_{i})$

Einzelwahrscheinlichkeiten: 	$p(x_i) = \sum_{j=1}^{M} p(x_i,y_j) =>$ Summe einer Zeile 	, 	

​													$p(y_j) = \sum_{i=1}^{N} p(x_i, y_j) => $ Summe einer Spalte 



allgmeine Matrix: 	$p(y_{j}|x_{i}) = \begin{pmatrix} p(y_{1}|x_1) & p(y_{2}|x_1) & ... & p(y_{N}|x_1)  \\ p(y_{1}|x_2) & p(y_{2}|x_2) & ... & p(y_{N}|x_2) \\ ... & ... & ... &... \\ p(y_{1}|x_N) & p(y_{2}|x_N) & ... & p(y_{N}|x_N) \end{pmatrix}$ 

​									$p(x_{i},y_{j}) = \begin{pmatrix} p(x_{1},y_1) & p(x_1, y_2) & ... & p(x_1,y_M) \\ p(x_2,y_1) & p(x_2,y_2) & ... & p(x_2,y_M) \\ ... & ... & ... &... \\ p(x_N,y_1) & p(x_N,y_2) & ... & p(x_N,y_M) \end{pmatrix}$

​	

bedingte Wahrscheinlichkeit: $ p(x_{i},y_{j}) = p(x_i) \cdot p(y_{j}|x_{i})$ 	=>	$p(y_{j}|x_{i}) = \frac {p(x_{i},y_{j})} {p(x_i)}$

stationäre Zustände einer binären Quelle: 

​	$ \bar p_{1} = \frac {p(x_1|x_2)}{p(x_2|x_1) + p(x_1|x_2)}$  

​	$ \bar p_{2} = \frac {p(x_2|x_1)}{p(x_2|x_1) + p(x_1|x_2)}$



Markov-Entropie:	$ H_m = \sum_j \sum_i \bar p(x_i) * p(x_j,x_i) * \log_{2}{\frac{1}{p(x_j,x_i)}}$ 	(es kann $\bar p(x_i)$ aus der Gleichung immer ausgeklammert werden)

​	$=>$ zweistufiger Prozess: $H_m = \sum_{i=1}^{N} p_i \cdot (log_2 \frac{1}{p_i} + log_2 M)$ (M - Anzahl der Unterelemente in der 2ten Stufe)



Entropien: 

​		$H(X) = \sum_{i=1}^N p(x_i) \cdot log_2 \frac{1}{p(x_i)} \frac {bit}{KZ}$	,	

​		$H(Y) = \sum_{j=1}^{M} p(y_j) \cdot log_2 \frac {1}{p(y_j)} \frac {bit}{KZ}$	,

​		$H(Y|X) = \sum p(x_i) \cdot ( \sum p(y_j|x_i) \cdot log_2 \frac{1}{p(y_j|x_i)}) \frac {bit}{KZ}$

Verbundsentropie: $H(X,Y) = H(X) + H(Y|X)$

​	vollständige Abhängigkeit: 		$H(X,Y) = H(Y)$

​	vollständig Unabhängigkeit: 	$H(X,Y) = H(X) * H(Y)$ oder $H(Y|X) = H(Y)$



Koderedundanz: $R_k = l_m \cdot H_k - H_m $ 	($H_k$ wird im Normalfall mit 1 angenommen)

mittlere Kodewortlänge: $l_m = \sum p_i \cdot l_i$ (ungleichmäßiger Kode)	,	$l = \lceil \log_2 N \rceil$ (gleichmäßiger Kode)

Kraft-Ungleichung: $\sum_{i=1}^{N} 2^{-l_i} \leqslant 1$ (notwendige aber nicht hinreichende Bedingung)

Schranken der Minimierung: $ H_m \leqslant l_m \lt H_m + 1$	--> mit Erweiterung: $ m \cdot H_m \leqslant m \cdot  l_m \lt m \cdot H_m + 1$



<h3>
    2.Übertragungskanal
</h3>
