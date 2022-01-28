## Hashing e Tabella Hash

Una tabella Hash è un array associativo, o [[1 - Introduzione|Dizionario]], usato per mettere in corrispondenza una chiave con un dato valore.

Per ricercare in una tabella hash utilizziamo **l'hashing**, una tecnica che elaborando un certo input con delle formule artimetiche, ottiene uno specifico output discreto, che permette di muoversi e accedere alla struttura dati in modo diretto con O(1) tempo sotto casi ragionevoli e O(n) nel worst case.

Le hash table vengono implementate su array, data lo loro capacità di indirizzamento diretto che permette di accedere ad un elemento in O(1). Nelle hash table viene calcolato l'indice d'indirizzamento dalla chiave dell'elemento.

È possibile che due chiavi diano lo stesso risultato una volta calcolate, quando questo accade viene creata una "collisione", ovvero stiamo cercando di inserire un elemento in una cella già occupata da un altro. Per risolvere questo problema abbiamo diversi sistemi, come l'utilizzo di linked list oppure semplicemento spostando avanti di 1 o di 2^i salti nell'array fino a quando non troviamo un spazio libero.

**Tabella ad indirizzamento diretto** T, ogni chiave nell'universo delle chiavi corrisponde ad un indice della tabella:
![[Pasted image 20211128122836.png]]

