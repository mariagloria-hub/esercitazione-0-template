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


"Ho verificato la correttezza del commit confrontando l'hash visualizzato su GitHub con l'output di git log --oneline dal terminale!"

Quando ricevo una modifica da remoto tramite github perché non è necessario eseguire di nuovo git clone? Non è necessario perché git clone serve solo la prima volta per scaricare l'intero repository e inizializzare la struttura di tracciamento .git sul mio computer. Una volta stabilita la connessione tra la cartella locale e il remoto (origin), per scaricare i nuovi commit e aggiornare i file basta usare git pull. Eseguire un nuovo clone creerebbe una cartella duplicata inutile.

Quali file ho incluso nel commit e perché:
Ho incluso i file hello.c e osservazioni.md. Il file hello.c contiene il codice sorgente C necessario per la compilazione ed esecuzione del programma. Il file osservazioni.md contiene la documentazione e le risposte alle domande dell'esercitazione. Non ho incluso l'eseguibile hello perché i file binari si ricostruiscono dal sorgente e non vanno tracciati con Git.
Come ho verificato che la versione provata sia presente su GitHub:
Ho aperto la pagina del repository su GitHub tramite browser e ho confrontato l'identificativo alfanumerico(hash) dell'ultimo commit con l'output del comando git log --oneline -5 eseguito dal mio terminale locale. Ho inoltre aperto i file hello.c e osservazioni.md direttamente sull'interfaccia web per confermare che il codice e il testo corrispondessero a quelli locali.
Che cosa ho osservato prima e dopo `git pull`, e perché non serve un nuovo clone:
Prima di eseguire git pull, la modifica apportata via browser al file osservazioni.md non era visibile sul file locale presente sul mio computer. Dopo aver eseguito git pull, Git ha scaricato il nuovo commit dal remoto e ha aggiornato automaticamente il file locale.
Non serve eseguire di nuovo git clone perché la copia locale è già collegata al repository remoto origin; git pull serve proprio a sincronizzare i nuovi commit mantenendo intatta la struttura e la cronologia locale.

## Step 2 — Eco: prima prova

Argomenti passati, comando e risultato:
./eco ciao 12 3.5
ciao 12 3.500000
Che cosa posso concludere:
I tre argomenti vengono letti dalla riga di comando. argv[0] contiene la stringa ./eco (nome dell'eseguibile), argv[1] contiene "ciao", argv[2] viene convertito da stringa ad intero tramite atoi (ottenendo 12), e argv[3] viene convertito da stringa a double tramite atof (stampato come 3.500000 grazie alla specifica %.6f). Il programma richiede argc == 4 perché conta sia il nome del programma sia i tre argomenti passati dall'utente.
## Step 2 — Eco: seconda prova

Argomenti passati, comando e risultato:
./eco 0012 12 1.25e1
0012 12 12.500000
Che cosa ho capito su testo, conversioni e stampa:
Se inviato come primo argomento (stringa), 0012 viene mantenuto inalterato con i suoi zeri iniziali.
Se inviato come secondo argomento (convertito in int), la conversione numerica elimina gli zeri iniziali non significativi.
Il valore 1.25e1 espresso in notazione scientifica viene convertito in un numero reale 12.5 e successivamente rappresentato con 6 cifre decimali (12.500000).
Per passare un testo contenente spazi come un singolo argomento (es. "ciao mondo") occorre racchiuderlo tra virgolette doppie nel terminale.
## Step 2 — Risultato ed errori

Previsioni per l'esecuzione con argomenti validi e per quella con `dodici`:
Con argomenti validi il risultato finisce dentro eco.txt, il terminale rimane silenzioso e il codice di uscita è 0. Con la stringa dodici, il programma gestisce l'errore: manda il messaggio di errore sul canale di errore standard (stderr) che appare a schermo sul terminale, mentre eco.txt rimane vuoto e il codice di uscita restituito è diverso da zero.
Contenuto di `eco.txt`, messaggi nel terminale e codici di uscita osservati:
- Prima prova (./eco ciao 12 3.5 > eco.txt): eco.txt contiene ciao 12 3.500000. Il terminale non mostra nulla. echo $? restituisce 0.
- Seconda prova (./eco2 ciao dodici 3.5 > eco.txt): eco.txt risulta vuoto. Sul terminale viene stampato l'errore: Il secondo argomento deve essere un intero in base 10. echo $? restituisce 2.
La redirezione > cattura unicamente lo standard output (stdout), lasciando intatto lo standard error (stderr) verso il terminale.
Come un controllo automatico può riconoscere un errore:
I sistemi di correzione automatica leggono il valore di ritorno del programma (echo $? o valore restituito dal main). Se questo valore è 0, l'esecuzione si considera completata correttamente; se è diverso da 0, il test viene contrassegnato come fallito.
## Step 2 — Parametri e calcolo fisico

Quando serve ricompilare e quando basta cambiare gli argomenti:
Quando serve ricompilare e quando basta cambiare gli argomenti:
Per variare un parametro di calcolo (come un passo temporale, un intervallo d'integrazione o una costante fisica), è sufficiente passare un valore differente sulla riga di comando senza ricompilare il codice. La ricompilazione si rende necessaria solo quando occorre modificare l'algoritmo o la formula matematica implementata nel sorgente C.
## Step 2 — Git

Come riconosco nella cronologia i commit dei due step:
I due step si distinguono tramite i messaggi associati ai commit leggibili con `git log --oneline`: il primo step è tracciato dal commit per la creazione ed esecuzione di `hello.c`, mentre il secondo step è associato ai commit contenenti `eco.c`, `eco2.c`.
Come ho verificato che la versione finale sia presente su GitHub:
Ho aperto la pagina del repository dal browser su GitHub e verificato che l'identificativo hash dell'ultimo commit in alto coincida con quello restituito da `git log --oneline -1` sul terminale locale.