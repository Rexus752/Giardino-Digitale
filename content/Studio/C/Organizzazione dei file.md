Di solito, quando si scrive un programma si fa cartella con il nome del progetto e al suo interno mettere file .c, .h e compilati. È possibile usare una sola cartella per contenere tutti i file di un progetto ed è ok per esercizi o progetti di piccolissima dimensione, ma non per progetti medio-grandi. Alternativa: organizzare i file in cartelle.

# Organizzazione tipica

![](Pasted%20image%2020240812203310.png)

Il file `README` è un file di testo (generalmente con estensione Markdown `.md`) che descrive a parole il progetto, i suoi file e tutto ciò che può essere utile. Si chiama `README` perché ci si aspetta che ogni utente lo legga prima di avventurarsi all'interno del codice.

Si compila sempre posizionandosi nella directory principale (`NOME-PROGETTO`) attraverso il comando
```c
gcc <path file(s) .c> -o <path file .out>
```

## Esempio 

![](Pasted%20image%2020240812203618.png)

## Osservazione: perché i pathname?

1. `gcc src/file1.c src/main.c -o bin/a.out`: la compilazione viene fatta nella cartella superiore a quella in cui si trovano i file. Occorre dire al compilatore dove troverà i sorgenti.
2. `#include "../include/file1.h"`: il file sorgente si trova in una cartella sorella di quella in cui si trova il file header. La posizione dell’header è data come sequenza di passi per raggiungerlo: sali nella cartella genitore con i due puntini `..` e poi scendi in `include`.

Se il progetto è in una sola cartella, ci posizioniamo sulla cartella del progetto quindi:
1. `gcc file1.c main.c -o a.out`: i sorgenti sono nella stessa cartella da cui si compila e lo sarà anche l’eseguibile
2. `#include "file1.h"`: gli header sono nella stessa cartella del file che li usa

# File System

## Pathname assoluti

Partono dalla radice, sono assoluti perché sono univoci (cioè non può esistere un duplice percorso assoluto per lo stesso file o la stessa cartella (stesso nodo dell'albero)).

## Pathname relativi

Partono all'interno di una cartella qualsiasi (anche la radice stessa) e navigano all'interno del file system attraverso le altre cartelle:
- Per risalire a una cartella superiore si usa `..`; si possono concatenare, tutti separati da uno slash `/` in Linux e backslash `\` in Windows, per risalire di tot cartelle (es. se si vuole risalire di tre cartelle, si usa `../../..`)
- Per entrare in una cartella inferiore si specifica il nome stesso della cartella

Per navigare, si arriva sempre alla prima cartella in comune tra la sorgente e la destinazione (navigando "verso l'alto" con `..`) e poi si comincia a scendere verso la cartella specifica attraverso i nomi di tutte le sottocartelle.

### Esempio