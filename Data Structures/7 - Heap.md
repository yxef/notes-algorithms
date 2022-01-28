Un heap è una struttura principalmente utilizzati per code di priorità.
Un heap è un albero binario che deve mantenere la proprietà degli heap intatta ovvero:

Per ogni A nodo genitore, i figli devono mantenere la proprietà dell'heap (devono essere o maggiori o minori del genitore a seconda se è un max o min heap)

Come muoversi in un Heap:
1. Figlio sinistro 2 x i
2. Figlio destro 2 x i+1
3. Parent 2 / i

Vantaggi heap: ottenere il max/min in tempo O(1), rimuovere il minimo in log n, inserire in tempo log n e heapsort in tempo n log n

Operazioni: estrare il max/min, creare un heap, heapify, increase key, delete, heapsort

Insert: fatto nell'ultimo spazio libero e viene chiamato heapify sul parent fino a quando la condizione dell'heap diventa vera.
Delete/Extract: l'oggetto viene estratto/deletato scambiandolo con l'ultimo elemento dell'heap e chiamando heapify sulla nuova root fino a quando non avvengono più scambi.
Increase/decrease key: chiamamo heapify sul parent di quello che incrementiamo fino a quando non scambia più

Heapify: risolve una anomalia, assume che i figli di i mantengono la proprietà heap mentre il nodo i no. Scambia il nodo i con il suo figlio maggiore/minore. se heapify effettua uno scambio, chiamerà di nuovo se stessa sul nuovo figlio per capire se deve farlo scendere di più. O(log n)

BuildxHeap: in un qualsiasi array input A, costruisce un heap in bottom-up chiamando parendo dall'ultimo parent fino ad 1, chiamando heapify ad ogni passaggio. O(N)

Heapsort funziona in 2 passaggi: 
1. effettua un BuildHeap sul nostro array input.
2. Estrae la root dell'heap una a una e mettendo il dato in fondo all'array
3. O (n log n)