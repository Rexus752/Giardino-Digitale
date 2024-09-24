---
icon: BoBxArrowFromLeft
iconColor: "#8888FF"
---
# Funzione

>[!definizione] _Definizione_: funzione
>Una **funzione**, denotata con le lettere latine minuscole (solitamente $f$, oppure anche $g$ e $h$ quando sono presenti più funzioni), è una [[Teoria degli insiemi#^2f81d7|relazione]] tra due insiemi $A$ e $B$, chiamati rispettivamente _dominio_ e _codominio_ della funzione, che associa a ogni elemento $x\in A$ del dominio uno e un solo elemento $y\in B$ del codominio:
>$$ \begin{align*} f \colon A &\to B\\ x&\mapsto y \end{align*} $$
>L’associazione degli elementi $x$ e $y$ appartenenti rispettivamente al dominio $A$ e al codominio $B$ si indica con $y=f(x)$.
>
>>[!esempio] _Esempio:_ $f \colon \mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$
>>La funzione $f \colon \mathbb{R}\to \mathbb{R},\quad x\mapsto x^2$ è una funzione che associa a ogni numero reale $x$ il suo quadrato $y=x^2$. Essa è una funzione perché per ogni numero il suo quadrato è unico e non può averne altri.
>
>>[!esempio] _Esempio:_ $R=\{(1,2),(1,3),(2,4)\}$ non è una funzione
>>Data una relazione $R=\{(1,2),(1,3),(2,4)\}$, essa non è una funzione in quanto c’è un elemento del dominio (l’elemento $1$) che è associato a più elementi del codominio (gli elementi $2$ e $3$).
>
>>[!notazione] _Notazione:_ diversi modi per indicare la relazione della funzione
>>Data una funzione che calcola il quadrato di ogni numero reale, le notazioni $f:\mathbb{R}\to \mathbb{R},\quad x\mapsto x^{2}$ e $f:\mathbb{R}\to \mathbb{R},\quad f(x)=x^{2}$ sono equivalenti (in particolare, nella seconda si può omettere la scrittura di dominio e codominio se sono già noti, quindi è possibile scriverla anche come $f(x)=x^{2}$).
>
>>[!notazione] _Notazione:_ convenzione sui nomi delle variabili
>>Sottolineiamo il fatto che il nome $x$ dato alla variabile in ingresso è puramente convenzionale: infatti, le relazioni $f(x) = 2x+1,\quad\forall x \in \mathbb{R}$ e $f(t) = 2t+1,\quad\forall t \in \mathbb{R}$ definiscono la stessa funzione $f$, nonostante la diversa lettera utilizzata per indicare la variabile indipendente: si tratta in entrambi i casi della funzione che associa a ogni numero reale il suo doppio aumentato di uno.
>
>>[!osservazione] _Osservazione_: funzione come dipendenza tra due grandezze
>>Il concetto di funzione è il modello matematico che esprime la *dipendenza* tra due grandezze. Se una certa grandezza $Y$ dipende da un'altra grandezza $X$ e se a ogni valore di $X$ è associato un unico valore di $Y$, allora $Y$ è una funzione di $X$: in questo caso si dice che $X$ è la grandezza _indipendente_ e che $Y$ è la grandezza _dipendente_.
>>Un esempio molto semplice è dato dalle grandezze $X$ e $Y$ definite rispettivamente come "lunghezza del lato di un quadrato" e "area del quadrato".
>>L'insieme dei possibili valori assunti da $X$, cioè il dominio, è $\{x\in\mathbb{R}\mid x>0\}$ e, a ogni $x$ si associa l'area corrispondente $y=x^2$ (in opportune unità di misura), che è l'unico valore dell'area del quadrato di lato avente lunghezza $x$.
>>Possiamo quindi affermare che l'area del quadrato è _funzione_ della lunghezza del suo lato, secondo la relazione $f(x)=x^{2},\quad\forall x>0$.
>
>>[!osservazione] _Osservazione_: funzione come concetto non strettamente algebrico
>>La nozione di funzione è molto generale e non si limita a considerare solo quelle funzioni che si possono scrivere esplicitamente usando le quattro operazioni aritmetiche ed altre funzioni note, come quelle trigonometriche.
>>Per esempio, si può scegliere di definire una funzione $f \colon \mathbb{N}\to\mathbb{N}$, $f(n)$ come l’$(n + 1)$-esimo numero primo, oppure una funzione $f\colon\mathbb{R}\to\mathbb{N}$, $f(x)$ come la 127-esima cifra di $x$ nel suo sviluppo decimale.
>
>>[!osservazione] _Osservazione_: funzione come processo con input e output
>>Il concetto di funzione può essere facilmente inteso in termini di processo che, dato un certo input, fornisce un determinato output.
>>Una funzione $f$ è assimilabile a una macchina che prende in ingresso un valore $x$ e restituisce in uscita un unico valore corrispondente $f(x)$:
>>$$ \boxed{x} \to \boxed{f(x)} $$
>>Il valore in uscita si ottiene spesso mediante una procedura che specifica le operazioni da effettuare sul valore in ingresso: per esempio, per la funzione $f \colon \mathbb{R} \to \mathbb{R}$ definita da $f(x)=2x+1,\quad\forall x \in \mathbb{R}$, la procedura può essere descritta dalle operazioni "moltiplica per 2" e "aggiungi 1":
>>$$ \boxed{x} \xrightarrow{\text{moltiplica per }2} \boxed{2x} \xrightarrow{\text{aggiungi }1} \boxed{2x+1} $$
>>Il modo più semplice per rappresentare il meccanismo input-output che soggiace al concetto di funzione è un diagramma a frecce come il seguente, che rappresenta una generica funzione $f\colon X\to Y,\quad x\mapsto f(x)$:
>>![asd](Pasted%20image%2020240220102800.png)
>^Funzione

>[!definizione] _Definizione_: grafico di una funzione
>Data una funzione $f\colon A\to B,\quad x\mapsto f(x)$, si definisce ***grafico*** di $f$ il sottoinsieme $\Gamma_{f} \subseteq \mathbb{R}^{2}$ (dove $\mathbb{R}^{2}$ indica l'insieme $\mathbb{R}\times \mathbb{R} = \{(x,y)\mid x\in \mathbb{R},y \in \mathbb{R}\}$ delle coppie di numeri reali) definito da
>$$\Gamma_{f} = \{(x,y)\in \mathbb{R}^{2}\mid x\in A, y=f(x)\} = \{(x,f(x))\mid x\in A\}$$
>cioè l'insieme delle coppie di elementi in $\mathbb{R}^{2}$ legate tra di loro dalla funzione $f$.
>
>>[!rappresentazione] _Rappresentazione_: grafico sul piano cartesiano
>>Per rappresentare il grafico "visivamente" si usa il _piano cartesiano_, cioè un piano composto da due rette perpendicolari tra loro, dette _assi cartesiani_, che hanno alcune caratteristiche particolari:
>>- Sono disegnate in modo che una di esse sia orizzontale e l'altra verticale;
>>- Ognuna di loro rappresenta una grandezza: generalmente la retta orizzontale, detta _asse delle ascisse_, rappresenta i valori che può assumere la $x$, mentre la retta verticale, detta _asse delle ordinate_, rappresenta i valori che può assumere la $y$;
>>- Sono orientate, cioè a una delle due estremità presentano una freccia che indica il verso in cui le grandezze aumentano di valore (generalmente verso destra per l'asse delle ascisse e verso l'alto per l'asse delle ordinate);
>>- Il loro punto di incontro viene detto _origine degli assi_ e viene indicato con $O$.
>>
>>Inoltre, le quattro parti in cui viene diviso il piano dagli assi prendono il nome di _quadranti_ e, partendo da quello in alto a destra e procedendo in senso antiorario, vengono numerati da 1 a 4.
>
>>[!esempio] _Esempio_: $f(x)=3x-1$
>>Il grafico della funzione $f\colon \mathbb{R}\to \mathbb{R}, \quad x\mapsto 3x-1$ è l'insieme $\Gamma_{f}=\{(x,y)\in \mathbb{R}^{2}\mid y=3x-1\}$ ed è rappresentato dalla seguente retta nel piano cartesiano:
>>![](Pasted%20image%2020240220105837.png)
>
>>[!esempio] _Esempio_: ricavare le informazioni dal grafico di una funzione
>>Si consideri la funzione $f$ che presenta il seguente grafico:
>>![](Pasted%20image%2020240220110213.png)
>>Il dominio $D$ di $f$, ossia l'insieme di tutti i valori $x$ per cui esiste $f(x)$, è dato da $D=[-2;1]\cup(2;5]$.
>>Si presti attenzione al fatto che $x=2$ non appartiene al dominio di $f$, infatti il pallino vuoto in corrispondenza del punto $(2,-3)$ significa che tale punto non appartiene al grafico di $f$; di conseguenza, non esistono punti sul grafico di $f$ aventi ascissa $x=2$ e, dunque, $2\notin D$.
>>%%mettere il piano cartesiano dopo la definizione di immagine e mettere il link alla parola "immagine" seguente%%
>>Per determinare l'immagine $f(D)$ di $f$ si devono trovare tutti i possibili valori $f(x)$ al variare di $x\in D$; essi si leggono sull'asse delle ordinate e sono tutte le quote $y$ alle quali esiste un punto sul grafico di $f$. Si ha quindi $f(D)=(-3;0]\cup[2;5]$.
>>![](Pasted%20image%2020240220110901.png)

^b8a997

# Uguaglianza di due funzioni

>[!definizione] _Definizione_: uguaglianza di due funzioni
>Date due funzioni $f$ e $g$, sono definite **uguali** se hanno lo stesso dominio e lo stesso codominio e se $f(x)=g(x)$ per ogni elemento $x$ del dominio.
>
>>[!esempio] _Esempio:_ uguaglianza di due funzioni apparentemente diverse
>>Date due funzioni in $\mathbb{R}$ $f(x)=3x^2-1$ e $g(x)=x^3+2x-1$ con dominio $\{0,1,2\}$, ossia $f,g\colon \{0,1,2\}\to\mathbb{R}$, allora $f=g$ perché:
>>- $f(0)=g(0)=-1$;
>>- $f(1)=g(1)=2$;
>>- $f(2)=g(2)=11$.

# Funzioni particolari

>[!definizione] _Definizione_: funzione identità
>Dato un insieme $X$, la **funzione identità** su $X$ è la funzione che associa a ogni elemento di $X$ se stesso:
>$$ \begin{align*} \text{id}_X \colon X &\to X\\ x&\mapsto x \end{align*} $$
>^c01106

>[!definizione] _Definizione_: funzione costante
>Dati due insiemi $A$ e $B$ non necessariamente distinti e un elemento fissato $\beta \in B$, la **funzione costante** con valore $\beta$ è la funzione che associa a ogni elemento di $A$ sempre lo stesso elemento $\beta$ di $B$:
>$$ \begin{align*} f_\beta\colon A &\to B\\ a&\mapsto \beta \end{align*} $$
>^40d00d

>[!definizione] _Definizione_: funzione proiezione
>Dati due insiemi $A$ e $B$, le **funzioni proiezioni** sui singoli fattori sono le funzioni che associano a ogni coppia di valori $(a,b)\in A\times B$ uno solo dei due valori:
>$$ \begin{align*} p_1\colon A\times B&\to A\\ (a,b)&\mapsto a \end{align*} $$
>$$ \begin{align*} p_2\colon A\times B&\to B\\ (a,b)&\mapsto b \end{align*} $$
>^12acc1

>[!definizione] _Definizione_: funzione restrizione
>Data una funzione $f\colon A\to B$ e un sottoinsieme $S \subseteq A$, si dice **restrizione** di $f$ a $S$ la funzione che restringe il dominio di $f$ a $S$:
>$$ \begin{align*} f_{\vert S}\colon S &\to B\\ x&\mapsto f_{\vert S}(x)=f(x) \end{align*} $$
>Essa è cioè una funzione che in $S$ si comporta esattamente come la funzione originaria si comporta in $A$, ma che si "dimentica" dei punti al di fuori di quel sottoinsieme.
>^c35b10
>
>>[!esempio] _Esempio:_ $f|_\mathbb{N}\colon\mathbb{N}\to\mathbb{R}$
>>Data una funzione $f \colon \mathbb{R}\to \mathbb{R},\quad x\mapsto x^2$, essa si può restringere al sottoinsieme $\mathbb{N}\subsetneq\mathbb{R}$ e diventa la funzione $f|_\mathbb{N}\colon \mathbb{R}\to \mathbb{R},\quad x\mapsto x^2$.

# Immagine e controimmagine

>[!definizione] _Definizione_: immagine e controimmagine di una funzione
>Data una funzione $f\colon A\to B$ e un elemento del dominio $x\in A$, si definisce _i**mmagine**_ di $x$ l’elemento del codominio $f(x)\in B$ associato a $x$ tramite la funzione $f$. Più in generale, dato un qualsiasi sottoinsieme del dominio $C \subseteq A$, l’immagine di $C$ è il sottoinsieme del codominio $f(C)\subseteq B$ per cui a ogni elemento $x\in C$ corrisponde uno e un solo elemento $f(x)\in f(C)$:
>$$ f (C) = \{f (x) \mid x \in C\} \subseteq B $$
>Data sempre la stessa funzione $f\colon A\to B$ e un elemento del codominio $y\in B$, si definisce **controimmagine** di $y$ l’elemento del dominio $f^{-1}(y)\in A$ associato a $y$ tramite la funzione $f^{-1}$, ossia l’[[#^3d14c8|inversa]] di $f$. Più in generale, dato un qualsiasi sottoinsieme del codominio $D\subseteq B$, la controimmagine di $B$ è il sottoinsieme del dominio $f^{-1}(D)\subseteq A$ per cui ogni elemento $y\in D$ corrisponde uno e un solo elemento $f^{-1}(y)\in f^{-1}(D)$:
>$$ f^{-1}(D) = \{f^{-1}(y) \mid y \in D\} \subseteq A $$
>^468653
>
>>[!esempio] _Esempio:_ immagini e controimmagini della funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$
>>Data una funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$ con immagine $\mathbb{N}\subsetneq\mathbb{R}$, si ha come controimmagine l’insieme $f(\mathbb{N})=\{0,1,4,9,16,\ldots\}$. Volendo associare a questo esempio le lettere usate nella definizione, si ha che:
>>- Il dominio è $A=\mathbb{R}$;
>>- Il codominio è $B=\mathbb{R}$;
>>- L’insieme delle immagini è $f(C)=f(\mathbb{N})=\{0,1,4,9,16,\ldots\}$ che è un sottoinsieme del codominio $B=\mathbb{R}$;
>>- L’insieme delle controimmagini è $f^{-1}(D)=f^{-1}(\{0,1,4,9,16,\ldots\})=\mathbb{N}$ che è un sottoinsieme del dominio $A=\mathbb{R}$.
>>
>>Inoltre, si può affermare che:
>>- La controimmagine di $f(x)=4$ è l’insieme con due elementi $f^{-1}(4)=\{-2,2\}$;
>>- La controimmagine dell’intervallo chiuso $D=[4,9]\subsetneq B$ è l’unione dei due intervalli chiusi $f^{-1}(D)=[-3,-2]\cup[2,3]\subsetneq A$;
>>- La controimmagine dell’intervallo chiuso $D=[-10,-5]\subsetneq B$ è l’insieme vuoto $f^{-1}(D)=\emptyset$, dal momento che nessun numero del dominio elevato alla seconda può dare un numero negativo.
>
>>[!esempio] _Esempio:_ controimmagine di una funzione costante
>>Data una [[#^40d00d|funzione costante]] $f_\beta\colon A\to B,\quad a\mapsto\beta$, se $T\subsetneq B$ è un sottoinsieme del codominio $B$ si ha:
>>- $\beta \in T\implies f^{-1}(T)=A$;
>>- $\beta \notin T\implies f^{-1}(T)=\emptyset$.
>
>>[!esempio] _Esempio:_ controimmagine di una funzione proiezione
>>Data una [[#^12acc1|funzione proiezione]] $p_2\colon A\times B\to B,\quad(a,b)\mapsto b$, allora $f^{-1}(b)=A\times\{b\},\quad\forall b \in B$.
>
>>[!esempio] _Esempio:_ controimmagine della funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto\sin x$
>>Data una funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto\sin x$ e dato come immagine un intervallo chiuso $[-1,1]$, allora la controimmagine dell’insieme $\mathbb{N}$ dei numeri naturali è l’insieme $f^{-1}(\mathbb{N})=\{\ldots,-\frac{3\pi}{2},-\pi,-\frac{\pi}{2},0,\frac{\pi}{2},\pi,\frac{3\pi}{2},\ldots\}=\{\frac{n\pi}{2}\mid n\in\mathbb{Z}\}.$

>[!notazione] _Notazione:_ funzioni $\text{Im}(f)$ e $\text{Co}(f)$
>Data una funzione $f$, per indicare la sua immagine e la sua controimmagine si possono anche usare rispettivamente le funzioni $\text{Im}(f)$ e $\text{Co}(f)$.
>
>>[!esempio] _Esempio:_ funzioni $\text{Im}(f)$ e $\text{Co}(f)$ con $f\colon A\to B$
>>Data una funzione $f\colon A\to B$, si ha che $\text{Im}(f)=B$ e $\text{Co}(f)=A$.

# Iniettività, suriettività e biettività

## Iniettività

>[!definizione] _Definizione_: iniettività
>Una funzione $f\colon A\to B$ si dice che è _**iniettiva**_ o che è una _**iniezione**_ se, per ogni scelta di due numeri $a_1,a_2\in A$ con $a_1\ne a_2$, si ha $f(a_1)\ne f(a_2)$:
>$$ a_1\ne a_2 \implies f(a_1)\ne f(a_2),\quad \forall a_1, a_2\in A $$
>^678c66
>
>>[!esempio] _Esempio:_ esempio grafico dell’iniettività
>>Un esempio grafico dell’iniettività è il seguente, in cui ogni elemento dell’insieme $A=\{2,4,6\}$ è associato a un solo elemento dell’insieme $B=\{9,7,5,3\}$:
>>![[Iniettività.png]]
>
>>[!esempio] _Esempio:_ iniettività della funzione $f\colon \mathbb{Z}\to\mathbb{Z},\quad n\mapsto2n+1$
>>Data una funzione $f\colon \mathbb{Z}\to\mathbb{Z},\quad n\mapsto2n+1$, essa è iniettiva. Infatti, dati due interi $m\ne n$ si ha certamente $f(m)=2m+1\ne f(n)=2n+1$.
>
>>[!esempio] _Esempio:_ non-iniettività della funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$
>>Data una funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$, essa non è iniettiva. Infatti, si ha $f(1)=f(-1)=1$ e, più in generale, $f(x)=f(-x),\quad \forall x \in \mathbb{R}$.
>
>>[!esempio] _Esempio:_ iniettività della funzione proiezione $p_1\colon A\times B\to A,\quad (a,b)\mapsto a$
>>Data una funzione proiezione $p_1\colon A\times B\to A,\quad (a,b)\mapsto a$, siccome si ha $p_1((a,b))=a$ per ogni $(a,b)\in A\times B$ la funzione è iniettiva solo se $B$ consiste di un unico elemento: se $B$ contiene due elementi distinti $b_1$ e $b_2$ allora $p_1((a,b_1))=p_1((a,b_2))$.
>
>>[!osservazione] _Osservazione_: rendere una funzione iniettiva restringendo il dominio
>>Una funzione $f\colon A\to B$ non iniettiva può diventare iniettiva [[#^c35b10|restringendo]] opportunamente il dominio. Per esempio, la funzione $f(x)=x^2$ che non è iniettiva sul dominio $\mathbb{R}$, può diventarlo se viene ristretto il dominio a $\mathbb{R}^{>0}$. Infatti, se $x$ e $y$ sono due numeri reali positivi distinti, allora sicuramente $x^2\ne y^2$.

## Suriettività

>[!definizione] _Definizione_: suriettività
>Una funzione $f\colon A\to B$ si dice che è _**suriettiva**_ o che è una _**suriezione**_ se ogni elemento del codominio è immagine di almeno un elemento del dominio:
>$$ \exists x \in A : f (x) = y,\quad \forall y \in B $$
>^6a357d
>
>>[!esempio] _Esempio:_ esempio grafico della suriettività
>>Un esempio grafico della suriettività è il seguente, in cui ogni elemento dell’insieme $B=\{9,7,5\}$ è associato ad almeno un elemento della funzione $A=\{2,4,6,8\}$:
>>![[Suriettività.png]]
>
>>[!esempio] _Esempio:_ non-suriettività della funzione $f\colon\mathbb{Z}\to\mathbb{Z},\quad x\mapsto 2x+1$
>>Data una funzione $f\colon\mathbb{Z}\to\mathbb{Z},\quad x\mapsto 2x+1$, le immagini dei singoli elementi sono sempre numeri dispari e ogni numeri intero dispari $m$ può essere scritto nella forma $m = 2k+1,\quad \forall k \in \mathbb{Z}$. Dunque $m=f(k)$ e si può concludere che l’immagine di $f$ è costituita dagli interi dispari, ovvero $\text{Im}(f)=2\mathbb{Z}+1$. Poiché $2\mathbb{Z}+1\ne\mathbb{Z}$, la funzione $f$ non è suriettiva.
>
>>[!esempio] _Esempio:_ non-suriettività della funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$
>>Data una funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$, le immagini dei singoli elementi sono sempre numeri reali non negativo e ogni reale non negativo $y$ può essere scritto nella forma $y=x^2,\forall x \in \mathbb{R}$. Dunque $y=f(x)$ e si può concludere che l’immagine di $f$ è costituita dai numeri reali positivi, ovvero $\text{Im}(f)=\mathbb{R}^{\ge0}$. Poiché $\mathbb{R}^{\ge0} \ne \mathbb{R}$ la funzione $f$ non è suriettiva.
>
>>[!esempio] _Esempio:_ suriettività della funzione $f\colon[0,+\infty]\to\mathbb{R},\quad x\mapsto\log(x)$
>>Data una funzione $f\colon[0,+\infty]\to\mathbb{R},\quad x\mapsto\log(x)$, ogni numero reale $r$ è il logaritmo di un altro qualsiasi numero reale $x$ (basti prendere $x=e^r$). Dunque, dato che $\text{Im}(f)=\mathbb{R}$, la funzione è suriettiva.
>
>>[!esempio] _Esempio:_ suriettività della funzione proiezione $p_1\colon A\times B\to A,\quad(a,b)\mapsto a$
>>Data una funzione proiezione $p_1:A\times B \to A$, poiché $B\ne\emptyset$ (se $B$ fosse vuoto allora $A\times B =A\times\emptyset=\emptyset$ e non si potrebbe parlare di funzione) e dato un $a\in A$ si può sempre scrivere $a=p_1((a,b)),\quad\forall b \in B$. Pertanto, ogni $a \in A$ è anche in $\text{Im}(p_1)$, quindi $A=\text{Im}(p_1)$ e $p_1$ è suriettiva.
>
>>[!osservazione] _Osservazione_: suriettività intesa come $\text{Im}(f)=B$
>>Un’altra definizione della suriettività è quella secondo cui la funzione $f$, per essere suriettiva, deve avere l’immagine corrispondente al codominio:
>>$$ \text{Im}(f)=B $$
>>In questo caso, infatti, si ha che non ci sono elementi del codominio senza una controimmagine in $A$.

# Biettività

>[!definizione] _Definizione_: biettività
>Una funzione $f\colon A\to B$ si dice che è _**biettiva**_ o che è una _**biezione**_ se è contemporaneamente sia [[#^678c66|iniettiva]] che [[#^6a357d|suriettiva]], ovvero se per ogni elemento del codominio $y\in B$ esiste ed è unico un elemento del dominio $x \in A$ tale che $f(x)=y$:
>$$ \exists! \space x\in A : f (x) = y,\quad \forall y \in B $$
>
>>[!esempio] _Esempio:_ esempio grafico della biettività
>>Un esempio grafico della suriettività è il seguente, in cui ogni elemento dell’insieme $B=\{9,7,5,3\}$ è associato a uno e un solo elemento della funzione $A=\{2,4,6,8\}$:
>>![[Biettività.png]]
>
>>[!esempio] _Esempio:_ biettività della funzione identità
>>Per ogni insieme $A$, la [[#^c01106|funzione identità]] $\text{id}_A:A\to A$ è biettiva, in quanto a ogni elemento del codominio è associato un solo elemento del dominio (ossia se stesso).
>
>>[!esempio] _Esempio:_ biettività della funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$ con restringimento di dominio
>>Data una funzione $f\colon\mathbb{R}\to\mathbb{R},\quad x\mapsto x^2$, essa non è né iniettiva, né suriettiva, ma può diventare biettiva restringendo il suo dominio a $\mathbb{R}^{>0}$ e pensandola con codominio $\mathbb{R}^{>0}$ (se il codominio fosse $\mathbb{R}$, allora non potrebbe essere suriettiva, in quanto non ci sono numeri che, elevati alla seconda, danno numeri negativi). In questo modo, per ogni numero reale $x>0$ esiste un solo $y>0$ tale che $y=x^2$.
>
>>[!esempio] _Esempio:_ biettività della funzione $f\colon A\times B\to B\times A,\quad(a,b)\mapsto(b,a)$
>>La funzione $f\colon A\times B\to B\times A,\quad(a,b)\mapsto(b,a)$ è una biezione. Infatti, ogni coppia $(b,a)\in B\times A$ è immagine solo di una coppia $(a,b)\in A \times B$.

## Relazioni con la cardinalità

>[!proposizione] _Proposizione:_ iniettività, suriettività e biettività dipendono dalla cardinalità
>Data una funzione $f\colon A\to B$, la sua iniettività, suriettività o biettività dipendono dalla sua cardinalità:
>1. $f$ è suriettiva se e soltanto se $|f^{-1}(b)|\ge1$ per ogni $b\in B$;
>2. $f$ è iniettiva se e soltanto se $|f^{-1}(b)|\le1$ per ogni $b\in B$;
>3. $f$ è biettiva se e soltanto se è sia suriettiva che iniettiva, cioè se $|f^{-1}(b)|=1$ per ogni $b \in B$.
>^b5091f
>
>>[!dimostrazione] _Dimostrazione_ 
>>1. La condizione che esista un elemento $a\in f^{-1}(b)$ (cioè che $|f^{-1}(b)|\ge1$) è equivalente, per la definizione di [[#^468653|controimmagine]], alla condizione che esista un $a \in A$ tale che $f(a)=b$;
>>2. Si può dimostrare analogamente che $f$ non è iniettiva se e soltanto se esiste un $b\in B$ tale che $|f^{-1}(b)|\ge2$, in quanto in questo caso esistono due elementi distinti $a_1\ne a_2$ nel dominio tali che $f(a_1)=f(a_2)=b$;
>>3. Una funzione per essere biettiva deve essere sia iniettiva che suriettiva, quindi dovendo essere $|f^{-1}(b)|$ sia $\ge1$ che $\le 1$, l’unico caso che soddisfa entrambe le condizioni è $|f^{-1}(b)|=1$.

# Composizione di funzioni

>[!definizione] _Definizione_: composizione di due funzioni
>Date due funzioni $f\colon A\to B$ e $g\colon B \to C$, la **composizione** di $f$ e $g$, denotata $g \circ f$, è la funzione:
>$$ \begin{align*} g\circ f \colon A &\to C\\ a&\mapsto g(f(a)) \end{align*} $$
>È importante osservare che la composizione $g \circ f$ è definita solo se il codominio di $f$ coincide col dominio di $g$.
>
>>[!notazione] _Notazione:_ composizione rappresentata con le frecce
>>La notazione "a frecce" delle funzioni permette di rappresentare semplicemente la composizione $g \circ f$ come:
>>$$ A \xrightarrow{f} B \xrightarrow{g} C,\quad A \xrightarrow{g\circ f} C $$
>>dove entrambi i percorsi che può seguire un elemento $a \in A$ per arrivare in $C$ danno lo stesso risultato.
>>^52824c
>
>>[!esempio] _Esempio:_ composizione di $f(x)=x^2,\quad g(x)=4x+1$
>>Date le funzioni $f\colon \mathbb{R}\to \mathbb{R},\quad f(x)=x^2$ e $g\colon \mathbb{R}\to \mathbb{R},\quad g(x)=4x+1$, allora la funzione composta $g\circ f$ è definita da
>>$$(g\circ f)(x)=g(f(x))=4f(x)+1=4x^2+1$$
>>Invertendo i ruoli di $f$ e $g$, è possibile definire anche la funzione composta $f\circ g$ definita da
>>$$(f\circ g)(x)=f(g(x))=(g(x))^2=(4x+1)^2$$
>
>>[!osservazione] _Osservazione_: composizione di una funzione costante con altre funzioni
>>Data una [funzione costante](#^40d00d) $f_\beta\colon A\to B,\quad a\mapsto\beta$, allora per ogni funzione $g\colon B\to C$ e per ogni funzione $h\colon D\to A$ si ha:
>>- $(g\circ f_\beta)(a)=g(\beta),\quad\forall a \in A$;
>>- $(f_\beta\circ h)(d)=f_\beta(h(d))=\beta,\quad\forall d \in D$.
>>
>>Quindi $g \circ f_\beta\colon A\to C$ è la funzione costante $f({g(\beta)})$ e $f_\beta\circ h\colon D \to B$ è la funzione costante $f_\beta$ con dominio $D$. Dal punto di vista grafico:
>>$$ D \xrightarrow{h} A \xrightarrow{f_\beta} B \xrightarrow{g} C, \quad D \xrightarrow{f_\beta} B, \quad A \xrightarrow{f(g(\beta))} C $$
>>%%da confermare che sia corretto%%
^Composizione-di-due-funzioni

## Proprietà delle composizioni

>[!proprieta] _Proprietà:_ non-commutatività della composizione di funzioni
>Date due funzioni $f\colon A\to B$ e $g\colon B \to C$, generalmente la loro composizione non è commutativa:
>$$ f\circ g \ne g \circ f $$
>
>>[!esempio] _Esempio:_ $f \colon \mathbb{R}\to \mathbb{R},\quad x\mapsto x^3$ e $g\colon \mathbb{R}\to \mathbb{R},\quad y\mapsto \sin y$
>>Date due funzioni $f \colon \mathbb{R}\to \mathbb{R},\quad x\mapsto x^3$ e $g\colon \mathbb{R}\to \mathbb{R},\quad y\mapsto \sin y$, se si prova a comporle in entrambe le "combinazioni" si ottiene:
>>- $h=g\circ f\implies h\colon \mathbb{R}\to\mathbb{R},\quad x\to \sin x^3$;
>>- $j=f\circ g\implies j\colon \mathbb{R}\to\mathbb{R},\quad x\to (\sin x)^3$.
>>- Si può notare come $h\ne j$, quindi $g\circ f \ne f \circ g$.
>
>>[!esempio] _Esempio:_ non-commutatività dell’identità composta tra funzioni
>>Date due funzioni $f$ e $g$, è possibile avere $g \circ f = \text{id}_A$ ma $f \circ g \ne \text{id}_B$, oppure è possibile avere $f \circ g = \text{id}_B$ ma non $g \circ f \ne \text{id}_A$. Per esempio, dati due insiemi non vuoti $A$ e $B$ con un elemento $β ∈ B$ e la funzione successione $s: A→ A × B,  a↦(a,β)$, allora:
>>- $p_1 \circ s(a)=p_1(s(a))=p_1((a,b))=a=\text{id}_A$;
>>- $s \circ p_1((a,b))=s(p_1((a,b)))=s(a)=(a,\beta)\ne\beta\ne\text{id}_B$.
>>
>>Dunque, $p_1 \circ s = \text{id}_A$ ma $s \circ p_1 \ne \text{id}_B$.
>>Oppure, possiamo anche considerare come esempio quest'altra situazione: ![[Pasted image 20240211180500.png]]
>>%%completare%%

>[!proprieta] _Proprietà:_ associatività della composizione di funzioni
>Date tre funzioni $f\colon A \to B$, $g\colon B\to C$ e $h\colon C \to D$, allora vale la proprietà associativa:$$ h\circ(g \circ f)=(h \circ g)\circ f $$
>^892c1f
>
>>[!dimostrazione] _Dimostrazione_ 
>>Seguendo la [[#^52824c|definizione di composizione di funzioni]], per ogni elemento $a \in A$ si ha:
>>- $(h\circ(g\circ f))(a)=h((g\circ f)(a))=h(g(f(a)));$
>>- $((h\circ g)\circ f)(a)=(h\circ g)(f(a))=h(g(f(a))).$
>>
>>Poiché i risultati coincidono, allora le due composizioni sono uguali.
>>$\blacksquare$
>[!proprieta] _Proprietà:_ la funzione identità è l’elemento neutro della composizione di funzioni
>La funzione identità ha la proprietà di essere neutra per la composizione, nel senso che per ogni funzione $f\colon A\to B$ si ha $f \circ \text{id}_A=f$ e $\text{id}_B\circ f = f$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>Seguendo la [[#^52824c|definizione di composizione di funzioni]], per ogni elemento $a \in A$ si ha:
>>- $(f\circ \text{id}_A)(a)=f(\text{id}_A(a))=f(a);$
>>- $(\text{id}_B\circ f)(a)=\text{id}_B(f(a))=f(a).$
>>
>>Poiché i risultati coincidono, allora le due composizioni sono uguali.
>>$\blacksquare$

### Trasmissioni di iniettività e suriettività

>[!proprieta] _Proprietà:_ trasmissione di iniettività e suriettività dalle singole funzioni alle composizioni
>Date due funzioni $f\colon A\to B$ e $g\colon B \to C$, allora:
>1. Se $f$ e $g$ sono iniettive, anche $g \circ f$ è iniettiva;
>2. Se $f$ e $g$ sono suriettive, anche $g \circ f$ è suriettiva.
>
>>[!dimostrazione] _Dimostrazione_ 
>>1. Dati due elementi $a_1,a_2 \in A:a_1\ne a_2$, poiché $f$ è iniettiva si ha $f(a_1)\ne f(a_2)$. Anche $g$ è iniettiva, dunque:
>>	$$ (g\circ f)(a_1)=g(f(a_1))\ne g(f(a_2))=(g\circ f)(a_2), $$
>>	dimostrando quindi che $g \circ f$ è iniettiva.
>>2. Dato un $c \in C$, poiché $g$ è suriettiva, esiste un $b \in B$ tale che $g(b)=c$. Anche $f$ è suriettiva, quindi esiste un $a \in A$ tale che $f(a)=b$. Mettendo insieme le due cose, si ha che:
>>	$$ c=g(b)=g(f(a))=(g\circ f)(a), $$
>>	dimostrando quindi che $g \circ f$ è suriettiva.
>>
>>L’ultima affermazione sulla biettività è una conseguenza immediata delle prime due.
>>$\blacksquare$
>
>>[!corollario] _Corollario:_ trasmissione di biettività dalle singole funzioni alle composizioni
>>Date due funzioni $f\colon A\to B$ e $g\colon B\to C$, se esse sono biettive, allora anche $g \circ f$ è biettiva.
>>^a36545

>[!proprieta] _Proprietà:_ trasmissione di iniettività e suriettività dalle composizioni alle singole funzioni
>Date due funzioni $f\colon A\to B$ e $g\colon B\to C$, allora:
>1. Se $g \circ f$ è iniettiva, allora $f$ è iniettiva;
>2. Se $g \circ f$ è suriettiva, allora $g$ è suriettiva.
>^c929f3
>
>>[!dimostrazione] _Dimostrazione_ 
>>1. Ipotizzando per assurdo che $f$ non sia iniettiva, allora esistono due elementi $a_1, a_2 \in A: a_1\ne a_2$ per cui $f(a_1)=f(a_2)$. Si deduce quindi che $(g\circ f)(a_1)=g(f(a_1))=g(f(a_2))=(g\circ f)(a_2)$, rendendo anche la composizione $g \circ f$ non iniettiva.
>>2. Se $g \circ f$ è suriettiva, per ogni $c \in C$ si ha un $a \in A$ tale che $(g \circ f)(a)=c$, quindi $g(f(a))=c$. Ponendo $f(a)=b$, si ha che $g(b)=c$, quindi $g$ è suriettiva.
>>
>>$\blacksquare$
>
>>[!corollario] _Corollario:_ trasmissione di biettività dalle composizioni alle singole funzioni
>>Date due funzioni $f\colon A\to B$ e $g\colon B\to C$, con $g\circ f$ biettiva, allora $f$ è iniettiva e $g$ è suriettiva.

## Inversa della composizione

>[!proposizione] _Proposizione:_ inversa di una composizione di funzioni
>Date due funzioni $f\colon A\to B$ e $g\colon B\to C$, l’inversa della loro composizione $g\circ f$ è la funzione $f^{-1}\circ g^{-1}$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>Per [[#^3d14c8|definizione]], l’inversa di una funzione è quella funzione tale per cui la loro composizione è uguale alla funzione identità.
>>Componendo insieme $g\circ f$ e $f^{-1}\circ g^{-1}$ si ha quindi per ogni $x\in A$:
>>$$
>>\begin{align*} 
>>((g\circ f)\circ(f^{-1}\circ g^{-1}))(x)
>>&=(g\circ f\circ f^{-1}\circ g^{-1})(x)=\\
>>&=(g(f(f^{-1}(g^{-1}(x)))))=\\
>>&=(g(g^{-1}(x)))=\\
>>&=x
>>\end{align*}
>>$$
>>Si può dimostrare che in questo caso vale la proprietà commutativa, quindi:
>>$$ ((g\circ f)\circ(f^{-1}\circ g^{-1}))(x)=((f^{-1}\circ g^{-1})\circ(g\circ f))(x)=x $$
>>$\blacksquare$

# Invertibilità di una funzione

>[!definizione] _Definizione_: funzione inversa
>Date due funzioni $f\colon A\to B$ e $g\colon B\to A$ (quindi il dominio di una è il codominio dell’altra e viceversa), si dicono l’una _**funzione inversa**_ dell’altra se $g \circ f = \text{id}_A$ e $f \circ g = \text{id}_B$.
>^3d14c8
>
>>[!osservazione] _Osservazione_: biettività delle funzioni invertibili
>>Poiché le funzioni identità $\text{id}_A$ e $\text{id}_B$ sono biettive, per la [[#^c929f3|trasmissione di iniettività e suriettività dalle composizioni alle singole funzioni]], se $f$ e $g$ sono inverse l’una dell’altra allora devono essere entrambe sia iniettive che suriettive, quindi entrambe biettive.
>
>>[!osservazione] _Osservazione_: $(f^{-1})^{-1}=f$
>>Poiché la relazione tra due funzioni di essere l’una l’inverso dell’altra è simmetrica, la funzione $f$ è l’inversa della funzione inversa $f^{-1}$:
>>$$ (f^{-1})^{-1}=f $$
>
>>[!osservazione] _Osservazione_: condizioni di esistenza di una funzione inversa
>>Data una funzione $f\colon A\to B$, è possibile definire una funzione $g\colon B\to A$ tale che $f$ e $g$ siano inverse l’una dell’altra a patto che sia rispettata una condizione: per la [[#^3d14c8|prima osservazione sulla definizione delle funzioni inverse]], una tale funzione $g$ può esistere solo se $f$ è biettiva (e di conseguenza anche $g$ stessa sarà biettiva).
>>Per la [[#^b5091f|cardinalità delle funzioni]], essendo $f$ una biezione, per ogni elemento $b \in B$ l’insieme delle sue controimmagini $f^{-1}(b)\subsetneq A$ è formato esattamente da un elemento, ossia $|f^{-1}(b)|=1$. Si ha quindi che $g(b)=a \iff f^{-1}(b)=\{a\}$. Calcolando le composizioni delle funzioni $f$ e $g$:
>>1. Per $g \circ f$ e per ogni $a \in A$ con $f(a)=b$, si ha che $(g\circ f)(a)=g(f(a))=g(b)=a$, dove l’ultima uguaglianza segue dal fatto che $f^{-1}(b)=\{a\}$. Dunque $g \circ f = \text{id}_A$.
>>2. Per $f \circ g$ e per ogni $b \in B$ con $f^{-1}(b)=\{a\}$, si ha che $(f\circ g)(b)=f(g(b))=f(a)=b$. Dunque $f \circ g = \text{id}_B$.
>>
>>Rispettando la [[#^3d14c8|definizione di funzioni inverse]], le funzioni $f$ e $g$ sono l’una l’inversa dell’altra.
>>^87fcbd
^Funzione-inversa

>[!teorema] _Teorema:_ esistenza unica dell’inversa di una biezione
>Data una funzione biettiva $f\colon A \to B$, allora esiste ed è unica una funzione $g\colon B\to A$ tale che $f$ e $g$ sono l’una l’inversa dell’altra.
>
>>[!dimostrazione] _Dimostrazione_ 
>>Una funzione $g$ che soddisfa la richiesta del teorema esiste per le condizioni di [[#^87fcbd|esistenza di una funzione inversa]], quindi per dimostrare questo teorema serve solamente dimostrare che è l’unica ad avere tale proprietà. Per fare ciò, si può supporre di avere una certa funzione $h\colon B\to A$ tale che anche $f$ e $h$ sono l’una l’inversa dell’altra e dimostrare che deve per forza essere $g=h$.
>>Se una tale funzione $h$ esiste, si può calcolare la composizione $g \circ f \circ h$ in due modi diversi.
>>1. Poiché $f$ e $g$ sono l’una l’inversa dell’altra, $(g \circ f) \circ h = \text{id}_A \circ h = h$;
>>2. Poiché $f$ e $h$ sono l’una l’inversa dell’altra, $g \circ (f \circ h)=g \circ \text{id}_B=g$.
>>
>>Si ha quindi che $g = h$.
>>$\blacksquare$

>[!proposizione] _Proposizione:_ inversa della composizione di funzioni
>Date due funzioni biettive $f\colon A\to B$ e $g\colon B \to C$, allora l’inversa della loro composizione $(g \circ f)^{-1}$ è uguale alla composizione delle loro inverse $f^{-1}\circ g^{-1}$:
>$$ (g \circ f)^{-1}=f^{-1}\circ g^{-1} $$
>
>>[!dimostrazione] _Dimostrazione_ 
>>Per dimostrare la correttezza dell’affermazione, basta osservare che, per la [[#^892c1f|proprietà associativa della composizione di funzioni]], si ha:
>>1. $(g \circ f)\circ(f^{-1}\circ g^{-1})=g\circ(f\circ f^{-1})\circ g^{-1}=g\circ \text{id}_B\circ g^{-1}=g\circ g^{-1}=\text{id}_C$;
>>2. $(f^{-1} \circ g^{-1}) \circ (g \circ f)= f^{-1} \circ (g^{-1} \circ g) \circ f = f^{-1} \circ \text{id}_B \circ f = f^{-1} \circ f = \text{id}_A$.
>>
>>$\blacksquare$

>[!proposizione] _Proposizione:_ unicità delle funzioni composte
>Date una funzione biettiva $f\colon A\to B$ e due funzioni $g_1,g_2:B\to Y$ e $h_1,h_2:X \to A$:
>1. $g_1\circ f=g_2\circ f\implies g_1=g_2$;
>2. $f \circ h_1 = f \circ h_2\implies h_1 = h_2$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>1. Se $g_1\circ f=g_2\circ f$, componendo a destra con l’inversa $f^{-1}$ si ha:
>>	$$\begin{align*}
>>	g_1
>>	&=g_1\circ\text{id}_A=\\
>>	&=g_1\circ(f\circ f^{-1})=\\
>>	&=(g_1\circ f)\circ f^{-1}=\\
>>	&=(g_2\circ f)\circ f^{-1}=\\
>>	&=g_2\circ(f\circ f^{-1})=\\
>>	&=g_2\circ\text{id}_A=\\
>>	&=g_2.
>>	\end{align*} $$
>>2. Se $f \circ h_1 = f \circ h_2$, componendo a sinistra con l’inversa $f^{-1}$ si ha:
>>	$$ \begin{align*} h_1&=\text{id}_B\circ h_1=\\ &=(f^{-1}\circ f)\circ h_1=\\ &=f^{-1}\circ (f\circ h_1)=\\ &=f^{-1}\circ (f\circ h_2)=\\ &=(f^{-1}\circ f)\circ h_2=\\ &=\text{id}_B\circ h_2=\\ &=h_2. \end{align*} $$
>>
>>$\blacksquare$

# Operazioni binarie

>[!definizione] _Definizione_: operazione binaria interna
>Dato un insieme non vuoto $A$, di definisce _**operazione binaria interna**_ (o, più semplicemente, _**operazione**_) su $A$ e si denota con il simbolo $\star$ una funzione che richiede due argomenti dello stesso insieme $A$ (si dice cioè che ha [[arietà|arietà]] 2) e restituisce un elemento di $A$:
>$$ \begin{align*} \star \colon A\times A &\to A\\ (a_1,a_2)&\mapsto a_3 \end{align*} $$
>
>>[!osservazione] _Osservazione_: significato di _binaria_ e _interna_
>>L’aggettivo _binaria_ si riferisce al fatto che l’operazione ha bisogno di una coppia di operandi, mentre l’aggettivo _interna_ evidenzia il fatto che sia gli operandi che il risultato dell’operazione appartengono al medesimo insieme.
>>%%Da vedere: [https://www.youmath.it/forum/algebra/32822-operazioni-interne-e-esterne.html](https://www.youmath.it/forum/algebra/32822-operazioni-interne-e-esterne.html)%%
>
>>[!notazione] _Notazione:_ $\star((a_1,a_2)) = a_1\star a_2$
>>Il valore dell’operazione $\star$ sulla coppia $(a_1,a_2)\in A\times A$ si esprime in simboli come $\star((a_1,a_2))$, ma per comodità si può anche usare la notazione $a_1 \star a_2$.

>[!definizione] _Definizione_: proprietà dell’operazione binaria interna
>Data un’operazione $\star$ su un insieme $A$, essa può avere le seguenti proprietà:
>1. _Commutatività_: $a_1\star a_2=a_2\star a_1,\quad\forall a_1,a_2\in A$;
>2. _Associatività_: $(a_1\star a_2) \star a_3 = a_1 \star (a_2 \star a_3),\quad\forall a_1,a_2,a_3 \in A$;
>3. _Esistenza dell’elemento neutro_: $\exists e \in A:a\star e=e\star a=a,\quad\forall a\in A$.
>%%Sistemare gli esempi%%
>
>>[!esempio] _Esempio:_ proprietà dell’addizione $+$ e della moltiplicazione $\cdot$
>>L’addizione $+$ e la moltiplicazione $\cdot$ sono operazioni commutative e associative su $\mathbb{N},\mathbb{Z},\Bbb{Q}$ e $\mathbb{R}$. Il numero neutro per l’addizione $+$ è lo $0$ perché $x+0=0+x=x$ per ogni $x$, mentre il numero neutro per la moltiplicazione $\cdot$ è l’$1$ perché $x\cdot1=1\cdot x=x$ per ogni $x$.
>
>>[!esempio] _Esempio:_ proprietà della sottrazione $-$
>>La sottrazione $-$ è un’operazione in $\mathbb{Z},\Bbb{Q},\mathbb{R}$ ma non in $\mathbb{N}$ (perché, per esempio, $1 - 2\notin\mathbb{N}$). Non è né commutativa, in quanto $a-b\ne b-a$ se $a\ne b$, né associativa in quanto $(a-b)-c\ne a-(b-c)$. Non esiste un elemento neutro e non è lo $0$ perché $x-0\ne0-x$ se $x\ne 0$.
>
>>[!esempio] _Esempio:_ proprietà della divisione $\div$
>>La divisione $\div$ non è un’operazione in alcun insieme numerico che contenga il numero $0$, dal momento che la divisione per $0$ non è definita.
>
>>[!esempio] _Esempio:_ proprietà dell’intersezione $\cap$ e dell’unione $\cup$
>>Dato un insieme $X$, l’intersezione $\cap$ e l’unione $\cup$ sono operazioni commutative e associative sull’insieme delle parti $P(X)$. Poiché $X\cap A=A$ e $\emptyset\cup A=A$ per ogni sottoinsieme $A \subseteq X$, l’insieme $X$ è neutro per l’operazione di intersezione $\cap$, mentre l’insieme vuoto $\emptyset$ è neutro per l’operazione di unione $\cup$.
>
>>[!esempio] _Esempio:_ proprietà della composizione di funzioni $\circ$
>>Dato un insieme non vuoto $X$ e dato un insieme di funzioni $F_X=\{\text{funzioni }f\colon X\to X\}$ con dominio e codominio $X$, la composizione $\circ$ è un’operazione su $F_X$ che è [[#^892c1f|associativa]], ma generalmente non è commutativa e ha la [[#^c01106|funzione identità]] $\text{id}_X$ come unico elemento neutro.

>[!proposizione] _Proposizione:_ unicità dell’elemento neutro
>Data un’operazione $\star$ su un insieme $A$, se un elemento neutro per $\star$ esiste, allora esso è unico.
>
>>[!dimostrazione] _Dimostrazione_ 
>>Se ci sono due elementi $e$ ed $e'$ neutri per $\star$, si deve dimostrare che $e = e'$. Si può calcolare il risultato dell’operazione tra i due elementi $e\star e'$ in due modi diversi:
>>1. Siccome $e$ è neutro, allora deve essere $e\star e'=e'$ ($e'$ è l’elemento mantenuto "invariato" dall’elemento neutro in questo caso);
>>2. Siccome $e'$ è neutro, allora deve essere $e\star e'=e$ ($e$ è l’elemento mantenuto "invariato" dall’elemento neutro in questo caso).
>>
>>Dato che l’operazione $e\star e'$ dà come risultati sia $e$ che $e'$, allora si ha che $e=e'$.
>>$\blacksquare$

>[!definizione] _Definizione_: invertibilità di un’operazione binaria interna
>Dato un’insieme $A$ con un’operazione $\star$ per cui esiste l’elemento neutro $e$, un elemento $a \in A$ si definisce _**invertibile**_ se esiste un altro elemento $b \in A$ (detto _inverso di $a$_) tali che il loro prodotto è uguale all’elemento neutro $e$:
>$$ a\star b=b\star a=e,\quad a,b,e\in A $$

%%Sistemare gli esempi%%
- **Invertibilità dell’addizione $+$**
    
    Per l’addizione $+$ su $\mathbb{N},\mathbb{Z},\Bbb{Q}$ ed $\mathbb{R}$ si cerca, dato un $a$, un numero $b$ tale che $a+b=0$ (dato che lo $0$ è l’elemento neutro dell’addizione). Allora, risolvendo l’equazione, si ha che $b=-a$ e quindi tutti gli elementi di $\mathbb{Z},\Bbb{Q}$ ed $\mathbb{R}$ sono invertibili, ma nel caso in cui l’addizione sia ristretta a $\mathbb{N}$ il solo elemento invertibile è lo $0$ stesso, in quanto se $n>0$ allora$-n<0$ e $\mathbb{N}$ non contiene numeri negativi.
    
- **Invertibilità della moltiplicazione $\cdot$**
    
    Per la moltiplicazione $\cdot$ in $\mathbb{N},\mathbb{Z},\Bbb{Q}$ ed $\mathbb{R}$ si cercano numeri $a$ tali che esista un $b$ con $a \cdot b = 1$. In base all’insieme dei numeri preso in considerazione, si hanno tre casi:
    
    1. se l’insieme è $\Bbb{Q}$ o $\mathbb{R}$, tale elemento $b$ esiste sempre eccetto nel caso di $a=0$ ($b=\frac{1}{a}$ non è definita per $a=0$) e, quindi, in questo caso ogni $a \ne 0$ è invertibile;
    2. se l’insieme è $\mathbb{N}$, l’unico elemento invertibile è $a=1$ ($b=\frac{1}{1}=1\in\mathbb{N}$);
    3. se l’insieme è $\mathbb{Z}$, gli unici elementi invertibili sono $1$ e $-1$ (per qualsiasi numero $a\ge2$ il suo reciproco non è in $\mathbb{Z}$).
- **Invertibilità dell’intersezione $\cap$ e dell’unione $\cup$**
    
    Un sottoinsieme $A \sub X$ è invertibile per l’operazione di intersezione $\cap$ in $P(X)$ se esiste un insieme $B \sub X$ tale che $A \cap B = X$. Siccome $A\cap B$ è sicuramente un sottoinsieme di $A$ (altrimenti non ci sarebbero elementi in comune), ciò può capitare solo se $A=X$ o $B=X$ e quindi $X$ è il solo elemento invertibile. Analogamente, un sottoinsieme $A \in X$ è invertibile per l’operazione di unione $\cup$ in $P(X)$ se esiste un insieme $B\sub X$ tale che $A \cup B = \emptyset.$ Siccome $A$ è sicuramente un sottoinsieme di $A \cup B$, ciò pu capitare solo se $A=\emptyset$ o $B=\emptyset$ e quindi $\emptyset$ è il solo elemento invertibile.
    
- **Invertibilità della composizione $\circ$**
    
    Le funzioni $f \in F_X$ invertibili per l’operazione di composizione sono solamente le funzioni biettive, in quanto:
    
    - se fossero solamente iniettive, allora ci potrebbero essere elementi del codominio che, invertendo le funzioni, diventerebbero elementi del dominio che non vengono presi in considerazione e in una funzione deve essere preso in considerazione tutto il dominio;
    - se fossero solamente suriettive, allora ci potrebbero essere elementi del codominio che sono associati a due o più elementi del dominio e che, invertendo le funzioni, diventerebbero elementi del dominio associati a due o più elementi del codominio e in una funzione ogni elemento del dominio può essere associato a un unico elemento del codominio. </aside>

</aside>

>[!proposizione] _Proposizione:_ unicità dell’inverso di un elemento
>Dato un insieme $A$ con un’operazione associativa $\star$ per cui esiste l’elemento neutro $e$ e un elemento invertibile $a \in A$, allora l’inverso di $a$ è unico, cioè presi due elementi $b, b' \in A$ tali che $b\star a=a\star b'=e$ si ha che $b=b'.$
>
>>[!dimostrazione] _Dimostrazione_ 
>>Per dimostrare che $b=b'$, si considera l’operazione $b\star a\star b'$ e si calcola in due modi diversi attraverso la proprietà associativa:
>>1. $(b\star a)\star b'=e\star b'=b'$;
>>2. $b\star(a\star b')=b\star e=b$.
>>
>>Si ha quindi che $b=b'$.
>>$\blacksquare$

>[!definizione] _Definizione_: elevamento a potenza di un elemento di un’operazione
>Dato un insieme $A$ dotato di un’operazione $\star$ e un elemento $a \in A$ che si vuole elevare a una potenza $n\in\mathbb{R}$:
>1. Se $n\ge1$, si definisce *$n$-esima potenza* di $a$ e si denota con $a^n$ l’elemento definito induttivamente come il prodotto di $a$ per $n$ volte:
>	$$ a^n=\underbrace{a\star\ldots\star a}_{n\text{ volte}} $$
>2. Se esiste l’elemento neutro $e$ per l’operazione $\star$, allora si pone $a^0=e$.
>3. Se $a \in A$ è invertibile e $n<0$, si pone $a^n=(a^{-1})^{|n|}$.
>
>>[!esempio] _Esempio:_ $a^3=a\star a\star a$
>>Dato un $a \in A$ e $n=3$, allora $a^3=\underbrace{a\star a\star a}_{3\text{ volte}}$.
>
>>[!esempio] _Esempio:_ $a^{-3}=(a^{-1})^3$
>>Dato un $a \in A$ e $n=-3$, allora $a^{-3}=(a^{-1})^{|-3|}=(a^{-1})^3$.

>[!proposizione] _Proposizione:_ $a^{m+n}=a^m\star a^n$
>Dato un insieme $A$ con un’operazione associativa $\star$, un elemento $a\in A$ e una coppia di elementi $m,n\in \mathbb{N}$ tali che $m,n\ge1$, allora vale la formula $a^{m+n}=a^m\star a^n$.
>Inoltre, dato un elemento neutro $e$ per $*$ e dato un elemento $a$ invertibile, allora la formula vale per ogni $m,n \in \mathbb{Z}$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>In base al valore delle potenze $m$ ed $n$, si possono avere 3 casi:
>>1. Per $m,n\ge0$, la formula da dimostrare si ottiene semplicemente separando i fattori:
>>	$$a^{m+n}=\underbrace{a\star\ldots\star a}_{\text{m+n fattori}}=\underbrace{a\star\ldots\star a}_{\text{m fattori}}\star\underbrace{a\star\ldots\star a}_{\text{n fattori}}=a^m\star a^n$$
>>2. Per $m,n\le0$, se l’operazione $\star$ possiede anche un elemento neutro $e$ e l’elemento $a$ è invertibile, allora si può trattare allo stesso modo il caso usando l’inverso $a^{-1}$ al posto di $a$:
>>	$$ (a^{-1})^{m+n}=\underbrace{(a^{-1})\star\ldots\star(a^{-1})}_{\text{m+n fattori}}=\underbrace{(a^{-1})\star\ldots\star(a^{-1})}_{\text{m fattori}}\star\underbrace{(a^{-1})\star\ldots\star(a^{-1})}_{\text{n fattori}}=(a^{-1})^{m}*(a^{-1})^{n} $$
>>3. Per $m>0,n<0$ (o viceversa), si pone $\bar{n}=-n>0$. Dato un $k=m+n=m-\bar n$, si possono considerare 3 casi:
>>	1. Per $k>0$ si ha che:
>>		$$ \begin{align*} a^{m+n}=a^k
>>		&=\underbrace{a\star\ldots\star a}_{\text{k fattori}}=\\
>>		&=\underbrace{a\star\ldots\star a}_{\text{k fattori}} \star \underbrace{a\star\ldots\star a}_{\text{n fattori}} \star \underbrace{a^{-1}\star\ldots\star a^{-1}}_{\text{n fattori}}=\\
>>		&=\underbrace{a\star\ldots\star a}_{\text{k+}\bar{n}\text{ fattori}} \star \underbrace{a^{-1}\star\ldots\star a^{-1}}_{\bar{n}\text{ fattori}}=\\
>>		&=a^{k+\bar n}\star(a^{-1})^{|n|}=\\
>>		&=a^m\star a^n \end{align*} $$
>>		![[Pasted image 20240211195324.png]]
>>		%%da sistemare%%
>>	2. Per $k=0$ si ha che $a^k=a^0=e$ e si procede come nel caso precedente rimpiazzando il primo prodotto di $k$ fattori con $e$;
>>	3. Per $k<0$ si ha che $a^k=(a^{-1})^{|k|}$ e si procede come nel primo caso $k>0$ sostituendo nelle espressioni l’elemento $a$ con $a^{-1}$.
>>
>>$\blacksquare$

%%Approfondire: [https://it.wikipedia.org/wiki/Proprietà_di_chiusura](https://it.wikipedia.org/wiki/Propriet%C3%A0_di_chiusura)%%
>[!definizione] _Definizione_: proprietà di chiusura di un insieme
>Dato un’insieme $A$ con un’operazione $\star$ e un sottoinsieme non vuoto $S\subseteq A$, l’insieme $S$ si definisce ***chiuso*** rispetto all’operazione $\star$ se, presi due elementi distinti $s_1$ ed $s_2$, il loro prodotto è sempre interno a $S$.
>
>>[!esempio] _Esempio:_ proprietà di chiusura di un insieme contenente solo un elemento neutro
>>Se per l’operazione $\star$ in $A$ esiste un elemento neutro $e$, il sottoinsieme $S=\{e\}$ è chiuso, in quanto $e\star e=e$.
>
>>[!esempio] _Esempio:_ proprietà di chiusura degli insiemi dei numeri pari e dispari
>>Considerando l’insieme $\mathbb{N}$ con l’operazione di addizione $+$, il sottoinsieme dei numeri pari $P\subseteq\mathbb{N}$ è chiuso perché la somma di due numeri pari è sempre pari.
>>Al contrario, il sottoinsieme dei numeri dispari $D\subseteq\mathbb{N}$ non è chiuso perché la somma di numeri dispari non è dispari (ma pari).
>
>>[!esempio] _Esempio:_ proprietà di chiusura delle operazioni di unione $\cup$ e intersezione $\cap$
>>Dato un insieme $X=\{1,2\}$, il suo [[Teoria degli insiemi#^84457e|insieme delle parti]] $\mathcal{P}(X)=\{\emptyset,\{1\},\{2\},\{1,2\},\}$ e un insieme $\mathcal{S}=\{Y\mid Y\subseteq \mathcal{P}(X) \land Y \ne \emptyset\}=\{\{1\},\{2\},\{1,2\},\}$ contenente tutti i sottoinsiemi possibili di $X$ tranne quello vuoto, allora $\mathcal{S}$ è chiuso rispetto all’operazione di unione $\cup$, in quanto se due elementi $Y_1,Y_2\in\mathcal{S}$ sono sottoinsiemi non vuoti di $X$, allora $Y_1\cup Y_2$ è sempre non vuoto.
>>Al contrario, l'insieme $\mathcal{S}$ non è chiuso rispetto all’operazione di intersezione $\cap$, in quanto può aversi $Y_1\cap Y_2=\emptyset$ anche se $Y_1$ e $Y_2$ non sono vuoti.

>[!proposizione] _Proposizione:_ proprietà di chiusura di un insieme di elementi invertibili
>Dato un insieme $A$ con un’operazione associativa $\star$ per cui esiste l’elemento neutro $e\in A$ e un sottoinsieme $U\subseteq A$ contenente tutti e soli gli elementi invertibili in $A$, allora $U$ è chiuso rispetto all’operazione $\star$.
>Più precisamente, se due elementi $a,b \in A$ sono invertibili, allora si ha che $(a\star b)^{-1}=b^{-1}\star a^{-1}$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>La formula rende esplicito il fatto che $a\star b\in U$ dal momento che contiene solamente gli elementi invertibili e, quindi, l’affermazione che $U$ sia chiuso segue immediatamente dalla definizione.
>>Per dimostrare la formula $(a\star b)^{-1}=b^{-1}\star a^{-1}$, basta osservare che, per la proprietà associativa, si hanno le seguenti equivalenze:
>>$$ \begin{align*}
>>(a\star b)\star (b^{-1}\star a^{-1})
>>&= a\star b\star b^{-1}\star a^{-1}\\
>>&= a\star (b\star b^{-1})\star a^{-1}\\
>>&=a\star e\star a^{-1}\\
>>&=a\star a^{-1}\\
>>&=e
>>\end{align*} $$
>>$$ \begin{align*}
>>(b^{-1}\star a^{-1})\star(a\star b)
>>&=b^{-1}\star a^{-1}\star a\star b\\
>>&=b^{-1}\star(a^{-1}\star a)\star b\\
>>&=b^{-1}\star e\star b\\
>>&=b^{-1}\star b\\
>>&=e
>>\end{align*} $$
>>Avendo ottenuto $(a\star b)\star (b^{-1}\star a^{-1})=(b^{-1}\star a^{-1})\star(a\star b)=e$, allora $b^{-1}\star a^{-1}$ dovrà essere necessariamente l'inverso di $(a\star b)$ e, di conseguenza, $(a\star b)^{-1}=b^{-1}\star a^{-1}$.
>>$\blacksquare$

# Fonti
- lezioni terracini, chen
- libro di bruno martelli
- libro di mdag
- lezioni seiler
- libro di analisi