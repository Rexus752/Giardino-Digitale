# Programma d'esame

Il programma fa riferimento al libro di testo “Analisi Matematica – Fare e comprendere” di Dambrosio (Zanichelli Editore). L’elenco delle dimostrazioni da studiare è riportato al fondo.

## Funzioni e modelli (Capitolo 1)

- Funzioni e grafici (Paragrafo 1): tutto
- Grafici e funzioni elementari (Paragrafo 2): tutto, tranne funzione parte intera (2.2.4)
- Nuove funzioni da funzioni assegnate (Paragrafo 3): tutto

## Introduzione al calcolo differenziale (Capitolo 2)

- Derivata di una funzione in un punto (Paragrafo 1): tutto
- La funzione derivata e le primitive di una funzione (Paragrafo 2): tutto
- Dal calcolo approssimato al calcolo esatto (Paragrafo 3): tutto

## Introduzione al calcolo integrale (Capitolo 3)

- Integrale definito (Paragrafo 1): tutto
- Integrale definito e area (Paragrafo 2): tutto
- Introduzione al Teorema fondamentale del calcolo integrale (Paragrafo 3): tutto

## Il concetto di limite (Capitolo 4)

- Limite di una funzione in un punto (Paragrafo 1): tutto
- Funzioni continue (Paragrafo 2): tutto
- Limite di una funzione all’infinito (Paragrafo 3): tutto
- Alcuni teoremi sui limiti (Paragrafo 4): tutto

## Calcolo differenziale (Capitolo 5)

- Derivate di una funzione (Paragrafo 1): tutto
- Il Teorema di Lagrange e le sue conseguenze (Paragrafo 2): tutto
- Approssimazione locale di funzioni (Paragrafo 3): tutto tranne la Definizione 5.3.6 ed il Teorema 5.3.9

## Calcolo integrale (Capitolo 6)

- Integrale definito e sue proprietà (Paragrafo 1): tutto
- Calcolo approssimato di un integrale definito e stima dell’errore (Paragrafo 2): tutto
- Dal calcolo approssimato al calcolo esatto: il Teorema fondamentale del calcolo integrale (Paragrafo 3): tutto
- Integrali impropri di funzioni positive (Paragrafo 5): tutto

## Successioni (Capitolo 7)

- Definizioni e risultati teorici (Paragrafo 1): tutto
- La successione geometrica (Paragrafo 2): tutto
- Confronti di crescita (Paragrafo 3): tutto
- Successioni definite per ricorrenza: si vedano gli estratti da Bramanti-Pagani-Salsa disponibili su Moodle. In particolare:
	- Generalità sulle equazioni alle differenze (Paragrafo 2).
	- Equazioni lineari del primo ordine a coefficienti costanti (Paragrafo 3): equazioni omogenee ed equazioni complete; soluzione generale dell’equazione omogenea e dell’equazione completa.
	- Equazioni autonome non lineari (Paragrafo 4): orbite, diagrammi a gradino e punti fissi (Paragrafo 4.1). Punti fissi e stabilità (Paragrafo 4.2 – Definizione 7.1 ed Esempio 4.2); stabilità per linearizzazione (Paragrafo 4.3 – Teorema 7.1).
	- Complessità dell’algoritmo di Merge-Sort (appunti docente)

## Risoluzione approssimata di equazioni (Capitolo 8)

- Il metodo di bisezione ed il Teorema di esistenza degli zeri (Paragrafo 1): tutto
- Il metodo di Newton (Paragrafo 2): tutto tranne il paragrafo 2.1 (il metodo di Newton e i frattali)

## Serie (Capitolo 9)

- La serie geometrica (Paragrafo 1): tutto
- La serie armonica (Paragrafo 2): tutto
- Definizioni e risultati generali (Paragrafo 4): tutto
- Serie a termini di segno positivo (Paragrafo 5): tutto

## Elenco delle dimostrazioni in programma
- Teorema della permanenza del segno: Teorema 4.4.1
- Teorema del confronto: Teorema 4.4.3
- Continuità delle funzioni derivabili: Proposizione 5.1.1
- Caratterizzazione delle funzioni a derivata nulla su un intervallo: Teorema 5.2.2
- Caratterizzazione delle funzioni a derivata seconda nulla su un intervallo: Teorema 5.2.3
- Caratterizzazione delle primitive della stessa funzione: Teorema 5.2.4
- Test di monotonia: Teorema 5.2.5
- Concavità e convessità di una funzione e monotonia della sua derivata prima: Teorema 5.2.6
- Successioni definite per ricorrenza: se una successione è convergente il limite è un punto fisso della funzione (dimostrazione non presente sul libro; studiare la dimostrazione sugli appunti delle lezioni)
- Teorema di esistenza degli zeri: Proposizione 8.1.1 e Teorema 8.1.1
- Teorema di convergenza del metodo di Newton: Teorema 8.2.2
- Condizione necessaria di convergenza di una serie: Proposizione 9.4.5
- Teorema della Media Integrale: Teorema 6.1.3 (dimostrazione non presente sul libro; studiare la dimostrazione sugli appunti delle lezioni)
- Teorema di Torricelli-Barrow: Teorema 6.3.6 (la dimostrazione presente sul libro è diversa da quella vista a lezione; studiare la dimostrazione sugli appunti!)
- Teorema Fondamentale del Calcolo Integrale: Teorema 6.3.5
- Criterio del confronto integrale per la convergenza di una serie: Proposizione 9.5.9

# Funzioni e modelli (Capitolo 1)

## Funzione lineare

$f \colon \mathbb{R} \to \mathbb{R}$ con $f(x) = mx + q, \quad m,q \in \mathbb{R}$

### Esempio: $f(x)= x + 1$ (cioè $m = 1, q = 1$)

| $x$  | $y = f(x)$ |
| ---- | ---------- |
| $-1$ | $0$        |
| $0$  | $1$        |
| $1$  | $2$        |
| $2$  | $3$        |

Grafico:
![](f(x)%20=%20x%20+%201.png)

## Grafico

$$
\begin{align*}
grafico(f)
&= \{(x,y) \in \mathbb{R} \mid y = f(x)\} \\
&= \{(x,y) \in \mathbb{R} \mid y = x + 1\}
\end{align*}
$$

Il grafico di una funzione lineare $f(x) = mx + q$ è sempre una retta nel piano

### Nota

$q$ è l'ordinata ("la $y$") del punto in cui la retta interseca l'asse $y$ ($f(0) = m \cdot 0 + q = q$)

### Nota

Per una funzione lineare $f(x) = mx + q$:
- $q = 0 \implies$ la retta passa per l'origine
- $m = 0 \implies f(x) = q \quad \forall x \in \mathbb{R}$
	![200](m%20=%200.png)
- $m \ne 0$: la funzione incrocia gli assi nei due punti $(0,q)$ e $\left(- \frac{q}{m}, 0\right)$, cioè
	- $f(0)=q$
	- $f\left(- \frac{q}{m}\right) = 0$ perché $f\left(- \frac{q}{m}\right) = m\left(- \frac{q}{m}\right) + q = 0$
	![](m%20ne%200.png)
	%% grafico sbagliato: è $- \frac{q}{m}$ e non $- \frac{m}{q}$ %%

### Esempio: $q = 0$

![](q%20=%200.png)

# Incremento e quoziente di Newton

Siano $P_1(x_1, y_1), P_2(x_2, y_2)$ due punti in $\mathbb{R}^2$ con $x_1 \ne x_2$:
- $\Delta x = x_2 - x_1$ è detta _incremento_ oppure _variazione_ della $x$
- $\Delta f = f(x_2) - f(x_1) = y_2 - y_1$ è detta _incremento_ oppure _variazione_ di $f$ nel passaggio da $x_1$ a $x_2$
- $\frac{\Delta f}{\Delta x} = \frac{f(x_2) - f(x_1)}{x_2 - x_1}$ è detto _quoziente di Newton_ di $f$ tra $x_1$ e $x_2$ (oppure _tasso medio di variazione_ di $f$ nel passaggio da $x_1$ a $x_2$)

