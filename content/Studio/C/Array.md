
Il C permette di usare gli array mono e multi-dimensionali, cioè sequenze di valori o elementi omogenei (cioè dello stesso tipo). Quelli bi-dimensionali sono anche detti _matrici_. 

`int v[10];`
- quanto spazio occupa? `sizeof(v) == sizeof(int)*10 == 40 byte`
- posso usare `v+1`? sì, es: `printf("%d", *(v+1))` e `*(v+1)` equivale a `v[1]`
- posso fare `v++`? no, `v` viene trattato come una costante non può essere modificato (perché in realtà `v++` corrisponde all'istruzione di assegnamento `v = v + 1`)

# Scorrere un array con il cursore

```c
#include <stdio.h>
#include <stdlib.h>

#define N 10

/*
 * questo programmino mostra l'uso di puntatori come cursori che
 * permettono di percorrere un array. Nel main trovate un array
 * interi allocato staticamente e un puntatore ad array (il cursore).
 *
 * Al cursore viene assegnato un riferimento all'ultimo elemento dell'array.
 * Tramite un ciclo for l'array viene quindi percorso a ritroso assegnando
 * valore 1 alla cella di indice 9, 2 a quella di indice 8 ecc. fino alla 
 * prima che varrà 10. Attenzione: per come è controllato l'array l'ultimo
 * assegnamento avviene al di fuori del ciclo.
 *
 * Per completare il programma aggiungiamo due funzioni: una per inizializzare
 * un array a valori da 100 a 109 e l'altra per visualizzare il contenuto di 
 * un array. Si chiamano init e stampa.
 *
 * Il loro scopo è mostrare sempre come si possano dichiarare in maniera 
 * alternativa i parametri che riceveranno dal chiamante un array di dati.
 * Init usa un puntatore, stampa usa un array non dimensionato.
 *
 */


/*
 * il parametro a corrisponderà, nell'invocazione di init, a un array.
 * Si potrebbe accedere alle celle dell'array usando l'indice tramite
 * la notazione a[i]. In questo esempio usiamo invece direttamente il puntatore.
 * L'indice viene incrementato ma solo per calcolare il valore della cella.
 * Per far progredire il puntatore si utilizza la forma abbreviata a++.
 * NB: il parametro della funzione, nell'esempio, contiene una copia 
 * dell'indirizzo passato all'atto dell'invocazione e tale copia è il cursore
 * che andiamo a sfruttare.
 */
void init(int *a) {
	for (int i = 0; i < N; i++, a++) {
		*a = 100 + i;
	}
}

// il seguente è un altro modo per dire che il parametro corrisponderà
// all'indirizzo di un elemento che fa parte di un array. Non cambia molto
// rispetto alla funzione precedente, semplicemente si evidenzia la natura
// di array dei dati trattati. Il for è implementato nella maniera base, cioè
// usando un indice intero incrementato a ogni iterazione per accedere alle
// varie celle
void stampa(int a[]) {
	printf("\n");
	for (int i=0; i<N; i++) printf("%d ", a[i]);
	printf("\n");
}

/* il nostro main */
int main() {
   int prova[N]; // ecco l'array su cui lavoreremo
   int *cursore; // ecco il cursore
   int valore;   // variabile che serve nell'ultimo for

   init(prova); // prova è un puntatore costante, si riferisce alla prima cella
		// dell'array dichiarato. L'indirizzo di tale punto di partenza
		// viene copiato nel parametro formale usato da init. Tale
		// funzione ne userà quindi una copia.

   stampa(prova); // vediamo cosa contiene prova

   // questo ciclo è gestito in maniera più complessa di come ho capito siete
   // abituati. Dettaglierò in poche slide il suo funzionamento
   for (cursore=prova+9, valore=10; cursore!=prova; cursore--,valore--) 
	   *cursore = valore;
   *cursore = valore;

   stampa(prova); // vediamo cosa contiene prova
}
```

Vedere il PDF https://informatica.i-learn.unito.it/pluginfile.php/399628/mod_folder/content/0/commenti-cursorep.pdf?forcedownload=1

## Dalla registrazione dell'array

Il nome dell'array è di per sè un puntatore: es.
```c
int main() {
	int prova[N];
}
```
sto dichiarando una variabile di nome `prova` che si troverà all'interno del record di attivazione del main che è predisposta a essere una collezione di elementi omogenei (cioè dello stesso tipo) di tipo intero.

Sullo stack di esecuzione, anziché una sequenza di celle (ognuna contenente un elemento), al nome `prova` viene assegnato solamente il valore dell'indirizzo della prima cella della "lista" e poi, tramite l'indice, cioè il valore numerico inserito nelle parentesi quadre dopo il nome `prova`, si arriva alla cella desiderata spostandosi a partire dalla cella iniziale: es. `prova[2]` significa che devo vedere l'elemento che sta 2 celle dopo a partire dalla prima cella iniziale, cioè la terza cella (che ha infatti indice `2` perché gli indici partono da `0` e quello della prima cella è `0`).

Si può usare però il puntatore direttamente come cursore per spostarsi nell'array anziché usare l'"offset" degli indici. Si può usare in 2 maniere:
- `void init(int *a)` è una funzione che ha come unico parametro un puntatore a intero (cioè un array), quindi nel main va `init(prova)`. Il compilatore non si lamenta anche se gli abbiamo passato un array (`prova`) anziché un puntatore a intero (`int *a`) proprio perché l'array `prova` è a tutti gli effetti un puntatore, cioè una variabile contenente come valore un indirizzo di memoria; nello stack di esecuzione, oltre al record di attivazione del `main`, verrà aggiunto il record di attivazione della funzione `init` che conterrà un parametro `int *a` contenente lo stesso indirizzo contenuto nella variabile `prova` del main. A questo punto, `prova` è un array costante e non può essere modificato, mentre `*a` è un puntatore a intero e può essere modificato:
	```c
	void init(int *a) {
		for (int i = 0; i < N; i++, a++) {
			*a = 100 + i;
		}
	}
	```
	Come funziona: nel `for`, l'indice `i` va da `0` (l'inizializzazione è `int i = 0`) a `N - 1` (perché il test è `i < N`), cioè scorre per tutti gli elementi dell'array che gli viene passato come parametro. L'incremento viene effettuato sia per `i`, che per `a`, cioè il valore del puntatore dell'array. Ciò significa che a ogni step del ciclo, incrementando il suo valore, il puntatore passerà alla cella successiva dell'array (es. la prima cella avrà `100` come valore, la seconda `101`, la terza `102` e così via). Attenzione: passa alla cella successiva, non al byte successivo: nel caso degli interi `int`, che occupano 4 byte, ogni incremento del puntatore in realtà lo sposta di 4 byte per passare all'intero successivo.
