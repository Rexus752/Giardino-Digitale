Tutti elementi dello stesso tipo, gestita con politica LIFO (Last In, First Out)

Operazioni:
- Push: aggiunge un elemento in cima alla pila. Non si può scegliere la posizione in cui aggiungerlo, viene sempre fatto in cima
- Pop: toglie un elemento dalla cima della pila e lo restituisce. Non si può scegliere l'elemento da togliere, sarà sempre l'elemento in cima a essere tolto
- Empty: test per controllare se la pila è vuota (serve nel pop per vedere se c'è un elemento da togliere)
- Full: test per controllare se la pila è piena (serve nel push per vedere se c'è spazio per aggiungere un nuovo elemento)
- Peek: test per guardare qual è l'elemento in cima alla pila (lo restituisce come nel pop ma senza toglierlo)

Non è un caso che lo stack di esecuzione si chiami così, perché i record di attivazione vengono sempre aggiunti in cima e rimossi dalla cima (non vengono rimossi record di attivazione nel mezzo perché quelli nel mezzo hanno bisogno dei risultati degli stack di attivazione in cima per essere rimossi, ergo c'è bisogno che prima quelli in cima vengano "risolti")

Prototipi:
```c
void push(tipodato elem, tipostack *s);
tipodato pop(tipostack *s);
int empty(tipostack s);
int full(tipostack s);
tipodato peek(tipostack s);
```

# Implementazioni tramite liste concatenate

```c
typedef struct nodo {
	int dato;
	struct nodo *next;
} lista, stack;
```

```c
int empty(stack s) {
	// Dato che in C NULL == falso, se la pila è vuota vale NULL, quindi !NULL = true (cioè SÌ, è piena)
	return !s;
}
```

```c
void push(int value, stack *s) {
	if (s) inserimento_in_testa(value, s);
}

int pop(stack *s) {
	if (s && !empty(*s)) {
		lista top = rimozione_in_testa(s);
		return top->dato;
	}
	else return NULL;
}
```

# Implementazione tramite array

Array, rispetto a lista concatenata, ha una dimensione finita preimpostata. La funzione `full` controlla se l'array è pieno
Si usa comunque uno `struct` perché, oltre all'array, per comodità c'è bisogno di salvare l'indice della cima `top`.
Bisogna anche scegliere se `top` farlo riferire all'indice dell'ultima cella piena o della prima cella vuota e, a seconda dei casi, inizialmente vale:
- `-1` se si riferisce all'ultima cella piena (non ce ne sono di piene, quindi si usa l'indice `-1` per farlo capire. Possiamo usare il `-1` perché non ci possono essere indici negativi)
- `0` se si riferisce alla prima cella vuota

Scegliamo la seconda implementazione (`top` si riferisce alla prima cella vuota).

```c
typedef struct {
	int dato[MAX];
	int top;
} stack;

void init(stack *s) {
	if (s) s->top = 0;
	else printf("Stack non definito");
}

int empty(stack s) {
	return (!(s.top));
}

int full(stack s) {
	return (s.top == MAX);
}

void push(int el, stack *s) {
	if (s) { 
		if (!full(*s)) { // Se non è pieno
			s->dato[s->top] = el; // Si fa semplicemente assegnamento perché è intero
			s->top++;
		} else printf("Stack pieno");
	} else printf("Stack non esiste");
}

int pop(stack *s) {
	int result = NOVALUE;
	if (s) {
		if (!empty(*s)) {
			result = s->dato[s->top - 1];
			s->top--;
		} else printf("Stack vuoto");
	} else printf("Stack non esiste");
	return result;
}

int peek(stack s) {
	int result = NOVALUE;
	if (s) {
		if (!empty(s)) {
			result = s.dato[s.top - 1];
		} else printf("Stack vuoto");
	} else printf("Stack non esiste");
	return result;
}

int main() {
	stack ms;
	...
	r = pop(&ms);
	// r può contenere un dato o NOVALUE
	if (r != NOVALUE) {
		// r si può usare come dato
		...
		} else {
		// r non si può usare perché è un NOVALUE
		...
	}
}
```

Con il `pop` il dato rimane nella cella che viene "liberata", ma teoricamente è un dato "inutile" che può essere sovrascritto con il prossimo `push`.

Stack si usa:
- Esecuzione dei processi nel Sistema Operativo
- Inversione di una stringa: si fa un push lettera per lettera in ordine e col pop si prende dall'ultima lettera alla prima al contrario
- Compilatori
- Browser (ritorno alla pagina precedente)
- Sistemi Operativi: nella sostituzione delle pagine nella RAM