## Esempio: $f(x) = {\color{red}3}x + 2, x_1 = 0, x_2 = 2$

$$
\Delta x = x_2 - x_1 = 2 - 0 = 2
$$
$$
\Delta f = f(x_2) - f(x_1) = f(2) - f(0) = 8 - 2 = 6
$$
$$
\frac{\Delta f}{\Delta x} = \frac{6}{2} = {\color{red}3}
$$

Da questo esempio possiamo notare in rosso che $\frac{\Delta f}{\Delta x} = m$ e da qui parte il prossimo teorema

# Proposizione: $\frac{\Delta f}{\Delta x} = m$

Sia $f(x) = mx + q$, allora $\frac{\Delta f}{\Delta x} = m$ per ogni $x_1, x_2$ con $x_1 \ne x_2$.

## Dimostrazione

$$
\displaylines{
\begin{align*}
\frac{\Delta f}{\Delta x}
&= \frac{f(x_2) - f(x_1)}{x_2 - x_1} \\
&= \frac{(mx_2 + q) - (mx_1 + q)}{x_2 - x_1} \\
&= \frac{mx_2 - mx_1 \cancel{+ q} \cancel{- q}}{x_2 - x_1} \\
&= \frac{m\cancel{(x_2 - x_1)}}{\cancel{x_2 - x_1}} \\
&= m
\end{align*} \\
\blacksquare
}
$$

# Definizione: pendenza

Si dice _pendenza_ di una funzione lineare $f(x) = mx + q$ il suo tasso di variazione medio $m$.

## Nota

$m$ si dice anche:
- _coefficiente di proporzionalità_ tra la variazione di $f$ e quella di $x$:
$$
\frac{\Delta f}{\Delta x} = m \implies \Delta f = m \cdot \Delta x
$$
- _coefficiente angolare_ della retta:
	![](Coefficiente%20angolare.png)
	$\tan \alpha = \frac{\Delta f}{\Delta x} = m$
	$\alpha = \arctan m$

## Pendenza di una funzione qualsiasi

![](Pendenza%20di%20una%20funzione%20qualsiasi.png)

$$
\frac{\Delta f}{\Delta x} = \frac{f(x_2) - f(x_1)}{x_2 - x_1}
$$
è il tasso medio di variazione di $f$ nel passaggio da $x_1$ a $x_2$.
Coincide con la pendenza della retta che passa per $(x_1, f(x_1))$ e $(x_2, f(x_2))$.

## Ragionamento: pendenza in un punto

In generale, la pendenza varia da punto a punto. Cerchiamo di definire la pendenza di $f$ in $x_1$.
Consideriamo $x_1$ e $x_2$ e consideriamo la retta passante per $(x_1, f(x_1))$ e $(x_2, f(x_2))$.
La pendenza di questa retta è
$$
\frac{\Delta f}{\Delta x} = \frac{f(x_2) - f(x_1)}{x_2 - x_1} = \frac{f(x_1 + \Delta x) - f(x_1)}{\Delta x}
$$
Tra il penultimo e l'ultimo passaggio va considerato che $x_2 = x_1 + (x_2 - x_1) = x_1 + \Delta x$.

### Idea

Se avviciniamo $x_2$ a $x_1$, cioè se $\Delta x$ si avvicina a $0$, allora la pendenza approssimata $\frac{\Delta f}{\Delta x}$ si avvicinerà sempre di più al valore effettivo della pendenza di $f$ in $x_0$.

## Definizione: pendenza in un punto

La pendenza di $f$ in $x_1$ è la pendenza della retta tangente al grafico di $f$ nel punto $(x_1, f(x_1))$:
$$
p_f(x_1) = \lim_{x_2 \to x_1} \frac{\Delta f}{\Delta x}
$$
oppure
$$
p_f(x_1) = \lim_{\Delta x \to 0} \frac{f(x_1 + \Delta x) - f(x_1)}{\Delta x}
$$
purché tale limite esista finito.

### Esempio: $f(x) = \ln(1 + 2x)$

![](f(x)%20=%20ln(1%20+%202x).png)

Condizioni di esistenza:
$$
1 + 2x > 0 \iff x > - \frac{1}{2}
$$
Vogliamo sapere la pendenza in $(0,0)$.
Vogliamo trovare $p_f(0)$:
$$
\lim_{x_2 \to x_1} \frac{f(x_2) - f(0)}{x_2 - 0} = \lim_{x_2 \to x_1} \frac{\ln(1 + 2x_2)}{x_2} \quad x_2 \ne 0
$$

| $x_2$  | $\frac{\ln(1 + 2x_2)}{x_2}$ |
| ------ | --------------------------- |
| $0,1$  | $1,8232 \ldots$             |
| $0,07$ | $1,8718 \ldots$             |
| $0,04$ | $1,9240 \ldots$             |
| $0,01$ | $1,9803 \ldots$             |
%% Sostituire la virgola con il punto %%

| $x_2$   | $\frac{\ln(1 + 2x_2)}{x_2}$               |
| ------- | ----------------------------------------- |
| $-0,1$  | $2,234 \ldots$ %% 3 cifre anziché 4 qua%% |
| $-0,07$ | $2,1546 \ldots$                           |
| $-0,04$ | $2,0845 \ldots$                           |
| $-0,01$ | $2,0232 \ldots$                           |
e così via

Congettura: $p_f(0) = 2$
![](Pendenza%20nel%20punto%200.png)

Procedimento: tracciare approssimativamente la retta tangente e scegliere due punti sulla retta per i quali si "vedono bene" i valori delle coordinate: $P_1(x_1, y_1), P_2(x_2, y_2)$ %%sistemare anche in RO la differenza tra le notazioni $P=(x,y), P(x,y), P \begin{pmatrix}x & y\end{pmatrix}$ ecc. (usare il primo metodo perché simile alla dichiarazione di vettori $v = (1, 2, 3, 4, 5)$ ecc.)%%, allora $m \approx \frac{y_2 - y_1}{x_2 - x_1}$.

Nell'esempio prendiamo $P_1 = (0,0), P_2 = (1,2)$
![](Zoom%20in.png)
Possiamo notare che il grafico di $f$ "diventa" la retta tangente.

## Definizione: funzione localmente dritta

Una funzione $f$ si dice _localmente dritta_ vicino a un punto $P_1=(x_1,f(x_1))$ se, ingrandendo il grafico di $f$ vicino a $P_1$, vediamo un grafico sempre più simile a una determinata retta. Chiamiamo $p_f(x_1)$ la pendenza di questa retta.

### Trovare l'equazione della retta tangente

Sia $p_f(x_1)$ pendenza di $f$ in $x_1$. La retta tangente passa per $(x_1, f(x_1))$ e ha pendenza $p_f(x_1)$:
$$
y = m x + q = p_f(x_1)x + q
$$
$$
f(x_1) = p_f(x_1)x_1 + q \implies q = f(x_1) - p_f(x_1)x_1
$$
$$
y = p_f(x_1)x + f(x_1) - p_f(x_1)x_1 \implies y = p_f(x_1)(x-x_1) + f(x_1)
$$
L'equazione $y = p_f(x_1)(x-x_1) + f(x_1)$ è l'equazione della retta tangente al grafico di $f$ nel punto $(x_1, f(x_1))$.

### Definizione: retta tangente

Se $f$ ammette pendenza in $x_0$, allora la retta $y = p_f(x_0)(x - x_0) + f(x_0)$ si dice _retta tangente_ al grafico di $f$ in $(x_0, f(x_0))$ (retta tangente a $f$ in $x_0$).
La retta:
- Passa per $(x_0, f(x_0))$;
- Ha pendenza $p_f(x_0)$.

