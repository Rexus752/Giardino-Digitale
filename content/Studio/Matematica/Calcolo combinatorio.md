---
icon: TiArrowsRandom
iconColor: "#FFFF88"
---
[https://it.wikipedia.org/wiki/Glossario_di_combinatoria](https://it.wikipedia.org/wiki/Glossario_di_combinatoria)

[https://it.wikipedia.org/wiki/Calcolo_combinatorio#Permutazioni](https://it.wikipedia.org/wiki/Calcolo_combinatorio#Permutazioni)

[https://www.youmath.it/lezioni/probabilita/calcolo-combinatorio.html](https://www.youmath.it/lezioni/probabilita/calcolo-combinatorio.html)

[https://www.matematika.it/public/allegati/39/15_04_Calcolo_combinatorio_1_0.pdf](https://www.matematika.it/public/allegati/39/15_04_Calcolo_combinatorio_1_0.pdf)

IDEA: aggiungere flowchart che fa tramite domande fa capire cosa usare tra metodo delle scelte successive, ordinamenti, disposizioni e combinazioni con o senza ripetizioni

di ogni categoria le possibili combinazioni si indicano con la cardinalità es. $|\text D_{n,k}|$ anziché $\text D_{n,k}$

# Equipotenza di insiemi

>[!definizione] _Definizione_: insiemi equipotenti
>Dati due insiemi $A$ e $B$, essi si definiscono _**equipotenti**_ se esiste una funzione biettiva $f\colon A\to B$ e, cioè, se hanno la stessa cardinalità:
>$$ |A|=|B| $$
>^6e7153

>[!esempio] _Esempio_: $|\mathbb{N}|=|2\mathbb{N}|$ (osservazione di Galileo Galilei)
>La funzione $f\colon\mathbb{N}\to2\mathbb{N},\quad n\mapsto 2n$ è una biezione (infatti ha come inversa la funzione $g\colon2\mathbb{N}\to\mathbb{N},\quad m\mapsto\frac m 2$), quindi gli insiemi $\mathbb{N}$ e $2\mathbb{N}$ sono equipollenti e, di conseguenza, $|\mathbb{N}|=|2\mathbb{N}|$.
>Si dice che questa osservazione risalga a Galileo Galilei.

>[!esempio] _Esempio_: $|\mathbb{N}|=|\mathbb{N}\times\mathbb{N}|$
>Preso l’insieme del prodotto cartesiano $\mathbb{N}\times\mathbb{N}$, si ordinano le coppie $(a,b)$ che contiene secondo le seguenti regole:
>1. Si ordinano prima secondo la crescita di $a+b$ (es. la coppia $(3,4)$ viene prima di $(1,7)$ perché $3+4<1+7$)
>2. A parità di $a+b$, si ordinano secondo la crescita di $a$ (es. la coppia $(3,4)$ viene prima di $(5,2)$ perché $3<5$).
>
>Si ottiene quindi una successione del genere:
>$$ (0,0), \space(0,1), \space(1,0), \space(0,2), \space(1,1), \space(2,0), \space(0,3), \space(1,2), \space(2,1), \ldots $$
>Se si numerano le coppie, partendo da $0$, secondo l’ordine di comparsa nella lista, si riesce a definire una biezione $f\colon\mathbb{N}\times\mathbb{N}\to\mathbb{N}$ e, quindi, $|\mathbb{N}|=|\mathbb{N}\times\mathbb{N}|$.

>[!osservazione] _Osservazione_: $|A|=|B|,|B|=|C|\implies|A|=|C|$
>Dal momento che la [[Introduzione alle funzioni#^a36545|composizione di biezioni è una biezione essa stessa]], si ha che se $|A|=|B|$ e $|B|=|C|$ (quindi $f\colon A\to B$ e $g\colon B\to C$ sono due funzioni biettive), allora anche $|A|=|C|$ (cioè $g\circ f\colon A\to C$ è biettiva).

---

>[!teorema] _Teorema_: ordinamento totale della cardinalità
>Dati due insiemi $A$ e $B$, si ha sempre $|A|\le|B|$ oppure $|B|\le|A|$.

---

>[!teorema] _Teorema_: Teorema di Cantor-Bernstein-Schröder
>Dati due insiemi $A$ e $B$, se $|A|\le|B|$ e $|B|\le|A|$, allora $|A|=|B|$.

# Infinità di un insieme

>[!definizione] _Definizione_: insieme infinito e finito
>Un insieme $A$ si dice _**infinito**_ se è [equipotente](#^6e7153) a un suo sottoinsieme proprio $B\subsetneq A$ (quindi $|B|=|A|$), cioè se esiste una funzione $f\colon A\to A$ iniettiva ma non suriettiva.
>Al contrario, un insieme $A$ si dice _**finito**_ se non è infinito, cioè se ogni funzione iniettiva $f:A\to A$ è una biezione.
>^0d6caa

---

>[!proposizione] _Proposizione_: $f\colon A\to A$ è iniettiva, suriettiva e biettiva
>Dati un insieme finito $A$ e una funzione $f\colon A\to A$, allora le seguenti affermazioni su $f$ sono equivalenti:
>- $f$ è iniettiva;
>- $f$ è suriettiva;
>- $f$ è biettiva.

>[!dimostrazione] _Dimostrazione_
>Per la [[#^0d6caa|definizione di insieme finito]], se $f$ è iniettiva, allora deve necessariamente essere anche suriettiva (quindi biettiva).
>Se $f$ è suriettiva, allora la sua controimmagine $f^{-1}(a)$ è non vuota per ogni $a \in A$ (perché si ha che ogni $a$ ha una controimmagine). Si definisce quindi una funzione $g\colon A\to A$ con
>%%completare!%%
>$\blacksquare$

---

> [!proposizione] _Proposizione:_ %%aggiustare%%
> Dati due numeri $m,n\in\mathbb{N}:m,n\ge 1$ e due insiemi $I_n=\{1,2,\ldots,n\}$ e $I_m=\{1,2,\ldots,m\}$, valgono le seguenti affermazioni:
> 1. Per ogni $n\ge1$ l’insieme $I_n$ è finito;
> 2. Se $m\mathbb{N}e n$, gli insiemi $I_m$ e $I_n$ non sono equipotenti, cioè $|I_m|\mathbb{N}e|I_n|$;
> 3. Se $m\le n$, allora $|I_m|\le|I_n|$;
> 4. Ogni insieme finito $X$ non vuoto è equipotente a un insieme $I_n$, cioè $\exists n\in\mathbb{N}:|I_n|=|X|$;
> 5. Per ogni insieme infinito $Y$ si ha $|\mathbb{N}|\le|Y|$.

>[!dimostrazione] _Dimostrazione_
>![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7455eedc-7f11-44f4-972b-9aed802c163c/Untitled.png)
>![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7a136acd-2bd8-4ddb-943c-7ef586bfd837/Untitled.png)
>![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/d55280dd-8095-4c9c-805f-f9e8c3f6bd34/Untitled.png)
>![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/acd2779c-3484-4bc5-8518-43adef1da235/Untitled.png)
>![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/4990bac2-1142-4a37-8e3c-20bf2c8d52af/Untitled.png)
>$\blacksquare$

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/428b0219-ab1e-4e29-bf3a-72a728a82c45/Untitled.png)

%%Sistemare tutto il capitolo 3.1 dal libro e vedere meglio lezione del 03/10%%

# Principio di inclusione-esclusione

>[!proposizione] _Proposizione_: cardinalità dell’unione di insiemi finiti disgiunti
>Dati degli insiemi finiti $A_1,A_2,\ldots,A_n$ a due a due disgiunti (cioè $A_i\ne A_j,\quad\forall i,j\ne n:i\ne j$), allora
>$$ \left|\displaystyle\bigcup_{i=1}^nA_i\right| =\sum^n_{i=1}|A_i|=|A_1|+|A_2|+\ldots+|A_n| $$
>^c3e0e3

>[!dimostrazione] _Dimostrazione_
>Non essendoci per ipotesi ripetizioni tra gli elementi dei vari insiemi $A_i$ (dato che sono disgiunti), elencare e contare gli elementi di $\displaystyle\bigcup_{i=1}^nA_i$ equivale a elencare e contare separatamente gli elementi di ciascun $A_i$. In concreto, posto $A_1=\{a_1,a_2,\ldots,a_{k_1}\},A_2=\{b_1,b_2,\ldots,b_{k_2}\},\ldots,A_n=\{z_1,z_2,\ldots,z_{k_n}\}$, si ha:
>$$ \displaystyle\bigcup_{i=1}^nA_i=A_1\cup A_2\cup\ldots\cup A_n=\{
>\underbrace{a_1,a_2,\ldots,a_{k_1}}_{k_1\text{ elementi di }A_1},
>\underbrace{b_1,b_2,\ldots,b_{k_2}}_{k_2\text{ elementi di }A_2},
>\ldots,
>\underbrace{z_1,z_2,\ldots,z_{k_n}}_{k_n\text{ elementi di }A_n}\} $$
>e, quindi, $|A_1\cup A_2\cup\ldots\cup A_n|=k_1+k_2+\ldots+k_n$.
>$\blacksquare$

---

>[!proposizione] _Proposizione_: principio di inclusione-esclusione per due insiemi
>Dati due insiemi finiti $A$ e $B$, allora:
>$$ |A\cup B|=|A|+|B|-|A\cap B| $$

>[!dimostrazione] _Dimostrazione_
>I due insiemi hanno cardinalità $|A|=m$ e $|B|=n$ con $k$ elementi comuni (cioè $|A\cap B|=k$). Si possono quindi elencare gli elementi di $A$ e $B$ come
>$$ A=\{a_1,\ldots,a_m\},B=\{b_1,\ldots,b_n\},\quad a_1=b_1,a_2=b_2,\ldots,a_k=b_k $$
>cioè i primi $k$ elementi di entrambi gli insiemi sono in comune.
>Si ha quindi che
>$$ A\cup B=\{\underbrace{a_1,\ldots,a_m}_{m\text{ elementi}}, \underbrace{b_{k+1},\ldots,b_{n}}_{n-k\text{ elementi}} \} $$
>cioè si prendono tutti gli $m$ elementi di $A$ e di $B$ si prendono solo gli elementi non in comune ad $A$ (cioè dal $k+1$-esimo elemento all’$n$-esimo, tralasciando i primi $k$ elementi perché sono appunto quelli in comune).
>Si ottiene quindi che $|A\cup B|=m+n-k=|A|+|B|-|A\cap B|$.
>$\blacksquare$

>[!osservazione] _Osservazione_: principio di inclusione-esclusione è generalizzazione della cardinalità dell’unione di insiemi finiti disgiunti
>Il principio di inclusione-esclusione è in realtà la generalizzazione della [[#^c3e0e3|cardinalità dell’unione di insiemi finiti disgiunti]], in quanto quest’ultima si calcola appunto su insiemi che per definizione sono disgiunti e, non avendo elementi in comune, non bisogna applicare alcuna “esclusione”.

>[!osservazione] _Osservazione_: ricavare una quantità dell’equazione dalle altre tre
>L’espressione del principio di inclusione-esclusione su due insiemi può riscriversi equivalentemente come
>$$ |A\cup B|+|A\cap B|=|A|+|B| $$
>da cui risulta più evidente come il principio possa essere usato per calcolare una qualunque delle quattro quantità quando le altre tre sono note.

>[!esempio] _Esempio_: persone che hanno ordinato entrambe le portate
>In un ristorante a un tavolo con $14$ persone sono stati ordinati $8$ primi e $11$ secondi e ognuno ha ordinato qualcosa. Quanti hanno ordinato sia il primo che il secondo?
>Indicando con $P$ l’insieme di coloro che hanno ordinato un primo e $S$ l’insieme di coloro che hanno ordinato il secondo, si vuole calcolare $|P\cap S|$. Le informazioni sono che $|P|=8$, $|S|=11$ e $|P\cup S|=14$. Dunque, per il principio di inclusione-esclusione, si ha che
>$$ |P\cup S|+|P\cap S|= |P|+|S|\implies 14+|P\cap S|=8+11\implies |P\cap S|=8+11-14 $$
>da cui $|P\cap S|=5$.

>[!esempio] _Esempio_: matricole che hanno superato almeno un esame
>Alla fine delle sessioni d'esame di un certo corso universitario, 152 matricole hanno superato l'esame di matematica e 144 matricole hanno superato l’esame di fisica. Sapendo che 89 matricole hanno superato entrambi gli esami, quante sono le matricole che hanno superato almeno uno dei due esami?
>Indicato con $M$ l’insieme delle matricole che hanno superato matematica e $F$ l’insieme di quelle che hanno superato fisica, il problema chiede di calcolare $|M \cup F|$. Si applica quindi il principio di inclusione-esclusione e si ottiene
>$$ |M\cup P|=|M|+|F|-|M\cap P|=152+144-89=207 $$

>[!esempio] _Esempio_: numeri naturali tra $1$ e $180$ non divisibili né per $3$, né per $5$
>Calcolare quanti sono i numeri naturali minori o uguali di $180$ che non sono divisibili né per $3$, né per $5$.
>Indicando con $I_{180}$ l'insieme dei numeri naturali minori o uguali di $180$ (cioè $I_{180}=\{x\in\mathbb{N}\mid x\le180\}$) e con $D_k$ il sottoinsieme di $I_{180}$ dei numeri divisibili per $k$, il problema consiste nel calcolare il [[Teoria degli insiemi#^c26337|complementare]] dell’unione dei numeri divisibili per $3$ o $5$ in $I_{180}$, cioè $|\complement_{I_{180}}(D_3\cup D_5)|=180-|D_3\cup D_5|$.
>Per il principio di inclusione-esclusione, $|D_3\cup D_5|=|D_3|+|D_5|-|D_3\cap D_5|$.
>Siccome c’è un numero divisibile per $k$ ogni $k$ elementi consecutivi di un insieme $I_n$, si ha che $|D_3|=\frac{180}3=60$ e $|D_5|=\frac{180}5=36$. Inoltre, un numero è divisibile per $3$ e per $5$ soltanto se è divisibile per il loro minimo comune multiplo $15$, cioè $D_3\cap D_5=D_{15}$ e, di conseguenza, $|D_{15}|=\frac{180}{15}=12$.
>Mettendo insieme tutto, si ha che
>$$ |\complement_{I_{180}}(D_3\cup D_5)|=180-|D_3\cup D_5|=180-(60+36-12)=180-84=96 $$
>^858acc

---

>[!proposizione] _Proposizione_: principio di inclusione-esclusione per tre insiemi
>Dati tre insiemi finiti $A$, $B$ e $C$, allora:
>$$ |A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|B\cap C|-|A\cap C|+|A\cap B\cap C| $$

> [!dimostrazione] _Dimostrazione_: tramite ragionamento logico
> Si inizia sommando il numero degli elementi di ciascun insieme, ottenendo $|A|+|B|+|C|$.
> Questo totale, però, non tiene conto del fatto che gli elementi comuni a due di questi insiemi sono stati contati due volte, per esempio un elemento in $|A\cap B|$ contribuisce al conto sia per $|A|$ che per $|B|$. Si corregge quindi sottraendo il quantitativo di elementi comuni a due insiemi, ottenendo $|A|+|B|+|C|-|A\cap B|-|B\cap C|-|A\cap C|$.
> Si considera ora il fatto che possono esserci elementi comuni ai tre insiemi, cioè in $A\cap B\cap C$. Tali elementi sono contati tre volte nella prima somma e sottratti altre tre volte nella “correzione”, in quanto un elemento in $A\cap B\cap C$ appartiene sia a $A\cap B$, sia a $B\cap C$ e sia ad $A\cap C$. Pertanto, per ottenere la formula corretta, bisogna ancora aggiungere $|A\cap B\cap C|$.
> $\blacksquare$

> [!dimostrazione] _Dimostrazione_: tramite applicazione del principio di inclusione-esclusione per due insiemi
> Una dimostrazione alternativa si può ottenere pensando inizialmente a $A\cup B$ come a un insieme a sé stante per applicare il principio su due insiemi e scrivere
> $$ |(A\cup B)\cup C|=|A\cup B|+|C|-|(A\cup B)\cap C| $$
> per poi riapplicarlo una seconda volta e scrivere
> $$ |A\cup B\cup C|=(|A|+|B|-|A\cap B|)+|C|-(|A\cap C|+|B\cap C|) $$
> $\blacksquare$

>[!osservazione] _Osservazione_: ricavare una quantità dell’equazione dalle altre sette
>L’espressione del principio di inclusione-esclusione su tre insiemi può essere usata per ricavare una qualsiasi delle quantità dell’equazione quando le altre sette sono note.

>[!esempio] _Esempio_: persone che hanno ordinato entrambe le portate
>Un cinema mette in programmazione un pomeriggio la trilogia di Matrix e con un unico biglietto si possono vedere un qualunque numero dei tre film. Alla fine della giornata il cinema ha venduto $129$ biglietti. Si sa che al primo film c’erano $109$ spettatori, $76$ al secondo e $55$ al terzo. Si sa anche che $52$ persone hanno visto i primi due film, $44$ gli ultimi due e $28$ spettatori erano presenti sia al primo che all’ultimo film. Quante persone hanno visto tutti e tre i film quel pomeriggio?
>Indicando con $S_i,\quad 1\le i\le 3$ l’insieme degli spettatori all’$i$-esimo film, se si “traducono” le informazioni in linguaggio matematico si ha che $|S_1\cup S_2\cup S_3|=129$, $|S_1|=109$, $|S_2|=76$, $|S_3|=55$, $|S_1\cap S_2|=52$, $|S_2\cap S_3|=44$ e $|S_1\cap S_3|=28$.
>Sostituendo questi numeri nella formula del principio di inclusione-esclusione per tre insiemi, si ottiene
>$$ 129=109+76+55-52-44-28+|S_1\cap S_2\cap S_3| $$
>da cui si ricava che $|S_1\cap S_2\cap S_3|=13$.

>[!esempio] _Esempio_: numeri naturali tra $1$ e $660$ divisibili per $5$, $6$ o $11$
>Si vuole calcolare quanti numeri naturali tra $1$ e $660$ sono divisibili per almeno uno tra $5$, $6$ o $11$.
>Come per l’esempio dei [numeri naturali tra $1$ e $180$ non divisibili né per $3$, né per $5$](#^858acc), si ha che nell’insieme $I_{660}$ contenente i numeri naturali da $1$ a $660$ sono presenti i sottoinsiemi $D_5$, $D_6$ e $D_{11}$ contenenti rispettivamente i numeri divisibili per $5$, $6$ e $11$.
>Si ha quindi che $|D_5|=\frac{660}5=132$, $|D_6|=\frac{660}6=110$ e $|D_{11}|=\frac{660}{11}=60$. Inoltre, $|D_5\cap D_6|=|D_{30}|=\frac{660}{30}=20$, $|D_5\cap D_11|=|D_{55}|=\frac{660}{55}=12$ e $|D_6\cap D_11|=|D_{66}|=\frac{660}{66}=10$. Infine, $|D_5\cap D_6\cap D_11|=|D_{330}|=\frac{660}{330}=2$. Applicando il principio di inclusione-esclusione, si ottiene che i numeri cercati sono
>$$ |D_5\cup D_6\cup D_{11}|=132+110+60-22-12-10+2=260 $$

>[!osservazione] _Osservazione_: principio di inclusione-esclusione su più insiemi
>Aumentando il numero degli insiemi presi in considerazione, il principio di inclusione-esclusione resta valido ma produce formule con un numero di termini sempre maggiore e perde presto la praticità di applicazione: infatti, già con quattro insiemi la formula include 16 termini. Formule più semplici si possono ottenere in casi speciali in cui alcune delle intersezioni sono vuote.

# Metodo delle scelte successive

>[!proposizione] _Proposizione_: cardinalità del prodotto cartesiano di una famiglia di insiemi
>Data una [famiglia di insiemi](Teoria%20degli%20insiemi.md#^a73b10) $\mathcal A=\{A_1,A_2,\ldots,A_k\}$, la [cardinalità del prodotto cartesiano sulla famiglia](Teoria%20degli%20insiemi.md#^423189) è uguale al prodotto delle singole cardinalità:
>$$ \left| \displaystyle\prod^k_{i=1}A_i \right|=
>\prod^k_{i=1}|A_i|=|A_1|\cdot|A_2|\cdot\ldots\cdot|A_k| $$
>^14f0e8

>[!dimostrazione] _Dimostrazione_
>Si può osservare preliminarmente che se $k\ge2$, gli insiemi $(A_1\times\ldots\times A_{k-1})\times A_k$ e $A_1\times\ldots\times A_{k-1}\times A_k$ sono [equipotenti](#^6e7153).
>Esiste infatti una biezione $f\colon(A_1\times\ldots\times A_{k-1})\times A_k\to A_1\times\ldots\times A_{k-1}\times A_k$ definita da $f((a_1,\ldots,a_{k-1}),a_k)=(a_1,\ldots,a_{k-1},a_k)$.
>Si può quindi dimostrare la proposizione per induzione su $k$. Il caso $k=2$ è già stato verificato nella proposizione sulla [cardinalità del prodotto cartesiano](Teoria%20degli%20insiemi.md#^423189), quindi si suppone $k>2$ e si ha che
>$$ \begin{align*} |A_1\times\ldots\times A_{k-1}\times A_k| &=|A_\times\ldots\times A_{k-1}|\cdot|A_k|\\ &=(n_1\cdot\ldots\cdot n_{k-1})\cdot n_k\\ &=n_1\cdot\ldots\cdot n_k \end{align*} $$
>dove la prima uguaglianza segue dall’osservazione preliminare e la seconda uguaglianza dall’ipotesi induttiva.
>$\blacksquare$

>[!osservazione] _Osservazione_: formulazione del metodo delle scelte successive
>La proposizione riguardante la [cardinalità del prodotto cartesiano di una famiglia di insiemi](#^14f0e8) si può applicare in situazioni presenti nella quotidianità se viene generalizzata in riferimento a situazioni in cui, dopo aver compiuto una determinata scelta tra un numero finito di opzioni, se ne presenta un’altra con un altro numero finito di opzioni: il cosiddetto [_metodo delle scelte successive_](#^49fa1b).

---

>[!teorema] _Teorema_: metodo delle scelte successive
>Se una certa situazione si ottiene con una successione di $k$ scelte indipendenti e per la prima scelta ci sono $n_1$ possibilità, $n_2$ per la seconda, $n_3$ per la terza e così via, il numero totale delle situazioni finali che si possono presentare è:
>$$ n=\displaystyle\prod^k_{i=1}n_i $$
>^49fa1b

>[!dimostrazione] _Dimostrazione_
>Considerando la successione di $k$ scelte indipendenti come una famiglia di $k$ insiemi $\mathcal A=\{A_1,A_2,\ldots,A_k\}$ contenente ognuno le possibili scelte che si possono effettuare, il numero delle situazioni finali che si possono presentare non è altro che la [cardinalità del prodotto cartesiano tra gli insiemi della famiglia](#^14f0e8) e, quindi, il prodotto tra le singole cardinalità degli insiemi.
>$\blacksquare$

>[!corollario] _Corollario_: scelte successive con lo stesso numero di possibilità
>Se una certa situazione si ottiene con una successione di $k$ scelte indipendenti date ognuna da $n$ possibilità, il numero totale delle situazioni finali che si possono presentare è $n^k$, in quanto esse non sono altro che %%cambiare link [disposizioni con ripetizione](https://www.notion.so/Calcolo-combinatorio-dcc12a40cae34849a6b8a6dd305ad0fb?pvs=21)%%.

> [!esempio] _Esempio_: codice PIN di uno smartphone
> Il codice PIN di uno smartphone è composto da una sequenza di $4$ cifre. Poiché le cifre disponibili sono $10$ (da 0 a 9), il totale dei PIN possibili è $10^4=10000$.

---

> [!notazione] _Notazione_: rappresentazione grafica attraverso il diagramma ad albero
> Il metodo delle scelte successive può essere visualizzato graficamente mediante l’utilizzo di un diagramma ad albero come quello della figura sotto. Esso va letto dal basso verso l’alto: il nodo al livello più basso, detto _radice_, rappresenta lo stato di partenza; le linee che dipartono da ciascun nodo, dette _rami_, rappresentano le possibili scelte; i nodi al livello più alto, detti _foglie_, sono le situazioni finali che si possono presentare. Nell’esempio le situazioni sono il risultato di una doppia scelta: per la prima ci sono $3$ alternative e per la seconda sempre $4$ altre alternative indipendenti dalle prime, da cui si ricava il totale delle foglie che è $12=3\cdot4$.
> ![](Rappresentazione%20grafica%20attraverso%20il%20diagramma%20ad%20albero.png)

%%completare%%
![](Pasted%20image%2020240212165951.png)
![](Pasted%20image%2020240212170008.png)

# Ordinamenti

> [!osservazione] _Osservazione_: ideazione dell’ordinamento
> A volte può capitare che si abbia un insieme finito $A=\{a_1,\ldots,a_n\}$ e si voglia calcolare in quali e quanti modi diversi si possano ordinare i suoi $n$ elementi. Per fare ciò, si può fare uso degli [ordinamenti](#^218a55).

> [!definizione] _Definizione_: ordinamento
> Dato un insieme $A$ finito con $|A|=n$, un **ordinamento** di $A$ è una funzione biettiva 
> $$ \begin{align*} f\colon I_n&\to A\\ n&\mapsto a \end{align*} $$
> dove $I_n=[1,n]=\{1,2,\ldots,n\}$. 
> Si denota $\mathcal O_A$ l’insieme dei possibili ordinamenti di $A$.
> ^218a55

> [!esempio] _Esempio_: possibili ordinamenti di $A=\{a,b,c\}$
> %%da scrivere%%

---

> [!proposizione] _Proposizione_: $|\mathcal O_A|=n!$
> Dato un insieme $A$ finito con $|A|=n$, i possibili ordinamenti di $A$ sono $n!$:
> $$ |\mathcal O_A|=n! $$

> [!dimostrazione] *Dimostrazione*
> Per sapere in quanti modi possibili si può costruire un ordinamento $f\colon I_n\to A$, in realtà basta costruire funzioni iniettive che, essendo [equipotenti](#^6e7153), [saranno automaticamente biettive](https://www.notion.so/Calcolo-combinatorio-dcc12a40cae34849a6b8a6dd305ad0fb?pvs=21).
> Come $f(1)$ si può scegliere un qualsiasi elemento di $A$, per esempio $f(1)=a_1$. Avendo però già scelto $a_1$, non possiamo sceglierlo nuovamente anche per $f(2)$, altrimenti si avrebbe $f(1)=f(2)$ e la funzione $f$ non sarebbe più iniettiva. In questo modo, la scelta di $f(2)$ è limitata nel sottoinsieme $A\setminus\{a_1\}$ che conta $n-1$ elementi.
> Continuando a scegliere le immagini dei numeri naturali successivi, si nota che ogni scelta $f(i)$ è limitata unicamente al sottoinsieme $A\setminus\{a_1,\ldots,a_{i-1}\}$ che conta esattamente $n-i$ elementi.
> Alla fine, per l’ultimo numero naturale $n$ si è obbligati a scegliere come $f(n)$ l’unico elemento non scelto fino a quel punto, avendo quindi una sola scelta disponibile.
> Quindi, per il metodo delle scelte successive il numero totale delle scelte, cioè il numero totale di funzioni biettive $I_n\to A$ è $n\cdot(n-1)\cdot\ldots\cdot2\cdot1=n!$.
> $\blacksquare$

> [!esempio] _Esempio_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/d32264ad-d60d-473d-b5a2-2bac2c1ac497/Untitled.png)

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/3e68f80c-f2fb-4db1-80b8-ed3aa4866271/Untitled.png)

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/5e6bafed-a74b-41b8-bd20-9383d7c669e7/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/2ea04e0b-fa83-43a5-b722-4391f8076f52/Untitled.png)

>[!osservazione] _Osservazione_:**

definizione di lista

riscrivere poi le altre definizioni come liste

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/32774ea0-6ff4-45bd-be9f-0ac1ab612f90/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/3f8b3103-c5d4-41f9-ade5-cf090f4618c5/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/4f95f5ae-e17e-4bc9-8fae-cbc6b9ef23e6/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/5f788e72-5864-4f16-aff6-401b119600a6/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/dd04b439-9cf6-4bee-8b75-42da4e368cf3/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/449801c2-d242-46d2-af33-1056be5da583/Untitled.png)

</aside>

>[!definizione] _Definizione_: anagramma**

Dato un insieme $A$ non vuoto di $n$ simboli e un ordinamento $f\colon I_n\to A$, un **anagramma** di $f$ è un ordinamento $h\colon I_n\to A$ ottenuto come composizione $h=f\circ g$ dove $g\colon I_n\to I_n$ è una biezione qualunque.

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c8c6880c-f06a-4bd8-bfef-123f1bccac26/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/8a2e3a56-56cc-47e3-a097-5c3882b67190/Untitled.png)

Anagrammi = ordinamenti con ripetizioni di elementi

</aside>

</aside>

>[!proposizione] _Proposizione_: possibili anagrammi di un insieme finito**

Dato un insieme finito $A$ con $|A|=n$ e un suo ordinamento $f\colon I_n\to A$ e supposto $\text{Im}(f)=\{a_1,\ldots,a_k\}$ dove ogni $a_i\in A$ compare $r_i\ge1$ volte in $f(1),\ldots,f(n)$, il numero totale dei suoi possibili anagrammi è:

$$ \frac{n!}{r_1!\cdot\ldots\cdot r_k!} $$

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/08927b89-1537-4ae8-b477-5287be7454f8/Untitled.png)

$\blacksquare$

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7bf66d1c-cfa2-4408-b58f-a2e7b2129e2a/Untitled.png)

</aside>

</aside>

### Disposizioni

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/8e0e69bb-0485-4e73-afa1-10590a295963/Untitled.png)

</aside>

>[!definizione] _Definizione_: disposizione con ripetizione**

Dato un insieme $A$ finito e un numero intero $k\ge1$, una **disposizione con ripetizione** di ordine $k$ in $A$ è una sequenza di $k$ elementi di $A$ non necessariamente a due a due distinti.

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/0442e3fd-dc97-43bc-b693-f8a62c9f086d/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/fdaddb87-4f94-4dda-9067-f2a617a0dcf6/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/b318b8f6-5012-4d85-8032-3a839c4d02c1/Untitled.png)

</aside>

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/1bf56fdf-a6a2-463c-aa23-ec2a155d8c16/Untitled.png)

</aside>

</aside>

>[!proposizione] _Proposizione_:** $\text{D'}_{n,k}=n^k$

Dato un insieme finito $A$ con $|A|=n$ e un numero intero $k\ge 1$, allora ci sono $n^k$ possibili disposizioni con ripetizione di ordine $k$ in $A$:

$$ \text{D'}_{n,k}=n^k $$

</aside>

>[!definizione] _Definizione_: disposizione senza ripetizione**

Dato un insieme $A$ finito e un numero intero $k\ge1$, una **disposizione senza ripetizione** (o **disposizione semplice**) di ordine $k$ in $A$ è una sequenza di $k$ elementi di $A$ a due a due distinti.

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/70309c0e-71b7-4869-b9f1-964b3f71a062/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/d719c289-8f7f-46bb-b55a-857744f6b644/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/9293f84b-0cfb-4b96-9c2f-c16a73d314ac/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/53101dac-6e42-455c-80d2-9377808169f5/Untitled.png)

</aside>

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c0309786-47af-463f-a3b2-5fa09b2b05bd/Untitled.png)

</aside>

</aside>

>[!proposizione] _Proposizione_:** $\text{D}_{n,k}=\frac{n!}{(n-k)!}=n\cdot(n-1)\cdot\ldots\cdot(n-k+1)$

Dato un insieme finito $A$ con $|A|=n$ e un numero intero $k\in[1,n]$, allora il numero delle possibili disposizioni senza ripetizione di ordine $k$ in $A$ è

$$ \text{D}_{n,k}=\frac{n!}{(n-k)!}=n\cdot(n-1)\cdot\ldots\cdot(n-k+1) $$

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/a0b00be0-1cc1-476d-bebd-9d46f5baf5c6/Untitled.png)

$\blacksquare$

</aside>

</aside>

### Combinazioni

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/e78459e6-3fe5-4edb-a518-9ddbb7df37d0/Untitled.png)

</aside>

>[!definizione] _Definizione_: combinazione senza ripetizione**

Dato un insieme $A$ finito con $|A|=n$ e un numero intero $k\in[0,n]$, una **combinazione senza ripetizione** (o **combinazione semplice**) di ordine $k$ in $A$ è un sottoinsieme $C\sube A$ con $|C|=k$.

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/2390e2c7-268e-4977-8eef-6f874d54f2bb/Untitled.png)

</aside>

</aside>

>[!proposizione] _Proposizione_:** $\text C_{n,k}=\frac{1}{k!}\text D_{n,k}=\frac{n!}{k!\cdot(n-k)!}=\frac{n\cdot(n-1)\cdot\ldots\cdot(n-k+1)}{k!}$

Dato un insieme $A$ finito con $|A|=n$ e un numero intero $k\in[0,n]$, il numero delle possibili combinazioni senza ripetizioni $C\sube A$ di ordine $k$ in $A$ è

$$ \text C_{n,k}=\frac{1}{k!}\text D_{n,k}=\frac{n!}{k!\cdot(n-k)!}=\frac{n\cdot(n-1)\cdot\ldots\cdot(n-k+1)}{k!} $$

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/9822f127-4d5d-44da-82ae-d0899eb4cf64/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/02b84760-129a-4745-bc0d-20928e0af790/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/8461a39a-2e62-4b76-9cff-9c808867bd3d/Untitled.png)

$\blacksquare$

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/9680f0b2-758b-4a44-ac30-e686f450bee4/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c0f03899-5bc2-4d81-86a2-2ef7f79175b2/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/d0586f44-eeb8-4df6-8fbf-602046c608fa/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7ac33065-b529-4244-ba7b-14b8f20e6302/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/fd39f92c-4119-429c-81e0-47b17438a9bc/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/b5dd3c6e-06b5-4ede-acd1-c4b9d078e1dc/Untitled.png)

</aside>

</aside>

>[!proposizione] _Proposizione_:** $\text C_{n,k}=\text C_{n,n-k}$

Dati due numeri interi $n$ e $k\in[0,n]$, allora

$$ \text C_{n,k}=\text C_{n,n-k} $$

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/30b9bb09-4d43-45c3-a3b4-a2373c2e6a57/Untitled.png)

$\blacksquare$

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/fcec0488-891c-45e8-a143-8618bdbf6f58/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7fd40f89-fe16-4984-836b-42f0d05b7838/Untitled.png)

</aside>

</aside>

>[!definizione] _Definizione_: combinazione con ripetizione**

Dato un insieme $A$ finito con $|A|=n$ e un numero $k\in\mathbb{N}$, una **combinazione con ripetizione** di ordine $k$ in $A$ è un sottoinsieme $C\sube A$ con $|C|=k$ in cui ciascun elemento può essere scelto più volte.

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/5b45f0af-fe03-439e-b33e-5786dc7e8b87/Untitled.png)

</aside>

</aside>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/dce5a629-0bf7-4616-b6aa-2897a183fd52/Untitled.png)

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/fd0bb387-cc05-47f9-b8fe-d16ff0cdef08/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/654105a6-5ac6-407c-a8f4-5790f0eb328f/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c90a63b6-1c05-4ca3-9985-694df6f6c5a5/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/29eea045-a378-4ab2-9df6-453be9bee860/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/a0124b03-7132-4a31-aa73-e2200e31782b/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/1832abce-327b-4f8a-a42e-760be3116aa8/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/5066cf40-8d7f-4469-9eed-b73b28a518d7/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/1db5f4b8-d188-4356-8f2e-34e0993cba97/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c475b196-3c91-4b12-b0b6-ed457d1b45bd/Untitled.png)

