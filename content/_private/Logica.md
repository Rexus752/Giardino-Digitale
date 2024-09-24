https://it.wikipedia.org/wiki/Logica_intensionale

# Esperimenti e dimostrazioni

Nella maggior parte delle discipline scientifiche (ad esempio fisica, chimica, biologia. . . ) per stabilire la verità di un’affermazione si ricorre a misurazioni, esperimenti o simulazioni: se gli esperimenti, magari fatti più volte e da più persone, confermano l’affermazione, allora questa viene accettata (almeno temporaneamente), altrimenti viene rifiutata.

In logica, il metodo scientifico NON funziona: infatti, controllare solo alcuni casi specifici può essere utile per avere indizi sulla verità o meno di un'affermazione, ma a volte non possono confermarla nella sua interezza. Ad esempio, nessun esperimento potrà mai stabilire se $\sqrt 2$ sia un numero razionale (ovvero se $\sqrt 2 = \frac{m}{n}$ con $m,n \in \mathbb{Z}$).

In matematica, per stabilire la verità di un'affermazione (di un _teorema_) si deve ricorrere a una _dimostrazione_.

## Congettura

Dato un intero $n$, il risultato di $991 \cdot n^2 + 1$ non è mai un quadrato perfetto (ovvero la sua radice quadrata non è un numero intero).

Si è dimostrato che tale congettura è falsa, anzi ci sono infiniti numeri del tipo $991 \cdot n^2 + 1$ che sono quadrati perfetti. Tuttavia, il più piccolo di tali
numeri è
$$
n = 12055735790331359447442538767 \approx 1,2 \cdot 10^{28}
$$

Quanto è grande questo numero? Confrontatelo con il numero di stelle nell'universo osservabile, ovvero: $\approx 3 \cdot 10^{23}$. Il nostro numero è enorme!
Quindi controllare a mano la congettura con degli esempi (anche moltissimi!) ci avrebbe erroneamente indotti a crederla vera.

# Teoremi e dimostrazioni

## Definizione: teorema

Un _teorema_ è un'affermazione (riguardante numeri, funzioni, enti geometrici, o altri oggetti matematici) che si vuole dimostrare, solitamente enunciato nella forma _"se valgono $P_1, P_2, \ldots, P_n$, allora vale anche $Q$"_ (dove le affermazioni $P_1, P_2, \ldots, P_n$ sono dette _ipotesi del teorema_, mentre $Q$ è detta _tesi del teorema_).

### Esempio

Se $n$ è un numero naturale dispari ed $m$ è un numero naturale pari, allora il risultato di $n + m$ è un numero dispari.

$$
\text{Se }
\underbrace{\text{$n$ è un numero naturale dispari}}_{P_1}
\text{ ed }
\underbrace{\text{$m$ è un numero naturale pari}}_{P_2}
\text{, allora }
\underbrace{\text{$n+m$ è dispari}}_{Q}
\text{.}
$$

### Notazione: conseguenza logica

Utilizzeremo la scrittura
$$
P_1, P_2, \ldots, P_n \vDash Q
$$
(che si legge _“Q è conseguenza logica di $P_1, P_2, \ldots, P_n$”_) per tradurre in un linguaggio simbolico il teorema con ipotesi $P_1, P_2, \ldots, P_n$ e tesi $Q$.

### Osservazione: differenza tra _teorema_, _proposizione_ e _lemma_

%% trasformare “ e ” in " e ’ in ' %%

In matematica sono di uso comune anche altri sinonimi di _“teorema”_, ad esempio _“proposizione”_, _“lemma”_ e così via. Dal punto di vista tecnico, tutti questi termini vogliono dire esattamente la stessa cosa, ovvero che quel che si sta affermando è un teorema.

La differenza tra le varie espressioni è l’importanza (del tutto soggettiva) che chi scrive o parla vuole attribuire all'affermazione che si sta dimostrando: solitamente si impiegano nel seguente modo:
- Il termine _"teorema"_ per riferirsi a tutte quelle affermazioni che si ritengono veramente importanti e significative;
- Il termine _"proposizione"_ per quelle che sono un po' meno importanti ma pur sempre abbastanza significative;
- Il termine _"lemma"_ per quelle affermazioni che di per se non sarebbero molto significative, ma che servono poi per dimostrare altri fatti più importanti.

Quando si analizza il ragionamento matematico, come faremo noi in questo corso, non si tiene conto di queste distinzioni e si parla sempre di teorema.

## Definizione: dimostrazione di un teorema

Una dimostrazione di un teorema è una catena di ragionamenti che ci permette di concludere che la tesi del teorema $Q$ deve essere vera partendo dall'assunzione che le ipotesi del teorema $P_1, P_2, \ldots, P_n$ siano vere.

### Esempio

Supponiamo di aver scritto il programma che controlla la ventilazione di una sonda spaziale. Verificare con un certo numero (anche elevatissimo!) di esperimenti o simulazioni che il programma non va in crash ed esegue correttamente tutte le operazioni che deve svolgere non è sufficiente... 

