- Set: dati omogenei non ordinati, ogni elemento compare al più una sola volta (ogni elemento è unico)
- Multiset: stessi elementi possono occorrere più volte

# Implementazione con lista concatenata

Dato che non sono liste ordinate, posso fare l'inserzione in testa per comodità

```c
typedef struct {
	struct nodo *dati;
	int size;
} Set;

void aggiungi(Set *s, int el) {
	ins_testa(el, s);
}

void toglitutti(Set *s, int el) {
	
}
```