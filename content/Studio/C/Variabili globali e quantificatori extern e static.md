Una variabile globale è una variabile dichiarata al top level, cioè all'esterno di ogni funzione (anche all'esterno dell'`int main`).
Se `typevar var` è una variabile globale dichiarata in un file `nomeFile.c`, allora:
- è accessibile da tutte le funzioni definite (solo dopo nel codice) in `nomeFile.c`
- è accessibile, in altri file che contengono la dichiarazione `extern typevar var;`, in tutte le funzioni definite dopo tale dichiarazione
- in `nomeFile.c`, una dichiarazione `extern typevar var` può precedere la definizione `typevar var` (infatti, una dichiarazione `extern typevar var` significa che la variabile `typevar var` è dichiarata in seguito nello stesso file oppure è dichiarata in un altro file).
Se `static typevar var` è una variabile globale dichiarata in un file `nomeFile.c`, allora:
- è accessibile da tutte le funzioni definite (solo dopo nel codice) in `nomeFile.c`
- NON è accessibile in altri file

La visibilità dei prototype delle funzioni è gestita in modo analogo (nota: per i prototype di funzioni il qualificatore `extern` è implicito, quindi non serve scriverlo.)