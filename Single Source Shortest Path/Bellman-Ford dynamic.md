Algoritmo per trovare una single source shortest path

Vantaggio: a differenza di dijkstra, funziona con edge negative

Dynamic programming: proviamo tutte le soluzione e prendiamo la migliore

Relaxiamo tutte le edges n-1 volte con n = numero vertici
il massimo numero di edges tra un vertice x ad un vertice y sono al massimo V-1 edges

relaxation: se la distanza da nodo u + il costo tra u e v è più piccolo della distanza diretta al nostro nodo destianazione[v] allora la nuova distanza di v è distanza di u + costo tra u e v
if(d[u]+cost(u,v) < d[v]){
	d[v]=d[u]+cost(u,v);
} 


creiamo una lista di edges

marchiamo il nodo parteza come 0 e tutte le altre le segnamo a infinito

relaxiamo per v-1 volte

una volta finito abbiamo lo shortest path verso ogni nodo dalla nostra single source

tempo O(|E| * |V|)
tempo medio O(n^2)
tempo peggiore O(n^3) se è un grafo completo dove ogni nodo ha n-1 edges

bellman ford ritorna false se è presente un ciclo cui peso totale del ciclo è negativo