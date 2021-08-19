# Formelsammlung für IKT Prüfung



### 1. Diskrete Informationsquellen



mittlerer Informationsgehalt: $H_{m} = \sum_{i} p(x_{i}) \cdot \log_{2}{\frac{1}{p(x_{i})}} = \frac{bit}{Zustand}$ 

Informationsgehalt bei gleichwahrscheinlichen N Zuständen: $H_{0} = \lceil log_{2}{N} \rceil = \frac{bit}{Zustand}$

Unbestimmtheit eines Ereignisses : $H_{i} = log_{2}{\frac{1}{p(x_{i})}} = \frac{bit}{Ereignis}$

Einsparung durch bessere Kodierung: $(1- \frac {l_m}{l}) \cdot 100$



Markov-Kette: 

- $p(y_{j}) = \sum p(x_{i}) \cdot p(y_{j}|x_{i})$​

- $p(x_i) = \sum p(y_j) \cdot p(x_i|y_j)$



Einzelwahrscheinlichkeiten: 	$p(x_i) = \sum_{j=1}^{M} p(x_i,y_j) =>$ Summe einer Zeile 	, 	

​													$p(y_j) = \sum_{i=1}^{N} p(x_i, y_j) => $ Summe einer Spalte 



Übergangswahrscheinlichkeiten: 	

​									$p(y_{j}|x_{i}) = \begin{pmatrix} p(y_{0}|x_0) & p(y_{1}|x_0) & ... & p(y_{N}|x_0)  \\ p(y_{0}|x_1) & p(y_{1}|x_1) & ... & p(y_{N}|x_1) \\ ... & ... & ... &... \\ p(y_{0}|x_N) & p(y_{1}|x_N) & ... & p(y_{N}|x_N) \end{pmatrix}$ 

​									$p(x_{i}|y_{j}) = \begin{pmatrix} p(x_0|y_0) & p(x_0|y_1) & ... & p(x_0|y_{M-1}) \\ p(x_1|y_0) & p(x_1|y_1) & ... & p(x_1|y_{M-1})) \\ ... & ... & ... &... \\ p(x_{N-1}|y_0) & p(x_{N-1}|y_1) & ... & p(x_{N-1}|y_{M-1}) \end{pmatrix}$ 

Verbundwahrscheinlichkeiten									

​									$p(x_{i},y_{j}) = \begin{pmatrix} p(x_{0},y_0) & p(x_0, y_1) & ... & p(x_0,y_M) \\ p(x_1,y_0) & p(x_1,y_1) & ... & p(x_1,y_M) \\ ... & ... & ... &... \\ p(x_N,y_0) & p(x_N,y_1) & ... & p(x_N,y_M) \end{pmatrix}$

​	

bedingte Wahrscheinlichkeit: $ p(x_{i},y_{j}) = p(x_i) \cdot p(y_{j}|x_{i}) = p(y_j) \cdot p(x_{i}|y_{j})$ 	

$p(y_{j}|x_{i}) = \frac {p(x_{i},y_{j})} {p(x_i)}$

$p(x_{i}|y_{j}) = \frac {p(x_{i},y_{j})} {p(y_j)}$



stationäre Zustände einer binären Quelle: 

​	$ \bar p_{1} = \frac {p(x_1|x_2)}{p(x_2|x_1) + p(x_1|x_2)}$  

​	$ \bar p_{2} = \frac {p(x_2|x_1)}{p(x_2|x_1) + p(x_1|x_2)}$



Markov-Entropie:	$ H_m = \sum_j \sum_i \bar p(x_i) * p(x_j,x_i) * \log_{2}{\frac{1}{p(x_j,x_i)}}$ 	(es kann $\bar p(x_i)$ aus der Gleichung immer ausgeklammert werden)

​	$=>$ zweistufiger Prozess: $H_m = \sum_{i=1}^{N} p_i \cdot (log_2 \frac{1}{p_i} + log_2 M)$ (M - Anzahl der Unterelemente in der 2ten Stufe)



Entropien: 

​		$H(X) = \sum_{i=1}^N p(x_i) \cdot log_2 \frac{1}{p(x_i)} \frac {bit}{KZ}$	,	

​		$H(Y) = \sum_{j=1}^{M} p(y_j) \cdot log_2 \frac {1}{p(y_j)} \frac {bit}{KZ}$	,

​		$H(Y|X) = \sum_i p(x_i) \cdot ( \sum_j p(y_j|x_i) \cdot log_2 \frac{1}{p(y_j|x_i)}) \frac {bit}{KZ}$

​		$H(X|Y) = \sum_j p(y_j) \cdot \sum_i p(x_i|y_j) \cdot log_2 \frac{1}{p(x_i|y_j)}$

Verbundsentropie: $H(X,Y) = H(X) + H(Y|X)$

​	vollständige Abhängigkeit: 		$H(X,Y) = H(Y)$

​	vollständig Unabhängigkeit: 	$H(X,Y) = H(X) * H(Y)$ oder $H(Y|X) = H(Y)$



Koderedundanz: $R_k = l_m \cdot H_k - H_m $ 	($H_k$ wird im Normalfall mit 1 angenommen)

