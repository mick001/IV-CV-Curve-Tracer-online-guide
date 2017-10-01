# IV & CV Curve Tracer online guide
A set of operational guides for the IV &amp; CV curve tracer (V. 2.0)

---

## What to do

+ Leggere il [changelog](https://github.com/mick001/IV-CV-Curve-Tracer-online-guide/blob/master/changelog.md).
+ Ottenere il [file Excel](https://github.com/mick001/IV-CV-Curve-Tracer-online-guide/blob/master/TEST_CHECKLIST.xlsx) contenente le procedure di test da effettuare dopo ogni modifica sostanziale dell'applicazione al fine della verifica del corretto funzionamento della stessa.
+ Per leggere la guida operativa dell'applicazione, scorrere sotto.

---

## Cosa contiene questa guida

+ **Impostazione della working directory**
+ **Tracciamento curva IV/CV semplice**
+ **Tracciamento curve IV/CV con l’applicazione di tensioni di polarizzazione**

---

## Impostazione della working directory

Ad ogni avvio, il programma utilizzerà di default la cartella data sul desktop dell’utente come working directory. Se la cartella C:/users/user/Desktop/data esiste già, il programma utilizzerà tale cartella, se invece non esiste, il programma la creerà.

Si consiglia di selezionare la working directory subito dopo l’avvio dell’applicazione e prima di iniziare ad utilizzare le funzionalità del programma.

Se si desidera modificare la working directory, è necessario effettuare la seguente procedura:
1.	Cliccare sul controllo Working directory path posizionato nel general panel tab del general pane (figura 5.2).
2.	Selezionare la nuova working directory dalla finestra di dialogo.
3.	Cliccare su “Seleziona carella”.

![Figura 5.2](https://user-images.githubusercontent.com/13961654/31053219-e392ff34-a698-11e7-81b5-bbae22098eb9.png)

---

## Tracciamento curva IV/CV semplice

Una volta avviato il programma, per tracciare una curva IV oppure una curva CV senza l’utilizzo di sorgenti di polarizzazione (ossia eseguendo il solo ciclo for interno), la procedura operativa alla quale attenersi è la seguente:
1.	Si sceglie la sorgente di tensione principale (in questo caso tale sorgente sarà anche l’unica sorgente utilizzata) e si seleziona il corrispondente instrument tab. A titolo di esempio, si utilizza come sorgente di tensione principale lo strumento Keithley 6430.
2.	Si seleziona dal menu a tendina VISA resource name Keithley 6430 (mostrato in figura 5.3) l’indirizzo GPIB dello strumento. Per visualizzare una lista degli indirizzi GPIB e seriali individuati dal programma è possibile utilizzare il controllo nel tab VISA resources del general pane descritto nella sezione 4.2. In ogni caso, anche il controllo VISA resource name Keithley 6430 nell’Instrument tab dello strumento mostrerà gli indirizzi GPIB e seriali disponibili.

 
Fig. 5.3 Dettaglio Instrument tab del Keithley 6430

3.	Se lo strumento è in grado di funzionare sia da sorgente di tensione che di corrente, si seleziona la funzione DC volts. Ad eccezione dello strumento Yokogawa 7651, si è scelto di impedire a priori l’utilizzo degli strumenti come sorgenti di corrente e quindi, nel caso del Keithley 6430, non è necessario selezionare la funzione DC volts siccome è già selezionata di default.
4.	Si imposta la corrente massima erogabile dallo strumento tramite il controllo Current Compliance [A]. In figura 5.3 il limite di corrente è stato fissato pari a 10 mA.
5.	Si selezionano eventuali impostazioni aggiuntive, specifiche dello strumento (ad esempio: canale, range della tensione di output, ecc…).

Se si desidera tracciare una curva IV si eseguano le istruzioni ai punti 6, 7 e 8 saltando le istruzioni ai punti 9, 10 e 11 mentre se si desidera tracciare una curva CV, si saltino le istruzioni ai punti 6, 7 e 8.

6.	Si seleziona l’Instrument tab dello strumento scelto per l’utilizzo come amperometro. A titolo di esempio si utilizza lo strumento Keithley 6485.
7.	Si seleziona dal controllo VISA resource name Keithley 6485 (mostrato in figura 5.4) l’indirizzo GPIB dello strumento.

 
Fig. 5.4 Instrument tab del Keithley 6485

8.	Si selezionano eventuali impostazioni aggiuntive dello strumento per la misura: autorange, tempo di integrazione, filtri digitali, funzioni matematiche, ecc… Si noti che è possibile utilizzare (al momento in cui viene scritto questo manuale) fino a 5 strumenti di misura (4 amperometri e 1’LCR meter) contemporaneamente. Per configurare ogni singolo amperometro è necessario ripetere, per ogni strumento, i punti 6, 7 e 8.
9.	Si seleziona l’Instrument tab dello strumento Agilent 4263B. Si seleziona dal controllo VISA resource name Agilent 4263B (mostrato in figura 5.5) l’indirizzo GPIB dello strumento.

 
Fig. 5.5 Dettaglio Instrument tab Agilent 4263B
 
10.	Si seleziona il livello e la frequenza del segnale di test, i parametri che si intende misurare, il tempo di misura, e la lunghezza del cavo utilizzato. Nell’esempio in figura 5.5 si è scelto di utilizzare un segnale di test pari a 20 mV con frequenza 100 Hz per la misura della capacità parallela equivalente e del fattore di perdita. Si è inoltre ritenuta trascurabile la lunghezza del cavo. Opzionalmente si possono impostare le funzioni matematiche sui due parametri di interesse.
11.	Qualora si utilizzi una sorgente unipolare per effettuare il tracciamento della curva CV (essenzialmente, lo strumento ISEG NHQ223M oppure lo strumento CAEN DT540P), si colleghi il dispositivo di scarica al PC e si effettui un test di verifica del corretto funzionamento mediante il pulsante “TEST DISCHARGE DEVICE” presente nell’Instrument tab della sorgente unipolare dopo aver inserito l’indirizzo seriale del dispositivo nel controllo Discharge device VISA resource name (ISEG NHQ223M). A titolo di esempio, viene riportato l’Instrument tab dello strumento ISEG NHQ223M in figura 5.6. Qualora il test abbia avuto esito positivo, si fissa il tempo scelto per la scarica mediante il controllo Seconds to wait after discharge [s] e si può procedere oltre. Qualora il test abbia invece avuto esito negativo, si provi a disconnettere e riconnettere il dispositivo di scarica al PC e ripetere il test.

 
Fig. 5.6 Dettaglio Instrument tab ISEG NHQ223M: in rosso il sotto pannello impostazioni e test del dispositivo di scarica

12.	Si seleziona il tab DC Sweep. Nel sotto pannello Sweep voltage source settings si imposta come sorgente di tensione lo strumento Keithley 6430 (figura 5.5) mediante il controllo Set voltage source. Si imposta la tensione iniziale (Start [V]), la tensione finale (Stop [V]) e l’incremento/decremento in valore assoluto (Step [V]). Nell’esempio mostrato in figura 5.7, si è scelta una tensione iniziale di 0 V, una tensione finale di 100 V e un incremento di 10 V. Qualora si decida di fornire al programma i valori di tensione da applicare attraverso un file esterno, si inserisca il percorso del file nel controllo Vsource file (single column txt or csv file) e si selezioni la spunta Set Vsource using external file. Il file deve essere in formato .txt oppure .csv, avere una singola colonna di numeri e nessuno spazio in fondo.
 
Fig. 5.7 Dettaglio del tab DC Sweep

13.	Si seleziona il tempo di attesa (in millisecondi) tra l’applicazione di tensione e la misura di corrente mediante il controllo Waiting time nel sotto pannello Timing settings. Eventualmente si imposta anche un timeout (in secondi). Nell’esempio si è scelto di non applicare nessun timeout e quindi il controllo Timeout time [s] è stato impostato al valore di default -1 corrispondente all’assenza di timeout. 
14.	Nel sotto pannello Other settings si può assegnare un nome personalizzato al file .csv che il programma produrrà come output mediante il controllo Output file name. A tale nome sarà inserito il suffisso “_” e l’estensione .csv.
15.	Nel sotto pannello Current and voltage sensing settings (figura 5.7) si seleziona l’interruttore booleano corrispondente allo strumento prescelto per effettuare la misurazione: nell’esempio si imposta al valore TRUE il controllo Use Keithley 6485 (I2).
16.	Nel caso in cui si volesse effettuare una media delle misurazioni effettuate e registrare il solo valor medio, si imposti il controllo Average count (I2) ad un valore diverso da 1. Il valore immesso rappresenta il numero di misure che verranno effettuate ad ogni ciclo di misura e mediate per ottenere il valore complessivo. Si noti che la media è effettuata dal programma e non dallo strumento. Nell’esempio si è scelto di effettuare 10 misurazioni ad ogni iterazione e salvare quindi il solo valor medio.
17.	Opzionalmente è possibile cambiare il nome della variabile misurata che comparirà nel file .csv di output mediante il controllo corrispondente. Nell’esempio si può intervenire sul controllo I2 name.
18.	Se lo si desidera, è possibile aggiungere alcune note nel controllo Notes.
19.	Selezionare la spunta nel controllo Clear graphs before new sweep se si desidera eliminare dai grafici i dati di misure effettuate precedentemente (figura 5.8).
20.	 Cliccare sul pulsante START DOUBLE IV SWEEP (figura 5.8): se i parametri immessi sono coerenti con le caratteristiche degli strumenti scelti comparirà una finestra con il riassunto dei parametri selezionati e la richiesta di conferma (figura 5.9). Nel caso in cui fossero presenti incongruenze tra i parametri scelti per la misura e gli strumenti selezionati, comparirà un messaggio di errore con informazioni utili per la correzione degli errori rilevati. Fino a quando gli errori non sono stati corretti, non è possibile avviare la funzione di misura.
 
Fig 5.8 Pulsanti di comando tab DC sweep

 
Fig 5.9 Finestra di conferma avvio della funzione di misura

21.	Cliccare “OK” per avviare la funzione di misura, altrimenti cliccare su “Cancel” per tornare allo stato Idle.
22.	Cliccando su “OK” si avvia la funzione di misura e il programma esegue i cicli di misura richiesti. Sul grafico corrispondente allo strumento di misura utilizzato, compariranno, istante per istante, i valori rilevati dallo strumento (oppure la loro media se si è attivata la media aritmetica al punto 16 di questa procedura).
Qualora si intenda mettere in pausa la funzione di misura, si clicchi il pulsante PAUSE SWEEPING LOOP indicato in figura 5.8. Cliccando il pulsante, il programma terminerà l’iterazione corrente del ciclo for interno e metterà in pausa la funzione di misura: comparirà una finestra che richiederà se continuare oppure arrestare la funzione di misura.
Nel caso in cui si voglia arrestare la funzione di misura prematuramente, si clicchi il pulsante STOP SWEEPING LOOP. Cliccando tale pulsante, il programma uscirà dal doppio ciclo for annidato e ritornerà in stato Idle dopo aver riportato gli strumenti in uno stato noto. I dati di misura vengono, in ogni caso, salvati ad ogni iterazione.

---

## Tracciamento curve IV/CV con l’applicazione di tensioni di polarizzazione

Si ricorda che delle due sorgenti di polarizzazione disponibili, una sola è indipendente. La sorgente dipendente dipende dall’array lineare di tensioni definito per la sorgente indipendente. Utilizzando la nomenclatura dei controlli delle sorgenti di polarizzazione del tab DC sweep, nel seguito si chiamerà la sorgente indipendente Bias1 e la sorgente dipendente Bias2. I casi possibili sono i seguenti tre:
1.	Bias1 è utilizzata e Bias2 non è utilizzata. Si applica una singola polarizzazione (indipendente) al DUT.
2.	Bias1 è utilizzata e anche Bias2 è utilizzata: i valori di tensione applicati al DUT da Bias2 sono funzione dei valori di tensione applicati al DUT da Bias1. Sia Bias1 che Bias2 sono utilizzati, si applica quindi una doppia polarizzazione al DUT.
3.	Bias1 non è utilizzata e Bias2 è utilizzata: i valori di tensione applicati al DUT da Bias2 sono funzione dei valori di tensione che Bias1 dovrebbe applicare al DUT se fosse utilizzata. Ma Bias1 non viene utilizzata: si applica quindi una singola polarizzazione al DUT tramite Bias2. Mediante questo metodo è possibile applicare una polarizzazione che cresce/decresce, per esempio, esponenzialmente oppure in modo logaritmico. 
Per tracciare più curve IV/CV al variare di una o due tensioni di polarizzazione, la procedura operativa è la seguente:
1.	Si sceglie la sorgente di tensione principale e si seleziona il corrispondente Instrument tab. A titolo di esempio, si utilizza come sorgente di tensione principale nuovamente lo strumento Keithley 6430.
2.	Si seguono le istruzioni per il set-up dello strumento indicate nei punti 2, 3, 4 e 5 della procedura contenuta nella sezione 5.3.

A questo punto, tenendo in considerazione le tre modalità di utilizzo delle sorgenti di polarizzazione Bias1 e Bias2 si decide quante e quali sorgenti di polarizzazione utilizzare. Nel punto 3 viene effettuato il setting di uno strumento per applicare la polarizzazione indipendente (Bias1) mentre nel punto 4 viene effettuato il setting di uno strumento per applicare la polarizzazione dipendente (Bias2). Si scelga quali punti saltare coerentemente con il tipo di polarizzazione che si intende applicare al DUT.

3.	Si sceglie la sorgente di tensione Bias1 (polarizzazione indipendente) e si seleziona il corrispondente Instrument tab. In questo caso si seleziona lo strumento Yokogawa 7651. L’Instrument tab di tale strumento è raffigurato in figura 5.10. Si imposta il VISA resource name dello strumento mediante l’apposito controllo, il range di tensione nel quale lo si intende utilizzare (oppure si fissa tale controllo ad un valore arbitrario in volt e poi si sceglie l’autorange), e il limite di corrente massima erogabile. Nell’esempio in figura 5.10 il range di tensione è stato fissato a 10 V (lo strumento sarà in grado di erogare una tensione compresa tra -10 V e 10 V). Si è scelto infine di limitare la corrente erogabile a 1 mA.

 
Fig. 5.10 Instrument tab Yokogawa 7651

4.	Si sceglie la sorgente di tensione Bias2 (polarizzazione dipendente) e si clicca sull’Insrument tab corrispondente. Nell’esempio, si sceglie lo strumento TTi QL355TP. Nella figura 5.11 è raffigurato il corrispondente Instrument tab. Si imposta il VISA resource name dello strumento, il canale che si intende utilizzare, il comportamento dello strumento nel caso in cui la corrente superi il limite di corrente erogabile e si fissa la corrente massima erogabile (20 mA nella figura 5.11).

 
Fig. 5.11 Instrument tab TTi QL355TP 


Se si desidera tracciare più curve IV si eseguano le istruzioni ai punti 6, 7 e 8 della sezione 5.3 per il setup di uno o più amperometri, invece se si desidera tracciare una curva CV, si seguano le istruzioni ai punti 9, 10 e 11 della sezione 5.3 per il setup dello strumento Agilent 4263B.
5.	Si seleziona il tab DC Sweep. Nel sotto pannello Sweep voltage source settings si imposta come sorgente di tensione lo strumento Keithley 6430 mediante il controllo Set voltage source. Si imposta la tensione iniziale (Start [V]), la tensione finale (Stop [V]) e l’incremento/decremento in valore assoluto (Step [V]). Nell’esempio, in fig. 5.12, si è scelta una tensione iniziale di 0 V, una tensione finale di 10 V e un incremento di 0.5 V

 
Fig. 5.12 Tab DC sweep: dettaglio sotto pannelli

6.	Nel sotto pannello Single/double DC bias settings si seleziona la sorgente indipendente (Bias1) mediante il menu a tendina Bias1. Si sceglie la tensione di polarizzazione iniziale (Start bias [V]), la tensione di polarizzazione finale (Stop bias [V]) e l’incremento/decremento in valore assoluto (Step bias [V]). Nell’esempio si è scelto di utilizzare i valori 0 V, 0.5 V e 0.1 V rispettivamente. Se si è scelto di utilizzare anche la sorgente di polarizzazione dipendente (Bias2), si sceglie dal menu a tendina Bias2 la sorgente scelta al punto 4 e si definisce la formula per il calcolo della tensione di polarizzazione dipendente nel controllo Bias 2 formula y=f(x). Anche in questo caso è possibile predefinire l’array di tensioni da utilizzare per la sorgente principale e per la sorgente di polarizzazione indipendente e caricare i file mediante gli appositi controlli presenti nel tab DC sweep come descritto nella sezione 5.3.
7.	Si seguono le istruzioni indicate a partire dal punto 13 (incluso) nella sezione 5.3.
Anche in questo caso è possibile mettere in pausa oppure arrestare prematuramente la funzione di misura esattamente come descritto al fondo della sezione 5.3.

