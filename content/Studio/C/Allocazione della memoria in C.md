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

## Organizzazione della memoria assegnata ad un programma C in esecuzione

1. Area programma: memorizza il programma (compilato e linkato) – la sua dimensione è fissata a compile time.
2. Area statica: memorizza le variabili globali, dichiarate al di fuori delle funzioni, allocate staticamente (quando inizia l’esecuzione del programma) e accessibili da tutte le funzioni – la sua dimensione è fissata a compile time.
3. Heap: memorizza variabili allocate dinamicamente – la sua dimensione varia durante l’esecuzione,.
4. Stack: memorizza le variabili dichiarate all'interno delle funzioni che sono attive (allocate automaticamente, aggiungendo/togliendo un record di attivazione in cima allo stack, quando l’esecuzione di una funzione inizia/termina) – la sua dimensione varia durante l’esecuzione.

La dimensione di STACK + HEAP è fissata a compile time, cioè lo spazio occupato da entrambe le memorie non può andare oltre quello fissato all'inizio della compilazione.

Lo stack è organizzato in record di attivazione, l'heap non è organizzato ma contiene informazioni sparse (perché il `malloc` non si occupa di riordinare la memoria allocata dinamicamente, ma la alloca in modo contiguo rispetto all'ordine di esecuzione delle istruzioni).

![](Pasted%20image%2020240806161550.png)

# Allocazione e deallocazione dinamica

L'allocazione e deallocazione dinamica di memoria vengono effettuate durante l’esecuzione del programma, occorre utilizzare delle funzioni di libreria:
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

Il suo unico parametro è `size_t size`, cioè un valore di tipo `size_t` da 4 byte unsigned (es. `malloc(8)` alloca 8 byte, cioè 8 byte nella RAM precedentemente riservati diventano disponibili per il processo, cioè il programma in esecuzione).

La funzione `malloc` ha anche un valore di ritorno di tipo `void *`, cioè ritorna un puntatore a un indirizzo di memoria di un tipo non ben-specificato che poi dovrà essere convertito nel tipo voluto da noi (es. se vogliamo allocare degli interi, il puntatore verrà castato in interi).

### Esempio: allocazione dinamica di un intero

Vogliamo allocare un intero e sappiamo che un intero occupa 4 byte. Faremo quindi:
```c
int *ptr;
ptr = (int *) malloc(4);
```

È ovvio che il tipo del puntatore e del casting devono coincidere (entrambi `int *`).

Problema: abbiamo allocato 4 byte, ma non è intuitivo sapere automaticamente quanti "valori" possiamo inserire (es. se vogliamo allocare un array di interi, dobbiamo calcolare noi il numero di byte totali). Per poter direttamente inserire il numero di valori che vogliamo allocare, usiamo la funzione `sizeof(type)`:
```c
int *array;
array = (int *) malloc(sizeof(int) * 8);
```
Così allocheremo lo spazio di 8 numeri interi (cioè $4 \times 8 = 32$ byte).

Scriviamo `int *array` e non `int[] *array` perché `array`, essendo appunto un array di valori, come variabile è in realtà un semplice puntatore all'array vero e proprio in memoria, quindi per scorrere l'array dobbiamo usare gli indici nelle parentesi quadre `[]`.

Con `sizeof()` possiamo usare sia dati primitivi di C, sia dati creati da noi con il `typedef`.

## Funzione `free`

Permette di liberare dinamicamente (durante l’esecuzione del programma) della memoria precedentemente allocata in maniera dinamica per poterla poi nuovamente usare con scopi diversi. Dopo `free` tale memoria non sarà più considerata (dal run-time del C) come allocata – ovvero sarà (ri)allocabile.

```c
cast-type *ptr;
ptr = (cast-type*) malloc(byte-size);
free(ptr);
```

# Allocazione statica vs dinamica

| Allocazione statica | Allocazione dinamica |
| ------------------- | -------------------- |
| `int x;`            | `int *x;`            |

Nella statica a `x` verrà assegnato il valore dell'intero, mentre nella dinamica a `x` verrà assegnato il valore di un puntatore a intero.

In entrambi i casi, finora, c'è un valore casuale assegnato a `x`.

---

| Allocazione statica | Allocazione dinamica                            |
| ------------------- | ----------------------------------------------- |
| `int x;`            | `int *x;`<br>`x = (int *) malloc(sizeof(int));` |

Nell'allocazione dinamica, dopo la seconda istruzione nella variabile `x` viene inserito il valore dell'indirizzo in memoria heap allocato dinamicamente. Ricordiamo che la variabile `x` è presente nello stack, solo l'indirizzo puntato dal valore di `x` è contenuto nell'heap.

---

| Allocazione statica  | Allocazione dinamica                                         |
| -------------------- | ------------------------------------------------------------ |
| `int x;`<br>`x = 0;` | `int *x;`<br>`x = (int *) malloc(sizeof(int));`<br>`*x = 0;` |

