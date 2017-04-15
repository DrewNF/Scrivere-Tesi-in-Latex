# Scrivere una Tesi in Latex
(Version 2.0, Last Update 15-04-2017)

### Guida per scrivere una Tesi in Latex, con tanto di Template in ITA & ENG e istruzioni per adattare l'immagine di copertina alla vostra Università (Default: Politecnico di Torino).

### Per qualsiasi dubbio o approfondimento, non esitate ad aprire una Issue, vi risponderò molto volentieri!

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
  
  L'ordine con cui vengono specificati questi punti dipende dalle scelte dell'autore, nel file fornitovi, l'ordine è quello classico, quindi potete tranquillamente lasciare le cose come stanno e modificare solamente capitoli e contenuti.
  
  **2. references.lib (File con le referenze alla bibliografia)**:
  
 Il references.lib file è molto comodo permette di specificare due diverse tipologie di sorgenti e richiamarle all'interno del testo, sarà poi il compilatore a stamparne la lista ordinata alla fine.
 Le possibilità sono le seguenti:
  
  
   ```latex      
    %%% ARTICLES

    @ARTICLE{lorem_article,
       author = {{Redmon}, J. and {Divvala}, S. and {Girshick}, R. and {Farhadi}, A.
      },
        title = "{You Only Look Once: Unified, Real-Time Object Detection}",
      journal = {ArXiv e-prints},
    archivePrefix = "arXiv",
       eprint = {1506.02640},
     primaryClass = "cs.CV",
     keywords = {Computer Science - Computer Vision and Pattern Recognition},
         year = 2015,
        month = jun,
       adsurl = {http://adsabs.harvard.edu/abs/2015arXiv150602640R},
      adsnote = {Provided by the SAO/NASA Astrophysics Data System}
    }

    %%% WEBSITE

    @online{lorem_web,
        author        = {Berkley},
        title         = {Caffe, Deep Learning Framework},
        year          = {2008},
        url           = {http://caffe.berkeleyvision.org/}
    }
  ```
  
 **3. image_support (Cartella contenente la immagini di supporto, es copertina) &**
 **4. image_thesis (Cartella contenente la immagini della tesi, es grafici schemi etc)**:
  
  Queste due cartelle sono state create per motivi di ordine generale, nel primo andranno inserite tutte quelle immagini che poi non verranno citate e usate nel testo principale.
  Mentre nella seconda cartella vanno caricate solo quest'ultime, cosichè non vi sarà possibilità di confonderne il contenuto.
  
 **5. chapters (Cartella contenente i relativi file dei capitoli)**:
 
 Infine in questa cartella vengono contenuti i file relativi ai singoli capitoli, dove saranno contenuti sezioni, sottosezioni, contenuti, citazioni, ma principalmente il testo.
 
## 2.Elementi Base per la Scrittura

In questo capitolo vi indicherò le principali formule utili per la stesura e strutturazione del testo all'interno dei singoli capitoli.
Per definire **Paragrafi e Sottoparagrafi** usiamo:

  ```latex      
    \section{Morbi}
    Morbi ac varius enim, ac lobortis odio. 
    \subsection{Et amo}
    Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus.
  ```
Per definire **Immagini** usiamo:

  ```latex      
    \begin{figure}[h!]
    \includegraphics[scale=0.3]{lorem_image.png} 
    \centering
    \caption{Morbi ac varius enim, ac lobortis odio. Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus. Pellentesque finibus urna eget maximus cursus. Aenean mollis ante nec dolor iaculis, ac malesuada enim ultrices. Aenean vulputate felis sapien, quis rhoncus odio dictum vitae.}
    \label{fig:template_cat_c}
    \end{figure}
  ```