Come si può garantire che una volta in funzione sulla sonda spaziale non si verifichi proprio una situazione, mai incontrata nelle simulazioni, che porti al blocco del sistema (per la gioia degli astronauti presenti a bordo, che morirebbero soffocati)? L’unico modo è fornire una dimostrazione del fatto che il programma funziona, ovvero della sua correttezza. Pur parlando di programmi e non di numeri, il concetto di dimostrazione è esattamente lo stesso usato in matematica quando si parla di teoremi.

## Definizione: contesto di un'affermazione

Il contesto di un'affermazione è il (dominio?) in cui ci si chiede se può essere vera o meno.

Stabilire che cosa sia un contesto/situazione in cui sia possibile valutare se una data affermazione $P$ sia vera o falsa è molto delicato. Negli esempi seguenti tutti le affermazioni $P$ che considereremo parleranno di numeri $n, m, x$: i “contesti” possibili saranno allora tutti i possibili valori che questi numeri possono assumere.

### Esempio

L’affermazione _"$n$ è un numero naturale dispari"_ è vera nella situazione in cui $n$ vale $3$, ma falsa quando $n$ vale $4$.

## Definizione: tautologia

Una tautologia è un'affermazione sempre vera in qualunque contesto, ossia un enunciato per il quale
$$
\vDash Q
$$
è un teorema che non ha bisogno di ipotesi.

$Q$ solitamente è della forma
$$
P \lor \lnot P
$$
(si legge _"$P$ oppure non-$P$"_) dove $P$ è una qualche affermazione e $\lnot P$ la sua negazione. Indipendentemente da che cosa asserisce $P$ e dal contesto in cui ci poniamo, dobbiamo concludere che $Q$ è valido.

### Esempio 

L'affermazione "un numero intero è pari, oppure non lo è." è una tautologia.

# Tipi di dimostrazioni

Ci sono diverse strategie dimostrative variamente utilizzate (spesso in combinazione tra loro). Nel seguito presenteremo le più comuni ossia:
- La dimostrazione diretta;
- La dimostrazione per assurdo;
- La dimostrazione per contrapposizione;
- La dimostrazione per composizione (o interpolazione);
- La dimostrazione per casi.

La correttezza di tutte queste strategie dimostrative può essere verificata in maniera rigorosa utilizzando la logica proposizionale.

## Definizione: dimostrazione diretta

Una dimostrazione diretta di un teorema della forma $P_1, P_2, \ldots, P_n \vDash Q$ è una dimostrazione in cui, sulla base di semplici e rigorosi ragionamenti, a partire dalle ipotesi $P_1, P_2, \ldots, P_n$ si stabilisce che in tale contesto anche la tesi $Q$ è verificata.

### Esempio

Teorema:
Se $n$ è un numero intero dispari e $m$ è un numero intero pari, allora il risultato di $n + m$ è un numero intero dispari.

Dimostrazione:
Siano $n$ ed $m$ interi qualsiasi e assumiamo che $n$ sia dispari ed $m$ pari, ovvero che $n = 2l + 1$ per qualche intero $l$, mentre $m = 2k$ per qualche intero $k$. Bisogna dimostrare che $n + m$ è dispari. Effettuando i calcoli si ha:
$$
\begin{align}
n + m &= (2l + 1) + 2k \\
&= (2l + 2k) + 1 \\
&= 2(l + k) + 1 \\
&= 2j + 1 \quad \text{con $j = l + k$}
\end{align}
$$

Questo dimostra che $n + m$ è dispari perché ha la forma $2j + 1$.
$\blacksquare$

## Definizione: dimostrazione per assurdo

Una dimostrazione per assurdo (o _dimostrazione indiretta_) di un teorema della forma $P_1, P_2, \ldots, P_n \vDash Q$ è una dimostrazione in cui si assume che la tesi $Q$ sia falsa e da questa assunzione si deriva (utilizzando anche le ipotesi $P_1, P_2, \ldots, P_n$) una contraddizione, ovvero una proposizione della forma
$$
R \land \lnot R
$$
che asserisce che una qualche affermazione $R$ è al contempo sia vera che falsa. Poiché una contraddizione è necessariamente falsa (una proposizione in un dato contesto può essere vera o falsa, ma non entrambe contemporaneamente!), questo prova che assumere che $Q$ sia falsa porta a conclusioni assurde, e quindi $Q$ non può che essere vera. 

In altre parole: si dimostra che se le premesse $P_1, P_2, \ldots, P_n$ sono vere non è possibile che $Q$ sia falsa.

Concretamente, in una dimostrazione per assurdo di un teorema del tipo
$$
P_1, P_2, \ldots, P_n \vDash Q
$$
si assume che le ipotesi $P_1, P_2, \ldots, P_n$ siano vere ma che, per assurdo, la tesi $Q$ sia falsa, e da questa assunzione si deriva una contraddizione.
Quando invece il teorema è del tipo
$$
\vDash Q
$$
ovvero quando si deve dimostrare $Q$ senza partire da alcuna ipotesi (cioè quando bisogna mostrare che $Q$ è una tautologia), allora una dimostrazione
per assurdo consiste semplicemente nell'assumere per assurdo che $Q$ sia falsa, e poi dimostrare che da quest’assunzione deriva una contraddizione.

