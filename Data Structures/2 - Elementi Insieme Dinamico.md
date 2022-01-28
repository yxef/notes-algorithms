In una tipica implementazione di un insieme dinamico, ogni elemento è rappresentato da un **oggetto**.
I campi di questo oggetto devono essere esaminati e manipolati.

Per alcuni tipi di strutture dati avremmo un campo *Chiave*, utilizzato per identificare l'oggetto. Questa chiave devono essere l'una diversa dall'altra, essendo un ID unico.

Inoltre l'oggetto può contenere *dati satelliti* che vengono spostati in altri campi dell'oggetto senza essere utilizzati dall'implementazione dell'insieme.

L'oggetto può avere campi che vengono manipolati dalle azioni e operazioni svolte sull'insieme.
Questi campi contengono **<u>dati</u>** o **<u>puntatori ad altri oggetti dell'insieme</u>**

Alcuni insieme dinamici presuppongono che le chiavi siano estratte da un insieme totalmente ordinato, come i numeri reali o l'insieme di tutte le parole secondo ordine alfabetico.
L'ordinamento totale ci consente di definire l'elemento minimo dell'insieme, per esempio, o di parlare del prossimo elemento più grande di un determinato insieme