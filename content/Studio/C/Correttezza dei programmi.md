# Una funzione deve funzionare

Una funzione ha un nome, insieme di parametri ognuno col suo tipo e spesso un valore di ritorno (altrimenti `void`) e dentro il codice. Una funzione deve funzionare, cioè deve svolgere il calcolo descritto nella sua specifica. La specifica è un testo che determina ciò che deve fare la funzione, come comportarsi e qual è il risultato che deve restituire passando determinati valori come parametri. 

## Esempio

"Dato un array, visualizza tutti i suoi valori"
Quindi la funzione, dato per esempio in input un array `[1, 2, 5]`, stamperà i valori `1`, `2` e `5`; se l'array è parzialmente pieno, mostrerà solo i valori presenti nell'array (cioè non valori casuali determinati da "memoria sporca"); se l'array è vuoto (cioè il parametro passato è un puntatore a `NULL` anziché a un array), non viene stampato nulla e quindi la funzione non deve impazzire nel caso di array "non convenzionali", ma deve saper trattare ogni caso possibile in modo corretto (eventualmente, se serve, deve segnalare la presenza di errori).

# Tipi di errori

Possono essere volontari o involontari, meno gravi o più gravi. Divisi in 4 tipologie (ma spesso si sommano tra di loro, non sono completamente separate):
1. Logica sbagliata: ho scritto una funzione che viene eseguita tranquillamente dal compilatore, ma non fa ciò che esattamente voglio (es. anziché calcolare somma, calcola differenza di due numeri)
2. Sintassi sbagliata: logica corretta, ma il programma non è scritto correttamente per il compilatore perché non rispetta la grammatica del linguaggio, quindi non può essere eseguito (es. dimenticarsi un `;` oppure usare un tipo di variabile errato)
3. Flussi di controlli sbagliati: sbagliare uscita da un ciclo, condizione di un if o sbagliare un richiamo ricorsivo
4. Caso dimenticato: non vengono gestiti correttamente tutti i casi possibili (es. alla funzione deve essere passata una stringa, ma la funzione non si comporta correttamente quando le si passa una stringa vuota `""`)

## Importante

Quando vogliamo risolvere un errore, bisogna leggere CIÒ CHE C'È SCRITTO concretamente, non ciò che crediamo di aver scritto (cioè, anziché provare a risolvere l'errore leggendo parola per parola e lettera per lettera ciò che abbiamo scritto nel codice, diamo per scontato che quel codice voglia dire ciò che vogliamo noi, che in realtà può essere tranquillamente sbagliato).

Spesso non si fa neanche volontariamente, cioè per quanto ci sforziamo a voler leggere in modo letterale il codice, non ci rendiamo conto che in realtà abbiamo scritto altro. Unica soluzione: far leggere il codice a qualcun'altro che non l'ha ancora mai letto ed è "fresco" di mente.

## 1

In questo caso tradiamo la specifica: o non abbiamo proprio capito come dovrebbe funzionare il programma, oppure semplicemente abbiamo scritto male il codice e il programma fa tutt'altro. Unica soluzione: provare a ragionare e capire cosa fa la funzione, anche seguendo passo dopo passo con il debug ogni singola istruzione.

## 2

Un po' più facile da risolvere, c'è il compilatore che spesso quando trova l'errore scrive proprio il punto esatto in cui si trova (e alcuni linguaggi tipo Rust ti dicono esattamente anche come puoi risolverlo, offrendoti ogni supporto di cui puoi aver bisogno).

## 3 e 4

Errori di programmazione veri e propri, a metà tra sintassi e logica. Riguardano unicamente la capacità di programmazione e possono avere effetti gravissimi.

# Bravo programmatore

Chi si fa guidare unicamente dal compilatore (GCC) o dal debugged (GDB), cioè anziché usarli come strumenti ausiliari li usa come strumenti principali, non è un programmatore. Il programmatore deve avere il controllo totale su tutto ciò che fa e deve sapere esattamente ciò che fa

Ideale:
1. Scrivere la specifica della funzione o del programma per esteso
2. Trascriverla in codice facendo attenzione alla sintassi
3. Provare a compilare
4. Se nessun errore sintattico, allora eseguire
5. Controllare tutti i casi possibili e vedere se il risultato che esce è quello atteso.

Per fare ciò, il codice va progettato e non semplicemente scritto istintivamente

