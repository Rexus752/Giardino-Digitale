---
icon: FasArrowsToCircle
iconColor: "#88FF88"
---
# Variazioni e incrementi

>[!definizione] _Definizione_: incremento
>Data una [funzione](Introduzione%20alle%20funzioni.md#^Funzione) $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$, per ogni coppia di punti nel dominio $x_{1}, x_{2} \in \text{Dom}(f)$ si definisce **_incremento_** o ***variazione*** di $x$ nel passaggio da $x_{1}$ a $x_{2}$ e si denota con $\Delta x$ la differenza:
>$$\Delta x = x_{2} - x_{1}$$
>Inoltre, si definisce **_incremento_** o **_variazione_** di $f$ in corrispondenza dell'incremento $\Delta x$ della variabile indipendente $x$ e si denota con $\Delta f$ la differenza:
>$$\Delta f = f(x_{2}) - f(x_{1})$$
^Incremento

>[!definizione] _Definizione_: tasso di variazione medio
>Data una funzione $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$, per ogni coppia di punti del dominio $x_{1}, x_{2} \in \text{Dom}(f)$ si definisce ***tasso di variazione medio*** di $f$ rispetto a $x$ nel passaggio da $x_1$ a $x_2$ il quoziente:
>$$\frac{\Delta f}{\Delta x} = \frac{f(x_{2}) - f(x_{1})}{x_{2} - x_{1}}$$
>
>>[!esempio] _Esempio_: tasso di variazione medio come velocità media di un oggetto
>>Si consideri un oggetto che si muove lungo una retta: se si indica con $x$ il tempo e con $f(x)$ la posizione sulla retta al tempo $x$ (misurata rispetto a un'origine fissata), allora il quoziente $\frac{\Delta f}{\Delta x}$ è proprio la _velocità media_ nell'intervallo di tempo $[x_1;x_2]$.

>[!definizione] _Definizione_: funzione limitata (superiormente, inferiormente)
>Data una funzione $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$:
>- $f$ si dice ***superiormente limitata*** sul dominio $\text{Dom}(f)$ se esiste un valore $M\in \mathbb{R}$ tale che $f(x)\le M,\quad\forall x \in \text{Dom}(f)$:
>![Funzione%20superiormente%20limitata.png](Funzione%20superiormente%20limitata.png)
>- $f$ si dice ***inferiormente limitata*** sul dominio $\text{Dom}(f)$ se esiste un valore $m\in \mathbb{R}$ tale che $f(x)\ge m,\quad\forall x \in \text{Dom}(f)$:
>![Funzione%20inferiormente%20limitata.png](Funzione%20inferiormente%20limitata.png)
>- $f$ si dice ***limitata*** se è sia superiormente sia inferiormente limitata sul dominio $\text{Dom}(f)$, ossia se esistono due valori $m,M\in \mathbb{R}$ tali che $m\le f(x)\le M,\quad\forall x \in \text{Dom}(f)$:
>![Funzione%20limitata.png](Funzione%20limitata.png)
>
>>[!osservazione] _Osservazione_: grafici contenuti in semipiani
>>Si osservi che:
>>- Il grafico di una funzione superiormente limitata è contenuto in un semipiano del tipo $\{(x,y)\in \mathbb{R}^{2}\mid y\le M\},\quad M\in \mathbb{R}$;
>>- Il grafico di una funzione inferiormente limitata è contenuto in un semipiano del tipo $\{(x,y)\in \mathbb{R}^{2}\mid y\ge m\},\quad m\in \mathbb{R}$;
>>- Il grafico di una funzione limitata è invece contenuto in una striscia orizzontale del tipo $\{(x,y)\in \mathbb{R}^{2}\mid m\le y\le M\},\quad m,M\in \mathbb{R}$.

# Punti di massimo e di minimo

>[!definizione] _Definizione_: punto di massimo e punto di minimo (relativo, assoluto)
>Data una funzione $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$:
>- Un punto $c\in \text{Dom}(f)$ si dice ***punto di massimo relativo (o locale)*** di $f$ su $\text{Dom}(f)$ se esiste un $r>0$ tale che $$f(x)\le f(c),\quad\forall x \in \text{Dom}(f)\cap(c-r,c+r)$$
>In questo caso, il valore $f(c)$ si dice *massimo relativo* di $f$.
>Se la disuguaglianza vale per ogni $x\in \text{Dom}(f)$, allora $c$ si dice ***punto di massimo assoluto*** di $f$ su $\text{Dom}(f)$ e il valore $f(c)$ si dice *massimo assoluto* di $f$ su $\text{Dom}(f)$;
>- Un punto $c\in \text{Dom}(f)$ si dice ***punto di minimo relativo (o locale)*** di $f$ su $\text{Dom}(f)$ se esiste un $r>0$ tale che $$f(x)\ge f(c),\quad\forall x \in \text{Dom}(f)\cap(c-r,c+r)$$
>In questo caso, il valore $f(c)$ si dice *minimo relativo* di $f$.
>Se la disuguaglianza vale per ogni $x\in \text{Dom}(f)$, allora $c$ si dice ***punto di minimo assoluto*** di $f$ su $\text{Dom}(f)$ e il valore $f(c)$ si dice *minimo assoluto* di $f$ su $\text{Dom}(f)$.
>
>>[!esempio] _Esempio:_ grafico di una funzione con punti di massimo e di minimo
>>Nel seguente grafico della funzione $f$ sono rappresentati:
>>- Il punto di minimo assoluto $x_1$;
>>- Il punto di massimo relativo $x_2$;
>>- Il punto di minimo relativo $x_3$;
>>- Il minimo assoluto $f(x_1)$;
>>- Il massimo relativo $f(x_2)$;
>>- Il minimo relativo $f(x_3)$.
>>
>>![Minimi%20e%20massimi%20relativi%20e%20assoluti.png](Minimi%20e%20massimi%20relativi%20e%20assoluti.png)

# Funzioni pari e funzioni dispari

>[!definizione] _Definizione_: funzione pari e funzione dispari
>Data una funzione $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$ con $\text{Dom}(f)$ [simmetrico](Simmetrico) rispetto all'origine:
>- $f$ si dice ***pari*** se $f(-x)=f(x),\quad\forall x \in \text{Dom}(f)$;
>- $f$ si dice ***dispari*** se $f(-x)=-f(x),\quad\forall x \in \text{Dom}(f)$.
>
>>[!osservazione] _Osservazione_: grafico di funzioni pari e dispari
>>In termini di [grafico](Introduzione%20alle%20funzioni.md#^b8a997) $\Gamma_f$ di $f$, è semplice osservare che vale:
>>- $(x,y)\in\Gamma_f\iff(-x,y)\in\Gamma_f$ per una funzione pari;
>>- $(x,y)\in\Gamma_f\iff(-x,-y)\in\Gamma_f$ per una funzione dispari.
>>
>>Ciò significa che il grafico di una funzione pari è simmetrico rispetto all'asse delle ordinate:
>>![Grafico%20funzione%20pari.png](Grafico%20funzione%20pari.png)
>>Invece, il grafico di una funzione dispari è simmetrico rispetto all'origine:
>>
>>![Grafico%20funzione%20dispari.png](Grafico%20funzione%20dispari.png)

# Funzioni periodiche

>[!definizione] _Definizione_: funzione periodica
>Data una funzione $f\colon \text{Dom}(f) \subseteq \mathbb{R}\to \mathbb{R}$, essa si dice ***periodica*** se esiste un $T>0$ tale che:
>1. L'insieme $\text{Dom}(f)$ soddisfa la proprietà $x\in \text{Dom}(f)\iff x+T \in \text{Dom}(f)$;
>2. Vale la relazione $f(x+T)=f(x),\quad\forall x\in \text{Dom}(f)$.
>In questo caso, il numero $T$ viene detto _periodo_ di $f$.
>
>>[!osservazione] _Osservazione:_ grafico di una funzione periodica
>>È semplice osservare che il grafico di una funzione $f$ periodica di periodo $T$ è invariante per traslazioni orizzontali di ampiezza $T$: questo significa che è sufficiente tracciare il grafico di $f$ su un intervallo di lunghezza $T$ e ripeterlo infinite volte a destra e a sinistra dell'intervallo considerato:
>>![Grafico%20funzione%20periodica.png](Grafico%20funzione%20periodica.png)

# Crescenza di funzioni e monotonia

>[!definizione] _Definizione_: funzioni crescenti e decrescenti
>Dato un intervallo $I \subseteq \mathbb{R}$ e una funzione $f\colon I\to \mathbb{R}$:
>- $f$ si dice **_crescente_** su $I$ se $$x_{1}<x_{2}\implies f(x_{1})\le f(x_{2}),\quad\forall x_{1},x_{2}\in I$$
>o, equivalentemente, se $$\Delta x>0 \implies \Delta f \ge0,\quad\forall x_{1},x_{2}\in I$$
>- $f$ si dice **_strettamente crescente_** su $I$ se $$x_{1}<x_{2}\implies f(x_{1})< f(x_{2}),\quad\forall x_{1},x_{2}\in I$$
>o, equivalentemente, se $$\Delta x>0 \implies \Delta f >0,\quad\forall x_{1},x_{2}\in I$$
>- $f$ si dice **_decrescente_** su $I$ se $$x_{1}<x_{2}\implies f(x_{1})\ge f(x_{2}),\quad\forall x_{1},x_{2}\in I$$
>o, equivalentemente, se $$\Delta x>0 \implies \Delta f \le0,\quad\forall x_{1},x_{2}\in I$$
>- $f$ si dice **_strettamente decrescente_** su $I$ se $$x_{1}<x_{2}\implies f(x_{1})>f(x_{2}),\quad\forall x_{1},x_{2}\in I$$
>o, equivalentemente, se $$\Delta x>0 \implies \Delta f <0,\quad\forall x_{1},x_{2}\in I$$
>
>>[!osservazione] _Osservazione_: 
>>Intuitivamente, una funzione è strettamente crescente se un aumento della variabile indipendente $x$ implica un aumento della variabile dipendente $f(x)$ e, analogamente, una diminuzione di $x$ implica una diminuzione di $f(x)$: le [variazioni](#^Incremento) $\Delta x$ e $\Delta f$ sono quindi concordi, cioè hanno lo stesso segno.
>>La definizione di crescenza stretta si può dare alternativamente dicendo che, dato un intervallo $I \subseteq \mathbb{R}$ e una funzione $f\colon I\to \mathbb{R}$, $f$ si dice _strettamente crescente_ su $I$ se
>>$$\frac{\Delta f}{\Delta x}>0,\quad\forall\Delta x \ne 0$$
>>Ovviamente, analoghe osservazioni valgono per le funzioni crescenti, decrescenti e strettamente decrescenti.
^Funzioni-crescenti-e-decrescenti

%%Mettere grafici per ogni esempio%%

>[!definizione] _Definizione_: funzioni monotone
>Dato un intervallo $I \subseteq \mathbb{R}$ e una funzione $f\colon I\to \mathbb{R}$:
>- $f$ si dice ***monotona*** su $I$ se è [crescente](#^Funzioni-crescenti-e-decrescenti) su $I$ oppure [decrescente](#^Funzioni-crescenti-e-decrescenti) su $I$;
>- $f$ si dice ***strettamente monotona*** su $I$ se è [strettamente crescente](#^Funzioni-crescenti-e-decrescenti) su $I$ oppure [strettamente decrescente](#^Funzioni-crescenti-e-decrescenti) su $I$.
>
>>[!osservazione] _Osservazione_: 
>>Il concetto di monotonia è legato a quello dell'[ordinamento sulla retta reale](Introduzione%20alle%20funzioni.md#^Funzione):
>>- Le funzioni crescenti mantengono l'ordinamento nel passaggio da $x$ a $f(x)$:
>>![Funzione%20crescente%20sulla%20retta%20reale.png](Funzione%20crescente%20sulla%20retta%20reale.png)
>>- Le funzioni decrescenti lo invertono:
>>![Funzione%20decrescente%20sulla%20retta%20reale.png](Funzione%20decrescente%20sulla%20retta%20reale.png)

>[!proposizione] _Proposizione:_ monotonia e invertibilità
>Dato un intervallo $I \subseteq \mathbb{R}$ e una funzione $f\colon I\to \mathbb{R}$ si ha che:
>- Se $f$ è [strettamente crescente](#^Funzioni-crescenti-e-decrescenti) su $I$, allora:
>	- $f$ è [invertibile](#^Funzione-inversa);
>	- $f^{-1}$ è [strettamente crescente](#^Funzioni-crescenti-e-decrescenti) su $f(I)$;
>- Se $f$ è [strettamente decrescente](#^Funzioni-crescenti-e-decrescenti) su $I$, allora:
>	- $f$ è [invertibile](#^Funzione-inversa);
>	- $f^{-1}$ è [strettamente decrescente](#^Funzioni-crescenti-e-decrescenti) su $f(I)$.

>[!proposizione] _Proposizione:_ somma di funzioni monotone
>Dato un intervallo $I \subseteq \mathbb{R}$ e due funzioni $f_{1} \colon I\to \mathbb{R}$ e $f_{2} \colon I\to \mathbb{R}$ si ha che:
>- Se $f_{1}$ ed $f_{2}$ sono entrambe [(strettamente) crescenti](#^Funzioni-crescenti-e-decrescenti) su $I$, allora $f_{1}+f_{2}$ è [(strettamente) crescente](#^Funzioni-crescenti-e-decrescenti) su $I$;
>- Se $f_{1}$ ed $f_{2}$ sono entrambe [(strettamente) decrescenti](#^Funzioni-crescenti-e-decrescenti) su $I$, allora $f_{1}+f_{2}$ è [(strettamente) decrescente](#^Funzioni-crescenti-e-decrescenti) su $I$.

>[!proposizione] _Proposizione:_ composizione di funzioni monotone
>Dati due intervalli $I \subseteq \mathbb{R}$ e $J \subseteq \mathbb{R}$ e due funzioni $f\colon I \to \mathbb{R}$ e $g \colon I \to \mathbb{R}$ con $f(I) \subsetneq I$, allora si ha che:
>- Se $f$ e $g$ sono entrambe [(strettamente) crescenti](#^Funzioni-crescenti-e-decrescenti) rispettivamente su $I$ e $J$, allora la loro [composizione](Introduzione%20alle%20funzioni.md#^Composizione-di-due-funzioni) $g\circ f$ è [(strettamente) crescente](#^Funzioni-crescenti-e-decrescenti) su $I$;
>- Se $f$ e $g$ sono una [(strettamente) crescente](#^Funzioni-crescenti-e-decrescenti) e l'altra  [(strettamente) decrescente](#^Funzioni-crescenti-e-decrescenti) rispettivamente su $I$ e $J$, allora la loro [composizione](Introduzione%20alle%20funzioni.md#^Composizione-di-due-funzioni) $g\circ f$ è [(strettamente) decrescente](#^Funzioni-crescenti-e-decrescenti) su $I$.
>
>>[!dimostrazione] _Dimostrazione_ 
>>Si dimostra solo il caso in cui $f$ e $g$ sono entrambi strettamente crescenti rispettivamente su $I$ e $J$; gli altri casi si dimostrano in modo analogo.
>>Dati due valori $x_{1},x_{2}\in I$ con $x_{1}<x_{2}$, bisogna dimostrare che
>>$$(g\circ f)(x_{1})<(g\circ f)(x_2)$$
>>Per ipotesi, $f$ è strettamente crescente su $I$, quindi si ha che $f(x_{1})<f(x_{2})$; d'altra parte, la funzione $g$ è strettamente crescente su $J$.
>>Applicando così $g$ nell'ultima disuguaglianza scritta, si ricava quindi che
>>$$g(f(x_{1})) < g(f(x_{2}))$$
>>cioè proprio la disuguaglianza che si doveva dimostrare.
>>$\blacksquare$
>
>>[!trucco-mnemonico] _Trucco mnemonico:_ la "_regola dei segni_"
>>Le relazioni espresse in questa proposizione sono dette "_regole dei segni_" per l'evidente analogia con l'usuale regola dei segni per il prodotto di due numeri reali.
>
>>[!esempio] _Esempio:_ composizione di due funzioni entrambe (strettamente) crescenti
>>![Composizione%20di%20due%20funzioni%20entrambe%20(strettamente)%20crescenti.png](Composizione%20di%20due%20funzioni%20entrambe%20(strettamente)%20crescenti.png)
>>%%completare%%
>
>>[!esempio] _Esempio:_ composizione di due funzioni entrambe (strettamente) decrescenti
>>![Composizione%20di%20due%20funzioni%20entrambe%20(strettamente)%20decrescenti.png](Composizione%20di%20due%20funzioni%20entrambe%20(strettamente)%20decrescenti.png)
>>%%completare%%

# Funzioni convesse e concave



# Comportamento asintotico all'infinito



# Fonti
- lezioni seiler
- libro di analisi

# Miglioramenti
- Fare grafici in Geogebra