</aside>

>[!proposizione] _Proposizione_:** $\text C'_{n,k}=\text C_{k+n-1,n-1}=\frac{(k+n-1)!}{(n-1)!k!}$

Dato un insieme $A$ finito con $|A|=n$ e un numero $k\in\mathbb{N}$, il numero delle possibili combinazioni con ripetizioni $C\sube A$ di ordine $k$ in $A$ è

$$ \text C'_{n,k}=\text C_{k+n-1,n-1}=\frac{(k+n-1)!}{(n-1)!k!} $$

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/bb4f7b06-a274-4c48-a856-584a2cae6883/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/f8b65e74-0ebc-4a46-bd09-78e71e8e9de5/Untitled.png)

$\blacksquare$

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/4b9090d3-3d33-4160-a8b1-2629f38c5c07/Untitled.png)

= 35

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/e4afc120-042b-4cbc-8991-dcabe6037279/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/4666b6c6-172b-4b7a-a525-b74bb7ec56b3/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/e652a0d1-d24f-46d5-9229-9c5c81f847f0/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/e0603c9c-5883-471d-81d2-b8ea52dc211e/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/9f6b6c0a-b88e-4fed-8972-fd7feca4cd92/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/83f7488a-5d09-4eb4-8e67-d9cfd14e086b/Untitled.png)

