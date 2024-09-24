---
icon: TiCirclesRelation
iconColor: "#FF88FF"
number headings: first-level 1, max 6, contents ^toc, skip, 1.1)
---
%%
Mettere colori agli heading
Risolvere problema link coi colori agli heading
%%

# 1) Introduzione agli insiemi

## 1.1) L'insieme

### 1.1.1) <span style="color:#FF88FF; background:#00000000">Definizione: insieme</span>

Un **insieme**, denotato con le lettere latine maiuscole (es. $A$, $B$, $C$, ecc.), è una collezione ben definita di oggetti distinti, detti _elementi dell'insieme_, generalmente denotati con le lettere latine minuscole (es. $a$, $b$, $c$, ecc.).
Per affermare l'appartenenza di un dato elemento a un insieme si usa il simbolo $\in$ e si legge come _"appartiene a"_ (es. $a \in A$ denota che l'elemento $a$ appartiene all'insieme $A$), mentre per negarla si usa il simbolo $\notin$ e si legge come _"non appartiene a"_ (es. $b \notin B$ denota che l'elemento $b$ non appartiene all'insieme $B$).

#### 1.1.1.1) <span style="color:#888888; background:#00000000">Osservazione: restrizioni sulla natura degli elementi di un insieme</span>

Non c'è alcuna restrizione su quale sia la natura degli oggetti che possono appartenere a un insieme: essi possono essere sia oggetti "matematici" (come i numeri), ma non solo (es. l'insieme delle capitali dei Paesi nel mondo). Non è neanche detto che gli oggetti dell'insieme debbano avere una natura "omogenea" (es. può esistere un insieme che ha come elementi il numero 4, il nome del Rettore dell'Università di Torino e la Mole Antonelliana).

#### 1.1.1.2) <span style="color:#888888; background:#00000000">Osservazione: significato di _"ben definita"_</span>

La richiesta che la collezione sia ben definita significa che non deve esserci alcuna ambiguità circa il fatto che un oggetto sia o meno un elemento di un dato insieme (es. l'insieme dei professori bravi dell'Università di Torino non può essere un insieme perché non è possibile definire in modo oggettivo quali professori ne facciano parte e quali no).

#### 1.1.1.3) <span style="color:#888888; background:#00000000">Osservazione: insiemi come elementi di altri insiemi</span>

Una volta definito correttamente un certo insieme, esso è certamente un oggetto e come tale può essere esso stesso elemento di un altro insieme: gli elementi di un insieme possono essere a loro volta insiemi (es. l'insieme $B$ può essere inteso come un elemento dell'insieme $A$).
Inoltre, dati un insieme $A$ e un suo elemento l'insieme $B\in A$, gli elementi di $B$ non sono elementi di $A$ (es. se abbiamo $B=\{3,4\}$ e $A=\{0,1,2,\{3,4\}\}$, con $B \in A$ sono 4, in quanto gli elementi $\{3,4\}$ di $B$ sono contati come un unico elemento in $A$).

#### 1.1.1.4) <span style="color:#888888; background:#00000000">Osservazione: unicità degli elementi</span>

Per definizione, essendo un insieme una collezione di oggetti distinti, esso non può avere elementi ripetuti (es. gli insiemi $A=\{0,0,1,2,3\}$ e $B=\{0,1,2,3\}$ sono lo stesso insieme).

#### 1.1.1.5) <span style="color:#888888; background:#00000000">Osservazione: irrilevanza dell'ordine degli elementi</span>

In un insieme non conta l'ordine degli elementi (es. gli insiemi $A=\{0,1\}$ e $B=\{1,0\}$ sono lo stesso insieme).

## 1.2) L'insieme vuoto

### 1.2.1) <span style="color:#FF88FF; background:#00000000">Definizione: insieme vuoto</span>

Un **insieme vuoto**, denotato col simbolo $\emptyset$, è un insieme privo di elementi.

#### 1.2.1.1) <span style="color:#888888; background:#00000000">Osservazione: l'insieme $A=\{\emptyset\}$ non è vuoto</span>

