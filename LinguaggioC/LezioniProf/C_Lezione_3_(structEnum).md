## I tipi primitivi

Si definisce tipo primitivo un tipo nativo di un determinato linguaggio di programmazione.
Per il C ne abbiamo già visti parecchi (`int`, `char`, `float`) anche se ce ne sono
molti altri (`long`, etc...)

## Eh ma i vettori?

No, i vettori non sono tipi primitivi. Anzi, tutto ciò che può essere costruito con un tipo primitivo non è un tipo primitivo (quindi ad esempio anche le `struct` che andremo a vedere fra poco)

## Le strutture in C

Il C mette a disposizione l'istruzione `struct` che consente di definire una variabile come un gruppo di variabili anche di tipo diverso.

La definizione di una struttura avviene nel modo seguente:
``` C
/**
 * Questa è la libreria delle stringhe dell'esercitazione precedente.
 */
#include "string.h"

#include <stdio.h>

typedef struct {
  /**
   * name of the person
   */
  char name[MAX_LENGTH];
  
  /**
   * age of the person
   */
  int age;

  /**
   * weight in kg of the person
   */  
  float weightKg;

  /**
   * height in cm of the person
   */  
  int heightCm;
} Person;

int main() {
  Person antonio;

  strcpy(antonio.name, "Antonio");
  antonio.age = 17;
  antonio.weightKg = 84.37;
  antonio.heightCm = 183;

  // defined below!
  printPerson(antonio);
}
```

In altre parole, quello che sta dentro la definizione di struttura non è la dichiarazione
di una variabile, ma indica che quando si dichiara una variabile struttura si dichiarano
automaticamente le quattro variabili che hanno il nome della variabile seguito da

- .name -> stringa
- .age -> `int`
- .weightKg -> `float`
- .heightCm -> `int`

È possibile passare una intera struttura a una funzione: basta che la definizione di struttura
preceda la definizione della funzione.

Nella funzione la definizione del parametro è uguale alla dichiarazione di una variabile, come
sempre.

``` C
/**
 * printPerson prints the details of a person struct.
 */
void printPerson(Person p) {
  printf(
    "Lui è %s, ha %d anni, è alto %d cm e pesa %f kg\n",
    p.name,
    p.age,
    p.heightCm,
    p.weightKg
  );
}
```

## I tipi `enum`

Gli enumerated types contengono un elenco di costanti che possono essere
indirizzate con valori `int`.

Per dichiarare tali tipi si utilizza `enum`; vengono dichiarati i tipi e le 
variabili come nell'esempio che segue:

``` C
// Quando vengono definiti, i valori dell'enum assumono valori crescenti da
// 0 di default
typedef enum {
  RED,    // = 0
  YELLOW, // = 1
  GREEN,  // = 2 
  BLUE   // = 3
} Color;

// Si possono anche definire dei valori da agganciare a ogni enum
// Ad esempio qui facciamo partire da 1 anziché da 0 i valori
typedef enum  {
  MONDAY = 1,
  TUESDAY = 2,
  WEDNESDAY = 3,
  THURSDAY = 4,
  FRIDAY = 5,
  SATURDAY = 6,
  SUNDAY = 7
} DayOfWeek;

int main() {
  Color rosso = RED;
  printf("RED = %d\n", rosso); // "RED = 0\n"

  DayOfWeek lunes = MONDAY;
  printf("LUNEDI' = %d", lunes);
}
```