- Secondo metodo:
	```c
	int *cursore; // ecco il cursore
	int valore;   // variabile che serve nell'ultimo for
	
	for (cursore=prova+9, valore=10; cursore!=prova; cursore--,valore--) 
	   *cursore = valore;
	*cursore = valore;
	```
	Nel ciclo for:
	- Inizializzazione: `cursore=prova+9, valore=10`
	- Test: `cursore!=prova`
	- Aggiornamento: `cursore--,valore--`
	Cioè, cosa fa:
	- `valore` viene inizializzato a `10` e decrementerà
	- `cursore` è un puntatore a intero e `cursore = prova + 9` significa che prende il valore del puntatore `prova` e lo incrementa di `9` celle, così `cursore` punta alla decima cella dell'array `prova` (che in questo caso è anche l'ultima perché l'array è di 10 celle) e questa è l'inizializzazione.
	- Nell'aggiornamento, sia `cursore` che `valore` vengono decrementati: ciò significa che a ogni step, il `cursore` si sposterà a puntare la cella precedente, mentre il `valore` diminuirà di 1.
	- Il test è che `cursore` sia diverso da `prova`, cioè quando il `cursore` arriva a puntare alla prima cella dell'array (che è il valore di `prova`), i due valori saranno uguali e il ciclo `for` terminerà.
	- Ciò significa che, andando a ritroso, dall'ultima cella dell'array fino alla prima, il `cursore` andrà ad assegnare a ogni cella i valori in modo decrescente.
	- Il ciclo for da solo non è sufficiente a riempire tutto l'array, perché arrivato all'ultima cella in cui `cursore == prova` non verrà effettuato l'assegnamento del valore perché uscirà dal ciclo, quindi va fatto subito dopo esternamente al ciclo.