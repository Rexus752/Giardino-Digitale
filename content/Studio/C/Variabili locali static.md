Una variabile locale (cioè dichiarata all'interno di una funzione) static è una variabile che mantiene il suo valore dopo che la funzione è terminata.
Ad esempio:
```C
int nextNumber() {
	static int counter = 1;
	return counter++;
}
```
restituisce:
- `1` la prima volta che è chiamata
- `2` la seconda volta che è chiamata
- ...
- `n` (a meno di overflow) l’n-esima volta che è chiamata