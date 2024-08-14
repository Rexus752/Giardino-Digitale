# Paradigma del C

Il C è un linguaggio appartenente al paradigma imperativo, cioè il concetto base del linguaggio è la variabile e l'operazione di base è l'assegnamento a variabile, con il programma che è una sequenza strutturata (strutturata = con strutture di controllo, cicli, ecc.) di istruzioni che operano su variabili.

# 1) Variabile

`int x`

IL SIMBOLO x HA DUE SIGNIFICATI DIVERSI A SECONDA CHE OCCORRA A SINISTRA O DESTRA DEL SIMBOLO `=`:
- A SINISTRA DENOTA UN **L-VALUE**, OVVERO L’INDIRIZZO DI UNA PORZIONE DI MEMORIA IN CUI È POSSIBILE SCRIVERE;
- A DESTRA DENOTA UN **R-VALUE**, OVVERO IL VALORE CONTENUTO NELLA PORZIONE DI MEMORIA DI DIMENSIONE sizeof(T), DOVE T È IL TIPO DI x, CHE INIZIA ALL’INDIRIZZO ASSOCIATO A x (ALL’INIZIO DELL’ESECUZIONE DEL PROGRAMMA IN CASO SI ALLOCAZIONE STATICA, AL MOMENTO IN CUI LA FUNZIONE IN CUI x È DICHIARATA IN CASO DI ALLOCAZIONE DINMAMICA)

