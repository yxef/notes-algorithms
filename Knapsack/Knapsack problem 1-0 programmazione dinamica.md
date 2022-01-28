questa versione di knapsack non possiamo prendere frazioni, possiamo solo prendere l'oggetto intero, e dobbiamo comunque calcolare la combinazione che ci dia il massimo profitto per peso

per fare questo usiamo l'approccio di dynamic programming che ci dice di provare tutte le soluzione e scegliere la migliore.
Nel nostro sacchetto ci sono al massimo 2^n combinazioni possibili, la presenza o l'assenza di un oggetto nel sacchetto è segnato con 0 e 1, quindi sono una combinazione binaria. Detto questo, non spenderemo questo tempo per provare tutte le combinazioni.

In questo problema utiliziamo il metodo della tabulazione. Creiamo un matrice che parte da 0 e che arrivi al peso della nostra sacca, ad esempio 8, per lunghezza e di altezza 0 a n elementi. (w+1, n+1)

Valutiamo la capacità della nostra sacchetta assumendo che abbia peso massimo 0 e uno alla volta andiamo ad aumentarlo di uno ad ogni passaggio, stesso per gli oggetti, prima consideriamo solo il primo oggetto, poi il primo e il secondo, poi il primo secondo e terzo e così via.

Riempiamo la tabella considerando 0 oggetti con pesi da 0 alla size dello zaino, dato che consideriamo 0 oggetti riempiamo la riga con 0, dato che generiamo 0 profitto inserendo nulla.

Per il livello successivo includiamo il primo oggetto, segnamo a 0 i profitti fino a quando non raggiungiamo un peso adeguato a contenere l'oggetto 1, scrivendo il profitto che genera sul resto dei pesi fino a considerare la sacca alla massima capienza. Dopo consideramo anche il secondo oggetto, inserendo sempre nei profitti il numero maggiore di profitto che possiamo generare a certi pesi tenendo conto di entrambi gli oggetti e delle loro combinazioni se possiamo permetterci di inserirli. Continuiamo così fino a quando non abbiamo considerato tutti gli oggetti.

Una volta completata la tabella dobbiamo ricavare quali oggetti effetivamente da inserire per ottenere quel profitto e per farlo andiamo cercare nell'ultima riga della tabella il profitto più alto e dove appare, per esempio se nell'ultima riga appare il profitto più alto allora vuol dire che dobbiamo inserire l'oggetto dato che quel numero può essere stato generato solo dall'inserimento di quell'oggetto, quindi nella nostra soluzione includiamo quell'oggetto. Prendiamo il peso massimo e sottraiamo il peso di questo oggetto. Ora dobbiamo controllare per il penultimo oggetto e vedere se ad indice peso rimanente che profitto viene generato, se quel valore era presente nelle righe precendenti, allora non includo l'oggetto e ripeto il processo nella colonna prima ancora fino a quando non consumo totalemente il peso della saccetta generando così il risultato.

costo algoritmo O(nxw) n = n oggetti e w = weight