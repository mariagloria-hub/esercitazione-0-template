# Osservazioni — Esercitazione 0

Gruppo: C11

Componenti (MariaGloria, Morabito, mariagloria-hub; Nicole, Micheletti, micheletti5)

URL del repository (non condiviso)
https://github.com/mariagloria-hub/esercitazione-0-template.git

Abbiamo lavorato da due computer separati

Compilate insieme le osservazioni e discutete le risposte: entrambi dovete
saper spiegare le prove svolte.

## Step 1 — Hello World: compilazione ed esecuzione

Comando di compilazione:
gcc -std=c17 -Wall -Wextra -Wpedantic hello.c -o hello
Comando di esecuzione e risultato osservato:
./hello
Hello, computational physics!
Che cosa ho capito su sorgente ed eseguibile:
hello.c è il file sorgente mentre hello è l'eseguibile. Se modifico il messaggio da sorgente e avvio l'eseguibile senza ricompilare, dal terminale osserverò ancora la vecchia stampa
Output richiesto e comportamento del programma prima della modifica:
L'output richiesto è Hello, computational physics!
Prima della modifica da terminale vedrò questo messaggio.
Se eseguo il programma reindirizzando l'output su file, sul terminale non appare nulla, il messaggio è stato salvato dentro output.txt
Esito dopo la modifica e spiegazione della correzione:
Redirezionando l'output su file si invia lo standard output al file anziché a schermo. Invece, se ho fatto un'eventuale modifica al testo, ripristinando la frase originale in hello.c e ricompilando torno all'output atteso.
## Step 1 — Git

Quali file ho incluso nel commit e perché:
Ho incluso hello.c e osservazioni.md. Non ho incluso hello(l'eseguibile) perché i file binari compilati vengono generati sul codice sorgente e non vanno tracciati su git.
Come ho verificato che la versione provata sia presente su GitHub:
Ho confrontato l'identificativo alfanumerico dell'ultimo commit mostrato da git log--oneline nel terminale con il codice del commit visualizzaato su github
Che cosa ho osservato prima e dopo `git pull`, e perché non serve un nuovo clone:

## Step 2 — Eco: prima prova

Argomenti passati, comando e risultato:

Che cosa posso concludere:

## Step 2 — Eco: seconda prova

Argomenti passati, comando e risultato:

Che cosa ho capito su testo, conversioni e stampa:

## Step 2 — Risultato ed errori

Previsioni per l'esecuzione con argomenti validi e per quella con `dodici`:

Contenuto di `eco.txt`, messaggi nel terminale e codici di uscita osservati:

Come un controllo automatico può riconoscere un errore:

## Step 2 — Parametri e calcolo fisico

Quando serve ricompilare e quando basta cambiare gli argomenti:

## Step 2 — Git

Come riconosco nella cronologia i commit dei due step:

Come ho verificato che la versione finale sia presente su GitHub:
