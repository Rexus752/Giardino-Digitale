# Cos'è

- GDB è un potente strumento di debugging attualmente mantenuto dalla Free Software Foundation
- Originariamente sviluppato da Richard Stallman nel 1986 %%inserire foto di stallman%%
- Supporta vari linguaggi di programmazione, tra cui il C
- E’ stato concepito per essere usato a riga di comando (shell testuale), anche se numerosi strumenti di sviluppo dotati di interfaccia grafica si possono collegare a esso, offrendo:
	+ Più facilità d’uso
	- Ma con meno funzionalità
- Il modo migliore per conoscerlo è tramite riga di comando.
Inoltre in certi casi (shell SSH) si ha a disposizione solo questa modalità d’uso

# Il problema dei bug

- I bug si annidano inevitabilmente anche nel codice sviluppato da ottimi programmatori
- Buona parte del tempo di un programmatore è speso, ahimè, nel trovare e risolvere i bug
- I bug possono produrre:
	- Crash
	- Cicli infiniti
	- Risultati sbagliati
	- Altri casi di comportamento anomalo
- Si differenziano anche tra:
	- Deterministici
	- Dipendenti dall'input
	- Random (questi in particolare hanno impatto sulla loro riproducibilità)

# Cosa fa GDB

- Dalla prima pagina della guida di GDB:
```
GDB allows you to see what is going on “inside” another program while it executes—or what another program was doing at the moment it crashed.
```
- E in particolare permette di:
	- Start your program, specifying anything that might affect its behavior.
	- Make your program stop on specified conditions.
	- Examine what has happened, when your program has stopped.
	- Change things in your program, so you can experiment with correcting the effects of one bug and go on to learn about another

# Pregi e difetti

+:
 - Permette di scovare i bug più ostici, che resistono a strategie di debug più semplici (es: le printf)
+ Può fare virtualmente "qualunque cosa", a patto di capire come fare (900 pagine di user manual…)
+ Può debuggare anche programmi già in esecuzione, e attaccarsi a processi remoti
+ Permette di fare un’analisi "post-mortem" di un programma andato in chash
-:
- L’interfaccia command-line può essere ostica
- Gli infiniti comandi e opzioni possono mettere in soggezione, ma non bisogna scoraggiarsi! Un uso "base" richiede di imparare poche cose

# Cosa ci fa vedere

- Per una dato processo, GDB permette di osservare/manipolare:
	- l’effetto di ciascuna linea di codice del file sorgente
	- variabili di tutti i tipi
	- lo stack delle varie chiamate a funzione in corso
	- posizioni arbitrarie nella memoria
	- i registri della CPU
	- i diversi (eventuali) thread del processo
- In pratica, ficca il naso (e le mani) in ogni parte di un processo

# Compilazione con opzione `-g`

Per debuggare un programma efficacemente, occorre includere nel file oggetto informazioni di debugging generate automaticamente in fase di compilazione con l’opzione `-g`.
Inoltre, sebbene gdb possa debuggare anche codice ottimizzato (`-O<n>`), è meglio non produrre codice ottimizzato in fase di debug

# Il core dump
 
- Se un programma va in crash, tutte le informazioni del processo vengono salvate in un file detto _core dump_ 
- GDB permette di ispezionare questo file come se fosse un processo in esecuzione 
  Molto utile per analisi "post mortem"

# Flusso tipico di una "sessione di debug"

- Inizio sessione di debug:
	- gdb eseguibile
- Per passare parametri sulla linea di comando:
	- gdb –args -eseguibile arg1 arg2 …
- Entro la sessione di debug:
	- (gdb) comando1
	- (output comando1)
	- (gdb) comando2
	- (output comando2)
	- …
	- (gdb) help comando
	- …
- Fine della sessione:
	- (gdb) quit

# Comandi più comuni

- `gcc -g -std=c99 -w <nome file .c> -lm`: compilazione del programma con caratteri per il debug 
- `layout next`: visualizzazione dell'assembler del codice
- `layout src`: visualizzazione del codice sorgente
- `run`: per eseguirlo
- `p <nome variabile>`: stampare il valore di una variabile
- `info locals`: variabili locali
- `info args`: argomenti
- `display <nome variabile>`: per visualizzare il valore di una variabile ogni volta che si va avanti nel programma
- `undisplay <nome variabile>`: per annullare il display

- `gcc -S main.c` per fermarci al pre-processing
- `gcc main.c` genera il .o binario assemblato

## Comandi per il controllo dell'esecuzione

- b (break): imposta un breakpoint ad una linea specifica del codice sorgente oppure ad una funzione, magari sotto condizione
- r (run): inizia esecuzione
- c (continue): continua esecuzione dopo un breakpoint
- n (next): esegue la prossima istruzione (senza entrare nelle funzioni chiamate)
- s (step): esegue la prossima istruzione (entrando nelle funzioni chiamate)
- f (finish): continua esecuzione fino al termine della funzione corrente
- `<CTRL-C>`: interrompe esecuzione del programma (come se si fosse raggiunto un breakpoint) (utile con loop infiniti)

## Altri comandi utili

- i b (info breakpoints): mostra i breakpoints attuali
- d (delete): rimuove il breakpoint n-esimo
	- `(gdb) d 2` rimuove il breakpoint 2
- watch myvar: ferma l’esecuzione del programma quando il valore di una variabile (o di una espressione) nel contesto corrente cambia
- watch myaddr: stop quando una locazione di memoria viene modificata
- i wat (info watchpoints): mostra i watchpoint attuali
- display myvar: stampa il valore di una variabile (espressione) a ogni arresto dell’esecuzione
- l (list): mostra il codice sorgente, con varie opzioni
	- `(gdb) l 5` mostra 10 line attorno alla linea 5

## Comandi per operazioni su variabili

- p (print): stampa il contenuto di una variabile o di un indirizzo in memoria
```bash
(gdb) p myvar
(gdb) p &myvar
(gdb) p argv[1]
(gdb) p A[10]@5  # Stampa 5 elementi a partire dalla pos 10 dell’array A
(gdb) *(long *)0x614c20  # Stampa un long a partire dall’indirizzo 0x614c20
```
- pt (ptype): stampa il tipo di una variabile
- Possiamo anche cambiare il valore di una variabile/locazione di memoria!:
```bash
(gdb) set var res=4
(gdb) set {int}0x83040 = 4  # Memorizza un intero a partire dall’indirizzo 0x83040
```

## Operazioni sullo stack

- bt (backtrace): visualizza lo stack di tutte le chiamate con i relativi argomenti
- f framenumber: seleziona un frame dello stack
- up: si sposta nel chiamante del frame corrente
- down: si sposta nel chiamato del frame corrente
- info locals: mostra le variabili locali del frame corrente
- info args: mostra gli argomenti del frame corrente

https://informatica.i-learn.unito.it/pluginfile.php/399204/mod_resource/content/2/TDD.pdf