### Osservazione: la pendenza $p_f(x_1)$ NON è sempre definita

$$
f(x) = |x| =
\begin{cases}
x & x \ge 0 \\
-x & x < 0
\end{cases}
$$

Con $x_1 = 0$ abbiamo
$$
\frac{\Delta f}{\Delta x} = \frac{f(x_2) - f(0)}{x_2 - 0} = \frac{|x_2|}{x_2} =
\begin{cases}
1 & x_2 \ge 0 \\
-1 & x_2 < 0
\end{cases}
$$
In questo caso non esiste $\displaystyle\lim_{x_2 \to 0} \frac{\Delta f}{\Delta x}$, quindi non è definita la pendenza $p_f(0)$.

### Esempio: $f(x) = \sqrt[3]{x}$

![](f(x)%20=%20sqrt3(x).png)

In questo caso, se $x_0 = 0$ e $x_1$ si avvicina a $0$, allora $\frac{\Delta f}{\Delta x}$ diventa sempre più grande e non si avvicina a nessun numero reale: il limite non è finito.

### Osservazione

Si può pensare alla retta tangente come a ciò che si ottiene facendo uno zoom vicino al punto in esame.
Zoommando sempre di più, il grafico "tende a essere rettilineo". La retta tangente è la "miglior" approssimazione lineare di $f$ in $x_0$. Non abbiamo info sul numero di intersezioni tra la retta tangente e il grafico di $f$.

### Osservazione

Spesso il grafico di $f$ sta "localmente dalla stessa parte" rispetto alla tangente:
![](Localmente.png)
A volte invece il grafico di $f$ attraversa la tangente:
![](Tangente.png)
Questi punti si dicono _punti di flesso_.

### Esercizio: dato il grafico di $f$, tracciare approssimativamente il grafico di $p_f$

![](Grafico%20pendenza.png)

# Esercizio 1

Calcolare $p_f(x)$ per la funzione $f(x) = x^2$.

Per definizione abbiamo:
$$
p_f(x) = \lim_{\Delta x \to 0} \frac{f(x_1 + \Delta x) - f(x_1)}{\Delta x}
$$
se esiste finito.
$$
\begin{align*}
p_f(x)
&= \lim_{\Delta x \to 0} \frac{f(x + \Delta x) - f(x)}{\Delta x} \\
&= \lim_{\Delta x \to 0} \frac{(x + \Delta x)^2 - x^2}{\Delta x} \\
&= \lim_{\Delta x \to 0} \frac{\cancel{x^2} + 2x\Delta x + (\Delta x)^2 \cancel{- x^2}}{ \Delta x} \\
&= \lim_{\Delta x \to 0} \frac{2x\Delta x + (\Delta x)^2}{\Delta x} \\
&= \lim_{\Delta x \to 0} \frac{\cancel{\Delta x}(2x + \Delta x)}{\cancel{\Delta x}} \\
&= \lim_{\Delta x \to 0} 2x + \Delta x \\
&= 2x
\end{align*}
$$
Quindi otteniamo che $p_f(x) = 2x, \quad\forall x \in \mathbb{R}$.

# Esercizio 2

Data $f(x)$ in figura, disegnare il grafico di $p_f(x)$
(premessa: supponiamo che $f \colon I \subseteq \mathbb{R} \to \mathbb{R}$, con $I \subseteq \mathbb{R}$ dominio e $\mathbb{R}$ codominio, ammetta pendenza $p_f(x) \quad \forall x \in I$. Allora ha senso considerare la funzione pendenza
$$
\begin{align*} p_f \colon I &\to \mathbb{R} \\ x&\mapsto p_f(x) \end{align*}
$$
).
![](Funzione%20pendenza.png)

Per $x < x_1$, abbiamo $p_f(x) > 0$ (la retta tangente "cresce" da sinistra verso destra). Idem per $x > x_3$.
Per $x_1 < x < x_3$, abbiamo $p_f(x) < 0$ (la retta tangente "decresce" da sinistra verso destra).
Si vede inoltre che $p_f(x)$ è più grande per $x \ll x_1$ o $x \gg x_3$. Per $x_1 < x < x_3$, abbiamo che $p_f(x)$ prima decresce, poi arriva in $x_2$ e poi cresce.
L'esercizio suggerisce che:
- $f$ è crescente in $(a,b) \impliedby p_f(x) \ge 0, x \in (a,b)$
- $f$ è decrescente in $(a,b) \impliedby p_f(x) \le 0, x \in (a,b)$
- $f$ è convessa su $(a,b) \impliedby p_f(x)$ è crescente su $(a,b)$
- $f$ è concava su $(a,b) \impliedby p_f(x)$ è decrescente su $(a,b)$

# Interpretazioni alternative

## Interpretazione cinematica

![](Interpretazione%20cinematica.png)

$s = s(t)$ descrive la posizione del punto materiale nel tempo $t$ (espressa in minuti).
![](Grafico%20cinematica.png)

Questo grafico descrive il moto di un punto che parte all'istante $0$ a $2m$ a destra di $0$. Il punto si sposta verso destra per $3$ minuti. Poi inverte la sua direzione e si sposta verso sinistra durante l'intervallo di tempo $[3,10]$.
$$
\frac{\Delta s}{\Delta t} = \frac{s(t_2) - s(t_1)}{t_2 - t_1}
$$
è la velocità media del punto nell'intervallo $[t_1, t_2]$. %%modificare tutte le coppie di variabili 1,2 in 0,1 es. x_0 e x_1 anziché x_1 e x_2%%
$$
\lim_{\Delta t \to 0} \frac{s(t_0 + \Delta t) - s(t_0)}{\Delta t}
$$
è la velocità istantanea del punto in $t_0$.
Quindi $p_s(t_0) = v(t_0)$ (cioè la velocità che si misura in metri/minuti %%usare i secondi al posto dei minuti in tutto il problema%%).
Possiamo anche considerare la funzione velocità istantanea $v(t)$.
$$
\frac{\Delta v}{\Delta t} = \frac{v(t_1) - v(t_0)}{t_1 - t_0}
$$
è l'accelerazione media in $[t_0,t_1]$, mentre
$$
\lim_{\Delta t \to 0} \frac{v(t_0 + \Delta t) - v(t_0)}{\Delta t}
$$
è l'accelerazione istantanea in $t_0$, cioè $a(t_0)$ che si misura in $metri/minuti^2$

## Dinamica delle popolazioni %%demografia (?)%%

La funzione $N(t)$ conta gli individui di una popolazione al variare del tempo (il tempo non ha valori negativi, quindi $t \ge 0$).
Unità di misure: N in milioni (di individui), t in anni
![](Dinamica%20delle%20popolazioni.png)
Abbiamo che
$$
\frac{\Delta N}{\Delta t} = \frac{N(t_1) - N(t_0)}{t_1 - t_0}
$$
è il tasso medio di crescita in $[t_0, t_1]$, mentre
$$
\lim_{\Delta t \to 0} \frac{N(t_0 + \Delta t) - N(t_0)}{\Delta t}
$$
è il tasso di crescita istantaneo in $t_0$.

# Calcolo differenziale

Queste motivazioni hanno portato allo sviluppo del calcolo differenziale.

## Definizione: derivabile

Data una funzione $f\colon(a,b) \to \mathbb{R}$ e un punto $x_0 \in (a,b)$, $f$ si dice _derivabile_ in $x_0$ se esiste ed è finito il limite
$$
\lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}
$$
($h = \Delta x$).

Se $f$ è derivabile, allora tale limite si chiama _derivata_ di $f$ in $x_0$ e si rappresenta con $f'(x_0)$ oppure $\frac{df}{dx}(x_0)$ oppure $\dot f(x_0)$ %%(vedere da wikipedia (dalla pagina dei simboli matematici) se è \dot o \circle, è un pallino sopra la f)%%.

