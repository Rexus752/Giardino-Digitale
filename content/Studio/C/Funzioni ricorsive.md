Un algoritmo ricorsivo è un procedimento che utilizza se stesso per fare un calcolo

Esempio: definizione del fattoriale
Dato n, numero naturale, il suo fattoriale ! è calcolato come segue:
```
n! = 1            se n == 0 || n == 1
n! = n * (n-1)!   se n > 0
```

5! è calcolato come 5 per il fattoriale del numero che precede 5 stesso
```
5!	= 5 * 4!
	= 5 * 4 * 3!
	= 5 * 4 * 3 * 2!
	= 5 * 4 * 3 * 2 * 1!
```

# Esempio

```c
int fattoriale (int n) {
	if (n < 0) fprintf(stderr, "errore");
	else if (n <= 1) return 1;
	else return n * fattoriale(n - 1);
}
```

Prima istruzione `if (n < 0) fprintf(stderr, "errore");` solo per verificare la correttezza (consistenza) dei dati (devono essere nel dominio voluto: quello degli interi positivi)
Caso base: `if (n <= 1) return 1;` che è anche un punto di stop, perché altrimenti se non ci fosse questo la funzione verrebbe chiamata ricorsivamente all'infinito.
Passo ricorsivo: `return n * fattoriale(n - 1);`

%% Fare vedere lo stack di esecuzione %%

# Ricorsione in testa e in coda

Solitamente, si fa prima il test del caso base e poi quello del passo ricorsivo (_ricorsione in coda_), perché è meno dispendioso verificare subito se il caso corrente rientra nel caso base e, quindi, in quel caso si può terminare subito la funzione; altrimenti, verrebbe sempre eseguito almeno una volta il passo ricorsivo. Si poteva fare anche come (_ricorsione in testa_):
```c
int fattoriale (int n) {
	if (n < 0) fprintf(stderr, "errore");
	else if (n > 1) return n * fattoriale(n - 1);
	else return 1;
}
```
che funziona ugualmente, ma non è ottimizzato.

%% Fare vedere lo stack di esecuzione %%

# Progresso e condizione di correttezza

Ciò che caratterizza il passo ricorsivo è che la chiamata ricorsiva determina un progresso, cioè ogni chiamata ricorsiva successiva elabora altri dati, non gli stessi di quella corrente, altrimenti elaborerà gli stessi dati all'infinito e non riuscirà mai a progredire verso il caso base che poi farà terminare l'algoritmo.

Ecco perché c'è la _condizione di correttezza_: una funzione ricorsiva deve sempre terminare e per farlo occorre essere sicuri che a un certo punto sarà raggiunto il caso base. Ecco perché il seguente programma:
```c
int fattoriale (int n) {
	if (n < 0) fprintf(stderr, "errore");
	else if (n <= 1) return 1;
	else return n * fattoriale(n);  // Anziché n * fattoriale(n - 1);
}
```
per il compilatore sarà sintatticamente corretto, ma logicamente errato perché non ha un progresso, dal momento che riceve in input come parametro un dato intero `n` e nella chiamata ricorsiva passa sempre lo stesso `n` (cioè elabora sempre lo stesso dato).

Esempio: se provo a calcolare `5!` così, il programma mi dirà che:
```
5!	= 5 * 5!
	= 5 * 5 * 5!
	= 5 * 5 * 5 * 5!
	= 5 * 5 * 5 * 5 * 5!
	= ...
```
che, oltre a essere matematicamente sbagliato, è logicamente sbagliato perché non ci sarà mai un termine all'algoritmo.

%% Fare vedere lo stack di esecuzione %%

# Lineare

È detta _lineare_ quando produce una singola sequenza di chiamate (come nel caso del [[fattoriale]]). La ricorsione lineare in coda corrisponde a un ciclo.

# Efficienza

La ricorsione permette di scrivere codice compatto e facile da interpretare.
La ricorsione comporta un _overhead_, cioè un tempo extra di esecuzione e occupazione di memoria dovuto alla creazione e rimozione del relativo record di attivazione. Se si vuole efficienza, quindi, meglio scegliere l'iterazione che fa uso di un unico record di attivazione.