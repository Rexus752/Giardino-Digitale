```c
int somma(int x, int y) {
	return x + y;
}
```

Il prototipo `int somma(int, int);` ci dice che la funzione `somma` ha due parametri di tipo `int` e restituisce un dato di tipo `int`.

Dichiarazione di puntatore a funzione:
```c
int (*puntfunc)(int, int);
```
`*puntfunc` è un puntatore a funzione. Attenti a non confondere con `int *puntfunc(int, int)` che è una funzione normale che restituisce puntatori a interi.

`*puntfunc` è un puntatore a funzioni che hanno 2 param interi e restituiscono interi. Serve per "generalizzare" tutte le funzioni di quel tipo o per "astrarre", per rendere agnostica la funzione a cui si riferisce.

# Esempio

```c
int somma(int, int);
int (*puntfunc)(int, int);

int somma(int x, int y) {
	return x + y;
}

int main() {
	puntfunc = somma;
	int risultato = (*puntfunc)(3, 3); // risultato = 6
}
```

# Vettore delle interruzioni

```c
// Array di 4 elementi che sono puntatori a funzioni
int (*handler[4])(int);
```
In memoria avremo un array di 4 elementi di nome `handler` in cui ogni elemento è un riferimento a funzione

```c
#include <stdio.h>
#include <stdlib.h>

// Variabili globali
int (*handler[4])(int);

// Prototipi di funzioni e relative implementazioni
int raddoppia(int);
int per10(int);
int incrementa(int);
int stampa(int);

int raddoppia(int x) {
	printf("Eseguo funzione raddoppia\n");
	return x * 2;
}

int per10(int x) {
	printf("Eseguo funzione per10\n");
	return x * 10;
}

int incrementa(int x) {
	printf("Eseguo funzione incrementa\n");
	return x + 1;
}

int stampa(int x) {
	printf("Eseguo funzione stampa: %d\n", x);
	return x;
}

int main() {
	// Inizializzazione dell'handler
	// Scelta di come inizializzare l'handler
	if (scelta == 1) {
		handler[0] = stampa;
		handler[1] = raddoppia;
		handler[2] = per10;
		handler[3] = incrementa;
	} else if (scelta == 2) {
		handler[0] = per10;
		handler[1] = raddoppia;
		handler[2] = per10;
		handler[3] = raddoppia;
	} else printf("Errore scelta");
	// Ciclo
	int finito = 0;
	while (!finito) {
		// Simuliamo l'occorrenza di un evento (lo inserisce l'utente)
		printf("Inserisci numero da 0 a 3: ");
		int scelta;
		scanf("%d", &scelta);
		// Se è tra quelli trattati, invochiamo l'handler giusto
		if (scelta >= 0 && scelta <= 3) {
			int risultato = (*handler[scelta])(scelta);
		}
		// Altrimenti, termina il ciclo
		else finito = 1;
	}
}
```