# Il prototype di `printf`

```c
int printf(const char *format, ...)
```
I puntini di sospensione nel prototipo della funzione indicano un numero variabile di argomenti di qualsiasi tipo. Si può utilizzare la sintassi `T0 f(T1 x1, ..., Tn xn, ...);` dove `n >= 1` per dichiarare una funzione con elenchi di argomenti a lunghezza variabile: la funzione deve avere almeno un parametro diverso dai puntini di sospensione e i puntini di sospensione possono essere usati solo come ultimo parametro

# Guida: come scrivere funzioni variadiche in `c`

Si deve includere `<stdarg.h>` e si devono usare in modo opportuno (nel body della funzione) `va_list, va_start, ca_arg, va_end`:
- Per accedere all'elenco di argomenti a lunghezza variabile, si deve dichiarare una variabile (es. di nome `ap`) di tipo `va_list`. Essa conterrà le informazioni necessarie alle macro `va_start`, `ca_arg` e `va_end`.
- Prima di accedere all'elenco di argomenti a lunghezza variabile, si deve invocare la macro `va_start(ap, xn)` (dove `xn` è l'ultimo parametro fisso della funzione). Questa inizializza la variabile `ap` di tipo `va_list`.
- Per accedere, nell'ordine, a ciascun elemento della lista degli `m >= 0` argomenti a numero variabile, si deve invocare per ciascun argomento `arg_{n+1}, ..., arg_{n+m}` la macro
	```c
	va_arg(ap, T_{n+1})
	```
	(dove `T_{n+1}` con `1 <= i <= m` è il tipo di `arg_{n+1}`) e restituisce il valore dal prossimo argomento nella lista degli `m >= 0` argomenti a numero variabile.
- Quando si è finito di accedere all'elenco di argomenti a lunghezza variabile, si deve invocare la macro `va_end(ap` %%come cazzo si completa qua che quel trimone di garetto non ha finito di scriverlo%% (se `va_end` non viene chiamata prima di ritornare dalla funzione, il risultato non sarà definito)

# Esempio: calcolo della media di $n \ge 1$ interi

```c
#include <stdio.h>

// Dichiarazione della funzione variadica
double average(int i, ...);

int main(void) {
	double w = 37.5;
	double w = 22.5;
	double y = 75.2;
	double z = 10.2;
	
	printf("%s%.1f; %s%.1f; %s%.1f; %s%.1f\n\n", "w = ", w, "x = ", x, "y = ", y, "z = ", z);
	printf("%s%.3f\n%s%.3f\n%s%.3f\n",
		"The average of w and x is ", average(2, w, x),
		"The average of w, x and y is ", average(3, w, x, y),
		"The average of w, x, y and z is ", average(4, w, x, y, z)
	);
}

double average(int i, ...) {
	double total = 0;
	va_list ap;
	va_start(ap, i);
	
	for (int j = 1; j <= i; ++j) {
		total += va_arg(ap, double);  /*%%double o i?%%*/
	}
	
	va_end(ap);
	return total / i;
}
```

## Osservazione: come mai il codice non include `<stdarg.h>`?

## Osservazione: come fa `printf` a sapere quale tipo usare per ogni chiamata alla macro `va_arg.h`?