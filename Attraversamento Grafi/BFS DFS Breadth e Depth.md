BFS Prima esploro completamente, coda
DFS Prima esploro i nuovi nodi, stack

BFS e DFS sono degli algoritmici permettono di attraversare grafi.
Definiamo le due operazioni basi: visitare un nodo e esplorare un nodo.
Visitare significa andare nel vertice mentre esplorare vuol dire visitare tutti i vicini del nostro corrente nodo.

In BFS: iniziamo dal primo vertice ed esploriamo tutti i suoi vicini, scrivendo quello che abbiamo trovato su una tabella, una volta esplorati tutti visitiamo il successivo vertice scritto nella tabella e effettuiamo l'esplorazione di tutti i suoi vicini, ripetiamo fino a quando non abbiamo inserito tutti i nodi nella tabella.
BFS è come esplorare un intero livello di un binary tree
Un implentazione di BFS è con una coda dove scrivo il nodi che sto visitando, cancello quello che sto correntemente esplorando ed aggiungo quelli nuovi che trovo. eventualmente la queue si libera ed avremmo esplorato completamente il grafo.
Il tempo di BFS è O(V+E)

In DFS: A differenza di BFS, dal nodo di partenza esploriamo fino a quando non incontriamo un nodo che non è già presente nella tabella, quando trovato ci spostiamo su di esso e continuiamo ad esplorare in quello, e così via fino a quando non vengono esplorati tutti i nodi. Una volta terminato l'esplorazione di tutti i vicini di un nodo, quando torniamo indietro continuiamo con le esplorazioni "lasciate in sospeso" e terminiamo effettivamente una volta che abbiamo inserito tutti i nodi nella tabella.
DFS è come esplorare in "preorder" o visitare prima tutti i nodi a sinistra andando verso destra.
DFS è implementabile utilizzando una stack, first in first out, questo perché appena trovo un nuovo vertice da aggiungere alla stack, sospendo l'esplorazione del numero corrente e continuo con quello nuovo
Il tempo di DFS è  O(V+E)

Le due generano risultati diversi, ma entrambe esplorano tutti i nodi