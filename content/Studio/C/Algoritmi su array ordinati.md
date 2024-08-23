Array ordinato = presi qualsiasi due suoi elementi, vale tra di loro una relazione di ordine, es. relazioni numeriche ($<, >, \le, \ge$) sui numeri (interi e decimali), ordine alfabetico sulle stringhe, insiemi più grandi che includono insiemi più piccoli ecc.

Si può sfruttare la relazione d'ordine per trovare l'elemento di interesse più velocemente.

# Ricerca binaria

Ricerca binaria: array ordinato, vogliamo cercare un elemento.
Come funziona: ogni volta considera un pezzo dell'array, nel primo passo l'intero array (dall'indice `0` all'indice `N-1`). Si calcola l'indice di un elemento medio, facendo la media aritmetica tra i due indici degli estremi e lo usiamo per orientarci: se l'elemento ricercato è, nell'ordine, minore dell'elemento centrale, allora esso sarà compreso nella prima metà dell'array e nel ciclo successivo sarà considerata solo la prima metà; viceversa, se è maggiore dell'elemento centrale, allora sarà compreso nella seconda metà dell'array e nel ciclo successivo sarà presa in considerazione solo la seconda metà dell'array.

## Definizione formale

- Dichiara due variabili `sx` e `dx` per delimitare la porzione di array `array[sx, ..., dx]` in cui cercare
- Finché la porzione non è vuota:
	- Dichiara una variabile `middle` per memorizzare l'indice a metà di `array[sx, ..., dx]` (cioè `middle = (sx + dx) / 2`)
	- Se `el < array[middle]`:
		- Restringi la porzione a `array[sx, ..., middle - 1]`
	- Altrimenti, se `el > array[middle]`:
		- Restringi la porzione a `array[middle + 1, ..., dx]`
	- Altrimenti
		- Restituisci `middle`
- Restituisci `-1`