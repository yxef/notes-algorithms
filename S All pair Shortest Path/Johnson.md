L'algoritmo di johnson trova lo shortest path tra tutte le coppie di nodi in tempo O(V^2 log V + V E) o anche O(N^2 log N + 2N)

Per un grafo sparso, è asintoticamente più veloce di Floyd-Warshall.

L'algoritmo ritorna o una matrice di pesi dei shortest paths per tutti i paia di vertici oppure ritorna falso se è presente un ciclo negativo.

Johnson usa come sottoroutine sia di dijkstra che di bellman-ford.

L'algoritmo usa un sistema di ribilanciamento dei pesi, se tutti i pesi delle edges *w* in un grafo G = (V,E) sono non negative, possiamo trovare lo shortest path tra tutti i vertici utilizzando dijkstra una volta per vertice [con la coda min-heap per fibonacci, il tempo minimo]

Se il grafo G ha delle edges negative ma nessun ciclo negativo, possiamo calcolare un nuovo set di pesi delle edges non negative che ci permette di usare lo stesso metodo.
Il nuovo set di pesi w^ deve soddisfare due proprietà:
1. per ogni paglia di vertici u,v E V, un path p è lo shortest path da u a v usando il peso in W e solo se p è anche lo shortest path tra u a v usando il set di pesi w^
2. Per tutte le edges u,v il nuovo set di edges w^(u,v) è non negativa

sarebbe da scrivere meglio: 

Johnson usa sistema di reweighting, creando un nuovo set di pesi utilizzando l'algoritmo bellman-ford partendo da un nodo fittizio S con edges a costo 0 collegate a tutti i nodi N. Con il nuovo set di pesi ottenuto, possiamo ricavare dei nuovi pesi per le nostre edges, usando la formula W^(edges nuove) =( W(edges) + peso partenza - peso arrivo ) in modo tale che le edges negative diventino pari o superiori a 0. eseguire questo ci permette di utilizzare l'algoritmo di dijkstra per N volte su tutti i nostri vertici ottennendo lo shortest path tra tutte le coppie