</aside>

</aside>

### APPLICAZIONE COMBINATA DI METODO DELLE SCELTE SUCCESSIVE

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/b25f1435-bba3-4aab-8476-b97e0573be62/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/56684273-f7b5-4373-a8f5-1b767a69755d/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/5b615031-3f35-4e0b-9b77-a9f8dd7aaacb/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c19d326a-97bc-4d8c-a636-6bda6033720b/Untitled.png)

</aside>

### Coefficienti binomiali

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/66979430-a9aa-41df-bf03-9a3ddadc3a0b/Untitled.png)

</aside>

>[!definizione] _Definizione_: coefficiente binomiale**

Dati due numeri interi $k$ ed $n$ con $0\le k\le n$, si definisce _**coefficiente binomiale**_ il numero

$$ \text C_{n,k}=\binom{n}{k}=\frac{n!}{k!(n-k)!} $$

</aside>

<aside> <img src="/icons/star-of-life_brown.svg" alt="/icons/star-of-life_brown.svg" width="40px" /> **_Proprietà_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/7640da27-345b-4a90-b1b5-36a7f856addb/Untitled.png)

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/0c1e184b-18c2-4192-a04a-fda5376d40dc/Untitled.png)

$\blacksquare$

</aside>

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/4df71f54-f4a4-4902-a04f-75a5ffa66481/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/a965cb13-256a-4202-bfe9-f7ca2072ce72/Untitled.png)

