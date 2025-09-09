<h1>Analisi Numerica per il Dimensionamento Illuminotecnico di un Monumento Storico</h1>

<p align="justify">
Questo progetto, sviluppato come parte della tesi di Laurea Triennale a carattere propedeutico, si concentra sull'implementazione di un modello numerico per lo studio dell'illuminazione artificiale esterna applicato alla conservazione e valorizzazione della Rocca di Sparafucile a Mantova.
</p>
<p align="justify">
L’intero dimensionamento si basa su un modello 3D fotogrammetrico della Rocca, ottenuto tramite rilievo con drone DJI da me eseguito (drone prestato dal Prof. Sala) e processato in 3DF Zephyr.
</p>
<p align="justify">
L'intero modello matematico è stato ideato e sviluppato in modo autonomo, senza l'ausilio di software di illuminotecnica dedicati. L'obiettivo è stato dimostrare come i principi del calcolo numerico possano essere applicati a un problema ingegneristico complesso, partendo da zero e arrivando a una soluzione valida e verificabile. Questo lavoro getta le basi per future analisi in ambito di laurea magistrale, con particolare riferimento all’utilizzo della mesh 3D per analisi FEM finalizzate al restauro.
</p>
<p align="justify">
Per un'analisi approfondita del modello numerico, della metodologia e dei contributi, fare riferimento al documento <a href="Dettagli_progetto.md"> Dettaglio_progetto </a>
</p>

<h2>Immagini Rappresentative</h2>

<p align="justify">
Di seguito una selezione di immagini che illustrano le fasi chiave del progetto, dalla modellazione alla visualizzazione dei risultati dell'analisi illuminotecnica. 
<b>Le immagini sono di proprietà del Comune di Mantova e sono utilizzate esclusivamente per scopi accademici, con divieto di uso commerciale.</b>

Una vista del modello 3D che mostra il posizionamento e l'orientamento di alcuni dei punti luce.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/fa50b67d-9f79-477c-aa42-d3fdf7da5c31" />

Dettaglio 3 GCP e identificazione della normale uscente al faretto.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/c2a4c5fd-d056-4d5e-83c9-c6ad2ea5d5a3" />

Dettaglio GCP per perimetri e centroidi sottosuperfici.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/40570b45-312e-4162-8a97-c2cd00e5b34b" />

Struttura del sistema lineare implementato.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/d4dbf31d-3c37-42b6-8b14-e7caeefb8a6b" />

</p>


<h2>Obiettivi Specifici</h2>

<p align="justify">

- <b> Implementazione di un modello numerico: sviluppo di uno script in Python per stimare le potenze dei faretti necessarie a garantire un certo livello di illuminamento sulla mesh del monumento. </b>

- <b> Applicazione dei metodi numerici: utilizzare il metodo di Gauss-Seidel e quello dei minimi quadrati per la risoluzione del sistema lineare. </b>

- <b> Analisi dei risultati: </b>

⇒ Metodo di GS: verificare la coerenza tra le potenze calcolate e quelle presenti nel datasheet punto luce.

⇒ Metodo dei MQ (illuminazione uniforme): verificare la coerenza tra gli illuminamenti calcolati e quelli imposti (uniforme).

⇒ Metodo dei MQ (illuminazione reale): verificare la coerenza tra gli illuminamenti calcolati e quelli imposti (reale).

- <b> Utilizzo di GCP: Utilizzo dei Punti di Controllo a Terra (GCP), nel sistema di riferimento locale di 3DF Zephyr, per la definizione dei perimetri e dei centroidi delle sottosuperfici in cui è stata divisa la mesh iniziale; per la definizione delle coordinate 3D e delle normali dei punti luce. Informazioni geometriche essenziali per il dimensionamento illuminotecnico. </b>
</p>

<h2>Metodologia</h2>

<p align="justify">
Il dimensionamento illuminotecnico è stato risolto come un sistema lineare Ax = b. La metodologia si basa su un approccio geometrico semplificato, utile per ottenere un ordine di grandezza delle potenze richieste tali da garantire un certo illuminamento imposto sulla superficie del monumento.
</p>

<p align="justify">
Il modello in sintesi:
</p>
<ul>
<li>La matrice A (lux/Watt) descrive l'effetto in termini di illuminamento di ciascun faretto su ogni punto di interesse della superficie del monumento. Ogni punto di interesse è rappresentato dal centroide della sotto-superficie.</li>
<li>Il vettore 
x rappresenta la potenza in Watt necessaria per ciascun faretto.</li>
<li>Il vettore 
b rappresenta gli illuminamenti desiderati sulle diverse superfici.</li>
</ul>

<h3>Metodo di Gauss-Seidel</h3>

<p align="justify">
È stato utilizzato per risolvere il sistema lineare in un primo approccio. Questo metodo è particolarmente utile quando la matrice A è sparsa. La convergenza del metodo è stata verificata assicurando che il raggio spettrale della matrice di iterazione B fosse minore di 1.
</p>

<h3>Metodo dei Minimi Quadrati</h3>

<p align="justify">
Successivamente, per superare i limiti di Gauss-Seidel, è stato applicato l'approccio ai minimi quadrati. Questo ha permesso di determinare le potenze per 16 faretti imponendo un illuminamento desiderato differenziato su 22 superfici. In seguito, la valutazione della soluzione ha mostrato che gli illuminamenti calcolati erano coerenti con quelli reali richiesti, confermando la bontà del modello numerico.
</p>

<h2>Conclusioni</h2>

<p align="justify">
Di seguito le immagini di output fondamentali del progetto, che riassumono i risultati chiave dell'analisi illuminotecnica.

Grafico degli illuminamenti - Metodo ai minimi quadrati 1

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/370b4c3a-707a-451f-a18e-0434ebb2e01c" />

Grafico degli illuminamenti - Metodo ai minimi quadrati 2

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/0f04f1df-ebbc-4a6b-8f9a-1356fa26be88" />

</p>
<h2>Autore</h2>

Davide Triboli

<h2>Relatori</h2>

Relatore: Prof. Remo Sala

Co-Relatore: Ing. Eduardo Minieri

<h2>Ringraziamenti</h2>

Prof.ssa Anna Scotti: Per l’importante supporto metodologico sul metodo dei minimi quadrati, fondamentale per lo sviluppo di questa analisi.

<h2>License</h2>

See <a href="LICENSE.md"> License. </a>

<h2>Struttura del repository</h2>
La repository è organizzata come segue:

Progetto_Tesi_Triennale_illuminazione/  
├─ <a href="Dimensionamento_illuminazioneEsterna_RoccaDiSparafucile_Mantova.ipynb"> Codice</a>: Codice impiegato per il dimensionamento.  
├─ <a href="README.md"> Readme</a>: Questa descrizione.  
├─ <a href="LICENSE.md"> License</a>: Licenza d’uso del progetto.  
├─ Dettaglio/  
│  └─ <a href="Dettagli_progetto.md"> Dettagli_progetto</a>: Documento descrittivo tecnico-metodologico.  
└─ COME_ESEGUIRE.md  
