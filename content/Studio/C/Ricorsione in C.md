# Ricorsione

- Definizione di ricorsione: una ricorsione è un algoritmo espresso in termini di se stesso, ovvero in cui l’esecuzione dell’algoritmo su un insieme di dati comporta la semplificazione o suddivisione dell’insieme di dati e l’applicazione dello stesso algoritmo agli insiemi di dati semplificati.
    - Casi in cui si usa: Tale tecnica risulta particolarmente utile per eseguire dei compiti ripetitivi su di un insieme di dati in input. L'algoritmo richiama se stesso generando una sequenza di chiamate che ha termine al verificarsi di una condizione particolare detta condizione di terminazione.
- Definizione di funzione ricorsiva: una funzione ricorsiva è una funzione che richiama se stessa in modo diretto o indiretto, cioè attraverso un'altra funzione.
    - Come funziona: la funzione ricorsiva è composta da due parti: il caso base, composto dalla condizione che ne fa terminare la ricorsione, e il passo induttivo, ossia l’operazione che svolge la funzione per scomporre il problema in un problema più piccolo.
    - L’involucro (wrapper) è una funzione ausiliaria che viene utilizzata nel caso in cui la ricorsione richiede un’inizializzazione complessa, cioè quando servono dei particolari valori iniziali da impostare manualmente.

Tipologie di ricorsione:

- In base ai collegamenti tra le funzioni ricorsive:
    - Ricorsione diretta: la funzione ricorsiva richiama se stessa;
    - Ricorsione indiretta (o mutua): la funzione ricorsiva, anziché richiamare se stessa direttamente, richiama una seconda funzione ricorsiva che richiama la prima (es. la funzione $\text{\tt{\color{blue}{f1}}}$ richiama la funzione $\text{\tt{\color{green}{f2}}}$ che a sua volta richiama $\text{\tt{\color{blue}{f1}}}$ e così via).
- In base a ???:
    - Ricorsione primitiva: ogni volta che la funzione ricorsiva richiama se stessa con un nuovo input, si avvicina progressivamente al caso base. Questo garantisce in modo semplice la terminazione.
- In base alla linearità:
    - Ricorsione lineare: la funzione ricorsiva esegue al massimo una sola chiamata ricorsiva al suo interno e, quindi, la sequenza delle chiamate forma una catena lineare di chiamate.
    - Ricorsione non-lineare: es. Fibonacci

# Ricorsione su array

La ricorsione su array avviene tramite l’utilizzo di indici che agiscono lungo l’intervallo degli elementi dell’array con l’obiettivo di restringerlo fino al caso base.

- Ricorsione controvariante: viene usato un intervallo semiaperto di indici crescenti $\text{\tt{i}}\in\text{\tt{[\color{blue}0, \color{pink}{len})}}$, cioè $\text{\tt{i}}$ va da $\text{\tt{\color{blue}0}}$ a $\text{\tt{\color{pink}{len}-1}}$.
    - Il caso base ha come condizione $\text{\tt{i}}\ge \text{\tt\color{pink}{len}}$ e verifica se l’array è vuoto (???)
    - Passo induttivo: si utilizza $\text{\tt{a[i]}}$ per compiere le operazioni e si fa la ricorsione con $\text{\tt i+1}$
    - Involucro: si inizia con $\text{\tt i=0}$

# Strutture dati ricorsive

Comporre dati la cui quantità è ignota a priori. In natura esistono già es. alberi: ogni albero ha il tronco da cui partono i rami che a loro volta possono avere altri rami e così via.

Una struttura dati ricorsiva è la [lista concatenata](Lista%20concatenata.md).