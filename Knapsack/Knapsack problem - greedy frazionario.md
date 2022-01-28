Abbiamo n oggetti
ogni oggetto ha un profitto associato ed un peso

abbiamo uno zainetto con una certa capacità e dobbiamo scoprire quali oggetti mettere nello zainetto per massimizzare il profitto.

assumiamo che possiamo prendere frazioni

Per risolvere questo problema di ottimizzazione dobbiamo inserire gli oggetti che hanno il profitto per peso più alto, che calcoliamo dividento profitto per il peso e poi selezioniamo i valori più alti inserendoli il più possible. nel nostro zaino array inseriamo un numero x tale che è compreso tra 0 e 1 per indicare la quantità di oggetto che andiamo a prendere, inserendo 1 se lo prendiamo completamente, frazioni se ne prendiamo solo una parte e 0 se lo ignoriamo.

moltiplicando i valori nell'array per il rispettivo peso ed andandoli a sommare, dimostriamo che abbiamo inserito fino a riempire il nostro zaino.

Per calcolare il profitto totale, moltiplichiamo il contenuto dell'array per il profitto singolo, la somma sarà il risultato