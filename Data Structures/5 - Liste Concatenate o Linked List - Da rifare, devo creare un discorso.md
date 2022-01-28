Una lista concatenata è una struttura dati fondamentale i cui oggetti sono disposti in ordine lineare.
A differenza degli array, il cui ordine lineare è determinato dagli indici dell'array, nella linked list l'ordine è determinato da un puntatore in ogni oggetto.

Ogni elemento della lista concatenata a due puntatori: un puntatore che indica all'oggetto precedente ed uno a quello successivo. Quell'elemento inoltre possede il suo valore chiave.

Esempio di linked list
![[Pasted image 20211121174127.png]]
L'oggetto inoltre può concatenare altri dati satellliti.

Dato un elemento *x* nella lista, next[x] punta al suo successore nella linked list, mentre prev[x] indica quello precedente
Se prev[x] = NIL, l'elemento, questo vuol dire che è il primo elemento della lista, quindi è la testa.
Se next[x] = NIL, l'elemento, questo vuol dire che è il l'ultimo elemento della lista, quindi è la coda.

Per indirizzare il primo elemento, salveremo il suo puntantore in un attributo head[L] che contiene il puntatore al primo oggetto.

se Head[L] = NIL allora la lista è vuota

Una lista può avere varie forme, può essere singolarmente o doppiamente concatenata, ordinata o meno, circolare o no.
Se una lista è **Singolarmente concatenata** omettiamo il puntantore prev in ogni elemento.
Se una lista è **ordinata** l'ordine lineare della lista corrisponde all'ordine lineare delle chiavi memorizzate negli elementi della lista. 
L'elemento minimo è la testa della lista mentre l'elemento massimo è la coda, o viceversa se sono ordinate al contrario.

In una lista *Circolare* il puntatore *prev* della testa punta alla coda della lista e viceversa per il puntantore *next*.

La funzione List-Search(L, k) trova il primo elemento con la chiave *k* nella lista *L* tramite una semplice ricerca lineare, restituendo un puntatore a quell'elemento.
Se nessun'oggetto con la chiave *k* è presente, allora viene restituito il valore NIL.
Codice:
![[Pasted image 20211121184949.png]]
Essendo una ricerca lineare il tempo impiegato è Θ(n) nel caso peggiore

L'inserimento in una lista concatenata di un elemento *x* il cui campo Key è già stato impostato avviene in tempo O(1). Questo perché andiamo semplicemente a cambiare il puntatore del primo oggetto e di x. 
Come successivo di x assegnamo il primo elemento.
Se head[L] non è NIL, vuol dire che effettivamente stava puntando a qualcosa quindi bisogna modificare anche lui, cambiando il suo elemento *prev* in modo che invece di indicare NIL indichi il nuovo elemento *x*. Successivamente assegnamo a head[L] il puntatore di x e segnamo il precedente di x come NIL dato che è la testa.

Codice a seguire:
![[Pasted image 20220117163904.png]]

Molto simile il cancellare per certi versi
![[Pasted image 20220117164045.png]]

Per semplificare questi processi, possiamo utilizzare delle *Sentinelle*.
Le *Sentinelle* sono oggetti fittizi che ci consentono di semplificare le condizioni al contorno.
Supponiamo di fornire alla lista L un oggetto *nil[L]* che rappresenta NIL ma ha tutti i campi degli altri elementi della lista, sostituiamolo con un riferimento alla sentinella *nil[L]*.
Questo trasforma una normale lista doppiamente incatenata in una **lista circolare doppiamente incatenata**
![[Pasted image 20211122173843.png]]
dove la sentinella *nil[L]* è posta tra la testa e la coda; il campo next[nil[L]] punta alla lista della testa, possiamo eleimiare del tutto l'attributo head[L], sostituendo i suoi riferimenti con i riferimenti a next[nil[L]]. Una lista vuota è formata soltanto dalla sentinella in quanto next[nil[L]] e prev[nil[L]] possono essere impostati entrambi a nil[L].

### Rappresentazioni di alberi con Radice

Possiamo utilizzare le liste per rappresentare strutture dati come alberi con radice.
Simile le linked list, immaginiamo che ogni nodo ha 3 campi, 1 per il parent (ovvero il nodo che gli è superiore) e 2 riservati per i puntatori del del figlio sinistra e quello destra
Esempio di alberi binari:
![[Pasted image 20211122175230.png]]

Questo ci apre la possibilità anche ad altri schemi, dove possiamo evere un numero costante di figli per nodo *k*, quindi invece di avere *left* e *right* avremmo *child1* *child2* *child3* ... *childK*.
Il problema di questa rappresentazione che non funzione se vogliamo una ramificazione senza limite ed inoltre andremo ad allocare un grande quantità costante di memoria.

Per risolvere questo problema usiamo una rappresentazione chiamata **Rappresentazione figlio-sinistro fratello-destro** che ci permette di occupare solo spazio O(n):
![[Pasted image 20211122175903.png]]

Questa rappresentazione permette di avere ogni nodo che indica il suo parent nel suo campo "Parent". Il campo figlio-sinistra o left-child che indica il figlio più a sinistra (che da inizio alla coda di siblings) e il campo right-sibling che è una code di fratelli che a loro volta avranno lo stesso parent del primo nodo più a sinistra.