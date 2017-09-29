# Changelog dell'IV & CV Curve Tracer

### DISCLAIMER
Questo changelog era inteso per uso personale e quindi non è stato mantenuto in modo "eccellente". Siccome può comunque essere utile, ho deciso di inserirlo nella documentazione.

---

### Questo changelog copre parte dei cambiamenti effettuati dalla versione 1.0 alla versione 2.0.

05/09/17
+ Accorpate funzioni IV DC sweep e CV DC sweep in una unico tab.

06/09/17
+ Sistemato bug nella generazione del report.
+ Aggiunto file .ini alla configurazione di build.
+ Risolto problema localizzazione e utilizzo virgola anzichè punto come separatore decimale nell'eseguibile.
+ Spostato segnale acustico a inizio sweep nello stato IV sweep.
+ Aggiunta opzione "Inline" a tuttle le text box presenti nel Front Panel.

07/09/17
+ Sistemato bug progress bar 0-100%.
+ Introdotta variabile globale "Single sweep" per segnalare l'utilizzo del solo ciclo interno.
+ Cambiata subVI calcolo parametri start stop e step della sorgente di bias.
+ Introdotti controlli per i grafici interattivi del primary e secondary parameter.
+ Aggiornato report con il contenuto della nuova variabile globale "Single sweep".
+ Sistemato bug step negativo: nello stato "Pre sweep checks" se il parametro step (o lo step bias) è uguale a zero il programma indica la presenza di un errore e non fa iniziare la sweep.
+ Sistemato bug update grafico corrente Keithley 6485
+ Testato dispositivo di invio segnale di scarica nel tracciamento di una curva CV con sorgenti unipolari: funziona.
+ Verificato funzionamento del doppio ciclo con solo bias dipendente funzione dei parametri Start bias, Stop bias e Step bias.
+ Fatto foglio Excel con procedure automatizzate di test.

08/09/17
+ Resi inutilizzabili i pulsanti about e refresh available visa resources durante l'esecuzione della funzione di misura.
+ In presweep checks e report se timeout == -1 ora compare "timeout: None".
+ Se scelgo BIAS1 == None ora sia nel report che nei check pre-sweep compare "Bias1: None".
+ Cambiato default setting dell'ISEG (current limit, autostart, Vramp).
+ Sistemato bug display limite corrente ISEG e Yokogawa.
+ Valore default limite corrente/tensione yokogawa modificato a 1 mA/V.
+ Scambiate posizioni di I1 e I2 negli headers.
+ Se utente interrompe sweep ora compare nel report la nota relativa all'interruzione.
+ Aggiunta subVI che determina la sorgente di tensione utilizzata.
+ Rinominate le subVIs.
+ Aggiunto al progetto subVI "scarica condensatori" per avvio dispositivo di invio segnale di scarica.
+ Effettuato test di scarica durante tracciamento curva CV con condensatore ceramico.
+ Limitato l'effettuamento della scarica alla condizione (sorgente di tensione == ISEG e Use Agilent 4263B == True).


09/09/17
+ Aggiunte istruzioni Keithley 6487 e ISEG.
+ Aggiunta VI richiesta status ISEG.
+ Aggiunto stato test discharge device.
+ Aggiunto codice test dispositivo di scarica in instrument tab ISEG.

10/09/17
+ Bug fix. Ora, quando si seleziona bias1 == None, nella preview prima della sweep viene visualizzato '-' nella voce "Bias1".
+ Il programma AVVISA che avverrà la scarica a fine ciclo durante l'utilizzo contemporaneo di ISEG NHQ223M e Agilent 4263B.
+ Implementati controlli pre-sweep su bias e sorgente principale.
+ Aggiunto tempo di scarica regolabile.

11/09/17
+ Sistemato bug rampa spegnimento Keithley 6487.
+ Aggiornato controllo voltage ramp Keithley 6487 e spostato nell'instrument tab dello strumento.
+ Testato test dispositivo di scarica.

12/09/17
+ Migliorato documentazione subVIs.
+ Eliminata case structure di verifica che bias1, bias2 e vsource siano diversi tra loro.
+ Aggiunta attesa 50ms dopo ciclo di misura.
+ Aggiunto CAEN 5470P.
+ Sistemato bug nella chiusura dello strumento Keithley 6430.
+ Aggiunto test discharge device su instrument tab CAEN 5470P.
+ Corretto errore che non permetteva a ISEG e TTI di andare a zero.
+ Sistemati nuovi grafici.

13/09/17
+ Aggiunto ETA (calcolo + indicatore).
+ Aggiunto indicatore IMON CAEN 5470P solo per utilizzo come Vsource.
+ Aggiunte info su open correction in instrument tab Agilent 4263B.
+ Corretto bug che non permetteva il rilevamento di errori dell'Agilent 4263B.
+ Aggiunto segnale di test pari a 20 mV driver nel driver dell'Agilent 4263B.
+ Aggiunta possibilità di impostare lunghezza cavo Agilent 4263B.
+ Aggiunto blocco che disabilita l'output del CAEN 5470P prima di chiudere la connessione con lo strumento.
+ Aggiunto stato "Print plots".
+ Ora dopo la sweep il programma carica i dati direttamente sulla scheda per la visualizzazione.
+ Aggiunta ricerca stampanti disponibili e scelta stampante per la stampa.
+ Aggiunto pulsante di stampa grafici.

14/09/17
+ Aggiunta possibilità di impostare una serie di tensioni sia a vsource che a vbias via file esterno.
+ Aggiunta autorange al driver Yokogawa 7651 e nell'applicazione.
+ Modificati limiti tensione applicabile a CAEN: la tensione minima è ora 10V.
+ Fatti test standardizzati (test del foglio excel) e correzioni minori.

15/09/17
+ Testato funzionamento Yokogawa come generatore di corrente (Bias) nel tracciamento di curve IV di BJT.
+ Eliminato la possibilità di utilizzare il Keithley 6430 come sorgente di corrente.

---
