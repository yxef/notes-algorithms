Quick sort è un algoritmo Divide et Impera per ordinare un array.

È conosciuto per essere un algoritmo in media O(n log n) che lo rende molto rapido e asintoticamente equivalente a merge sort. Nel caso peggiore è un algoritmo O(n^2) ma è difficile che accada.

La parte fondamentale di questo algoritmo è la funzione Partition che richiede come input un array A, un indice d'inizio ed un indice di fine.

Come inizializzazione, il contenuto dell'elemento A[r] viene selezionato come Pivot. Lo scopo del pivot è di confrontare se stesso con gli altri elementi dell'array per trovare la sua posizione corretta in esso. Per fare questo inizializziamo due indicatori, i che parte da p-1 e j che parte da p.

Successivamente scorriamo il nostro array usando il puntatore j che arriva fino ad r-1, una posizione prima del pivot, e durante questo ciclo confrontiamo il pivot con con l'elemento in posizione j, se il pivot è più piccolo od uguale, incrementiamo il puntatore i di 1 e scambiamo a[i] con a[j], questo perché vuol dire che abbiamo trovato un elemento che dovrebbe essere a sinistra del nostro pivot, dato che è più piccolo.

Una volta finito questo ciclo, abbiamo essenzilamente ottenuto due sottoarray, p, i e i+1, j. In posizione i+1 andiamo ad inserire il nostro pivot, essendo quella la sua posizione e ritorniamo i+1 come indice di mezzo degli array.

Successivamente, verranno fatto ricorsive chiamate a quicksort prendendo come input i due sottoarray generati, escludendo i pivot.

Queste chiamate ricorsive vengono fatte fino a quando p è più piccolo di r, perché se p è >= a r allora vuol dire che il sottoarray che abbiamo passato è di un solo elemento il che vuol dire che è già ordinato.

Il vantaggio di quicksort è che non bisogna fare nessun passaggio di ricostruzione a differenza di altri algoritmi di ordinamento, dato che una volta completato questo ultimo step tutto il resto dell'array è stato ordinato