L'insieme $A=\{\emptyset\}$ non è un insieme vuoto: l'insieme vuoto è privo di elementi, mentre l'insieme $A$ ha un elemento, ossia l'elemento-insieme vuoto $\emptyset \in A$ ([come già osservato](#<mark%20style="background%2088888888;">1.1.1.3\)%20BoBxGlassesAlt%20Osservazione%20insiemi%20come%20elementi%20di%20altri%20insiemi%20skip), un insieme può avere come suoi elementi altri insiemi).

## Singoletto

Definizione: Si dice _singoletto_ o _insieme unitario_ l'insieme formato da un solo elemento (es. $\{0\}$ o anche $\{\{1,2,3\}\}$)

## 1.3) Cardinalità di un insieme

### 1.3.1) <span style="color:#FF88FF; background:#00000000">Definizione: cardinalità di un insieme</span>

La **cardinalità** di un insieme $A$, denotata $|A|$, è il numero degli elementi di $A$. Quindi, se $A$ contiene un numero finito $n$ di elementi si denota $|A|=n$ (es. $|\emptyset|=0$), mentre se $A$ contiene infiniti elementi si denota $|A| = \infty$.

%% Esiste anche notazione $\#A$%%

#### 1.3.1.1) Esempio: $|\{0,1\}|=2$

Dato un insieme $A=\{0,1\}$, la sua cardinalità $|A|=|\{0,1\}|$ è pari a $2$, dal momento che gli unici elementi che contiene sono i numeri $0$ e $1$.

#### 1.3.1.2) Esempio: $|\{\{0,1\}, 0, 1\}|=3$

Dato un insieme $A=\{0,1\}$ e un insieme $B$ che ha come elementi l'insieme $A$ e i numeri $0$ e $1$, quindi $B=\{\{0,1\},0,1\}$, la sua cardinalità $|B|=|\{\{0,1\},0,1\}|$ è pari a $3$, in quanto l'insieme $A$ viene considerato come un unico elemento in $B$, mentre gli altri due numeri $0$ e $1$ vengono considerati ognuno come un elemento a sé stante.
%%mettere colori%%

#### 1.3.1.3) Esempio: $|\mathbb{N}|=\infty$

La cardinalità dell'insieme dei numeri naturali $\mathbb{N}$, quindi $|\mathbb{N}|$, è uguale a $\infty$, in quanto l'insieme $\mathbb{N}$ contiene infiniti elementi che vanno da $0$ a $+\infty$.

## 1.4) Rappresentazioni di un insieme

### 1.4.1) Notazione: rappresentazione per elencazione di un insieme

La **rappresentazione per elencazione** di un insieme prevede di indicare tutti gli elementi che appartengono ad un insieme semplicemente elencandoli uno ad uno, all'interno di parentesi graffe. Quando si rappresenta un insieme per elencazione, non ha mai importanza l'ordine con cui si scrivono gli elementi e, inoltre, tale metodo è pratico solo quando l'insieme in questione contiene pochi elementi.

#### 1.4.1.1) Esempio: $A=\{1,2,3,4,5,6,7,8,9\}$

La notazione $A=\{1,2,3,4,5,6,7,8,9\}$ definisce correttamente l'insieme $A$ come l'insieme dei numerali naturali compresi tra 1 e 9.

#### 1.4.1.2) Esempio: $B=\{\text{Francia}, \space\text{Germania}, \space\text{Svizzera}\}$

La notazione $B=\{\text{Francia}, \space\text{Germania}, \space\text{Svizzera}\}$ definisce correttamente l'insieme $B$ come un insieme contenente alcune nazioni europee.

### 1.4.2) Notazione: rappresentazione per caratteristica di un insieme

La **rappresentazione per caratteristica** di un insieme consiste nel dare una proprietà che risulti verificata da tutti gli elementi dell'insieme e solo da essi. Dunque, la forma generale della definizione di un insieme $X$ con questo metodo è porre
$$
X=\{x\in U\mid P(x)\}
$$
(da leggersi _"gli elementi $x$ dell'insieme $U$ tali che $x$ soddisfa la proprietà $P$"_) dove l'insieme $U$, detto _insieme universale_, che può essere implicito o esplicito, è definito precedentemente e funziona da ambito del discorso.

#### 1.4.2.1) Esempio: $C=\{\text{cittadini italiani}\},D=\{x\in\mathbb{R}\mid x^2>1\}$

Le notazioni $C=\{\text{cittadini italiani}\}$ e $D=\{x\in\mathbb{R}\mid x^2>1\}$ definiscono correttamente due insiemi nonostante non siano elencati esplicitamente tutti i loro elementi, specialmente nel caso dell'insieme $D$ che sarebbe matematicamente impossibile, essendo questo insieme infinito.
In particolare, gli oggetti a cui applicare i due criteri sono presi a priori da un certo insieme di riferimento, esplicito nel caso di $D$ (l'insieme $\mathbb{R}$ dei numeri reali) ed implicito nel caso di $C$ (avrebbe senso applicare il criterio su un insieme di esseri umani).

### 1.4.3) Notazione: rappresentazione grafica di un insieme

La **rappresentazione grafica di un insieme** consiste nel rappresentarlo con una regione di piano limitata da una curva chiusa: gli elementi dell'insieme sono scritti all'interno della linea chiusa, mentre gli elementi che non appartengono all'insieme stanno all'esterno. Il nome dell'insieme, invece, viene posto all'esterno della linea chiusa vicino a essa. Forme grafiche di questo tipo sono generalmente denominate _diagrammi di Eulero-Venn_ ed offrono un supporto intuitivo notevole nel rappresentare gli insiemi.

### 1.4.4) Notazione: rappresentazione per intervalli di un insieme

La **rappresentazione per intervalli di un insieme** si può usare nel caso in cui l'insieme contiene tutti i numeri (generalmente in $\mathbb{R}$) compresi tra due valori detti _estremi dell'intervallo_, che possono essere compresi o meno nell'intervallo stesso. Per indicare l'intervallo, quindi, si racchiudono i due valori, separati da una virgola, in due parentesi che sono quadre se i valori sono compresi nell'intervallo o, altrimenti, tonde.

%%fare un esempio con solo estremi esclusi e uno con solo estremi inclusi%%

#### 1.4.4.1) <span style="color:#888888; background:#00000000">Osservazione: intervalli con un solo estremo incluso</span>

Gli intervalli non devono necessariamente avere entrambi gli intervalli inclusi o esclusi: possono averne anche uno solo incluso e l'altro escluso.

##### 1.4.4.1.1) Esempio: $A=\{x\in\mathbb{R}\mid x >-1 \land x \le 4\} = (-1,4]$

Dato un insieme $A=\{x\in\mathbb{R}\mid x >-1 \land x \le 4\}$, esso si può anche rappresentare come l'intervallo $(-1,4]$ dal momento che esso racchiude tutti i numeri $x\in\mathbb{R}$ compresi tra $-1$ escluso e $4$ incluso.

# 2) Sottoinsiemi

## 2.1) <span style="color:#FF88FF; background:#00000000">Definizione: sottoinsieme</span>

Dati due insiemi $A$ e $B$, $B$ si dice _**sottoinsieme**_ di $A$ e si denota con $B \subseteq A$ se ogni elemento di $B$ è anche un elemento di $A$:
$$ B\subseteq A=\{b \in B \mid b \in A\} $$
$A$ viene chiamato _soprainsieme_ di $B$.

### 2.1.1) Esempio: sottoinsiemi di $A=\{0,1,2,3,4\}$

Dato un insieme $A=\{0,1,2,3,4\}$, possibili sottoinsiemi di $A$ sono gli insiemi $B=\{0,1,2\}$ e $C=\{4\}$, in quanto gli elementi che contengono appartengono anche ad $A$. Sono sottoinsiemi di $A$ anche l'insieme vuoto $\emptyset$ e un insieme $D=\{0,1,2,3,4\}$, ossia i suoi sottoinsiemi banali.

## 2.2) <span style="color:#FF88FF; background:#00000000">Definizione: sottoinsiemi banali</span>

Per ogni insieme $X$ si ha sempre che $\emptyset \subseteq X$ e $X \subseteq X$: questi sono detti ***sottoinsiemi banali*** di $X$.

### 2.2.1) Esempio: sottoinsiemi banali di $A=\{0,1,2,3,4\}$

Dato un insieme $A=\{0,1,2,3,4\}$, i suoi sottoinsiemi banali sono l'insieme vuoto $\emptyset$ e l'insieme $D=\{0,1,2,3,4\}$.

## 2.3) <span style="color:#FF88FF; background:#00000000">Definizione: sottoinsieme proprio</span>

Dati un insieme $A$ e un suo sottoinsieme $B$ con $B \ne A$, $B$ è detto sottoinsieme proprio di $A$ e si può indicare anche con il simbolo $\subsetneq$ per evidenziarne la disuguaglianza: $B\subsetneq A$.

### 2.3.1) Esempio: sottoinsiemi propri di $A=\{0,1,2,3,4\}$

Dato un insieme $A=\{0,1,2,3,4\}$, dei suoi possibili sottoinsiemi propri sono gli insiemi $E=\{1,3,4\}$ ed $F=\{0,1,2,3\}$.

## 2.4) Insieme delle parti

### 2.4.1) <span style="color:#FF88FF; background:#00000000">Definizione: insieme delle parti</span>

Dato un insieme $A$, si definisce insieme delle parti di $A$ e si denota $\mathcal{P}(A)$ l'insieme i cui elementi sono tutti i sottoinsiemi di $A$:
$$\mathcal{P}(A)=\{B\mid B \subseteq A\}$$

#### 2.4.1.1) Esempio: insieme delle parti di $A=\{a,b,c\}$

Dato un insieme $A=\{a,b,c\}$, si ha $\mathcal{P}(A)=\{\emptyset, \{a\}, \{b\}, \{c\}, \{a,b\}, \{b,c\}, \{a,c\},A\}$.

#### 2.4.1.2) <span style="color:#888888; background:#00000000">Osservazione: $\mathcal{P}(\emptyset)=\{\emptyset\}$</span>

L'unico sottoinsieme di $\emptyset$ è $\{\emptyset\}$. Pertanto, $\mathcal{P}(\emptyset)=\{\emptyset\}$ e, dunque, $\mathcal{P}(\emptyset)\ne\emptyset$.

#### 2.4.1.3) <span style="color:#888888; background:#00000000">Osservazione: $\mathcal{P}(\{a\})=\{\emptyset,\{a\}\}$</span>

Dato un insieme $A$ con un solo elemento $a \in A$, gli unici sottoinsiemi sono quelli [banali](#<mark%20style="background%20FF88FF88;">%20RiBookOpenFill%20Definizione%20sottoinsiemi%20banali%20%20skip), quindi $\mathcal{P}(A)=\mathcal{P}(\{a\})=\{\emptyset,\{a\}\}$.

# 3) Uguaglianza di due insiemi

## 3.1) Proposizione: uguaglianza di due insiemi

Dati due insiemi $A$ e $B$, essi sono uguali solo se $A\subseteq B$ e $B\subseteq A$ contemporaneamente.

### 3.1.1) Dimostrazione

Se $A=B$, allora $A$ e $B$ hanno esattamente gli stessi elementi, cioè ogni elemento di $A$ è anche un elemento di $B$ (e quindi $A \subseteq B$) e ogni elemento di $B$ è anche un elemento di $A$ (e quindi $B \subseteq A$).
Viceversa, se $A \subseteq B$ e $B \subseteq A$, allora $A$ e $B$ devono contenere esattamente gli stessi elementi, perché l'esistenza di un $x \in A \mid x \notin B$ contraddice l'ipotesi $A \subseteq B$ e l'esistenza di un $y \in B \mid y \notin A$ contraddice l'ipotesi $B \subseteq A$.
$\blacksquare$

# 4) Operazioni sugli insiemi

## 4.1) Intersezione

### 4.1.1) <span style="color:#FF88FF; background:#00000000">Definizione: intersezione di due insiemi</span>

Dati due insiemi $A$ e $B$, si dice _**intersezione**_ di $A$ e $B$ e si denota $A\cap B$ l'insieme che comprende gli elementi che appartengono contemporaneamente sia ad $A$ che a $B$:
$$ A \cap B = \{x \mid x \in A \land x \in B\} $$
Due insiemi $A$ e $B$ si dicono _disgiunti_ se non hanno elementi in comune:
$$ A \cap B = \emptyset $$

#### 4.1.1.1) Esempio: intersezione di due insiemi

Dati due insiemi $A=\{n \in \mathbb{N} \mid n \text{ è pari}\}$ e $B=\{n\in\mathbb{N}\mid10\le n^2 \le200\}$, allora si ha che $A \cap B = \{4,6,8,10,12,14\}$.​

#### 4.1.1.2) Esempio: intersezione di tre insiemi

Dati tre insiemi $A=\{a,b,c,d,e\}$, $B=\{d,e,f,g\}$ e $C=\{g,h,i\}$, allora si ha che: $A\cap B = \{d,e\}$, $B\cap C = \{g\}$, $A \cap C = \emptyset$ e $A\cap B\cap C=\emptyset$.

#### 4.1.1.3) Esempio: intersezione di insiemi delle parti

Dato un insieme $X=\{a,b,c,d\}$ e dati due insiemi
$$
A=\{S\in \mathcal{P}(X)\mid|S|=2\}=\{\{a,b\}, \{a,c\}, \{a,d\}, \{b,c\}, \{b,d\}, \{c,d\}\}, \\
B=\{S\in \mathcal{P}(X)\mid c \in S\}=\{ \{c\}, \{a,c\}, \{b,c\}, \{c,d\}, \{a,b,c\}, \{b,c,d\}, \{a,c,d\}, \{a,b,c,d\}\}
$$
allora $A \cap B = \{\{a,c\},\{b,c\},\{c,d\}\}$.

## 4.2) Unione

### 4.2.1) <span style="color:#FF88FF; background:#00000000">Definizione: unione di due insiemi</span>

Dati due insiemi $A$ e $B$, si dice _**unione**_ di $A$ e $B$ e si denota $A\cup B$ l'insieme contenente tutti gli elementi di entrambi gli insiemi:
$$ A \cup B = \{x \mid x \in A \lor x \in B\} $$
Gli elementi che si trovano sia in $A$ che in $B$ vengono presi in considerazione una volta sola perché, [come già osservato](#^Insieme), non ci possono essere elementi ripetuti in un insieme.

#### 4.2.1.1) Esempio: unione di due insiemi

Dati due insiemi $A=\{0,1\}$ e $B=\{2,3,4\}$, si ha che $A\cup B=\{0,1,2,3,4\}$.

#### 4.2.1.2) Esempio: unione di tre insiemi

Dati tre insiemi
$$
A=\{a,b,c,d,e\} \\
B=\{d,e,f,g\} \\
C=\{g,h,i\} \\
$$
allora si ha che $A \cup B = \{a,b,c,d,e,f,g\}$, $B\cup C = \{d,e,f,g,h,i\}$, $A \cup C = \{a,b,c,d,e,g,h,i\}$ e $A\cup B \cup C = \{a,b,c,d,e,f,g,h,i\}$.

#### 4.2.1.3) Esempio: unione degli insiemi dei numeri pari e dispari

Dati due insiemi $A=\{n \in \mathbb{N} \mid n\mod2=0\}$ e $B=\{n \in \mathbb{N} \mid n\mod2=1\}$, ossia rispettivamente gli insiemi dei numeri naturali pari e dispari, allora $A \cup B = \mathbb{N}$.

## 4.3) Differenza

### 4.3.1) <span style="color:#FF88FF; background:#00000000">Definizione: differenza tra due insiemi</span>

Dati due insiemi $A$ e $B$, si dice _**differenza**_ tra $A$ e $B$ e si denota $A\setminus B$ l'insieme degli elementi presenti in $A$ ma non in $B$:
$$ A \setminus B = \{x \mid x \in A \land x \notin B\} $$

#### 4.3.1.1) Esempio: differenza tra due insiemi

Dati due insiemi $A=\{0,1,2\}$ e $B=\{2\}$, si ha che $A\setminus B=\{0,1\}$.

## 4.4) Complementare

>[!definizione]+ Definizione: complementare di un insieme
>Dati due insiemi $A$ e $B$ con $A\subseteq B$, si dice _**complementare**_ di $A$ in $B$ e si denota $\complement_B(A)$ il sottoinsieme degli elementi di $B$ non in $A$:
>$$\complement_B(A)=\{x\mid x\in B \land x \notin A\}$$
>
>>[!osservazione]+ Osservazione: $\complement_B(A)=B\backslash A$
>>Dati due insiemi $A$ e $B$ con $A\subseteq B$, il complementare $\complement_B(A)$ di $A$ in $B$ si può esprimere anche come la [differenza](#^Differenza-tra-due-insiemi) $B\backslash A$ tra $B$ e $A$: $\complement_B(A)=B\backslash A$.
>
>>[!osservazione]+ Osservazione: $\complement_B(\complement_B(A)) = A$
>>Dati due insiemi $A$ e $B$ con $A\subseteq B$, il doppio complementare $\complement_B(\complement_B(A))$ di $A$ in $B$ è sempre uguale ad $A$: $\complement_B(\complement_B(A)) = A$.
>
>>[!osservazione]+ Osservazione: $\Bbb{I}=\complement_\Bbb{R}(\Bbb{Q})$
>>L'insieme dei numeri irrazionali $\Bbb{I}$ si può esprimere come complementare di $\Bbb{Q}$ in $\Bbb{R}$: $\Bbb{I}=\complement_\Bbb{R}(\Bbb{Q})$.
^Complementare-di-un-insieme

## 4.5) Prodotto cartesiano

>[!definizione]+ Definizione: prodotto cartesiano di due insiemi
>Dati due insiemi $A$ e $B$, si definisce ***prodotto cartesiano*** di $A$ e $B$ e si denota $A \times B$ l'insieme i cui elementi sono coppie di elementi con il primo elemento in $A$ e il secondo in $B$:
>$$A \times B=\{(a,b)\mid a \in A \land b \in B\}$$
>
>>[!esempio]+ Esempio: prodotto cartesiano tra due insiemi
>>Dati due insiemi $A=\{1,2\}$ e $B=\{3,4,5\}$, si ha che $A\times B=\{(1,3),(1,4),(1,5),(2,3),(2,4),(2,5)\}$.​
>
>>[!esempio]+ Esempio: prodotto cartesiano tra due intervalli e relativa rappresentazione grafica
>>Dati due insiemi $A=\{x\mid 0\le x\le1\}$ e $B=\{x\mid -1\le x\le0\}$, %%collegare a rappresentazione intervalli%% rappresentabili anche con gli intervalli chiusi $A=[0,1]$ e $B=[-1,0]$, il loro prodotto cartesiano $A\times B$ è rappresentabile su un piano cartesiano come l'insieme di tutti i punti compresi tra il punto $\color{Red}A(0,1)$ e il punto $\color{Green}B(-1,0)$:
>>
>>![[Prodotto cartesiano tra due intervalli e relativa rappresentazione grafica.png]]
>
>>[!osservazione]+ Osservazione: $A\times\emptyset=\emptyset$
>>Il prodotto cartesiano tra un insieme $A$ e l'insieme vuoto $\emptyset$ è sempre pari all'insieme vuoto $\emptyset$:
>$$A\times\emptyset=\emptyset$$
>
>>[!osservazione]+ Osservazione: $A \ne \emptyset \land B \ne \emptyset \implies A \times B \ne \emptyset$
>>Il prodotto cartesiano tra due insiemi A e B non vuoti è sempre pari a un insieme non vuoto:
>$$A \ne \emptyset \land B \ne \emptyset \implies A \times B \ne \emptyset$$
>
>>[!osservazione]+ Osservazione: valenza geometrica del prodotto cartesiano
>>Se si interpreta l'insieme $\mathbb{R}$ dei numeri reali come una retta, allora il prodotto cartesiano $\mathbb{R}^2=\mathbb{R}\times\mathbb{R}$ è l'insieme formato da tutte le coppie $(x, y)$ di numeri reali:
>>$$ \mathbb{R}^2 = \{(x, y)\mid x \in \mathbb{R}\land y \in \mathbb{R}\} $$
>>In altre parole, $\mathbb{R}^2$ non è nient'altro che il piano cartesiano, in cui un elemento di $\mathbb{R}^2$ è un punto identificato dalla coppia $(x, y)$; stesso discorso si può fare per l'insieme $\mathbb{R}^3$, ossia l'insieme che rappresenta lo spazio cartesiano in cui i punti sono identificati dalle tre coordinate $(x,y,z)$.
^Prodotto-cartesiano-di-due-insiemi

>[!proposizione]+ _Proposizione:_ cardinalità del prodotto cartesiano
>Dati due insiemi finiti $A$ e $B$, con $|A|=m$ e $|B|=n$, allora la cardinalità del loro prodotto cartesiano $|A\times B|$ è uguale al prodotto delle loro cardinalità $m\cdot n$; se, invece, almeno uno tra $A$ e $B$ è infinito, allora anche $|A \times B|$ è infinito:
>$$|A|=m,|B|=n\implies|A\times B| = \begin{cases} m\cdot n &\text{se } m,n\ne\infty \\ \infty &\text{se } m,n=\infty \end{cases}$$
>
>>[!dimostrazione]+ _Dimostrazione_ 
>>Se $A$ e $B$ sono finiti con $|A|=m$ e $|B|=n$, si possono numerare ed elencare i loro elementi come $A=\{a_1,a_2,...,a_m\}$ e $B=\{b_1,b_2,...,b_n\}$ e si possono organizzare gli elementi di $A \times B$ in una tabella:
>>$$\begin{matrix} (a_1,b_1) & (a_1,b_2) & \dots & (a_1,b_n) \\ (a_2,b_1) & (a_2,b_2) & \dots & (a_2,b_n) \\ \vdots & \vdots & \ddots & \vdots \\ (a_m,b_1) & (a_m,b_2) & \dots & (a_m,b_n) \\ \end{matrix}$$
>>La tabella include chiaramente tutti gli elementi di $A \times B$ una volta sola e, quindi, devono essere $m \cdot n$ in totale, essendo $m$ in verticale ed $n$ in orizzontale. Il caso in cui uno degli insieme è infinito è chiaro, in quanto la tabella risulterà avere righe o colonne infinite.
>>$\blacksquare$
^Cardinalita-del-prodotto-cartesiano

# 5) Proprietà delle operazioni sugli insiemi

>[!proprieta]+ _Proprietà:_ associatività
>Dati tre insiemi $A,B,C$, per la proprietà **associativa** degli insiemi valgono le seguenti identità:
>- $(A\cap B)\cap C=A\cap (B\cap C)$;
>- $(A\cup B)\cup C=A\cup(B\cup C)$.

>[!proprieta]+ _Proprietà:_ idempotenza
>Dato un insieme $A$, per la proprietà di **idempotenza** degli insiemi valgono le seguenti identità:
>- $A\cap A=A$;
>- $A\cap\emptyset=\emptyset$;
>- $A\cup A=A$;
>- $A\cup\emptyset=A$.

>[!proprieta]+ _Proprietà:_ distributività
>Dati tre insiemi $A$, $B$ e $C$, per la proprietà **distributiva** degli insiemi valgono le seguenti identità:
>- $(A\cup B)\cap C = (A\cap C) \cup (B \cap C)$;
>- $(A\cap B)\cup C = (A\cup C) \cap (B \cup C)$.
>
>>[!dimostrazione]+ _Dimostrazione:_ $(A\cup B)\cap C = (A\cap C) \cup (B \cap C)$
>>La prima identità $(A\cup B)\cap C = (A\cap C) \cup (B \cap C)$ si dimostra usando la tecnica della doppia inclusione usata anche per dimostrare l'[uguaglianza di due insiemi](#^Uguaglianza-di-due-insiemi).
>>Quindi, si deve dimostrare che $(A\cup B)\cap C\subseteq (A\cap C) \cup (B \cap C)$ e $(A\cap C) \cup (B \cap C) \subseteq (A\cup B)\cap C$.
>>###### Dimostrazione di $(A\cup B)\cap C\subseteq (A\cap C) \cup (B \cap C)$
>>- Sia $x \in (A \cup B) \cap C$;
>>- Sviluppando le definizioni, si trova che $x\in (A \cup B) \land x \in C$, quindi $(x\in A \lor x \in B) \land x \in C$;
>>- Si può ipotizzare che $x$ si trovi:
>>	- In $A$, quindi si ha che $x \in A \cap C$;
>>	- In $B$, quindi si ha che $x \in B \cap C$;
>>	- Sia in $A$ che in $B$, quindi si ha che $x \in (A \cap C) \cup (B \cap C)$, che può valere anche per i due casi precedenti;
>>- Si dimostra quindi così che $(A\cup B)\cap C\subseteq (A\cap C) \cup (B \cap C)$.
>>###### Dimostrazione di $(A\cap C) \cup (B \cap C) \subseteq (A\cup B)\cap C​$
>>- Sia $x\in(A\cap C) \cup (B \cap C)$;
>>- Sviluppando le definizioni, si trova che $x\in A \cap C$ oppure $x \in B \cap C$;
>>- Prendendo il caso di $x\in A\cap C$ (ma vale ugualmente anche per $x \in B \cap C$), si ha che $x$ si deve trovare necessariamente in $A$, quindi $x\in (A\cup B)\cap C$ (perché non importa se $x$ si trova in $A$ e $B$);
>>- Si dimostra quindi così che $(A\cap C) \cup (B \cap C) \subseteq (A\cup B)\cap C$.
>>
>>Avendo dimostrato quindi entrambe le inclusioni, per la tecnica della doppia inclusione si può affermare che $(A\cup B)\cap C = (A\cap C) \cup (B \cap C)$.
>>$\blacksquare$
>
>>[!dimostrazione]+ _Dimostrazione:_ $(A\cap B)\cup C = (A\cup C) \cap (B \cup C)$ 
>>%%finire di scrivere%%

>[!proprieta]+ _Proprietà:_ leggi di De Morgan
>Dato un insieme $X$ e due suoi sottoinsiemi $A,B\subseteq X$, allora valgono le seguenti identità dette ***leggi di De Morgan***:
>- $\complement_X(A\cap B)=\complement_X(A)\cup \complement_X(B)$;
>- $\complement_X(A\cup B)=\complement_X(A)\cap \complement_X(B)$.
>
>>[!dimostrazione]+ _Dimostrazione:_ $\complement_X(A\cap B)=\complement_X(A)\cup \complement_X(B)$
>%%finire%%
>>![[Pasted image 20240210184935.png]]
>
>>[!dimostrazione]+ _Dimostrazione:_ $\complement_X(A\cup B)=\complement_X(A)\cap \complement_X(B)$
>>%%finire%%

# 6) Famiglia di insiemi

>[!definizione]+ Definizione: famiglia di insiemi
>Un insieme $\mathcal A$ si definisce famiglia di insiemi se gli $n$ elementi che contiene sono tutti insiemi:
>$$\mathcal A=\{A_i : i\in[1,n]\}$$
>^a73b10

>[!definizione]+ Definizione: intersezione e unione su famiglie di insiemi
>Data una famiglia di insiemi $\mathcal A$, l'unione degli $A_i$ è l'insieme degli elementi che appartengono a un qualsiasi $A_i$:
>$$\displaystyle\bigcup_{i=1}^nA_i=\{x : x\in A_i,\quad \exists i\in [1,n]\}$$
>L'intersezione degli $A_i$ è l'insieme degli elementi che appartengono a ogni $A_i$:
>$$\displaystyle\bigcap_{i=1}^nA_i=\{x : x\in A_i,\quad\forall i \in [1,n]\}$$
>
>>[!esempio]+ Esempio: intersezione di una famiglia di insiemi $\mathcal A$
>Data una famiglia di insiemi $\mathcal A$ formata dagli $n$-esimi insiemi $A_n\in\mathcal A$ con $n \in \mathbb{N}\setminus\{0\}$ in cui ogni $A_n$ è definito come l'[intervallo aperto](#^Insieme) che va da $-\frac{1}{n}$ a $\frac{1}{n}$, quindi $A_n=(-\frac{1}{n},\frac{1}{n})$. Si ha quindi che $\displaystyle\bigcap_{n=0}^{+\infty}A_n=\{0\}$ perché $0 \in A_n$ per ogni $n \in \mathbb{N}\setminus\{0\}$.

>[!definizione]+ Definizione: prodotto cartesiano su famiglie di insiemi
>Data una famiglia di insiemi $\mathcal A=\{A_1,A_2,\ldots,A_n\}$, il prodotto cartesiano degli $A_i$ è l'insieme delle $n$-ple $(a_1,a_2,\ldots,a_n)$ con $a_i\in A_i$:
>$$ \displaystyle\prod_{i=1}^nA_i=\{(a_1,a_2,\ldots,a_n) : a_i\in A_i,\quad \forall i\in [1,n]\} $$
>
>>[!esempio]+ Esempio: prodotto cartesiano tra tre insiemi
>Dati tre insiemi $A=\{1,2\}$, $B=\{3,4\}$ e $C=\{5,6\}$, allora si ha che $A\times B\times C=\{(1,3,5),(1,3,6),(1,4,5),(1,4,6),(2,3,5),(2,3,6),(2,4,5),(2,4,6)\}$.

# 7) Ricoprimento e partizione

>[!definizione]+ Definizione: ricoprimento
>Dati un insieme $X$ e una famiglia di sottoinsiemi $\mathcal A$ di $X$, allora la famiglia $\mathcal A$ si definisce un _**ricoprimento**_ di $X$ se l'unione di tutti gli $n$ insiemi $A_i$ della famiglia dà come risultato $X$:
>$$ \displaystyle\bigcup_{i=1}^nA_i=X $$
>^1fcd51
>
>>[!esempio]+ Esempio: ricoprimento di $\mathbb{R}$ con 3 sottoinsiemi
>Dati un insieme $X = \mathbb{R}$ e una famiglia $\mathcal A=\{A_1,A_2,A_3\}$ con $A_1=\{x\in\mathbb{R} : x<0\}$, $A_2=\{x\in\mathbb{R} : x>0\}$ e $A_3=\{x\in\mathbb{R} : -1<x<1\}$, allora la famiglia $\mathcal A$ è un ricoprimento di $X$ perché comprende qualsiasi numero reale $x$ in $\mathbb{R}$:
>>- Se $x$ è negativo, allora è compreso in $A_1=\{x\in\mathbb{R} : x<0\}$;
>>- Se $x$ è positivo, allora è compreso in $A_2=\{x\in\mathbb{R} : x>0\}$;
>>- Se $x=0$, allora è compreso in $A_3=\{x\in\mathbb{R} : -1<x<1\}$.
>
>>[!esempio]+ Esempio: ricoprimento di $\mathbb{R}$ con infiniti sottoinsiemi
>>Dati un insieme $X=\mathbb{R}$ e una famiglia di insiemi $\mathcal A$ con $A_n=[n,n+1]$, allora la famiglia $\mathcal A$ è un ricoprimento di $X$ perché, per un qualsiasi indice $n\in\mathbb{Z}$, esisterà un insieme $A_n$ i cui elementi saranno tutti quei numeri reali compresi nell'intervallo $[n,n+1]$ con gli estremi inclusi. In questo modo, si riesce a ricoprire l'intero insieme $X$ (e quindi $\mathbb{R}$).
>
>>[!esempio]+ Esempio: ricoprimento di $\mathbb{R}$ con infiniti sottoinsiemi
>>Dati un insieme $X=\mathbb{R}$ e una famiglia di insiemi $\mathcal A$ con $A_n=[n,n+1]$, allora la famiglia $\mathcal A$ è un ricoprimento di $X$ perché, per un qualsiasi indice $n\in\mathbb{Z}$, esisterà un insieme $A_n$ i cui elementi saranno tutti quei numeri reali compresi nell'intervallo $[n,n+1]$ con gli estremi inclusi. In questo modo, si riesce a ricoprire l'intero insieme $X$ (e quindi $\mathbb{R}$).
^Ricoprimento

>[!definizione]+ Definizione: partizione
>Dati un insieme $X$ e una famiglia di insiemi $\mathcal A$ una famiglia di $n$ sottoinsiemi di $X$, allora la famiglia $\mathcal A$ è una **partizione** di $X$ se e solo se sono soddisfatte le seguenti condizioni:
>1. È un [ricoprimento](#^Ricoprimento) di $X$;
>2. Non ci sono sottoinsiemi vuoti, ossia $A_i \ne \emptyset, \quad \forall i \in [1,n]$;
>3. Non ci sono due diversi sottoinsiemi con elementi in comune, ossia $A_i\cap A_j = \emptyset,\quad\forall i,j \in [1,n]:i \ne j$.
>
>>[!esempio]+ Esempio: partizione di $\mathbb{Z}$ tra numeri pari e dispari
>>Dati un insieme $X = \mathbb{Z}$ e una famiglia $\mathcal A=\{A_1,A_2\}$ con $A_1=\{x : 2x \in X\}$ e $A_2=\{x : 2x+1 \in X\}$, allora la famiglia $\mathcal A$ è una partizione di $X$ perché è un ricoprimento (condizione 1 della definizione), non contiene elementi vuoti (condizione 2) e $A_1 \cap A_2=\emptyset$ perché non esistono numeri sia pari che dispari (condizione 3).
>
>>[!esempio]+ Esempio: partizione tra un insieme e il suo complementare
>>Dato un sottoinsieme [[#^5cc3b3|non banale]]+ $A$ di un insieme $X$ (quindi $A \ne X$), allora $\{A,\complement_X(A)\}$ è una partizione di $X$ perché, per definizione, $A\cap \complement_X(A)=\emptyset$.
>
>>[!esempio]+ Esempio: partizione di $\Bbb{Q}$ come famiglia di insiemi di frazioni
>>Data una famiglia $\mathcal P$ di sottoinsiemi di $\Bbb{Q}$ con $P_n=\{q=\frac{a}{n}\in\Bbb{Q} : a \in \mathbb{Z} \land \frac{a}{n}\text{ è ridotta ai minimi termini}\}$, allora $\mathcal P$ è una partizione di $\Bbb{Q}$ perché la scrittura di un numero razionale come frazione ridotta ai minimi termini con denominatore positivo è unica (quindi $P_m \cap P_n=\emptyset,\quad \forall m,n\in\mathbb{N}:m\ne n$). Inoltre, si può notare che $P_1=\mathbb{Z}$.

# 8) Relazioni tra insiemi

>[!definizione]+ Definizione: relazione tra due insiemi
>Dati due insiemi $A$ e $B$ non vuoti, si definisce _**relazione**_ tra $A$ e $B$ e si denota $A\mathcal{R}B$ un sottoinsieme del [[#^f8c559|prodotto cartesiano]]+ tra $A$ e $B$:
>$$ A \mathcal{R} B = \{(a,b) : (a,b) \in A \times B\} $$
>^2f81d7
>
>>[!esempio]+ Esempio: relazione tra due insiemi
>>Dati due insiemi $A=\{1,2,3\}$ e $B=\{3,4,5\}$, una loro possibile relazione è $A\mathcal{R}B=\{(1,3), (3,3), (2,4)\}$.
>
>>[!osservazione]+ Osservazione: relazioni tra più insiemi o tra una famiglia di insiemi
>>Una relazione si può stabilire anche tra un numero $n$ di insiemi $S_1,S_2,\ldots,S_n$ ed è un sottoinsieme del loro prodotto cartesiano $S_1\times S_2\times\ldots\times S_n$.
>>In egual modo, una relazione su una [[#^a73b10|famiglia di insiemi]]+ $\mathcal S$ è un sottoinsieme del loro prodotto cartesiano $\displaystyle\prod_{i=1}^nS_i$.

>[!definizione]+ Definizione: relazione di equivalenza
>Dato un insieme $X$, si definisce _**relazione di equivalenza**_ su $X$ e si denota con il simbolo $\sim$ una [[#^2f81d7|relazione]]+ che occorre fra alcune coppie di elementi di $X$ e che soddisfa le seguenti proprietà:
>1. _Riflessività_: $x\sim x,\quad \forall x \in X$;
>2. _Simmetria_: $x\sim y\implies y\sim x,\quad \forall x,y\in X$;
>3. _Transitività_: $x\sim y,y\sim z\implies x\sim z,\quad \forall x,y,z\in X$.
>
>>[!esempio]+ Esempio: relazione di divisibilità tra due interi
>>Dato un numero naturale $n\in \mathbb{N}$, un numero intero $x\in\mathbb{Z}$ si dice _**divisibile**_ per $n$ e si denota con $n|x$ se esiste un $k\in \mathbb{Z}$ tale che $kn=x$. Si può definire una relazione di equivalenza sull'insieme $\mathbb{Z}$ degli interi affermando che, dati due elementi $x,y\in\mathbb{Z}$, $x$ è in relazione a $y$ se la loro differenza è divisibile per $n$:
>>$$ x\sim y\iff n|(x-y) $$
>>Si può dimostrare che questa è una relazione di equivalenza verificando le tre proprietà:
>>1. _Riflessività_: $n|(x-x)\implies n|0$ vale, perché $0$ è divisibile per qualsiasi numero naturale $n$;
>>2. _Simmetria_: $n|(x-y)\implies n|(y-x)$ vale, perché se $x-y$ è divisibile per $n$, allora è divisibile anche il suo opposto $y-x$; per esempio, $2|(12-6)\implies 2|(6-12),\quad n=2,x=12,y=6$.
>>3. _Transitività_: $n|(x-y),n|(y-z)\implies n|(x-z)$ vale, perché se $x-y$ e $y-z$ sono divisibili per $n$, lo è anche $x-z$; per esempio, $2|(12-6),2|(6-4)\implies 2|(12-4),\quad n=2,x=12,y=6,z=4$.

>[!definizione]+ Definizione: classe di equivalenza e insieme quoziente
>Dato un insieme $A$ e un insieme $X$, si dice _**classe di equivalenza**_ di $a$ rispetto alla relazione di equivalenza $\sim$ e si indica con $[a]_\sim$ l'insieme degli elementi di $X$ che hanno una relazione di equivalenza con $a$:
>$$ [a]_\sim=\{x\in X\mid x\sim a\} $$
>L'insieme delle classi di equivalenza $[a]_\sim$ si dice _**insieme quoziente**_ di $X$ per la relazione $\sim$ e si indica con $X/\sim$:
>$$ X/\sim =\{[a]_\sim\mid a\in X\} $$
>
>>[!esempio]+ Esempio: relazione di equivalenza su automobili con stesso colore
>>Dato un insieme $X$ di tutte le automobili e una sua relazione di equivalenza $\sim$ letta come _"ha lo stesso colore di"_, allora una classe di equivalenza può essere quella che comprende tutte le automobili verdi, mentre l'insieme quoziente $X/\sim$ è l'insieme dei colori delle automobili.
>
>>[!esempio]+ Esempio: insieme $\Bbb Q$ dei numeri razionali come insieme quoziente
>>L'insieme $\Bbb Q$ dei numeri razionali può essere espresso come un insieme quoziente. Data una coppia $(p,q)$ ottenuta dal prodotto cartesiano $\mathbb{Z}\times (\mathbb{Z}\setminus\{0\})$ (quindi $p$ può essere qualsiasi numero intero, mentre $q$ qualsiasi numero intero eccetto lo $0$), si può definire una relazione di equivalenza come:
>>$$ (p,q)\sim(p',q')\iff pq'=p'q $$
>>Ciò è verificabile se si interpreta la coppia $(p,q)$ come una frazione $\frac{p}{q}$, quindi questa relazione di equivalenza indica che due frazioni sono in relazione tra loro se sono uguali il prodotto tra il numeratore di uno e il denominatore dell'altro: $\frac{p}{q}=\frac{p'}{q'}\iff pq'=p'q$ (es. prendendo le frazioni $2\over 3$ e $4\over 6$, si può constatare che $2\cdot6=3\cdot4$).
>>Se si prende l'insieme quoziente di questa relazione, ossia $[\mathbb{Z}\times (\mathbb{Z}\setminus \{0\})]/\sim$, si può notare come esso corrisponda proprio all'insieme $\Bbb Q$ dei numeri razionali perché comprende tutte le combinazioni possibili di numeri presenti in $\Bbb Q$.

Fonti
- lezioni terracini, chen
	^Lezioni
- libro di bruno martelli
- libro di mdag

Insiemi numerabili = posso contare gli elementi dell'insieme, cioè posso associare in modo biunivoco ogni elemento dell'insieme ai numeri naturali. %%e in relazione alla cardinalità come funziona?%%
$\mathbb{R}$ è un insieme NON numerabile, mentre $\mathbb{N}$ sì (la sua cardinalità è $\infty$)