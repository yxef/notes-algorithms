Abbiamo due algoritmi greedy per trovare il minimum cost spanning tree cioè l'albero di connessione minimo, primm e kruskal
un minimum cost spanning tree è un sottoalbero che attraversa tutti i vertici una volta pagando il minimo costo possibile quindi dobbiamo prendere tutti i vertici e |v|-1 edges

Questi algoritmi condividono uno stesso metodo generico per la crescita del minimum spanning tree, mantenendo la stessa invariante di ciclo: Prima di ogni iterazione, A è un sottoinsieme di qualche minimum spanning tree.
Dopo aver stabilito l'invariante possiamo fare che ad ogni step determiniamo una safe edge che possiamo aggiungere al nostro sotto albero senza violare la nostra condizione, assicurandoci che comunque la nostra sottosoluzione trovata è un minimum spanning tree

Kruskal opera sui propri nodi come disjointed sets. Ci sono due principali operazioni che vengono effettuate su questa struttura dati: Find e Union
Find: trova un nodo e a quale set appartiene
Union: unisce due nodi appartenenti a due set diversi con una edge, creando un singolo set. Se proviamo ad effettuare una union su due nodi appartenenti ad uno stesso set creiamo/detectiamo un ciclo.

Partendo da un nostro set universale di nodi, se effetuiamo la union find per ogni edge presente nel grafo, se eventualmente troviamo una edge che connette due nodi già nello stesso set vuol dire che è presente un ciclo

In kruskal, selezioniamo sempre la edge che costa il minimo. Iniziamo creando un set per ogni vertice. per ogni edge che connette due vertici, verifichiamo con find se appartengono allo stesso set, e se meno allora andiamo ad aggiungerli al nostro set soluzione ed effuiamo una union sui due.
![[Pasted image 20220118104254.png]]

Nell'algoritmo di primm invece, procediamo scegliendo un qualsiasi vertice. Da questa posizione, iniziamo a scegliere sempre la edge che costa meno già connessa a vertici che abbiamo già scelto. Questo fino a quando non abbiamo esplorato tutti i vertici e completato il minimum cost spanning tree.
![[Pasted image 20220118104317.png]]


Il costo di questi algoritmi è theta di |V| * |E|
se prendiamo V come N, dato che al meglio le Edges siano pari o superiori a V possiamo dire che è in theta (n^2)

Possiamo ottenere delle prestazioni migliori se conserviamo le edges in un min heap, migliorando il tempo a n log n