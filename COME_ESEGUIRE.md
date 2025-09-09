# Come eseguire il progetto

Questo progetto è stato sviluppato in Jupyter Notebook e può essere eseguito facilmente tramite **Google Colab**, senza necessità di installare software in locale.

## Esecuzione con Google Colab

1. Clicca sul pulsante qui sotto per aprire direttamente il notebook:

[![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/davidetriboli/Progetto_Tesi_Triennale_illuminazione/blob/main/Dimensionamento_illuminazioneEsterna_RoccaDiSparafucile_Mantova.ipynb)

2. Una volta aperto in Colab:
   - Controlla che sia selezionato un runtime Python 3 (menù `Ambiente di esecuzione` → `Modifica tipo di ambiente di esecuzione` → `Python 3`).
   - Non è necessario installare librerie aggiuntive: Colab include già `numpy`, `scipy` e `matplotlib`.

3. Esegui le celle in ordine dall’alto verso il basso.

## Output attesi
- Calcolo delle potenze dei faretti.
- Grafici di confronto tra distribuzione dell'illuminazione ideale e reale.
- Dati numerici utili al dimensionamento illuminotecnico.

---

📌 **Nota**: il notebook utilizza dati geometrici (centroidi, normali) ottenuti da fotogrammetria. Se vuoi modificare la mesh o aggiungere nuovi faretti/superfici, aggiorna i file di input e rilancia il notebook.
