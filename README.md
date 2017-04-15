# Scrivere una Tesi in Latex
(Version 0.1, Last Update 20-03-2017)

### Guida per scrivere una Tesi in Latex, con tanto di Template in ITA & ENG e istruzioni per adattare l'immagine di copertina alla vostra Università (Default: Politecnico di Torino).

Questa Repository ha lo scopo di spingere ed aiutare gli studenti ad utilizzare [Latex](https://www.latex-project.org/), per sviluppare più agilmente la propria Tesi, Paper Accademici o perchè no, Libri.

Prima di iniziare dovrete iscrivervi all'editor Online di Latex [ShareLatex](https://www.sharelatex.com?r=cd3f76de&rm=d&rs=b).
Questo ha alcuni lati pratici positivi: tutto sincronizzato online, quindi sempre reperibile ovunque, ma sopratutto non si rischia di perdere **NULLA!**

Se preferite lavorare con la versione offline potete utilizzare comunque il progetto da me condiviso, ma non affronterò in questa guida nulla a riguardo.

Versione Inglese della Guida, con versione Inglese anche dei File: [Write Thesis in Latex](https://github.com/DrewNF/Write-Thesis-in-Latex)

### LET'S START

Una volta scaricato il file .zip Thesis Template Polito ITA/ENG, vi basterà scompattarlo, andare sul vostro Account [ShareLatex](https://www.sharelatex.com?r=cd3f76de&rm=d&rs=b), iniziare un nuovo progetto e quando vi è richiesto fare l'upload di un progetto esistente; completato il caricamento avrete la vostra Tesi pronta per essere scritta!

Di seguito un indice di quello che descriverò in questa guida:

1. **[Struttura del Progetto](#1struttura-del-progetto);**
2. **[Elementi Base per la Scrittura](#2elementi-base-per-la-scrittura);**
3. **[Link Utili](#3yolo-script-usage)**
4. **[Copyright](#4copyright);**
5. **[State of the Project](#5state-of-the-project).**
6. **[Acknowledgements](#6acknowledgements).**


## 1.Struttura del Progetto

Latex è un compilatore di Testi, quindi necessita di una struttura di file, che una volta compilati compone in un testo unico, non dovremmo occuparci quindi di nulla ovvero: identazione, allineamento etc, dobbiamo solo impostare i giusti parametri e tutto verrà fatto in automatico.
Il progetto ha una struttura abbastanza semplice e intuitiva:
  1. **main.tex** (File principale);
  2. **references.lib** (File con le referenze alla bibliografia);
  3. **image_support** (Cartella contenente la immagini di supporto, es copertina);
  4. **image_thesis** (Cartella contenente la immagini della tesi, es grafici schemi etc);
  5. **chapters** (Cartella contenente i relativi file dei capitoli);

Vediamo ora nel dettaglio i singoli elementi:

  **1. main.tex (File principale)** :
  
  In questo file vengono:
  - Importate le impostazioni utili per la formattazione del Testo;
  - Importato il file relativo alla bibliografia;
  - Scritti i capitoli utili come Dediche e Riconoscimenti.
  - Importati singoli capitoli contenuti nella cartella chapters;
  - Stampate le liste dei contenuti utili;
  
  In dettaglio, **qua importiamo le impostazioni**:
  
   ```latex      
    parser = argparse.ArgumentParser()
    \usepackage{fancyhdr}
    \usepackage{listings}
    \usepackage[italian]{babel}
    \usepackage{subcaption}
    \usepackage{caption}
    \usepackage[table,xcdraw]{xcolor}
    \usepackage{comment}
    \usepackage{adjustbox}
  ```
  
   **Qua importiamo il file della bibliografia**:
  
  ```latex      
    \addbibresource{references.bib}
  ```
  
   **Qua scriviamo capitoli inline nel file**:
  
  ```latex      
    \chapter*{Dediche}
    % DEDIC£
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pellentesque massa eu lacus vestibulum elementum. 
  ```
  
   **Qua importiamo i singoli capitoli**:
  
  ```latex      
    \chapter{Stato dell'Arte}
    \input{chapters/4_stateoftheart}
    \chapter{Metodologia}
    \input{chapters/5_methodology}
    \chapter{Sviluppo del Lavoro}
    \input{chapters/6_development}
    \chapter{Valutazione del Lavoro}
    \input{chapters/7_evaluation}
    \chapter{Conclusioni}
    \input{chapters/8_conclusion}
  ```
    
   **Infine stampiamo le liste dei contenuti**:
  
  ```latex      
    \tableofcontents
    \listoffigures
    \listoftables
    \printbibliography 
  ```
## 2.Elementi Base per la Scrittura
## 3.Link Utili
## 4.Copyright
## 5.State of the Project
## 6.Acknowledgements


