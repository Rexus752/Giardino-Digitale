```c
#include <stdio.h>

typedef struct {
	char nome[MAXS];
	char razza[MAXS];
	int eta;
	char genere;
} Cane;

typedef struct {
	Cane ospiti; // Cani presenti nel canile
	int size; // Numero di cani presenti
} MultiSetC;

typedef struct cl {
	Cane cani;
	struct cl *next;
} *ListC;

void init_MultiSetC(MultiSetC *m) {
	init_ListC(&(m->ospiti))
	m->size = 0;
}

void init_ListC(ListC *l) {
	*l = NULL;
}

void aggiungi_cane(MultiSetC *m) {
	Cane temp;
	printf("Inserire il nome: ");
	scanf("%s", temp.name);
	printf("Inserire la razza: ");
	scanf("%s", temp.razza);
	printf("Inserire l'età: ");
	scanf("%d", temp.eta);
	printf("Inserire il genere (M o F): ");
	scanf("%c", temp.genere);
	// Fare controllo sul genere se è corretto
	add_MultiSetC(m, temp);
}

void add_MultiSetC(MultiSetC *m, Cane new) {
	if (m) {
		m->size++;
		add_ListC(&(m->ospiti), new);
	} else printf("Non esiste");
}

void add_ListC(ListC *l, Cane new) {
	if (l) {
		ListC nodo = crea_nodo(new);
		nodo->next = *m;
		*m = nodo;
	} else printf("Non esiste");
}

ListC crea_nodo(Cane new) {
	ListC temp = (ListC) malloc(sizeof(struct cl));
	if (temp) {
		temp->new = new;
		temp->next = NULL;
	}
	return temp;
}

int main() {
	// --- Inizializzazione dei dati ---
	MultiSetC ospiti;
	init_MultiSetC(&ospiti);
	Cane tempc;
	FILE *fp = fopen("cani.txt", "r"); // Apertura file
	while (!feof(fp)) { // Finché non si raggiunge la fine del file
		fscanf(fp, "%s %s %d %c\n", tempc.nome, tempc.razza, &(tempc.eta), &(tempc.genere));
		add_MultiSetC(&ospiti, tempc);
	}
	fclose(fp); // Chiusura file
	// --- Uso del programma ---
	int finito = 0;
	while(!finito) {
		printf("\nElenco comandi:\n");
		printf("1) Inserisci un cane;\n");
		printf("2) Rimuovi un cane;\n");
		printf("3) Visualizza la lista dei cani;\n");
		printf("4) Termina il programma.\n");
		printf("Inserisci il numero del comando da eseguire: ");
		int cmd;
		scanf("%d", &cmd);
		switch (cmd) {
			case 1:
				aggiungi_cane(&ospiti);
				break;
			case 2:
				togli_cane(&ospiti);
				break;
			case 3:
				visualizza_cani(ospiti);
				break;
			case 4:
				finito = 1;
				break;
			default:
				printf("Comando non corretto.\n");
				break;
		}
	}
	// --- Salvataggio dei dati ---
	FILE *fp = fopen("cani.txt", "w"); // Apertura file
	fprint_MultiSetC(dati, ospiti); // Scrittura dei dati 
	fclose(fp); // Chiusura file
}
```