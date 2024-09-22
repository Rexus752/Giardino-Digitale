```c
void *x;
```
Puntatore generico:
- Ha una dimensione precisa (quella che basta per salvare un indirizzo a qualcosa);
- Come puntatore fa riferimento ad altre porzioni di memoria;
- Il tipo dei dati riferito non è specificato.

# Albero generico

```c
typedef struct gnode *GTree;

struct gnode {
	void* data;
	GTree left;
	GTree right;
	char type[MAX];
}

lista crea_nodo()
```