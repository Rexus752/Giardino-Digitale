https://informatica.i-learn.unito.it/pluginfile.php/399204/mod_resource/content/2/TDD.pdf

Una libreria NON è un programma perché contiene codice, funzioni, macro ecc. ma NON contiene un main (quindi non può essere eseguito autonomamente).

# Primo esempio

1. File `square.h`: scrivere cosa deve fare la funzione che voglio scrivere
```c
/** @brief Restituisce il quadrato del suo argomento
*/
int square(int n);
```
2. File `main.c`: scrivere il codice dell'applicazione che la usa
```c
#include <stdio.h>
#include "square.h"

/** @brief Legge un intero e ne stampa il quadrato
*/
int main() {
	int num;
	int res;
	scanf("%d", &num);
	res = square(num);
	printf("%d\n", res);
}
```
%%aggiustare gli argomenti del main%%
3. File `square.h`: scrivere il codice della funzione
```c
/** @brief Restituisce il quadrato del suo argomento
*/
int square(int n) {
	return n * n;
};
```

# Esempio espanso con `stoi.h`, `sqr.c` e `test_stoi.c`

%%File .c quando va eseguito, .h quando è una libreria o semplice raccolta di funzioni%%
Numero non più letto da input, ma da linea di comando durante esecuzione

File `stoi.h`:
```c
/**
* @brief Converte una stringa in intero
*
* Restituisce il numero 'int' rappresentato dalla stringa in argomento:
* 1. Saltando gli eventuali spazi bianchi iniziali;
* 2. Riconoscendo l'eventuale segno;
* 3. Fermandosi al raggiungimento del primo carattere non numerico.
*
* @param s Una stringa da convertire
* @return Il numero intero rappresentato nella stringa (il valore di ritorno non è definito nel caso di un overflow)
*/
int stoi(char *s) {
	int num = 0;
	int i = 0;
	// Parsifica (e memorizza in num il valore di) un naturale decimale
	// fino al raggiungimento della fine della stringa s,
	// o fino a quando incontra un carattere non numerico
	// INVARIANTE DI CICLO: num contiene il naturale le cui cifre sono (nell'ordine) quelle in s[0...i-1]
	while (s[i] != '\0' && (s[i] >= '0' && s[i] <= '9')) {  // Finché c'è un carattere disponibile ed è compreso tra 0 e 9
		num = (num * 10) + (s[i] - '0');
		i++;
	}
	return num;
};
```

File `sqr.c`:
```c
#include <stdio.h>
#include <stdlib.h>
#include "stoi.h"
#include "square.h"
/**
* @brief Accetta un intero sulla riga di comando e ne stampa il quadrato
*
* @param argc Il numero di argomenti inseriti sulla riga di comando (incluso il nome del programma)
* @param argv Un array di stringhe che memorizza gli argomenti inseriti
*/
int main(int argc, char *argv[]) {
	if(argc != 2) {
		puts("Usage: sqr number");
		exit(EXIT_FAILURE);
	}
	int num = stoi(argv[1]);
	int res = square(num);
	printf("%d\n", res);
}
```
%%aggiustare gli argomenti del main%%

File `test_stoi.c`:
```c
#include <stdio.h>
#include "stoi.h"
int main(void) {
	puts("BEGIN TEST stoi");
	{  // Ogni blocco codifica uno UNIT TEST isolato dagli altri
		char *s = "";
		int n = stoi(s);
		if !(0 == n) {
			printf("--TEST 1 FAILED--\n");
			printf("INPUT: %s\n", s);
			printf("EXPECTED: %d\n", 0);
			printf("RESULT: %d\n", n);
		} else {
			printf("--TEST 1 PASSED--\n");
		}
		printf("\n");
	}
}
```
%%mettere altri unit test, magari in matrice%%

# Esempio espanso con segno

%%Fare test case con solo "+" o "-" (restituisce errore)%%

# Esempio con spazi bianchi iniziali

%%Fare solo alcuni test case con spazi bianchi iniziali%% 