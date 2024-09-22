La coda (_queue_) (o fila) è gestita con politica FIFO (First In, First Out): l'aggiunta viene fatta in coda (_tail_), la rimozione viene fatta in testa (_head_).

Due operazioni:
- `enqueue`: aggiunge un elemento in coda
- `dequeue`: toglie l'elemento in testa

```c
void enqueue(tipodato el, queue *q);
tipodato dequeue(queue *q);
int empty(queue q);
int full(queue q);
tipodato peek(queue q);
void init(queue *q);
```

# Implementazione con array

- `tail` indice dell'ultimo elemento inserito in coda;
- `head` indice del primo elemento inserito in testa;

Per questo si aggiunge il campo `num`, perché nel caso in cui si aggiunge il primo elemento `tail` e `head` assumono valore `1` e non possiamo controllare se la coda è vuota controllando se `tail == head` (perché sarà vero sia se `tail = head = 0` sia se `tail = head = 1`).

## Problema dello spazio iniziale

Facendo `dequeue`, può capitare che si arrivi a un punto in cui la `tail` arriva alla fine dell'array, quindi teoricamente l'array sarebbe pieno, ma in realtà non lo è perché c'è lo spazio iniziale in testa dove gli elementi sono stati rimossi: per questo si rende l'array circolare.

```c
typedef struct {
	int dato[MAX];
	int head;
	int tail;
	int size;
} queue;

void init(queue *q) {
	q->head = 0;
	q->tail = 0;
	q->size = 0;
}

int empty(queue q) {
	return (!(q.size));
}

int full(queue q) {
	return (q.size == MAX);
}

void enqueue(queue *q, int el) {
	if (q) {
		if (!full(*q)) {
			q->tail = (q->tail + 1) % MAX; // Si passa alla cella successiva
			q->dato[q->tail] = el; // Inseriamo l'elemento
			q->size++; // Aumenta la grandezza
		} else printf("Coda piena");
	} else printf("Coda non esistente");
}

int dequeue(queue *q) {
	int result = NOVALUE;
	if (q) {
		if (!empty(*q)) {
			result = q->dato[q->head]; // Assegniamo il dato
			q->head = (q->head + 1) % MAX; // Spostiamo la head avanti di 1
			q->size--; // Diminuisce la grandezza
		} else printf("Coda vuota");
	} else printf("Coda non esistente");
	return result;
}
```

# Implementazione con lista concatenata

```c
struct node {
	int data;
	struct node *next;
};

typedef struct {
	struct node *head;
	struct node *tail;
	int size;
} Queue;

void init(Queue *q) {
	q->head = NULL;
	q->tail = NULL;
	q->size = 0;
}

int empty(Queue q) {
	return (!(q.size));
}

int full(Queue q) {
	return false;
}

void enqueue(Queue *q, int el) {
	struct nodo new_node = crea_nodo(el);
	if (q) {
		if (empty(*q)) {
			q->head = new_node;
			q->tail = new_node;
			q->size = 1;
		} else {
			q->tail->next = new_node;
			q->tail = new_node;
			q->size++;
		}
	}
}

int dequeue(Queue *q) {
	int result = NOVALUE;
	if (q) {
		if (!empty(*q)) {
			result = q->head->data;
			struct nodo temp = q->head;
			q->head = q->head->next;
			free(temp);
			temp = NULL;
			q->size--;
		}
	}
	return result;
}

int dequeue(Queue *q) {
	int result = NOVALUE;
	if (q) {
		if (!empty(*q)) {
			result = q->head->data;
		}
	}
	return result;
}

int main() {
	Queue q;
	init(&q);
}
```

Coda serve a:
- Nei Sistemi Operativi per l'assegnazione della CPU ai processi
- Nei sistemi client-server per l'esecuzione delle richieste;
- Strategia di ricerca negli alberi (es. ricerca in ampiezza);