Passi di base per progettazione di funzioni:
1. Scrivere (in un testo) eventuali assunzioni sui dati ricevuti dalla funzione
2. Identificare i possibili casi da trattare e scrivere un esempio per ciascuno
3. Se la funzione contiene cicli, scrivere quale condizione è vera ad ogni iterazione (invariante di ciclo)
4. Scrivere la condizione che sarà vera (sui dati e sull'eventuale output prodotto) al termine dell'esecuzione

## Esempio

1. Assunzioni iniziali: assumo che la funzione riceva due valori, dividendo e divisore, e che il divisore sia diverso da zero.
2. Descrizione del codice che esplica la funzione: effettua il calcolo (semplice, un'istruzione sola)
3. Condizione sul risultato: se l'assunzione iniziale è vera il risultato sarà il valore prodotto dal primo parametro fratto il secondo parametro, altrimenti restituisco il dividendo e un messaggio di errore.

# Scrittura del codice

La scrittura del codice viene effettuata per raffinamenti successivi, cioè, coerentemente con le assunzioni fatte, si scrive sotto forma di commenti quel che farà la funzione. Si trasformano quindi via via i commenti in codice e alla fine si prova il codice sull'insieme di casi precedentemente identificati.

# Codice lineare

Quando il codice è lineare (semplice sequenza di calcoli senza strutture di controllo), gli unici errori sono di tipo sintattico e di tipo logico (1 e 2). Gli errori di tipo sintattico si scoprono tramite il compilatore, mentre quelli di tipo logico tramite la test suite, cioè un insieme di test pre-impostati in cui con determinati input (che comprendono tutti i casi possibili) ci si aspetta un determinato output e, se non dovesse corrispondere, si sa che si deve agire su quel determinato caso.

## Test suite (banco di prova)

Si identificano tutti i casi possibili a cui la funzione può essere applicata e si identifica un esempio per ciascuno. Gli esempi saranno utilizzati in altrettante invocazioni della funzione, per esempio in un main.
Essi devono essere corredati di codice di output (a terminale o su file) che mostri all'utente il risultato o l'eventuale errore.

# Codice strutturato

Quando invece il codice è strutturato o fa dei richiami ricorsivi:
1. Bisogna garantire la terminazione della funzione (non vi sono esecuzioni infinite)
2. Bisogna garantire che ogni passo (iterazione) dell'esecuzione rispetti una proprietà di correttezza (_correttezza parziale_) (viene fatto quanto previsto dalla specifica) 

Quindi terminazione + correttezza parziale = correttezza del programma

## Correttezza parziale

Esempio: abbiamo una funzione con determinati parametri in ingressi e determinati variabili restituite in uscita. La proprietà che vale sui dati che saranno elaborati dalla funzione è detta _predicato di input_ `P_IN(x1, ..., xn)`, mentre quella che vale sui dati elaborati e sull'output prodotto è detta _predicato di output_ `P_OUT(x1, ..., xn, y)`.

Indichiamo con $\tt func(t_1 \; p_1, \ldots, t_n \; p_n)$ una funzione. Tale funzione ha $n$ parametri $p_1, \ldots, p_n$ rispettivamente di tipo $t_1, \ldots, t_n$. Esempio: `quadrato(int x)` ha un solo parametro di tipo intero.
Diciamo che $\tt func(t_1 \; p_1, \ldots, t_n \; p_n)$ è parzialmente corretta quando, per ogni ennupla di valori $(x1, ..., xn)$ rispettivamente di tipo $t_1, \ldots, t_n$ (es. nel caso di `quadrato(int x)` le ennuple sono tutti i singoli valori interi possibili es. 0, 1, 2, -4, ecc.), se vale che:
1. `P_IN(x1, ..., xn)` è vera
2. l'esecuzione di $\tt func(t_1 \; p_1, \ldots, t_n \; p_n)$ termina restituendo $y$
allora `P_OUT(x1, ..., xn, y)` è vera.

`P_IN(x1, ..., xn)` è una proprietà dell'input, mentre `P_OUT(x1, ..., xn, y)` è una proprietà che lega l'input e l'output (es. per il quadrato(int x), `P_IN(x)` è "x è un numero intero", `P_OUT(x, y)` è "y =\= x\*x").

## Terminazione

Una funzione $\tt func(t_1 \; p_1, \ldots, t_n \; p_n)$ è **terminante** se per ogni ennupla di valori $(x1, ..., xn)$ tali per cui `P_IN(x1, ..., xn)` è vera, l'esecuzione di $\tt func(t_1 \; p_1, \ldots, t_n \; p_n)$ si conclude.
Esempio: per $\tt quadrato(int \; x)$, quando $\tt P\_IN(x)$ è vera (input valido), allora $\tt quadrato$ ha fine.

# Esempio

Calcolare il valore minimo di un array.

Scriviamo un primo canovaccio:
1. Assumo di ricevere un array di dimensione N (N>0)
2. Il valore restituito sarà uno dei valori contenuti nell'array, precisamente il più piccolo
3. Definisco una variabile di comodo dello stesso tipo degli elementi dell'array che conterrà il suddetto valore (anche il minimo "parziale" trovato fino a un certo punto dell'array)
4. La inizializzo opportunamente
5. Uso un ciclo che scorre l'array
6. A ogni iterazione la variabile conterrà il valore più piccolo fra quelli visti al momento
7. Per decidere se aggiornarla, la confronto con l'elemento corrente
8. Alla fine restituisco il valore contenuto nella variabile di comodo

Quindi
```c
/*
P_IN: assumo di riceve un array di dimensione N (N>0)
P_OUT: il valore restituito sarà uno dei valori contenuti nell'array, precisamente il più piccolo
*/
int minimo(int a[], int N) {
	int temp;  // Definisco una variabile di comodo
	temp = a[0];  // La inizializzo opportunamente
	for (int i = 0; i < N; i++) {  // Uso un ciclo che scorre l'array
		// A ogni iterazione la variabile conterrà il valore più piccolo fra quelli visti al momento
		if (a[i] < temp)  // La confronto con l'elemento corrente
			temp = a[i];  // Per decidere se aggiornarla
	}
	return temp;  // Alla fine restituisco il valore contenuto nella variabile di comodo
}
```

`temp = a[0];` perché `temp` deve contenere un valore iniziale per effettuare il primo confronto e non può essere un valore casuale o valori tipo `0` (perché ci possono essere valori tutti positivi maggiori di `0` nell'array e a quel punto il minimo sarebbe proprio lo `0` che neanche è presente nell'array).

Ottimizzazione: ciclo for con `int i = 1` perché il valore iniziale di temp, cioè a[0], sarà confrontato con a[0] e così facciamo un confronto inutile.

## Terminazione

Ora va dimostrata la terminazione:
- Una sequenza termina sempre, se i suoi passi terminano
- Un ciclo termina se iterazione dopo iterazione ci si avvicina alla condizione di uscita
- Qualcosa di simile vale per le funzioni ricorsive

Vediamo che:
- `minimo` contiene un ciclo for
- La condizione di uscita è che l'indice `i` diventi uguale o maggiore di `N`
- A ogni iterazione l'indice `i` viene incrementato di `1` con `i++` nel ciclo
- Quindi prima o poi renderà vera la condizione di uscita, portando `minimo` a terminare

La terminazione va dimostrata guardando il codice effettivo, non le intenzioni del programmatore. Se per errore `minimo` contenesse questo ciclo for: `for (int i = 0; i < N; ) {}`, non potremmo dire che `i` viene incrementata a ogni iterazione. 

# Altro esempio

Cerca se un elemento è presente in un array di N numeri interi: se è presente, restituisce l'indice di una cella che lo contiene, altrimenti restituisce `-1` (-1 perché è un numero intero, quindi coerente con il tipo della variabile di ritorno, e non può mai essere un valore di un indice, perché gli indici vanno da 0 in poi). Restituisce l'indice di UNA CELLA e non DELLA CELLA perché ci possono essere più celle che contengono lo stesso elemento ricercato (es. si cerca un 3 in [4, -2, 3, 5, 3], ci sono due volte 3).

Aspettative:
- P_IN: array ha un numero di elementi N>0
- P_OUT: se risultato>=0 allora array[risultato] == elemento ricercato, altrimenti elemento ricercato NOT IN array

Cosa deve fare:
- Percorro iterativamente l'array finché o trovo l'elemento ricercato o controllo l'intero array
- A ogni iterazione, se il valore corrente == all'elemento ricercato, allora memorizzo l'indice in una variabile ed esco dal ciclo
- Alla fine del ciclo faccio controllo per vedere se nella variabile di ritorno c'è un valore >=0, se sì significa che abbiamo trovato un elemento, altrimenti continuo
- Restituisco l'output

```c
int cerca(int array[N], int el) {
	// Percorro iterativamente l'array finché o trovo l'elemento ricercato o controllo l'intero array
	int result = -1;
	for (int i = 0; i < N || result != -1; i++) {
		if (array[i] == el)
			result = i;
	}
	return result
}
```

## Terminazione

Termina? Sì, per lo stesso motivo dell'esempio precedente

# Notazione

A volte nelle proprietà di input e di output occorre riferirsi sia ai valori iniziali di qualche variabile, sia ai valori che si hanno al termine dell'esecuzione.
Esempio:
```
void scambia(int[] arr, int i, int j) {
	int temp = arr[i];
	arr[i] = arr[j];
	arr[j] = temp;
}
```

Usiamo quindi l'apice `'` per indicare un valore iniziale. Esempio:
- P_IN(arr, i, j): `i` e `j` sono indici validi di `arr`
- P_OUT(arr, i, j): `a[i] == a'[j]` e `a[j] == a'[i]`
L'apice `'` significa "prima"

Stessa cosa per puntatori:
```
void scambia_p(int *px, int *py) {
	int temp = *px;
	*px = *py;
	*py = temp;
}
```
- `P_IN(*px, *py)`: `*px` e `*py` sono puntatori validi
- `P_OUT(*px, *py)`: `*px == (*py)'` e `*py == (*px)'`