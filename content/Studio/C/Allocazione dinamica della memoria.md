# Tipi di memoria in C

Nella modello di memoria della macchina astratta C esistono tre tipi di memoria per allocare le variabili:
1. Memoria statica, usata per memorizzare le variabili globali (e le variabili locali static).
2. Memoria automatica (_stack_), usata per memorizzare i record di attivazione delle funzioni. Ogni record di attivazione è costituito da:
	1. L’indirizzo di codice dell’istruzione successiva a quella che ha invocato la funzione (indirizzo di rientro);
	2. I parametri della funzione;
	3. Le variabili locali (non static) alla funzione.
3. Memoria dinamica (heap), usata per allocare variabili (spazi di memoria) la cui dimensione si conosce solo in fase di esecuzione (Esempio: in un programma che dopo aver acquisito il numero di rilevazioni disponibili da una sonda di temperatura, le memorizzi in un vettore). (I VLA (variable-length array) sono stati introdotti in C99, con le versioni precedenti di C si deve usare la memoria dinamica per gestire questo esempio. Ma, come vedremo, la memoria dinamica ha anche altri utilizzi.)
	
In C, l’allocazione nella memoria heap e la sua liberazione sono espliciti, cioè si usano apposite chiamate a funzioni:
- La funzione `malloc` della libreria `stdlib.h` alloca uno spazio di memoria contiguo nell’heap e restituisce un puntatore al primo byte allocato. In caso di fallimento restituisce il valore `NULL` che corrisponde all'indirizzo riservato `0`.
- La funzione `free` della libreria `stdlib.h` libera lo spazio di memoria precedentemente allocato con la `malloc`.

# Organizzazione della memoria assegnata ad un programma C in esecuzione

1. Memorizza il programma (compilato e linkato) – la sua dimensione è fissata a compile time.
2. Memorizza le variabili globali, dichiarate al di fuori delle funzioni, allocate staticamente (quando inizia l’esecuzione del programma) e accessibili da tutte le funzioni – la sua dimensione è fissata a compile time.
3. Memorizza variabili allocate dinamicamente – la sua dimensione varia durante l’esecuzione, ma la dimensione di STACK + HEAP è fissata a compile time.
4. Memorizza le variabili dichiarate all'interno delle funzioni che sono attive (allocate automaticamente, aggiungendo/togliendo un record di attivazione in cima allo stack, quando l’esecuzione di una funzione inizia/termina) – la sua dimensione varia durante l’esecuzione.

![](Pasted%20image%2020240806161550.png)

# Allocazione e deallocazione dinamiche

Ovvero effettuate durante l’esecuzione del programma, occorre utilizzare delle funzioni di libreria:
```c
#include <stdlib.h>
void *malloc(size_t size);
void free(void *ptr);
```

## Funzione `malloc`

Permette di allocare dinamicamente (durante l’esecuzione del programma) una quantità di memoria specificata.
```c
cast-type *ptr;
ptr = (cast-type*) malloc(byte-size);
```

## Funzione `free`

Permette di liberare dinamicamente (durante l’esecuzione del programma) della memoria precedentemente allocata in maniera dinamica. Dopo free tale memoria non sarà più considerata (dal run-time del C) come allocata – ovvero sarà (ri)allocabile.

```c
cast-type *ptr;
ptr = (cast-type*) malloc(byte-size);
free(ptr);
```

## Allocazione statica/automatica vs dinamica

![](Pasted%20image%2020240806163226.png)

![](Pasted%20image%2020240806163243.png)

![](Pasted%20image%2020240806163250.png)

## Deallocazione: funzione `free`

![](Pasted%20image%2020240806163301.png)

## Confronto schematico

![](Pasted%20image%2020240806163416.png)

# Allocazione di array

`int v[10];`
- quanto spazio occupa? `sizeof(v) == sizeof(int)*10 == 40 byte`
- posso usare `v+1`? sì, es: `printf(“%d”, *(v+1)) *(v+1)` equivale a `v[1]`
- posso fare `v++`? no, `v` non può essere modificato

## Allocazione dinamica di un array

