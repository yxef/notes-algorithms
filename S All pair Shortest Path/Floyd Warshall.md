All pair shortest path.
esempio, abbiamo 4 vertici, devo trovare lo shortest path tra 1 e 2,3,4. allo stesso modo devo trovare lo shortest path tra 2 e 1,3,4 e così via fino a quando non trovo tutte le coppie di shortest path.

Questo problema è risolvibile con Dynamic programming, ed utilizzando una matrice di decisioni.

Inizializiamo la matrice VxV inserendo in posizione i (vertice di partenza) e posizione j (vertice di arrivo) in cui inseriamo il costo che dovremmo pagare per fare l'attraversamento. come primo passo metteremo solo le connessioni dirette e segneremo ad infinito ogni nodo non raggiungibile. Inoltre nelle caselle di valore i x i andremmo ad inserire 0, impendendo i loop di nodi che indichino se stessi.

Una volta creata questa matrice generica, ora continuiamo ad elaborare la matrice assumendo che ogni altro nodo debba passare per il nodo 1. Prendiamo la matrice originale e copiamo la riga 1x1 e la colonna 1x1 (dato che queste non cambiano). Successivamente andiamo a riempire il resto dei costi assumendo che ogni nodo debba passare per 1, esempio da 2 a 4 2->1->4, e scrivendo in posizione 2,4 il rispettivo costo se questo è minore del costo della matrice predente nella stessa posizione.

Ripetiamo questo fino a quando non generiamo la matrice An dove avremmo l'all pairs shortest path 
O(n^3)
 ![[Pasted image 20220115200530.png]]