Per definire **Tabelle** usiamo:

  ```latex      
    \begin{table}[h!]
    \centering
    \begin{tabular}{|c|c|c|c|}
    \hline
    \textbf{Team name}      & \textbf{Entry description}                                                                                                & \textbf{\begin{tabular}[c]{@{}c@{}}Number of\\  object \\ categories won\end{tabular}} & \textbf{mAP}                    \\ \hline
    \textbf{NUIST}          & \begin{tabular}[c]{@{}c@{}}cascaded region regression \\ + tracking\end{tabular}                                          & 10                                                                                     & {\color[HTML]{FE0000} 0.808292} \\ \hline
    \textbf{NUIST}          & \begin{tabular}[c]{@{}c@{}}cascaded region regression \\  + tracking\end{tabular}                                         & 10                                                                                     & 0.803154                        \\ \hline
    \textbf{CUVideo}        & \begin{tabular}[c]{@{}c@{}}4-model ensemble with\\ Multi-Context Suppression and\\ Motion-Guided Propagation\end{tabular} & 9                                                                                      & 0.767981                        \\ \hline
    \textbf{Trimps-Soushen} & Ensemble 2                                                                                                                & 1                                                                                      & 0.709651                        \\ \hline
    \end{tabular}
    \caption{Morbi ac varius enim, ac lobortis odio. Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus. Pellentesque finibus urna eget maximus cursus. Aenean mollis ante nec dolor iaculis, ac malesuada enim ultrices. Aenean vulputate felis sapien, quis rhoncus odio dictum vitae.}
    \label{tab:template_table_c}
    \end{table}
  ```
Un consiglio per la creazione e gestione delle tabelle, è di usare il seguente [Editor On line](http://www.tablesgenerator.com/) che permette di creare la tabella graficamente e quindi esportare poi il codice nel file Latex.

Per citare nel testo rispettivamente **Bibliografia**, **Immagini**, **Tabelle**  usiamo:

  ```latex      
   \cite{lorem_article} 
   
   \ref{fig:template_cat}
   
   \ref{tab:template_table}
  ```
La comodità di citare così le nostre fonti, è che non dovremmo occuparci di controllare le referenze numeriche e l'ordine, perchè Latex lo farà al posto nostro.

Per creare **elenchi puntati** usiamo:

  ```latex      
    \begin{itemize}
      \item  Contribution 1;
      \item  Contribution 2;
      \item  Contribution 3.
    \end{itemize}
  ```

Per conoscenze e formattazioni più approfondite, vi rimando alla sezione coi link utili dove inserirò tutti i link a guide ufficiali che spiegano le differenti possibilità di formattazione del testo, dalla sua grandezza all bold e italic, a composizioni multi-immagine etc...
  
## 3.Link Utili

  - [Upload di un Progetto](https://it.sharelatex.com/learn/Uploading_a_project);
  - [Uso della Bibliografia](https://it.sharelatex.com/learn/Using_bibliographies_in_ShareLaTeX);
  - [Inserire le Immagini](https://it.sharelatex.com/learn/Inserting_Images);
  - [Inserire le Tabelle](https://it.sharelatex.com/learn/Tables);
  - [Paragrafi e Nuova Linea](https://it.sharelatex.com/learn/Paragraphs_and_new_lines);
  - [Grossetto, Corsivo e Sottolineato](https://it.sharelatex.com/learn/Bold,_italics_and_underlining);
  - [Utilizzare le Liste](https://it.sharelatex.com/learn/Lists).
  - [Headers & Footers](https://it.sharelatex.com/learn/Headers_and_footers);
  - [Note a Piè Pagina](https://it.sharelatex.com/learn/Footnotes);
  - [Allineamento del Testo](https://it.sharelatex.com/learn/Text_alignment).

## 4.Copyright

According to the LICENSE file of the original code:
  - Me and original author hold no liability for any damages;
  - Do not use this on commercial!.

## 5.State of the Project

Il progetto ha lo scopo di racchiudere in un unica pagina:
- Le informazioni utili per scrivere un testo con Latex;
- File Progetto per scrivere il testo principale;
- File Progetto per scrivere il riassunto.

## 6.Acknowledgements

Ringrazio il mio Erasmus+ alla FIB UPC Barcelona Tech, per avermi spinto a utilizzare e approfondire la mia conoscienza su latex e i suoi grandi pregi.