```c
int *d;
d = (int*) malloc(sizeof(int)*10);  // d = 0xabcf08134ba0
// d* = valore nell'indirizzo di memoria 0xabcf08134ba0 = valore non noto
```

## Generalizziamo

![](Pasted%20image%2020240806165356.png)

```c
T *d; 
d = (T*) malloc(sizeof(T)*ESPR);
```
- Quanto spazio occupa (indirizzo in memoria heap)? `spazio per l’array + sizeof(T*)`, cioè +8 byte
- posso usare `d+1`? sì
- posso usare `d++`? sì, vedi slide successiva

# Effetto di `d++`

![](Pasted%20image%2020240806165527.png)

# Deallocazione di un array

```c
T *d;
d = (T*) malloc(sizeof(T)*ESPR);
free(d); 
```

La porzione di RAM occupata dall’array saràconsiderata (dal run-time del C) come non allocata - e quindi (ri)allocabile.

Però rimane il valore dell'indirizzo in `d`: fare quindi `d = NULL;` (ATTENZIONE: il valore di d non diventa NULL per effetto della free!)

## Esempio di un uso errato

```
char *d = (char*) malloc(sizeof(char)*10);
...
free(d); // senza mettere a NULL il puntatore
... 
if (d != NULL) { 
	printf(..., d[0]);
	...
};
```
Il valore NULL del puntatore segnala che non si riferisce ad un’area di memoria allocata. Occorre mantenere la consistenza se no il suo valore sarà non significativo e l’esecuzione successiva sarà errata.

ATTENZIONE: è possibile che per un po' lo spazio liberato dalla `free` sembri ancora disponibile all'esecuzione: gli assegnamenti/le `printf` non danno errore. Tuttavia, quella memoria può essere riassegnata per un altro uso in qualsiasi momento! Mettereste qualcosa di utile in una cassettiera abbandonata per strada, dopo avere chiamato l'AMIAT?

# Passaggio di array come parametro

```c
int main() {
	int astatico[N];
	int *adinamico = (int*) malloc(sizeof(int) * N);
	
	init(astatico);
	stampa(astatico);
	
	init(adinamico);
	stampa(adinamico);
}
```
L'effetto sarà uguale o diverso?
Risposta: sarà uguale perché anche il nome di un array statico corrisponde a un puntatore.

# Allocazione di `struct`

```c
typedef struct {
	char titolo[MAXT];
	int pagine;
	char autore[MAXN];
	float prezzo;
} Libro;
Libro L1;
```
Questo è un prototipo di struttura, non ha allocata memoria. Occorre dichiarare variabili di tipo `Libro`, come `L1`.

## Strutture allocate dinamicamente

```c
Libro *L;
L = (Libro*) malloc(sizeof(Libro);
(*L).pagine = 200;
// oppure più solitamente
L->pagine = 200;

// Per disallocare:
free(l);
l = NULL;
// Necessarie entrambe per mantenere la consistenza dell'implementazione
```

# Passaggio di struct come parametro

```c
struct prova {
	int x;
	int y;
};
void stampa(struct prova p) {
	printf("\nx = %d\n", p.x);
	printf("y = %d\n", p.y);
};

int main() {
	struct prova statica;
	struct prova *dinamica = (struct prova*) malloc(sizeof(struct prova));
	// inizializzo statica a (10, 10) e dinamica a (20, 20)
	statica.x = 10; statica.y = 20;
	dinamica->x = 20; dinamica->y = 20;
};
```

Come invoco `stampa` sulle due variabili?
```c
stampa(statica);
stampa(*dinamica);
```
(a differenza degli array, solo "dinamica" è puntatore)

```c
void init(struct prova *p) {
	p->x = 15;
	p->y = 25;
}
```
`init` è una funzione che modifica la variabile passata come argomento. A questo fine dobbiamo necessariamente usare un puntatore

Come invoco `init` sulle due variabili?
```c
init(&statica);
init(dinamica);
```
Per far modificare `statica` occorre passare il suo indirizzo (puntatore a statica), invece `dinamica` è già l’indirizzo della struct allocata dinamicamente