int x; DICHIARAZIONE
x = 0; ASSEGNAZIONE, DI x SI USA L’INDIRIZZO
x = x+1; ASSEGNAZIONE IN CUI È USATO ANCHE IL VALORE (la prima x è l'indirizzo, la seconda x è il valore)

## 1.1) Indirizzo di una variabile

L’indirizzo di x si ottiene con l’operatore unario &:
&x : indirizzo di x

![](Pasted%20image%2020240803165715.png)

![](Pasted%20image%2020240803165734.png)

![](Pasted%20image%2020240803165747.png)

## 1.2) Operatori `&` e `*`

`&var` indica l’indirizzo della variabile `var`
`*indexp` l’operatore `*` dereferenzia un’espressione, cioè permette di accedere al contenuto della cella che ha l’indirizzo calcolato dall'espressione `indexp`
`*(&var)` come caso particolare, indica il contenuto della variabile che ha per indirizzo `&var`, ovvero equivale a `var`

# 2) Struct

Le strutture (struct) in C sono collezioni di dati correlati che possono essere disomogenei (cioè di tipo diverso)

Tipo che identifica una collezione di dati correlati che possono essere disomogenei (`libro` è il _tag_ o _etichetta_ della struttura):
```c
struct libro {
	char titolo[MAXT];
	int pagine;
	char autore[MAXN];
	float prezzo;
};
```

Questo è un prototipo di struttura. Non ha allocata memoria.
In seguito è possibile dichiarare variabili di tipo `struct libro` (è un tipo unico).
Esempio:
```c
struct libro L; 
```

Abbiamo dichiarato una variabile di nome `L` e di tipo `struct libro`.
`struct libro* Lptr = &L;` per il puntatore
`L.pagine = 200;` con l'operatore `.`
`ptrL->pagine = 200;` con l'operatore `->`
![](Pasted%20image%2020240803181827.png)
Nota: L’operatore `->` permette di accedere più semplicemente alla struct noto il suo puntatore, risparmiando la scrittura (equivalente): `(*ptrL).pagine = 200`

## 2.1) Utilizzo con le funzioni

- Le variabili struct nelle funzioni vengono passate per valore! (come se passassi una variabile di tipo primitivo, es: `int`)
- I membri della struct sono passati nel modo in cui verrebbero passate variabili dello stesso tipo
	- Pertanto la funzione chiamata non modifica la struct nel chiamante! %%ma se vengono passate come le variabili dello stesso tipo, allora non dovrebbero essere modificate se vengono passate per valore?%%
	- Per modificare la struct bisogna passarla per riferimento con l'operatore `&`
- Passare le strutture per riferimento è più efficiente (non occorre la copiatura dell’intera struttura, si lavora direttamente sull'"originale")
- Si può sfruttare questa peculiarità delle strutture per passare ad una funzione un array per valore (se ciò è desiderato), "impacchettandolo" in una struttura!

### 2.1.1) Esempio

```c
void stampalibro(struct libro L) {
	// richiede la copia di sizeof(struct libro) bytes!
}
void stampalibro(struct libro* Lptr) {
	// molto più efficiente
}
```

## 2.2) Padding

I campi hanno dimensione diversa e sono allocati in ordine di specifica. I sistemi operativi non allocano la memoria a byte ma a gruppi di 4, 8, 16 … byte. Una struct può avere allocata un po’ più memoria dello stretto necessario per riempire lo spazio rimanente (padding).

inizializziamo uno struct e due elementi P1, P2
```c
struct prova {
	char x;
	char y;
	int z;
} P1, P2;
```
(la parte `struct prova {...}` è letteralmente la parte di dichiarazione del tipo, stessa cosa con `int P1, P2`). 

## 2.3) Osservazione: conseguenze del padding %%confronti tra strutture%%

Notiamo che:
- `sizeof(struct prova) = 8`
- `sizeof(char)*2 + sizeof(int) = 6`

`P1 = P2; // OK`
`if (P1 == P2) … // NON SI PUÒ FARE! Perché?`

## 2.4) Strutture autoreferenziali

Una struct non può contenere un membro del proprio tipo di struct, ma può contenere un puntatore a quel tipo di struct.

Ad esempio:
```c
struct employee {
	char firstName[20];
	char lastName[20];
	struct employee manager;
};
```
NON SI PUÒ FARE, mentre:
```c
struct employee {
	char firstName[20];
	char lastName[20];
	struct employee* managerPtr;
};
```
è un'operazione fattibile.

`struct employee` è detta _struct autoreferenziale_ (_self-referential struct_)

### 2.4.1) Esempio più complesso

Dichiarazione nutrizionale di un alimento:
```c
struct dich_nutriz {
	int energia;
	float grassi;
	float carboidrati;
	float fibre:
	float proteine;
	float sale;
}
```

Posso costruire tipi di dati/variabili complessi/e, es.
```c
struct cibo {
	char nome[MAX];
	struct dich_nutriz tabella;
} dispensa[MAXD];
```

in dispensa ci sono tanti cibi, mantengo associata a ciascuno la sua dichiarazione nutrizionale (es. per applicazione dietologica)

`dispensa[MAXD]` è un array di struct, ognuna comprende un nome e una dichiarazione nutrizionale (struct annidata)

![](Pasted%20image%2020240806115005.png)

# 3) `typedef`

Il `typedef` consente di creare sinonimi (o alias) per tipi precedentemente definiti. Spesso (ma non solo) usato con le struct, esempio:

```c
typedef struct {
	char titolo[MAXT];
	int pagine;
	char autore[MAXN];
	float prezzo;
} Libro; // nuovo tipo “Libro”
Libro L1, L2; // variabili di tipo “Libro”
```

e in questo caso la struct tag non è più necessaria perché possiamo usare direttamente la parola `Libro` per dichiarare il tipo delle variabili, come abbiamo fatto con `L1` e `L2`.

## 3.1) Convenzione scrittura del nome

Per convenzione, si scrive in MAIUSCOLO la prima lettera dei nomi dei tipi che sono sinonimi di altri tipi, es.
```c
typedef char* Stringa;
```

Dopodichè è permesso scrivere le variabili in minuscolo come al solito, ad esempio:
```c
Stringa s;
Stringa doc[MAXLINES];
int strcmp(Stringa, Stringa);
```

# 4) `enum`

Permette di definire una lista di valori interi costanti convenientemente rinominati con etichette (univoche), dichiarando solo per la prima etichetta il valore iniziale e, a seguire, le altre etichette avranno valori crescenti di un'unità %%mamma mia come cazzo l'ho scritta 'sta frase%%. Ad esempio:
```c
enum months {JAN = 1, FEB, MAR, APR, MAY, JUN, JUL, AUG, SEP, OCT, NOV, DEC};
/* JAN è 1, FEB è 2, e così via */
```

Convenzionalmente si scrivono le etichette in maiuscolo. Sono un mezzo efficiente (preferibile alle `#define`) per
associare valori interi a dei nomi.

## 4.1) Combinazione di `typedef` ed `enum`

Posso anche combinare `typedef` e `enum`:
```c
typedef enum outcome {OUTOFMEMORY = −1, ALREADYPRESENT, INSERTED} Outcome;
```
Cioè, prima enumeriamo una variabile `outcome` con le tre etichette e, successivamente, la definiamo come un nuovo tipo `Outcome`, che ora è un intero che può valere `-1`, `0` o `1`. Per esempio:
```c
Outcome operazione(...) {
	...
	return OUTOFMEMORY;
}
```
e questa funzione ritornerà il valore `-1` (perché nell'`enum` abbiamo assegnato `-1` all'etichetta `OUTOFMEMORY`).
# 5) `union`

Variabili simili alle strutture, ma che in un dato momento contengono uno solo dei membri specificati entro le parentesi graffe `{}`. Sintassi identica a quella per le strutture, sostituendo la keyword `struct` con la keyword `union`:
```c
union myunion {
	char cval;
	int ival;
	float fval;
} u;
```
LA VARIABILE `u` PUO’ CONTENERE:
- UN CHAR DI NOME `cval`
OPPURE
- UN INTERO DI NOME `ival`
OPPURE
- UN FLOAT DI NOME `fval`

## Differenza tra `union` e `struct`

Attenzione alla differenza tra strutture e unioni:
![](Pasted%20image%2020240806123333.png)

## Sintassi

Stessa sintassi e operazioni delle strutture:
```c
union myunion {
	char cval;
	int ival;
	float fval;
} u, *ptru;
u.cval = ’h’;
u.ival = 0xDE4D7E91; /* sostituisce cval! */
ptru = &u;
ptru->fval = 3.14; /* sostituisce ival! */
```
Alla fine delle operazioni, `u` (e il suo puntatore `*ptru`) saranno di tipo `float` e avranno come valore `3.14`.

## Unioni e strutture annidate

### Struttura in un'unione

Nota: come membro di una unione potrei avere una struttura!
```c
union name1 {
	struct name2 {
		int i;
		float f;
	} svar;
	double d;
} uvar;
uvar.svar.i = 1;
```
E cioè, l'unione `name1` può avere solo un tipo di valore alla volta tra la struttura `name2` (e i suoi membri `i` ed `f`) oppure il decimale `d`. Si dichiara quindi una variabile `uvar` di tipo `union name1` e successivamente, con l'istruzione `uvar.svar.i = 1;`, si sceglie di impostare il suo valore come `struct name2` con il valore `float` indefinito e il valore `int` uguale a `1`.

### Unione in una struttura

Similmente, un'unione può apparire in una struttura:
```c
struct {
	int flags;
	char *name;
	int utype;
	union {
		int ival;
		float fval;
		char *sval;
	} u;
} symtab[NSYM];
```
Questo è un esempio realistico di uso delle unioni per realizzare una "tabella di simboli"

## Cosa contengono in un dato istante?

È responsabilità del programmatore tenere traccia di quale sia il tipo attualmente registrato in una unione. Un approccio comune è quello di memorizzare in una variabile il tipo correntemente memorizzato nella unione, tramite ad esempio un piccolo intero con valori definiti tramite enumerazione:
```c
enum Union_Tag {IS_INT, IS_CHAR};
struct TaggedUnion {
	enum Union_Tag tag;
	union {
		int i;
		char c;
	} data;
};
```
SI PARLA IN QUESTO CASO DI UNA "UNIONE ETICHETTATA" (TAGGED UNION)

## Esperimento pratico

- Scrivere un semplice programma di test, `unione.c`, copiando le dichiarazioni qui sotto:
	```c
	enum Union_Tag {IS_INT, IS_CHAR};
	struct TaggedUnion {
		enum Union_Tag tag;
		union {
			int i;
			char c;
		} data;
	};
	```
- Scrivere una funzione che, dato un puntatore ad un'unione etichettata, stampa opportunamente il valore in essa contenuto
- Scrivere un semplice main per provarne il funzionamento
- Cosa succede se si prova a estrarre da un'unione un tipo sbagliato?

## Riassunto

- Una unione è in pratica una struttura nella quale tutti i membri hanno spiazzamento nullo rispetto alla base e la struttura è sufficientemente grande da contenere il membro più ampio, garantendo il corretto allineamento in memoria per tutti i tipi presenti nella union
- Sono utili in Sistemi Operativi, ad esempio nelle primitive di allocazione dinamica di memoria, oppure nella costruzione di tabelle di simboli di tipo diverso
