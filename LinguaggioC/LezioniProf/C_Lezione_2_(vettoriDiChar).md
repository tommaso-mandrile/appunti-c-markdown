## I vettori di caratteri

In C le stringhe si rappresentano come vettori di `char` che terminano con
il carattere `\0`.

``` C
#include <stdio.h>

// definisco una costante a livello di compilatore
#define MAX_LENGTH 40

int main() {
  // dichiaro una stringa di lunghezza massima
  // 40 caratteri (MAX_LENGTH)
  char string[MAX_LENGTH];

  printf("Inserisci una stringa in input:\n");
  scanf("%s", string);

  printf("Hai inserito \"%s\" in input\n", string);
}
```
