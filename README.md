**# Analisi Numerica per il Dimensionamento Illuminotecnico di un Monumento Storico**
<p align="justify">
Questo progetto, sviluppato come parte della tesi di Laurea Triennale, si concentra sull'implementazione di un modello numerico preliminare per lo studio dell'illuminazione artificiale esterna. L'applicazione è stata la Rocca di Sparafucile a Mantova. L'intero dimensionamento è stato reso possibile a partire da un modello 3D fotogrammetrico della Rocca, ottenuto tramite un rilievo con drone DJI e processato nel software 3DF Zephyr. L'obiettivo è stato sviluppare un metodo per il dimensionamento dell'illuminazione artificiale esterna, tenendo conto del risparmio energetico e dell'effetto scenografico desiderato. L'intero modello matematico è stato ideato e sviluppato in modo autonomo, senza l'ausilio di software di illuminotecnica dedicati, per dimostrare come i principi del calcolo numerico possano essere applicati a un problema ingegneristico complesso. Questo lavoro getta le basi per future analisi in ambito di laurea magistrale.
</p>

Struttura del Sistema Lineare
<p align="justify">
Il modello numerico si basa sulla risoluzione di un sistema lineare della forma:


Ax=b

La matrice A rappresenta i contributi illuminotecnici dei faretti su ogni sotto-superficie. Il vettore 
mathbfx rappresenta la potenza in Watt necessaria per ciascun faretto. Il vettore 
mathbfb rappresenta gli illuminamenti desiderati sulle diverse superfici.
</p>

Metodologie
<p align="justify">
Per la risoluzione del problema, sono stati esplorati due approcci principali. Lo script di base è stato sviluppato in Python e caricato su Colab per stimare le potenze dei faretti.
</p>

Metodo di Gauss-Seidel
<p align="justify">
È stato utilizzato per risolvere il sistema lineare in un primo approccio. Questo metodo iterativo è particolarmente utile quando la matrice di coefficienti A è sparsa, cioè con molti zeri. Si basa sulla formula iterativa:


x 
(k+1)
 =Bx 
(k)
 +g

dove B=M 
−1
 N è la matrice di iterazione e 
mathbfg=M 
−1
 
mathbfb. La convergenza del metodo è stata verificata assicurando che il raggio spettrale della matrice B fosse minore di 1. Una prima valutazione ha mostrato che gli illuminamenti ottenuti non soddisfacevano la richiesta di uniformità, portando a un cambio di approccio.
</p>

Metodo dei Minimi Quadrati
<p align="justify">
Per superare i limiti di Gauss-Seidel, è stato applicato l'approccio ai minimi quadrati. Questo ha permesso di determinare le potenze per 16 faretti imponendo un illuminamento desiderato differenziato su 22 superfici (con valori tra 7 e 40 Lux). I risultati hanno mostrato potenze calcolate più accurate, con valori positivi e fisicamente interpretabili. La valutazione della soluzione ha confermato la coerenza tra gli illuminamenti calcolati e quelli reali richiesti, confermando la bontà del modello numerico e la sua efficacia in scenari realistici.
</p>

Immagini Rappresentative
<p align="justify">
Ecco una selezione di immagini che illustrano le fasi chiave del progetto. Le immagini sono di proprietà del Comune di Mantova e sono utilizzate esclusivamente per scopi accademici, con divieto di uso commerciale.
</p>

: Viste della mesh 3D del monumento, generata tramite fotogrammetria digitale (frontale e posteriore).

: Una vista del modello 3D che mostra il posizionamento e l'orientamento di alcuni dei corpi illuminanti per l'analisi.

: Dettaglio dei GCP e identificazione della normale uscente al faretto.

: Dettaglio della struttura del sistema lineare implementato.

Struttura della Repository
images/: Contiene le immagini chiave del progetto.

notebooks/: Contiene il notebook Jupyter Dimensionamento_illuminazioneEsterna_RoccaDiSparafucile_Mantova.ipynb con l'analisi numerica completa.

reports/: Include i report finali, le tabelle dei risultati e i grafici dell'analisi illuminotecnica.

README.md: Questo file.

Autore
Davide Triboli

Relatori
Relatore: Prof. Remo Sala

Co-Relatore: Ing. Eduardo Minieri

Ringraziamenti
Prof.ssa Anna Scotti: Per l’importante supporto metodologico sul metodo dei minimi quadrati, fondamentale per lo sviluppo di questa analisi.
