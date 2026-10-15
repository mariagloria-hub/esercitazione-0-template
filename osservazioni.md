# Osservazioni — Esercitazione 0

Gruppo: C11

Componenti (MariaGloria Morabito, mariagloria-hub; Nicole Micheletti, micheletti5)

URL del repository
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
hello.c è il file sorgente, un file di testo scritto in linguaggio C che il computer non può eseguire direttamente; invece, hello è l'eseguibile, il file binario generato dal compilatore gcc, contenente le istruzioni in linguaggio macchina che la CPU può eseguire direttamente. Se modifico il messaggio da sorgente e avvio l'eseguibile senza ricompilare, dal terminale osserverò ancora la vecchia stampa, perché è come se stessi ancora eseguendo la vecchia versione del programma, infatti, il file eseguibile non si aggiorna da solo quando modifico il file .c, per aggiornarlo è necessario ricompilare il sorgente.

Quando ricompilo il compilatore legge la nuova versione del file sorgente, la traduce in linguaggio macchina e sovrascrive il vecchio eseguibile. Dopo la ricompilazione l'eseguibile conterrà le nuove istruzioni.

Per quanto riguarda la domanda come distinguo ciò che stampa il programma da ciò che mostra il terminale e cosa osservo se eseguo aggiungendo  > output.txt  : il terminale mostra sia l'output prodotto dai programmi creati (lo standard output o stdout), sia messaggi di sistema o prompt di shell. Quando eseguo il programma reindirizzando l'output su file, a schermo non compare più la stampa del programma, l'output viene scritto all'interno del file output.txt, infatti, redirezionando l'output su file si invia lo standard output al file anziché a schermo. Se apro il file output.txt, vedrò che contiene esattamente la stringa stampata dal programma. Questo dimostra che il messaggio appartiene allo standard output generato direttamente dall'eseguibile, a differenza dei messaggi della shell. 

Output richiesto e comportamento del programma prima della modifica:
L'output richiesto è "Hello, computational physics!"
Prima della modifica, eseguendo make check il sorgente veniva compilato correttamente senza errori, ma l'esecuzione dell'eseguibile non stampava nulla a schermo a causa del TODO presente all'interno della funzione main.

Esito dopo la modifica e spiegazione della correzione:
Dopo aver modificato il file hello.c inserendo la chiamata alla funzione printf("Hello, computational physics!\n"); all'interno del main,
eseguendo nuovamente make check, il programma stampa a schermo la frase richiesta seguita dal ritorno a capo.


## Step 1 — Git

Risposte alle domande del README
Che differenza c'è fra salvare un file, creare un commit e fare push?
Quando salvo un file in emacs sto scrivendo le modifiche dal programma di testo al disco fisso del computer. Git non ha ancora registrato né tracciato questa modifica. Creare un commit con git commit significa creare un'istantanea locale dello stato del progetto nel database di Git sul computer. Resta esclusivamente sul mio dispositivo. Fare git push, invece, significa inviare i commit creati localmente al repository remoto ospitato su GitHub, sincronizzando il cloud con il mio computer.

Quali modifiche mostra git diff? Quali file occorrono a un compagno per ricompilare il programma sul proprio computer?
git diff mostra le differenze riga per riga tra i file attualmente salvati sul disco e l'ultima versione registrata, ossia le modifiche non ancora preparate per il commit.
File necessari per ricompilare: a un compagno servono solo i file sorgente (hello.c), ed eventuali file di "documentazione" (osservazioni.md, README.md). Gli eseguibili (hello) e i file oggetto (.o) invece non vanno inviati a Git.

Come puoi verificare che su GitHub ci sia proprio la versione provata?
Aprendo la pagina del repository su GitHub nel browser, posso controllare l'hash identificativo dell'ultimo commit su GitHub e confrontarlo con l'output di git log --oneline -5 sul terminale: l'identificativo dovrebbe essere identico.
Inoltre, posso cliccare sui file hello.c e osservazioni.md direttamente nell'interfaccia di GitHub per verificare che il testo corrisponda a quello presente sul computer.

Quali file ho incluso nel commit e perché:
Ho incluso hello.c e osservazioni.md. Non ho incluso hello(l'eseguibile) perché i file binari compilati vengono generati sul codice sorgente e non vanno tracciati su git.
Come ho verificato che la versione provata sia presente su GitHub:
Ho confrontato l'identificativo alfanumerico dell'ultimo commit mostrato da git log--oneline nel terminale con il codice del commit visualizzato su github.

Verificato che l'hash del commit su github corrisponde a quello locale
Che cosa ho osservato prima e dopo `git pull`, e perché non serve un nuovo clone: Prima del git pull la modifica fatta online non era presente sul pc locale. Dopo il git pull, il file si è aggiornato con la nuova riga. Non serve un nuovo clone perché git pull scarica e integra solo i nuovi commit da remoto aggiornando la copia locale già esistente.
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