### Esempio

Teorema:
Per ogni coppia di numeri reali $x$ e $y$, se $\underbrace{x + y \ge 2}_{P}$ allora $\underbrace{x \ge 1 \text{ oppure } y \ge 1}_{Q}$.

Dimostrazione:
Siano $x$ e $y$ due numeri reali qualsiasi e supponiamo per assurdo che $P$ sia vera ma $Q$ sia falsa, ovvero che valgano $x + y \ge 2$ e $x, y < 1$  (si osservi
che assumere che "$x \ge 1$ oppure $y \ge 1$” sia falsa è equivalente ad assumere che "$x < 1$ e $y < 1$" sia vera).
Dalla negazione di $Q$ segue che $x + y < 1 + 1$, ovvero $x + y < 2$. Ma questo contraddice l’assunzione $P$, quella per cui $x + y \ge 2$.
Questo dimostra (per assurdo) che se vale $P$ allora $Q$ non può essere falsa. In altre parole, è vero che se vale $P$ allora deve valere anche $Q$, quindi il teorema è dimostrato.
$\blacksquare$

### Esempio

Teorema:
Per ogni numero intero $n$, se $\underbrace{n^2 \text{ è pari}}_{P}$, allora $\underbrace{n \text{ è pari}}_{Q}$.

Dimostrazione:
Supponiamo per assurdo che $P$ sia vera ma $Q$ sia falsa (ovvero che $n$ sia dispari) e facciamo vedere che queste assunzioni portano ad una contraddizione. Sia $n$ dispari, ovvero $n = 2m + 1$ per qualche intero $m$.
Allora possiamo calcolare:
$$
\begin{align}
n^2 &= (2m + 1)^2 \\
&= 4m^2 + 4m + 1 \\
&= 2(2m^2 + 2m) + 1
\end{align}
$$
per cui $n^2$ è dispari (essendo della forma $2j+1$ con $j = 2m^2 + 2m$), ma ciò contraddice l'ipotesi iniziale $P$ per la quale $n^2$ è pari. Abbiamo una contraddizione, quindi se vale $P$ deve necessariamente valere anche $Q$.
$\blacksquare$

## Definizione: dimostrazione per contrapposizione

Una dimostrazione per contrapposizione di un teorema della forma $P_1, P_2, \ldots, P_n \vDash Q$ è una dimostrazione in cui la tesi $Q$ viene negata e, a partire da questa, si deve dimostrare che anche le ipotesi $P_1, P_2, \ldots, P_n$ vengono negate:
$$
\lnot Q \vDash \lnot(P_1, P_2, \ldots, P_n)
$$
Infatti, supponiamo di aver stabilito la correttezza del teorema $\lnot Q \vDash \lnot(P_1, P_2, \ldots, P_n)$ e di essere in un contesto in cui valgono le ipotesi $P_1, P_2, \ldots, P_n$. Allora in tale contesto anche la tesi $Q$ deve essere vera, perché se fosse falsa (ovvero se valesse $\lnot Q$) allora si avrebbe che sia $P_1, P_2, \ldots, P_n$ (per ipotesi) che $\lnot(P_1, P_2, \ldots, P_n)$ (per il teorema $\lnot Q \vDash \lnot(P_1, P_2, \ldots, P_n)$) sarebbero vere, contraddizione!
Posto di sapere che $\lnot Q \vDash \lnot(P_1, P_2, \ldots, P_n)$, questo argomento mostra che in ogni contesto in cui valgano le ipotesi $P_1, P_2, \ldots, P_n$ deve valere anche la tesi $Q$, ossia che $P_1, P_2, \ldots, P_n \vDash Q$.

### Esempio

Teorema:
Se $\underbrace{n^2 \text{ è un numero intero pari}}_{P}$, allora $\underbrace{n \text{ è un numero intero pari}}_{Q}$.

Dimostrazione:
Usando la dimostrazione per contrapposizione, l'enunciato diventa:
Se $\underbrace{n \text{ è un numero intero dispari}}_{\lnot Q}$, allora $\underbrace{n^2 \text{ è un numero intero dispari}}_{\lnot P}$.
Si può procedere adesso anche col metodo diretto: assumiamo che $n$ sia dispari, ovvero che $n = 2k + 1$ per qualche intero $k$: bisogna dimostrare allora che anche $n^2$ è dispari. Svolgendo i calcoli si ha che:
$$
\begin{align}
n^2 &= (2k + 1)^2 \\
&= (4k^2 + 4k + 1) \\
&= 2(2k^2 + 2k) + 1
\end{align}
$$
quindi n^2 è dispari (poiché è della forma $2j + 1$ con $j = 2k^2 + 2k$).
$\blacksquare$

## Definizione: dimostrazione per composizione

Una dimostrazione per composizione (o _dimostrazione per interpolazione_) di un teorema della forma $P_1, P_2, \ldots, P_n \vDash Q$ è una dimostrazione in cui, dopo aver dimostrato