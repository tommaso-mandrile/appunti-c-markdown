# Il linguaggio C

Il linguaggio C fu originariamente sviluppato da Dennis Ritchie
presso i Bell Labs della AT&T tra il 1969 e il 1973, con lo scopo
di utilizzarlo per la stesura del sistema operativo UNIX.

Quello che successe dopo era inaspettato e rivoluzionario:
divento un linguaggio general purpose che abbatteva molte barriere
del tempo e aveva una efficienza senza pari.

### "Hello world"

Eccovi l'esempio di Hello world che si trova direttamente nel libro
del C, scritto dagli autori del linguaggio stesso:

``` C
#include <stdio.h>
    
int main() { 
   printf("Hello world!\n");
   return 0;
}
```

Qui di seguito lo stesso codice, ma con alcuni commenti

``` C
// include è la direttiva al compilatore per includere le librerie
// quando il nome della libreria è chiuso fra <> significa che la
// libreria è di sistema. 
//
// Le librerie personali si includono tramite doppi apici ""
#include <stdio.h>

// int main è il punto di ingresso del nostro programma
// in questa funzione si entra appena si avvia il programma
// compilato
int main() { 
   printf("Hello world!\n");

   // se è andato tutto bene, si ritorna 0, altrimenti un 
   // qualsiasi valore diverso da 0 permetterà di segnalare
   // un errore
   return 0;
}
```

## La funzione `printf`

la funzione `printf` permette di stampare a video una stringa formattata. La notazione è formata
da alcuni simboli che servono per stampare variabili. 

| Simbolo | Significato
| ------- | ------------
| `%c` | Carattere
| `%d` | Numero decimale intero
| `%s` | stringa
| `%f` | Floating point number (numero con la virgola)

Andiamo subito con esempi pratici

``` C
int number = 5;
printf("il doppio di %d è %d", number, number * 2);

char symbol = '|';
printf("il carattere 'pipe' è %c", symbol);

float pi = 3.14;
printf("il pi greco si approssima con %f", pi);
```

# La funzione `scanf`
la funzione `scanf` permette di leggere in input dei valori di diverso tipo, partendo da un 
modo simile alla funzione `printf`.

``` C
int number;
printf("Inserisci un numero:\n");
scanf("%d", &number);
printf("Hai letto %d", numero);

int numero1, numero2;
printf("Inserisci due numeri separati da un trattino\n");
scanf("%d-%d", &numero1, &numero2);
printf("Hai letto %d e %d separati da un trattino", numero1, numero2);
```

