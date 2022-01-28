Ci sono due tipi di operazioni che possiamo fare:
	 -**Interrogazioni o Query**
	 -**Operazioni di Modifica**
Le prime sono tutte quelle operazione che restituiscono informazioni sull'insieme mentre le altre intendono cambiare il nostro Set/Insieme

Lista di tipiche operazioni che vengono implementate

- #### *Search(S, k)*
	- Una query che, dato un set *S* e una valuta chiave *k*, ritorna un puntatore all'oggetto in *S* tale che x.key == k o NIL/NULL se nessun elemento appartiene ad *S*
- #### *Insert(S, x)*
	- Una operazione di modifica che inserisce nel set S un elemento che viene indicato da *x*. 
	- Diamo per scontato che gli altri attributi dell'elemento *x* che vengono richiesti dal Set *S* per l'inserimento siano già inizializzati
- #### *Delete(S, x)*
	- Un operazione di modifica che, dato un puntatore *x* ad un elemento dell'inisieme *S*, rimuove *x* da *S*
- Minimum(S)
- Maximum(S)
- Successor(S, x)
- Predecessor(S, x)

