# Suggerimenti operativi

- Quando abbiamo a che fare con array di strutture, dobbiamo tenere a mente che i nostri
  array non sono allocati dinamicamente, quindi dobbiamo tenere una variabile da parte per
  tenere il conto di quanti elementi su tutti quelli possibili sono stati caricati (in
  maniera simile come quando per le stringhe usiamo un carattere terminatore)
- Gli algoritmi di ordinamento che studiamo vengono chiamati "algoritmi di ordinamento per
  confronti": questo perché basano il loro intero funzionamento su confronti (`x < y`) e
  conseguenti scambi sulla base del risultato di essi
- Le funzioni `swap`, `hasLessHeight` e `hasLessWeight` possono essere riutilizzate negli
  algoritmi di ordinamento che andrete a implementare (Si richiede di ordinare sia per peso
  che per altezza, riutilizzate il codice!)
