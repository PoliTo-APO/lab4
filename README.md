# Laboratorio 4
In questo laboratorio si sviluppano i primi **programmi a oggetti**.
Gli argomenti su cui prendere confidenza sono:
- costruttori
- variabili d'istanza e di classe
- metodi
- notazione pubblico/privato
- getters e setters
- overriding operatori
- semplici relazioni tra classi

Gli ultimi due esercizi, invece, trattano l'argomento della **ricorsione**.

## Esercizio 1
Scrivere una classe che tenga il conto dei canestri fatti da una squadra di basket.

Tramite il metodo *add_match* deve essere possibile registrare una partita, dato il nome della squadra avversaria e il numeri di canestri fatti.
Il metodo *get_average* deve restituire la media di canestri fatti per partita.
Il metodo *get_teams* deve restituire una lista contente i nomi delle squadre contro cui si ha giocato.
Il metodo *get_summary* deve restituire una stringa che riporti il numero totale di canestri e la media di canestri fatti per partita.

Scrivere una funzione *main* che testi le funzionalità della classe sviluppata.

**Suggerimento**: sviluppare un'unica classe

## Esercizio 2
Scrivere una classe che rappresenti un documento d'identità.

Il costruttore deve accettare come parametro il nome e il cognome dell'intestatario e opzionalmente l'anno in cui il documento è stato rilasciato.
Se non specificato usare *2022* come valore di default.

Scrivere i getters per nome, cognome e anno di rilascio.

Scrivere il metodo *set_birth_year* che permetta registrare l'anno di nascita.
Se l'anno di nascita è maggiore dell'anno di rilascio l'anno di nascita deve essere impostato uguale all'anno di rilascio.
Scrivere un getter per ottenere l'anno di nascita.

Il costruttore deve definire un ulteriore attributo, rappresentante il numero documento.
Il numero documento deve incrementare di uno per ogni nuovo documento.
Il numero documento deve essere ottenibile tramite getter.

Scrivere una funzione *main* che testi le funzionalità della classe sviluppata.

**Suggerimento**: per aggiornare il numero documento si può usare una proprietà di classe
che tiene conto di quante volte il costruttore viene chiamato.

## Esercizio 3
Creare la classe *Player* che rappresenti un giocatore.
Il costruttore deve ricevere nome, cognome ed età del giocatore.
Questi valori devono essere ottenibili tramite getters.

Creare la classe *Team* che rappresenti una squadra.
Il costruttore deve ricevere il nome della squadra e la città a cui appartiene.
Questi valori devono essere ottenibili tramite getters.

Il giocatore deve avere un metodo *set_team* che registra la squadra in cui gioca il giocatore.
Il metodo riceve come parametro un oggetto della classe *Team*.
Scrivere un getter della classe giocatore che restituisca il *Team* del giocatore.
Se una squadra non è registrata deve restituire *None*.

La squadra deve avere un metodo *add_player* che riceve un oggetto di tipo *Player* da aggiungere alla squadra.
Il metodo *get_players* della squadra restituisce la lista di *Players* che giocano nella squadra.

Scrivere una funzione *main* che testi le funzionalità delle classi, associando i giocatori alle squadre e viceversa.

## Esercizio 4
Scrivere la classe *Matrix* che rappresenti una matrice 2x2.

Il costruttore deve ricevere come unico argomento una tabella rappresentante la matrice.
Scrivere due getters che restituiscano il numero di righe e il numero di colonne.

Implementare gli operatori *\_\_add\_\_*, *\_\_sub\_\_*, *\_\_mul\_\_* di modo che effettuino la somma, differenza e prodotto riga-colonna di due matrici.
Scrivere l'operatore *\_\_eq\_\_* di modo che sia possibile verificare l'uguaglianza di due matrici.

Implementare il metodo *\_\_str\_\_* per fornire una rappresentazione in stringa della matrice.

Scrivere una funzione *main* esegua operazioni tra oggetti della classe *Matrix* (*+*, *-*, *\**).
Testare anche l'operatore di confronto (*==*) e la rappresentazione in *str* provando a stampare un oggetto *Matrix*.


## Esercizio 5
Scrivere una funzione ricorsiva che accetti un intero *n* come parametro e restituisca la
somma di tutti gli interi da *1* a *n*. Esempio:
```
X: 4
Output: 10
Esercizio 2
```


## Esercizio 6
Scrivere una funzione ricorsiva che sia in grado d'implementare una funzionalità simile a
quella del ”Paint Bucket” (secchiello) presente negli editor d'immagini.

Data una matrice (l’immagine), contenete interi (colori di ciascun pixel),
un intero (nuovo colore) e una posizione (coordinate pixel di partenza),
il programma deve cambiare il colore all’insieme di tutti i pixel contigui aventi lo
stesso colore del pixel di partenza (e contenente lo stesso).

I pixel confinanti in un vertice sono considerati contigui.

```python
Immagine di partenza
1 1 1 1 1 1 1 1 1 1
1 1 1 1 0 4 1 1 1 1
1 1 1 0 0 4 0 1 1 1
1 1 1 0 0 4 0 1 1 1
1 1 0 0 0 4 0 0 1 1
1 0 0 0 0 4 0 0 0 1
1 1 1 1 1 4 1 1 1 1
1 1 3 3 3 3 3 3 3 1
1 1 1 3 3 3 3 3 1 1
2 2 2 2 2 2 2 2 2 2

Nuovo colore: 5
Posizione: (2,7) # (riga, colonna) partendo da 0

Immagine risultante
5 5 5 5 5 5 5 5 5 5
5 5 5 5 0 4 5 5 5 5
5 5 5 0 0 4 0 5 5 5
5 5 5 0 0 4 0 5 5 5
5 5 0 0 0 4 0 0 5 5
5 0 0 0 0 4 0 0 0 5
5 5 5 5 5 4 5 5 5 5
5 5 3 3 3 3 3 3 3 5
5 5 5 3 3 3 3 3 5 5
2 2 2 2 2 2 2 2 2 2

Nuovo colore: 6
Posizione: (4,6) # (riga, colonna) partendo da 0

Immagine risultante
5 5 5 5 5 5 5 5 5 5
5 5 5 5 0 4 5 5 5 5
5 5 5 0 0 4 6 5 5 5
5 5 5 0 0 4 6 5 5 5
5 5 0 0 0 4 6 6 5 5
5 0 0 0 0 4 6 6 6 5
5 5 5 5 5 4 5 5 5 5
5 5 3 3 3 3 3 3 3 5
5 5 5 3 3 3 3 3 5 5
2 2 2 2 2 2 2 2 2 2 

```

Assumendo
- ![#sail](https://placehold.co/15x15/ffffff/ffffff.png) `0`
- ![#sky](https://placehold.co/15x15/91e6e4/91e6e4.png) `1`
- ![#sea](https://placehold.co/15x15/0d15f0/0d15f0.png) `2`
- ![#boat](https://placehold.co/15x15/e2663d/e2663d.png) `3`
- ![#main-mast](https://placehold.co/15x15/c0a535/c0a535.png) `4`
- ![#sky-dawm](https://placehold.co/15x15/ffab98/ffab98.png) `5`
- ![#black-sail](https://placehold.co/15x15/000000/000000.png) `6`

le immagini sono le seguenti:

<img src="img/boat_day.png" width="200" />
<img src="img/boat_night.png" width="200" />
<img src="img/boat_night_black.png" width="200" />