Quindi $f'(x_0) = p_f(x_0)$.
Se $f$ è derivabile in tutti i punti di $(a,b)$, si può definire la funzione derivata (prima) di $f$:
$$
\begin{align*} f' \colon (a,b) &\to \mathbb{R} \\ x&\mapsto f'(x) \end{align*}
$$

### Osservazione

In termini cinematici:
$$
s'(t) = v(t)
$$

### Osservazione

Se è ben definita la funzione derivata, è naturale chiedersi se sia essa stessa derivabile. Se sì, possiamo definire la _derivata seconda_ di $f$ in $x_0$ come
$$
f''(x_0) = (f')'(x_0)
$$
(cioè derivata prima della derivata prima)

Si definiscono derivate di qualsiasi ordine.

## Teorema 1 - Test di monotonia

Il calcolo differenziale permette di avere informazioni sul comportamento di una funzione per esempio, anticipiamo che
$f \colon (a,b) \in \mathbb{R}$ derivabile, allora:
- $f$ crescente in $(a,b) \impliedby f'(x) \ge 0 \quad \forall x \in (a,b)$
- $f$ decrescente in $(a,b) \impliedby f'(x) \le 0 \quad \forall x \in (a,b)$

## Teorema 2 - Test di convessità

$f \colon (a,b) \to \mathbb{R}$ derivabile, allora
- $f$ convessa su $(a,b) \iff f'$ è crescente in $(a,b) \iff f''(x) \ge 0 \quad \forall x \in (a,b)$
- $f$ concava su $(a,b) \iff f'$ è decrescente in $(a,b) \iff f''(x) \le 0 \quad \forall x \in (a,b)$

Le seconde biimplicazioni valgono se $f$ è derivabile almeno 2 volte.

## Osservazione

In termini cinematici:
- $s(t)$ è crescente $\iff v(t) \ge 0$
- $s(t)$ è decrescente $\iff v(t) \le 0$
- $s(t)$ è convessa $\iff v(t)$ è crescente $\iff a(t) \ge 0$

![](Termini%20matematici%20derivata%20seconda.png)

## Esercizio

Dato il seguente grafico di $s(t)$:
![](Grafico%20di%20s(t).png)

1. Descrivere il moto
2. Tracciare un grafico di $v(t)$
3. Determinare un valore approssimato di $v(t)$

### Punto 1

Il punto all'istante $0$ si trova in $0$ con velocità $0$. Si muove verso destra accelerando per $1$ minuto. Poi decelera, avanzando fino a $1,5m$ a destra di $0$ all'istante $2$.
Poi inverte il moto, spostandosi verso sinistra per $2 minuti$, fino ad arrivare a $-1,8m$ ($1,8m$ di distanza da $0$ verso sinistra).
Il punto poi si sposta verso destra per $3$ minuti.

### Punto 2

![](Grafico%20di%20v(t).png)

Gli $0$ della $v$ sono i punti del grafico di $s$ a pendenza $0$.
Test di monotonia:
- $v(t) \ge 0 \quad \forall t \in [0,2]$
- $v(t) \le 0 \quad \forall t \in [2,4]$
- $v(t) \ge 0 \quad \forall t \in [4,7]$
Test di convessità:
- $v(t)$ è crescente in $[0,1]$
- $v(t)$ è decrescente in $[1, 3.4]$
- $v(t)$ è crescente in $[3.4, 7]$
### Punto 3

Per determinare $v(7)$, ricordiamo che $v(7)$ è la pendenza della tangente a $s$ in $t=7$.
$$
v(7) \simeq p_s(7) \simeq \frac{r(6,4) - r(7)}{6,4-7} = \frac{0 - s(7)}{-0,6} = \frac{-2,2}{-0,6} = 3,\overline{6}
$$

## Definizione: primitiva

Data $f \colon (a,b) \to \mathbb{R}$, possiamo determinare $g \colon (a,b) \to \mathbb{R}$ derivabile, tale che $g'(x)=f(x) \quad \forall x \in (a,b)$

Se tale $g$ esiste, la chiamiamo primitiva di $f$

### Esempio

Abbiamo visto che, posto $f(x)=x^2$, abbiamo che $f'(x)=p_f(x)=2x$, quindi $x^2$ è una primitiva di $2x$.

### Osservazione: se una primitiva esiste, non è unica

![](Primitiva%20non%20unica.png)

La pendenza di una qualsiasi parabola $x^2 + c$ con $c \in \mathbb{R}$ è la stessa di $x^2$ SE E SOLO SE $x^2 + c$ è anch'essa una primitiva di $2x$ per ogni $c \in \mathbb{R}$.

### Osservazione

Questo fatto ha una chiara interpretazione cinematica: se vogliamo ricostruire $s(t)$ a partire da $v(t)$ è necessario conoscere $s(t_0)$ per un certo $t_0$, altrimenti ci sono infiniti spazi percorsi in un tempo $t$ a una velocità $v(t)$.

Es. se $t=2s, v(t)=5m/s$, allora ci sono infiniti spazi da $2s \cdot 5 \frac{m}{s} = 10 m$ in cui possiamo essere andati, per esempio da $t_0 = 0m$ a $t_1 = 10m$ o da $t_0=5m$ a $t_1 = 15m$ ecc.

## Teorema

Sia $f \colon (a,b) \to \mathbb{R}$, allora:
1. $g$ è una primitiva di $f$ in $(a,b) \implies g+c$ è una primitiva, $\quad \forall c \in \mathbb{R}$;
2. $g$ e $h$ sono primitive di $f$ in $(a,b) \implies g(x) - h(x) = c \quad \forall x \in [a,b]$ per un certo $c \in \mathbb{R}$.

### Osservazione

Le primitive sono univocamente determinate a meno di costanti additive.

# Integrali

## Definizione: integrale indefinito

Data $f \colon (a,b) \to \mathbb{R}$, l'insieme di tutte le primitive di $f$ si dice _integrale indefinito_ di $f$:
$$
\int f(x)dx = \{\text{primitive di }f\}
$$

### Esempio

$$
\int 2xdx = x^2 + c, \quad \forall c \in \mathbb{R}
$$

### Esercizio

Dato il seguente grafico di $v(t)$:
1. Descrivere (per quanto possibile) il moto;
2. Sapendo che $s(0)=2$, tracciare un grafico di $s(t)$.
%% se questo esercizio non c'entra nulla con integrali, spostare via da qua %%
![](Grafico%20integrali.png)

#### Punto 1

Il punto si muove verso destra per $2s$. Nell'intervallo $[0,1]$ accelera. In $[1,2]$ rallenta. Il punto inverte il moto e si sposta verso sinistra in $[2,3]$.

#### Punto 2

![](s(t).png)

Problema: non conosciamo la posizione finale (o qualsiasi altra posizione) per $s$.
Possiamo solo descrivere monotonia e convessità. Per risolvere questo problema ci sarà utile l'integrale definito.

## Integrale definito

![](Integrale%20definito.png)

Problema: calcolare l'area tra grafico di $f$ e asse $x$. Ricordiamo che l'area di un rettangolo di base $b$ e l'altezza $h$ è $b \cdot h$.
Ragioniamo per approssimazione.
Fissiamo $n \ge 1$. Dividiamo $[a,b]$ in $n$ sottointervalli di ampiezza $\frac{b-a}{n}$ e otteniamo
$$
x_i = a + i\frac{b - a}{n} \quad \forall i \in \{0, \ldots, n\}
$$

Scegliamo un intervallo $z_i \in [x_{i-1}, x_i]$ in modo arbitrario (punti di campionamento).

Definiamo $g \colon [a,b] \to \mathbb{R}$ ponendo
$$
g(x) = f(z_i) \quad \text{se } x \in[x_{i-1}, x_i]
$$
con $g$ che è costante a tratti.
La regione sottesa al grafico di $g$ è un plurirettangolo. La sua area è la somma delle aree dei singoli rettangoli:
$$
\sum_{i=1}^n \frac{b-a}{n} \cdot f(z_i) = \underbrace{S_n(f; z_i, \ldots, x_n)}_{\text{somma di Riemann}}
$$

La somma di Riemann è un valore approssimato dell'area sottesa al grafico di $f$.

### Idea

Se prendo $n$ sempre più grande, otterrò un'approssimazione migliore

### Definizione: integrale definito

Se $\displaystyle\lim_{n \to + \infty} S_n(f; z_i, \ldots, x_n)$ esiste ed è finito e non dipende dalla scelta degli $z_i$ %%perché dovrebbe dipendere? in che casi?%%, diciamo che $f$ è _integrabile_ su $[a,b]$.
Il valore
$$
\displaystyle\lim_{n \to + \infty} S_n(f; z_i, \ldots, x_n)
$$
si dice _integrale definito_ di $f$ in $[a,b]$ e si indica con
$$
\int_a^b f(x)dx
$$
ed è l'area sottesa al grafico di $f$.

### Osservazione

- L'integrale definito è un numero, mentre l'integrale indefinito è un insieme di funzioni. In partenza, si tratta di oggetti completamente diversi.
- $$
\int_a^b f(x)dx = \int_a^b f(t)dt = \int_a^b f(\sigma)d\sigma
$$
%%vedere se è un sigma o che simbolo%%La variabile di integrazione è "muta".
	Per questo a volte
	$$
	\int_a^b f = \int_a^b f(x)dx
$$
- $\int_a^b f$ è un'area con segno:
	- $\int_a^b f = -Area(rossa)$ e $\int_a^b |f| = Area(verde) = Area(rosso)$
		![](Area%201.png)
	- $\int_a^b f = Area(A_1) - Area(A_2) + Area(A_3)$
		![](Pasted%20image%2020240625202125.png)
	
	per avere l'area "senza segno" si considera $\in_a^b |f(x)|dx$ con $\int_a^b |f| = Area(A_1) + Area(A_2) + Area(A_3)$

- Non è difficile ottenere dei valori approssimati per $\int_a^b f$:
$$
\int_a^b f(x)dx \simeq \sum_{i=1}^n f(z_i) \frac{b-a}{n}
$$
se $n$ è "grande".

Una scelta naturale è $z_i = \frac{x_i + x_{i-1}}{2}$, cioè il punto medio tra $[x_{i-1},x_i]$.
$$
\int_a^b f(x)dx \simeq \sum_{i=1}^n f\frac{b-a}{2}
$$
%%perché $f(z_i)$ e non $f$?%%
(formula del punto medio con $n$ suddivisioni)

- L'integrale è usato per calcolare il lavoro di una forza. Precisamente:
	![](Lavoro%20di%20una%20forza.png)
	sull'oggetto agisce una forza parallela allo spostamento e dipendente solo da $s$: $F = F(s) \in \mathbb{R}$.
	La forza può sia favorire lo spostamento (se $F > 0$: forza "motore") che opporsi allo spostamento (se $F < 0$: forza "resistente").
	Se $F$ è costante, allora $L_{F;[a,b]} = F\cdot(b-a)$
	Se $F$ NON è costante, allora $L_{F;[a,b]} = \int_a^b F(s)ds$
- Unità di misura:
$$
\int_a^b F(s)ds = \lim_{n \to + \infty} \sum_{i=1}^n F(z_i) \frac{b-a}{n}
$$
%%Negli appunti c'era scritto $n \to \infty$ è giusto o è corretto $n \to + \infty$?%% 
$F(z_i)$ si misura in Newton, $\frac{b-a}{n}$ in metri: $[N] \cdot [m] = [Joule]$
Se $v$ è una velocità,
$$
\int_a^b v(t)dt = \left[\frac{m}{s}\right]  \cdot [s] = [m]
$$
L'integrale della velocità nel tempo è uno spostamento.
- L'integrale si può anche considerare come un valore medio di una funzione:
	Dati $n$ numeri $y_1, \ldots, y_n$, la loro media è
	$$
	m = \frac{y_1, \ldots, y_n}{n}
$$
Se $f \colon [a,b] \to \mathbb{R}$ è una funzione, si può pensare di definire il suo valor medio prendendo $n$ punti $z_1, \ldots, z_n \in [a,b]$ e calcolando
$$
\frac{f(z_1), \ldots, f(z_n)}{n}
$$
Se $z_1, \ldots, z_n$ sono presi come nella definizione di integrale ($z_i \in [x_{i-1}, x_i] \forall i$), allora
$$
\begin{align*}
\frac{f(z_i) + \ldots + f(z_n)}{n}
&= \sum_{i=1}^n \frac{1}{n}f(z_i) \\
&= \sum_{i=1}^n \frac{1}{b-a} \cdot \frac{b-a}{n} f(z_i) \\
&= \frac{1}{b-a} \sum_{i=1}^n \frac{b-a}{n} f(z_i) \\
&= \frac{1}{b-a} S_n(f; z_i, \ldots, z_n) \underrightarrow{n \to \infty} \\
&= \frac{1}{b-a} \int_a^b f
\end{align*}
$$
(se $f$ è integrabile).
%%$n \to \infty$ o $n \to +\infty$?%% 

## Definizione

$$
\frac{1}{b-a} \int_a^b f(x)dx
$$
 si dice _media integrale_ di $f$ in $[a,b]$

# ?

Avevamo visto che
$$
\int_a^b v(t)dt = \left[\frac{m}{s}\right] \cdot [s] = [m] 
$$
è una lunghezza, ma di quale lunghezza si tratta?
$v(t)$ è la velocità di un punto la cui posizione è descritta da $s(t)$:
$$
s'(t) = v(t)
$$
cioè $s$ è una primitiva di $v$.
$$
\int_a^b v(t)dt = \lim_{n \to \infty} \sum_{i=1}^n v(z_i) \cdot \frac{b-a}{n}
$$
%%$n \to \infty$ o $n \to +\infty$?%%
dove
$$
a = t_0 < t_1 < \ldots < tn = b
$$
sono una suddivisione di $[a,b]$ in $n$ sottointervalli di ampiezza $\frac{b-a}{n}$ e $z_i \in [t_{i-1},t_i]$ sono i punti di campionamento, scelti arbitrariamente.
Se $[t_{i-1}, t_i]$ è "piccolo", cioè se $m$ è "grande", allora
$$
\underbrace{v(z_i)}_{\text{velocità istantanea in }z_i} \simeq \underbrace{\frac{s(t_i) - s(t_{i-1})}{t_i - t_{i-1}}}_{\text{velocità media in} [t_{i-1}, t_i]} = \frac{s(t_i) - s(t_{i-1})}{\frac{b-a}{n}}
$$
Quindi
$$
\begin{align*}
\int_a^b v(t)dt
&= \lim_{n \to \infty} \sum_{i=1}^n v(z_i) \frac{b-a}{n} \\
&\simeq \lim_{n \to \infty} \sum_{i=1}^n \frac{s(t_i) - s(t_{i-1})}{\cancel{\frac{b-a}{n}}} \cdot \cancel{\frac{b-a}{n}} \\
&= \lim_{n \to \infty} \sum_{i=1}^n (s(t_i) - s(t_{i-1})) \\
&= \lim_{n \to \infty}
[
({\color{blue}{\cancel{s(t_1)}}} - s(t_0))
+
({\color{red}{\cancel{s(t_2)}}} - {\color{blue}{\cancel{s(t_1)}}})
+
({\color{green}{\cancel{s(t_3)}}} - {\color{red}{\cancel{s(t_2)}}})
+ \ldots +
(s(t_n) - {\color{yellow}{\cancel{s(t_{n-1})}}})
] \\
&= \lim_{n \to \infty} [s(t_n) - s(t_0)] \\
&= \lim_{n \to \infty} [s(b) - s(a)] \\
&= s(b) - s(a)
\end{align*}
$$
%%$n \to \infty$ o $n \to +\infty$? (se non l'ho scritto da qualche parte fare una ricerca globale in tutto il documento e vedere se o sempre specificato $n \to +\infty$)%%

In prima approssimazione
$$
\int_a^b v(t)dt \simeq s(b) - s(a)
$$
Dimostreremo che
$$
\int_a^b v(t)dt = \underbrace{s(b) - s(a)}_{\text{spostamento "netto" in [a,b]}}
$$
Questo non va confuso con la distanza percorsa dal punto.
Per calcolare lo spazio percorso si usa
$$
\int_a^b |v(t)|dt
$$

Notiamo anche che
$$
\underbrace{
\frac{1}{b-a} \int_a^b v(t)dt
}_{\text{valore medio di $v$ in $[a,b]$ in senso integrale}}
=
\underbrace{
\frac{s(b)-s(a)}{b-a}
}_{\text{velocità media in $[a,b]$}}
$$

# ?

Torniamo all'esercizio di prima:
![](Grafico%20s.png)

Sapendo che $s(0)=2$, vorremmo disegnare il grafico di $s$.
Per quantificare la posizione finale, possiamo ora usare la formula
$$
s(b)-s(a) = \int_a^b v(t)dt
$$
$\int_a^b v(t)dt$ lo possiamo approssimare usando, ad esempio, la formula del punto medio vista precedentemente: fissiamo $n=5$ e dividiamo l'intervallo $[0,3]$ in $5$ sottointervalli di ampiezza $0.6$. I punti medi degli intervalli trovati sono:
$$
\displaylines{
0.3 \mapsto v(0.3) = 0.4 \\
0.9 \mapsto v(0.9) = 0.9 \\
1.5 \mapsto v(1.5) = 0.7 \\
2.1 \mapsto v(2.1) = -0.1 \\
2.7 \mapsto v(2.7) = -1
}
$$
Di conseguenza, la formula del punto medio con $5$ suddivisioni ci dà
$$
\begin{align*}
\int_a^b v(t)dt
&=  \sum_{i=1}^5 v(z_i) \frac{b-a}{n} \\
&= 0.6 \cdot (0.4 + 0.9 + 0.7 - 0.1 - 1) \\
&= 0.6 \cdot 0.9 \\
&= 0.54
\end{align*}
$$
Ma allora
$$
s(b) - s(a) = \int_a^b v(t)dt \simeq 0.54 \implies s(b) \simeq s(a) + 0.54 = 2.54
$$

Osservazione: per stimare il valore massimo di $s$, possiamo stimare $\int_a^b v(t)dt$.
La formula
$$
s(b) - s(a) = \int_a^b v(t)dt
$$
è un caso particolare del TEOREMA DI TORRICELLI-BARROW

# Teorema di Torricelli-Barrow

Se $F$ è una primitiva di $f$, allora
$$
\int_a^b f(x)dx = F(b) - F(a)
$$
(1° teorema fondamentale del calcolo integrale)

## Osservazione

Il calcolo di integrali definiti è ricondotto a quello di integrali indefiniti, e viceversa.
Scriviamo
$$
F(b) = F(a) + \int_a^b f(x)dx
$$
e se, al posto di $b$, usiamo una variabile $x$, abbiamo
$$
F(x) = F(a) + \int_a^x f(t)dt \quad \forall x \in [a,b]
$$

La funzione
$$
x \in [a,b] \mapsto \int_a^x f(t)dt
$$
che associa a ogni punto $x$ l'area sotto il grafico tra $a$ e $x$:
![](Funzione%20integrale.png)

Si dice _funzione integrale_ di $f$ o _funzione di accumulazione_ di $f$.

$$
\underbrace{F(x)}_{\text{primitiva di $f$}} = \underbrace{F(a)}_{\text{costante}} + \int_a^x f(t)dt
\implies
\int_a^x f(t)dt = \underbrace{F(x) - F(a)}_{\text{primitiva - costante = primitiva!}}
$$

# Teorema fondamentale del calcolo integrale

Sia $f\colon [a,b] \to \mathbb{R}$ una funzione. Sia $G(x) = \int_a^x f(t)dt$. Allora $G$ è derivabile e $G'(x)=f(x)$, cioè $G$ (funzione integrale di $f$) è una primitiva di $f$

Questo è il secondo teorema fondamentale. I 2 teoremi fondamentali legano integrale indefinito e integrale definito, e quindi legano calcolo integrale e calcolo differenziale.

# Limiti

Distanza $d$ di 2 punti sulla retta reale:
![](Distanza%20due%20punti.png)

La distanza di $x$ da $0$ è la lunghezza del segmento di estremi $0$ e $x$:
$$
d(x,0) = \begin{cases}
x & \text{se } x \ge 0 \\
-x & \text{se } x < 0
\end{cases} = |x\
$$
Più in generale, la distanza di $x$ da $y$ è la lunghezza del segmento di estremi $x$ e $y$, cioè
$$
d(x,y) = \begin{cases}
y-x & \text{se } y \ge x \\
x-y & \text{se } y < x
\end{cases} = |y-x|
$$
![](Distanza%20x-y.png)

## Osservazione

$$
d(x,y) = d(y,x)
$$
perché
$$
|y-x| = |x-y|
$$
La distanza è una [[relazione simmetrica]].

## Osservazione

$$
|x| = 0 \iff x = 0
$$
e
$$
|x|>0 \quad \forall x \ne 0
$$

## Esercizio 1

%%collegare alla rappresentazione con intervalli di Teoria degli Insiemi%%

Quali sono i punti che distano al più $2$ da $0$?
Risposta:
$$
\begin{align*}
\{\text{punti che distano al più $2$ da $0$}\}
&= \{x \in \mathbb{R} \mid d(x,0) \le 2\} \\
&= \{x \in \mathbb{R} \mid |x| \le 2\} \\
&= \{x \in \mathbb{R} \mid -2 \le x \le 2\} \\
&= [-2,2]
\end{align*}
$$
E abbiamo
$$
|x| \le a \iff -a \le x \le a
$$
e
$$
|x| \ge a \iff x \ge a \lor x \le - a
$$


Quali sono i punti che distano meno di $2$ da $0$?
Risposta:
$$
\begin{align*}
\{\text{punti che distano meno di $2$ da $0$}\}
&= \{x \in \mathbb{R} \mid d(x,0) < 2\} \\
&= \{x \in \mathbb{R} \mid |x| < 2\} \\
&= \{x \in \mathbb{R} \mid -2 < x < 2\} \\
&= (-2,2)
\end{align*}
$$

Potrei anche considerare intervalli che includono un solo estremo:
$$\{x \in \mathbb{R} \mid a < x \le b\} = (a,b]$$

## Esercizio 2

Quali sono i punti che distano meno di $3$ dal punto $1$?
Risposta:
$$
\begin{align*}
\{x \in \mathbb{R} \mid d(x,1) < 3\}
&= \{x \in \mathbb{R} \mid |x-1| < 3\} \\
&= \{x \in \mathbb{R} \mid -3 < x-1 < 3\} \\
&= \{x \in \mathbb{R} \mid -2 < x < 4\} \\
&= (-2,4)
\end{align*}
$$

# Intorno di un punto sulla retta reale

## Definizione: intorno

Dati $c,r \in \mathbb{R}$ con $r > 0$, si dice _intorno di centro $c$ e raggio $r$_ l'insieme
$$
I_r(c) = \{x \in \mathbb{R} \mid d(x,c) < r\} = (c-r, c+r)
$$

## Definizione

Si dice che una proprietà vale definitivamente per $x$ che tende a $c$ se esiste un $r > 0$ tale che la proprietà vale $\forall x \in I_r(c)$ tranne al più che in $c$.

### Esempio

$\frac{1}{x^2} > 1$ vale definitivamente per $x \to 0$, infatti
$$
\frac{1}{x^2} > 1
\iff
\begin{cases}
x^2 < 1 \\ x^2 \ne 0
\end{cases}
\iff
\begin{cases}
-1 < x < 1 \\
x \ne 0
\end{cases}
\iff
x \in I_1(0) \setminus \{0\}
$$
Quindi, se $x \in I_1(0)$ e $x \ne 0$, allora vale $\frac{1}{x^2} > 1$.

## Definizione: retta reale estesa

Introduciamo la _retta reale estesa_:
$$
\overline{\mathbb{R}} = \mathbb{R}\cup \{-\infty\} \cup \{+\infty\}
$$

## Definizione: intorni di $+\infty$ e $- \infty$

Un intorno di $+ \infty$ è un insieme del tipo
$$
I_a(+ \infty) \overset{\text{def}}{=} (a, + \infty) \quad a \in \mathbb{R}
$$
%%capire se utilizzare in tutte le definizioni $\overset{\text{def}}{=}$ oppure $:=$ %%

Un intorno di $- \infty$ è un insieme del tipo
$$
I_a(- \infty) \overset{\text{def}}{=} (a, - \infty) \quad a \in \mathbb{R}
$$

![](Intorni%20di%20infiniti.png)

## Definizione

Si dice che una proprietà è definitivamente vera per $x \to +\infty$ se esiste un $a \in \mathbb{R}$ tale che la proprietà è vera $\forall x \in I_a(+ \infty)$.

### Esempio:

$x^3 > 8$ è definitivamente vera per $x \to +\infty$, infatti
$$
x^3 > 8 \iff x > 2 \iff \forall x \in I_2(+\infty) = (2, + \infty)
$$

# Limite

Il limite di una funzione è un operatore che permette di studiare il comportamento di una funzione nell'intorno di un punto, grazie al quale è possibile stabilire a quale valore tende la funzione man mano che i valori della variabile indipendente si avvicinano a quel punto.

## Limite finito (rosso) al finito (blu): $\displaystyle\lim_{x \to {\color{blue} c \in \mathbb{R}}} f(x) = {\color{red} l \in \mathbb{R}}$ 

### Premesse per la definizione del limite

Il limite che si vuole definire è $\lim_{x \to x_0} \text{f(x) = } l$, dove $f(x)$ è una funzione reale di una variabile reale. Affinché si possa definire il limite appena scritto, serve che il punto $x_0$ sia un punto di accumulazione per il dominio $\mathbb{D}$ della funzione $f(x)$, altrimenti non avrebbe senso cercare il limite della funzione se il valore a cui tende non avesse valori intorno.

La scrittura $x \to x_0$ significa che consideriamo valori della variabile $x$ sempre più vicini al punto $x_0$, tenendo nel frattempo d’occhio il variare del valore della variabile dipendente $y$ dato proprio dalla funzione $f(x)$.
### Obiezione: calcolo diretto della funzione $f(x_0)$

**Non si fa prima a calcolare direttamente il valore della funzione $f(x)$ nel punto $x_0$, quindi $f(x_0)$?**

Dipende, ma generalmente no: il limite è stato inventato proprio per quei casi in cui non è possibile farlo, per esempio nei casi in cui la funzione non è verificata per quel valore a cui vogliamo tendere, ma per cui in ogni caso vogliamo saperne il valore.

Esempio: consideriamo la funzione $f(x)=\frac{x+3}{x-2}$ e poniamo caso che noi vogliamo sapere il valore del limite di $x$ tendente a $2$, quindi $x \to 2$ che nella scrittura del limite diventerebbe $\lim_{x \to 2} \frac{x+3}{x-2}$: sostituendo direttamente $2$ alla $x$, quindi calcolando direttamente il valore di $f(2)$, ci troveremmo con il denominatore pari a $0$, quindi con una frazione impossibile e non potremmo mai sapere il risultato dell’operazione. Il limite ci permette quindi di ottenere il risultato di ciò non andando ad agire direttamente sul punto in cui $x$ ha valore $2$, ma osservando i valori circostanti, per questo si dice che $x$ tende a $2$.
### L’introduzione della variabile dell’ampiezza $\epsilon$

Notiamo quindi che quanto più la variabile $x$ si avvicina (tende) a $x_0$, tanto più la funzione $f(x)$ tenderà al valore $l$. Più in generale, quindi, se prendiamo un qualunque valore di $x$ in un intorno di $x_0$ sempre più piccolo (più vicino a $x_0$), allora $f(x)$ si troverà sempre più vicino a $l$, quindi in un intorno sempre più piccolo.

Ora consideriamo che questi intorni siano circolari ed esprimiamo lo stesso concetto diversamente: considerato un qualsiasi intorno circolare di $l$ di ampiezza $\epsilon$, che indichiamo con $\mathbb{I}_\epsilon(l)$, esiste sempre un $\mathbb{I}(x_0)$ i cui punti $x$ hanno la propria immagine contenuta in $\mathbb{I}_\epsilon(l)$. I punti di tale intorno sono proprio quei valori di $x$ che soddisfano la disequazione $|f(x) - l| < \epsilon$.

Riassumendo, quindi, per qualsiasi valore di $\epsilon>0$ ($\epsilon$ viene considerato maggiore di 0 perché non avrebbe senso avere un’ampiezza di valore negativo), esiste un intorno $\mathbb{I}(x_0)$ dipendente da $\epsilon$, per cui per ogni $x$ appartenente a questo intorno si ha che $x$ soddisfa la disequazione $|f(x) - l| < \epsilon$.
### Definizione formale

La funzione $f(x)$ ha per limite il numero reale $l$, per $x$ che tende a $x_0$, quando, comunque si scelga un numero reale positivo $\epsilon$, si può determinare un intorno completo $\mathbb{I}$ di $x_0$ tale che $|f(x) - l| < \epsilon$ per ogni $x$ appartenente a $l$, diverso (al più) da $x_0$.

### Appunti del corso A
$$
\lim_{x \to {\color{blue} c \in \mathbb{R}}} f(x) = {\color{red} l \in \mathbb{R}}
$$

Idea: se $x$ si avvicina a $c$, allora $f(x)$ si avvicina a $l$:
![](Limite%20finito%20al%20finito.png)

$|x - c|$ piccolo $\implies |f(x) - l|$ piccolo

Per formalizzare questa idea, si usano i quantificatori.

Definizione: sia $f \colon I_r(c) \setminus \{c\} \to \mathbb{R}$ e sia $l \in \mathbb{R}$, si dice che _$f$ tende a $l$ per $x$ che tende a $c$_ e si scrive
$$
\lim_{x \to c} f(x) = l
$$
Se $\forall \epsilon > 0 \quad \exists \delta > 0: \underbrace{0 < |x-c| < \delta}_{d(x,c) < d, \quad x \ne c} \implies \underbrace{|f(x) - l| < \epsilon}_{d(f(x), l)}$

In termini di intorni:
$$
\forall \epsilon > 0,\exists \delta > 0: x \in I_\delta(c) \setminus \{c\} \implies f(x) \in I_\epsilon(l)
$$
![](Pasted%20image%2020240702140920.png)

- Fissiamo arbitrariamente $\epsilon > 0$
- Vogliamo trovare un $\delta > 0$ tale che se $x \in I_\delta(c) \setminus \{c\}$, allora il grafico di $f$ in questo intorno sta nella striscia orizzontale $\{l - \epsilon < y < l + \epsilon\}$

Osservazione:
$$
\lim_{x \to c} f(x) = l \iff \forall \epsilon > 0 \text{ la proprietà $f(x) \in I_\epsilon(l)$ è vera definitivamente per $x \to c$}
$$

Esempio:
$$
\lim_{x \to 0} x^2 = 0
$$
Verifichiamolo. Vogliamo verificare che
$$
\forall \epsilon > 0, \exists \delta > 0: 0 < |x| < \delta \implies |x^2| < \epsilon
$$

Fissiamo $\epsilon > 0$:
$$
|x^2| < \epsilon \iff x^2 < \epsilon \iff -\sqrt\epsilon < x < \sqrt\epsilon \iff |x| < \sqrt\epsilon
$$
Quindi
$$
\forall \epsilon > 0, \text{se } 0 < |x| < \sqrt\epsilon \implies |x^2| < \epsilon
$$
Quindi la definizione è verificata, con $\delta = \sqrt\epsilon$.



Osservazione: sia ora
$$
f(x) = \begin{cases}
x^2 & se x \ne 0 \\
5 & se x = 0
\end{cases}
$$

![](Pasted%20image%2020240702141651.png)
$$
\lim_{x\to0} f(x) = 0 = \lim_{x\to 0} x^2
$$
Nella definizione di limite, non è coinvolto il valore della funzione in $x = c$, ma solo i valori "vicini".
![](Pasted%20image%2020240702141746.png)
![](Pasted%20image%2020240702141755.png)

In tutti questi casi, $\lim_{x \to c} f(x) = l$

## Limite finito (rosso) all'infinito (blu)

$$
\lim_{x \to {\color{blue} \pm \infty}} f(x) ={\color{red} l \in \mathbb{R}}
$$

Idea: se $x$ diventa molto grande, $f(x)$ si avvicina sempre più a $l$.

Definizione: sia $f \colon (a, + \infty) \to \mathbb{R}$ %%perché il dominio è $(a, + \infty)$? e nel caso di $- \infty$?%% e sia $l \in \mathbb{R}$, si dice che $f$ tende a $l$ per $x$ che tende a $+ \infty$:
$$
\lim_{x \to \pm \infty} f(x) = l
$$

Se $\forall \epsilon > 0, \exists N > 0 : x > N \implies |f(x) - l| < \epsilon$

In termini di intorni:
$$
\forall \epsilon > 0,\exists N > 0: x \in I_N(+ \infty) \implies f(x) \in I_\epsilon(l)
$$
%%e nel caso di $-\infty$?%%

![](Pasted%20image%2020240702144250.png)

Fissato un $\epsilon > 0$, riusciamo a trovare un $N > 0$ tale che a destra di $N$ (cioè per $x > N$) il grafico di $f$ è contenuto nella striscia $\{l - \epsilon < y < l + \epsilon\}$.

Osservazione:
$$
\lim_{x \to + \infty} f(x) = l \iff \forall \epsilon > 0 \text{ la proprietà $|f(x)-l|< \epsilon$ vale definitivamente per $x \to + \infty$}
$$

Se $\lim_{x \to + \infty} f(x) = l \in \mathbb{R}$, si dice che $y=l$ è un asintoto orizzontale (destro) per $f$.

Definizione:
$$
\lim_{x \to - \infty} f(x) = l \in \mathbb{R} \iff \forall \epsilon > 0, \exists N > 0: x < -N \implies |f(x) - l| < \epsilon
$$

![](Pasted%20image%2020240702144539.png)

Se $lim_{x \to - \infty} f(x) = l \in \mathbb{R}$, si dice che $y = l$ è un asintoto orizzontale (sinistro) di $f$.

Osservazione: nel caso di limiti finiti (sia al finito che all'infinito) a volte si può parlare di limiti per eccesso o per difetto.

Definizione: dati $c \in \overline{\mathbb{R}}, l \in \mathbb{R}$
Se $\lim_{x \to c} f(x) = l$ e $f(x) > l$ definitivamente per $x \to c$, si dice che $f$ tende a $l$ per eccesso (dall'alto) e si scrive
$$
\lim_{x \to c} f(x) = l^+
$$
Se $\lim_{x \to c} f(x) = l$ e $f(x) < l$ definitivamente per $x \to c$, si dice che $f$ tende a $l$ per difetto (dal basso) e si scrive
$$
\lim_{x \to c} f(x) = l^-
$$

Esempio: $\lim_{x \to 0} x^2 = 0^+$
$\lim_{x \to + \infty} \frac{1}{x} = 0^+$

Lo verifichiamo con la definizione: vogliamo verificare che $\forall \epsilon > 0, \exists N > 0: x > N \implies \left|\frac{1}{x}\right| < \epsilon$. Se completiamo questa verifica, siccome $\frac{1}{x}>0, \forall x > 0$ (definitivamente per $x \to + \infty$), avremo dimostrato $\lim_{x \to + \infty} \frac{1}{x} = 0^+$.

Fissiamo $\epsilon > 0$:
$$
\left|\frac{1}{x} < \epsilon \right| \iff |x| > \frac{1}{\epsilon} \iff x < - \frac{1}{\epsilon} \lor x > \frac{1}{\epsilon}
$$

Quindi, se $x > \frac{1}{\epsilon} \implies \left| \frac{1}{x} \right| < \epsilon$.
Quindi vale la definizione di limite con $N = \frac{1}{\epsilon}$.
![](Pasted%20image%2020240702145930.png)

Osservazione: non tutti i limiti sono per eccesso o per difetto:
$$
f(x) = \frac{\sin x}{x} =\frac{1}{x} \cdot \sin x
$$
![](Pasted%20image%2020240702150021.png)
In questo caso $f(x) \to 0$ per $x \to +\infty$, ma non ci tende né per eccesso, né per difetto.

# Proprietà algebriche dei limiti finiti

Sia $c \in \overline{\mathbb{R}}$ ($c$ può essere finito o $\pm \infty$), siano $f,g \colon I_\delta(c) \setminus \{c\} \to \mathbb{R}$ (oppure $I_N(+ \infty)$ o $I_{-N}(-\infty)$), siano $l,m \in \mathbb{R}$.
Supponiamo che
$$
\lim_{x \to c} f(x) = l
$$
e
$$
\lim_{x \to c} g(x) = m
$$

Allora:
- $\lim_{x \to c} (f(x) + g(x)) = l + m$
- $\lim_{x \to c} f(x) \cdot g(x) = l \cdot m$
- Se $m \ne 0$, $\lim_{x \to c} \frac{f(x)}{g(x)} = \frac{l}{m}$

# Premessa - disuguaglianza triangolare

$$
|a + b| \le |a| + |b| \quad \forall a,b \in \mathbb{R}
$$

Dimostrazione:
Per definizione, $-|a| \le a \le |a|$ e $-|b| \le b \le |b|$ per ogni a,b
Sommiamo:
$$
-|a| - |b| \le a + b \le |a| + |b| \iff |a+b| \le |a| + |b|
$$
$\blacksquare$

Dimostrazione (somma dei limiti): $c \in \mathbb{R}$
Vogliamo dimostrare che $\forall \epsilon > 0, \exists \delta > 0: 0 < |x-c| < \delta \implies |(f(x) + g(x)) - (l+m)| < \epsilon$
Sappiamo che
$$
\lim_{x \to c} f(x) = l
$$
e
$$
\lim_{x \to c} g(x) = m
$$
quindi per $f(x)$
$$
\forall \epsilon > 0, \exists \delta_1 > 0: 0 < |x-c| < \delta_1 \implies |f(x) - l| < \frac{\epsilon}{2}
$$
(siccome $\epsilon$ è arbitrario, anche $\frac{\epsilon}{2}$ lo è)
e per $g(x)$
$$
\forall \epsilon > 0, \exists \delta_2 > 0: 0 < |x-c| < \delta_2 \implies |g(x) - m| < \frac{\epsilon}{2}
$$

Fissiamo $\epsilon > 0$:
$$
|(f(x) + g(x)) - (l+m)| = |\underbrace{(f(x)-l)}_a + \underbrace{(g(x)-m)}_b| \le |f(x)-l| + |g(x)-m| < ecc.
$$
(per la disuguaglianza triangolare)

Supponiamo che $0 < |x-c| < \underbrace{\min\{\delta_1, \delta_2\}}_\delta$