Dopo l'assegnazione del valore:
- Nell'allocazione statica, la `x` (salvata nello stack) conterrà il valore `0`;
- Nell'allocazione dinamica, la `x` (salvata nello stack) conterrà il valore dell'indirizzo in memoria heap e i 4 byte contigui a quell'indirizzo in memoria heap, invece, conterranno lo `0`.

---

| Allocazione statica  | Allocazione dinamica                                                       |
| -------------------- | -------------------------------------------------------------------------- |
| `int x;`<br>`x = 0;` | `int *x;`<br>`x = (int *) malloc(sizeof(int));`<br>`*x = 0;`<br>`free(x);` |

Dopo l'esecuzione della `free`, la variabile `x` continuerà a contenere il valore dell'indirizzo in memoria heap, ma quando proveremo ad operarci il programma ci restituirà un errore %%segmentation fault?%%.

Sta al programmatore quindi completare quell'operazione con `x = NULL`.

## Confronto schematico

Statica (ottimizzata per il tempo):
- Pro: accesso più rapido perché so già dove si trova la mia variabile, senza dover risalire all'indirizzo ecc.
- Contro: occupo memoria anche per variabili che non uso (es. dichiaro `int array[100]` ma uso solo le prime 5 celle)

Dinamica (ottimizzata per lo spazio):
- Pro: occupo solo la memoria che mi serve, senza sprecarne alcuna (se non mi serve la posso liberare direttamente)
- Contro: accesso meno rapido perché per accedere alla memoria dobbiamo navigare con i puntatori

# Allocazione e deallocazione dinamiche di un array

## Allocazione dinamica di un array

Array di 10 interi:
```c
int *d;
d = (int*) malloc(sizeof(int)*10);  // d = 0xabcf08134ba0
// d* = valore nell'indirizzo di memoria 0xabcf08134ba0 = valore non noto
```

## Generalizziamo

```c
type *ptr; 
ptr = (type*) malloc(sizeof(type)*n);
```
- Quanto spazio occupa in totale l'array? `sizeof(type)*n` nell'heap (array vero e proprio) + `sizeof(type)` nello stack (valore del puntatore)
- posso usare `ptr+1`? sì
- posso usare `ptr++`? sì, vedi slide successiva

### Effetto di `ptr++`: spostamento del puntatore

Incrementare il puntatore con `ptr++` significa incrementarlo di `sizeof` byte in base al tipo dell'array: es. con un array di interi, `ptr++` incrementerà `ptr` di 4 byte per farlo passare all'elemento successivo. L'elemento precedente è accessibile ancora attraverso l'espressione `ptr-1` o, modificando il valore di `ptr`, con `ptr--`.

## Deallocazione dinamica di un array

```c
type *ptr; 
ptr = (type*) malloc(sizeof(type)*n);
free(ptr);
```

La `free` va fatta quando si vuole liberare la porzione di RAM occupata dall’array perché non ci serve più. Sarà considerata (dal run-time del C) come non allocata - e quindi (ri)allocabile.

Però rimane il valore dell'indirizzo in `ptr`: fare quindi `ptr = NULL;` (ATTENZIONE: il valore di d non diventa NULL automaticamente per effetto della free!) https://it.wikipedia.org/wiki/Dangling_pointer

## Esempio di un uso errato

```c
char *ptr = (char*) malloc(sizeof(char)*10);
...
free(ptr); // senza mettere a NULL il puntatore
... 
if (ptr != NULL) { 
	printf(..., d[0]);
	...
};
```

Il valore `NULL` del puntatore segnala che non si riferisce ad un’area di memoria allocata. Occorre mantenere la consistenza se no il suo valore sarà non significativo e l’esecuzione successiva sarà errata.

ATTENZIONE: è possibile che per un po' lo spazio liberato dalla `free` sembri ancora disponibile all'esecuzione e gli assegnamenti o le `printf` non diano istantaneamente errore. Tuttavia, quella memoria può essere riassegnata per un altro uso in qualsiasi momento! Mettereste qualcosa di utile in una cassettiera abbandonata per strada, dopo avere chiamato l'AMIAT che può venire a ritirarla da un momento all'altro?

## Passaggio di array come parametro

```c
int main() {
	int stat[n];
	int *dyn = (int*) malloc(sizeof(int) * n);
	
	init(stat);
	print(stat);
	
	init(dyn);
	print(dyn);
}
```

Nel caso dell'array statico, sappiamo che quando lo passiamo semplicemente come `stat` stiamo passando in realtà il puntatore all'array: quindi, nel caso di una funzione che fa uso del parametro modificandolo (come la funzione `init` che inizializza l'array che le viene passato), le modifiche vengono effettuate in realtà direttamente sull'array originale.
Anche nel caso di `dyn`, nell'allocazione dinamica la variabile che "rappresenta" l'array è in realtà un puntatore al primo elemento dell'array: anche in questo caso, se si prova a modificare l'array, le modifiche si rifletteranno anche al di fuori della funzione stessa perché si sta operando per riferimento e non per valore.

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