$\blacksquare$

</aside>

</aside>

>[!osservazione] _Osservazione (O ALGORITMO?)_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/420e84ff-c2dc-40e9-928f-098b6b8f12d9/Untitled.png)

</aside>

>[!proposizione] _Teorema_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/6e26c25c-7841-423c-9672-c86284245a98/Untitled.png)

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/80d4570a-edfc-46e7-b2e0-237c8e0f6a65/Untitled.png)

$\blacksquare$

</aside>

</aside>

>[!proposizione] _Teorema/Proposizione/Lemma_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/d1c4f4cf-b0d1-44ef-b632-980600b69fac/Untitled.png)

>[!dimostrazione] _Dimostrazione_:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/1f5f90b9-58e5-4aae-b174-4e1138c8ee6e/Untitled.png)

$\blacksquare$

</aside>

>[!osservazione] _Osservazione_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/54eda5fb-743b-4798-8cd9-e23e7bbea708/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/a3649234-7ce4-41b7-a892-729ed324e45f/Untitled.png)

</aside>

>[!esempio] _Esempio_:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/cfc02782-32cb-4970-a52f-a4fec194fba9/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/c98db435-d734-4d3d-b774-64324d6e2d4d/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a714ae77-bb9a-47e7-9edc-72ecdb45d298/67dc940c-82f4-4f90-9ad5-e579b02eafff/Untitled.png)

</aside>

</aside>


