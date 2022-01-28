Un grafo a più stadi è un grafo direzionato con cui ci si può muovere solo a stadi successivi a quello presente
avendo un grafo direzionato con i rispettivi pesi, dobbiamo attraversare il grafo fino ad arrivare all'ultimo stadio pagando il costo minore.
Risolviamo questo problema con dynamic programming, prendendo una serie di decisioni scrivendo i vari costi in tabella.
Avendo una tabella di grandezza O(n) salviamo il costo e la distanza dal nostro target. Lo riempiamo in modo backwards, partiamo dall'ultimo indice che è il nostro target e segniamo il costo pari a sero e distanza pari al vertice che bisogna attraversare per arrivare al nostro target, in questo caso sarebbe se stesso. Una volta completato questo andiamo ad analizzare gli elementi del livello precedente, quindi se il target è il nodo 12 ed andiamo ad analizzare il nodo 9, 10 e 11, scriveremo nel'indice costo il prezzo da pagare per attraversare l'edge che li connette sommandolo al costo di arrivare a 12 da 12, che in quel caso è zero
quindi per esempio se analiziamo 9 con costo 4 per arrivare a 12 scriviamo in tabella a indice 9 costo = 4 destinazione = 12
e continuiamo così, scegliendo sempre quelli che costano meno nello stage successivo (se sono connessi) fino a completare il path che costa meno dal primo stage

O(log n)? O(n^2)?
![[Pasted image 20220115172625.png]]