mittlere Kodewortlänge: $l_m = \sum p_i \cdot l_i$ (ungleichmäßiger Kode)	,	$l = \lceil \log_2 N \rceil$ (gleichmäßiger Kode)

Kraft-Ungleichung: $\sum_{i=1}^{N} 2^{-l_i} \leq 1$ (notwendige aber nicht hinreichende Bedingung)

Schranken der Minimierung: $ H_m \leq l_m \lt H_m + 1$	--> mit Erweiterung: $ m \cdot H_m \leqslant m \cdot  l_m \lt m \cdot H_m + 1$



<h3>
    2.Übertragungskanal
</h3>
Transinformation: $ H_T = H(X) - H(X|Y) = H(Y) - H(Y|X)$

symmetrisch gestörter Binärkanal ($p_s = \delta = \epsilon$): 

​		$H_T = H(Y) + (1-p_s) \cdot \log_2 (1-p_s) + p_s \cdot \log_2 p_s$

​		$p(y_0) = (1-\epsilon) \cdot p(x_0) + \delta \cdot p(x_1)$

​		$p(y_1) = \epsilon \cdot p(x_0) + (1-\delta) \cdot p(x_1)$

Zeichenwahrscheinlichkeiten (allgmein): 

$p(y_0) = p(x_0) \cdot p(y_0|x_0) + p(x_1) \cdot p(y_0|x_1) ... \\ p(y_1) = p(x_0) \cdot p(y_1|x_0) + p(x_1) \cdot p(y_1|x_1) ...$



allgemeine Übertragung (siehe Übertragungskanal.png):

- Quelleninformationsfluss : $I_Q = f_Q \cdot H_Q \frac{bit}{s}$
- Anzahl der Kanalzeichen : $l \geq \lceil \frac{H_0}{H_K} \rceil $
- Quellenkodeinformationsfluss : $I_{KQ} = f_Q \cdot l \cdot H_K$ => Bedingung: $I_{KQ} \geq I_Q$

- Kanalinformationsfluss: $I_K = v_ü = v_s \cdot H_K \frac{bit}{s}$
- Transinformationsfluss: $I_T = v_s \cdot H_T$
- Kanalkapazität (maximalwert des Trnasinformationsflusses): $C = max\{I_T\} = max \{v_s \cdot H_T \}$ mit der Nebenbedingung: 
  - $v_{smax} = 2 B $
  - $I_{KQ} \leq C$​ 
- Kapazitätsauslastung: $A = \frac{I_T}{C} \cdot 100\% = \frac{v_s \cdot H_T}{2B \cdot H_T} \cdot 100\% = \frac{v_s}{2B} \cdot 100\%$​



ungesicherte Übertragung (alles von der allgemeinen Übertragung mit den ein paar Änderungen):

-  Kanalinformationsfluss: $I_K = I_{KQ}$
- Schrittgeschwindigkeit: $v_s = \frac{I_{KQ}}{H_K} = f_q \cdot l$

- Transinformationsfluss Bedingung: $I_T \lt I_{KQ}$



gesicherte Übertragung (alles von der allgemeinen Übertragung mit den zusätzlichen Berechnungen):

- Länge der Kodewörter mit Redundanz: $n = l + \Delta l = l + (\frac{H_K}{H_T} - 1) \cdot l$
-  Kanalinformationsfluss: $I_K = I_{KK} = f_Q \cdot n \cdot H_K$

- $I_{KK} = f_Q \cdot n \cdot H_K$ mit der Bedingung: $I_{KK} \gt I_{KQ}$
- Schrittgeschwindigkeit: $v_s = f_q \cdot l \cdot \frac{H_K}{H_T} =  f_q \cdot n$
- Transinformationsfluss Bedingung: $I_T = I_{KQ}$



### Kanalkodierung

Grad Fehlererkennung: $d_{min} = f_e + 1 \rightarrow$ Korrektur: $f_e = \lfloor \frac{d_{min}}{2} \rfloor$

verfälschte Stellen: $d_{min} = 2 \cdot f_k + 1 \rightarrow$ Korrektur: $f_k = \lfloor \frac{d_{min}-1}{2} \rfloor$

Bündelungsfehler = $f_b \leq k$

Schranken: 

- $f_k = 1 \to 2^k \geq 1 + n$
- $f_k = 2 \to 2^k \geq 1 + n + \frac{n \cdot (n-1)}{2}$
- $k \geq log_2 \sum_0^{f_k} {n \choose i}$

Generatormatrix: $G_{l \times n} = [I_lC]$​ 

- Anfang bildet die Einheitsmatrix
- jede Zeile beinhaltet ein Codewort
- mittels der Matrix kann ein Codewort codiert werden

Kontrollmatrix: $H_{k \times n} = [C^T I_K]$

- Transponierung der Codewört + auffüllen mit der Einheitsmatrix
- Ziel: Testen ob ein Fehler bei Übertragen aufgetreten ist $\to$ wenn s gleich 0 dann ist er nicht erkennbar oder nicht da 

Orthogonalitätsbedingung: $G \cdot H^T = (H \cdot G^T)^T = 0$

Anzahl Stellen: $n = l + k$

zyklischer Hammingcode Parameter: $(2^{k_1}-1, 2^{k_1}-1-k_1, d_{min}=3)$

