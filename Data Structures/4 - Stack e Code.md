Gli stack e le code sono insiemi/set dinamici dove l'elemento che viene rimosso dall'operazione Delete è predeterminato.

In uno *Stack* l'elemento cancellato è sempre l'ultimo: questo perché lo stack implementa lo scheda LIFO (Last-in, First-Out)
Gif dimostrativa:
<iframe src="https://miro.medium.com/max/800/1*kkK3EZNOzBsuwkDNvSVR9g.gif" border = 0, frameborder = 0, height=400, width=500></iframe>

In uno *Stack*, l'operazione d'Insert è detta "Push", mentre quella di Delete è detta Pop.
Lo stack ha un attributo chiamato top[S] che contieni l'indicatore all'ultimo elemento aggiunto nello stack. Questo è l'elemento che viene poi eliminato una volta che viene chiamata Pop, a meno che non vengo *inserito* un altro elemento, che in quel caso divento lui il nuovo top[S].
Per implementare uno Stack, possiamo usare un array di grandezza *n* a seconda di quanto vogliamo che sia la nostra capienza massima. Questo stack può contenere da 1 a *n* elementi.
Lo Stack è formato dagli elementi che vanno da 1 a top[S], che indica l'ultimo elemento inserito e quindi quello che è in cima.
Se top[S] = 0 allora vuol dire che lo stack è vuoto, non contiene elementi.
L'operazione *STACK-EMPTY* verifica se lo stack è vuoto.
Se cerchiamo di fare un Pop quando lo stack è vuoto abbiamo un **Underflow**.
Se cerchiamo di fare un Push quando lo staco è vuoto abbiamo un **Overflow**

Codice per le operazioni dello Stack:
![[Pasted image 20211121172558.png]]



In una ***coda***, l'elemento cancellato è sempre il primo che abbiamo inserito, lo schema si chiama FIFO (First-in, First--out).
"Video" dimostrativo:
![[P09U.mp4]]

L'operazione Insert è detta "*Enqueue*", ovvero "Incoda". L'operazione di Delete invece viene chiamato "*Dequeue*" ovvero "Scodare"(?). Come nella stack, anche queste operazioni non hanno bisogno di argomenti.
La coda a un inizio(head) e una fine (tail). Quando un elemento viene inserito nella coda, quello prende posto alla fine della coda e diventa la nuova tail.
L'elemento rimosso è sempre quello nell'head, che è quella che è rimasta più a lungo in attesa.

Implementazione di una coda su un Array, possiamo vedere come non abbiamo bisogno di spostare i nostri dati ma solo i puntatori:
![[Pasted image 20211121173441.png]]

Rapidamente, queste sono le operazioni che vengono effettuate sulla coda:
![[Pasted image 20211121173633.png]]
