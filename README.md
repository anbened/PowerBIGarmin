# Power BI & Garmin data

:point_right: **ATTENZIONE**: modifiche al progetto, correzioni, aggiunta di nuove funzionalità sono documentate [QUI](CHANGELOG.md) 	:point_left:  

:point_right: **ATTENZIONE**: Per fare domande, condividere idee, suggerire correzioni, ... [QUI](https://github.com/anbened/PowerBIGarmin/discussions) :point_left:  
  
  
![Intro image](../main/images/intro.png)


- [Introduzione](#Introduzione)
  - [Info per NON tecnici (per chi NON conosce Power BI)](#info-per-non-tecnici--per-chi-non-conosce-power-bi)
    - [Cosa è Power BI Desktop](#cosa-%C3%A8-power-bi-desktop)
    - [Che cosa avviene dietro le quinte](#che-cosa-avviene-dietro-le-quinte)
  - [Info per tecnici (per chi conosce Power BI)](#info-per-tecnici--per-chi-conosce-power-bi)
  - [ISTRUZIONI: Come poter fare le vostre analisi sui dati dei vostri allenamenti](#come-poter-fare-le-vostre-analisi-sui-dati-dei-vostri-allenamenti--istruzioni)
  - [Come utilizzare le analisi](#come-utilizzare-le-analisi)
  - [Esempi di analisi](#esempi-di-analisi)
    - [Report Principale Intro](#report-principale---intro)
    - [Report Trend di allenamento](#analisi-trend-di-allenamento)
    - [Report Analisi Mensile](#analisi-mensile)
    - [Report Analisi Settimanale](#analisi-settimanale)
    - [Report Analisi ore di allenamento](#analisi-ore-di-allenamento)

  
    
# Introduzione
Chi mi conosce sa perfettamente delle mie due principali passioni: i **dati** e la **corsa** (nello specifico le corse di lunghissima distanza in montagna: le **ultratrail**).  
Da sempre traccio e memorizzo tutti i dati utili dei miei allenamenti ma, nel tempo, ho avuto la necessità di renderli più fruibili tramite analisi che rispondessero alle mie necessità di conoscenza.  
E visto che quest'anno mi sono dato degli obiettivi ancora più ambiziosi, ho bisogno di vedere e capire - nel tempo - come e se sto progredendo.  
Per questo motivo, in un paio di weekend, è nato questo progetto di analisi in **Power BI** sui dati che il mio **Garmin** memorizza e mette a disposizione (per essere precisi, io utilizzo un orologio *Fenix 6X Pro* con relativa fascia cardiaca *HRM-Pro*)  
  
Il progetto (in costante evoluzione) è costituito, di fatto, da un solo file (estensione PBIX) che sfrutta i dati che possono essere scaricati dall'area riservata Garmin: https://connect.garmin.com/modern/   

## Info per non tecnici (= per chi NON conosce Power BI)
Le analisi vengono fatte tramite uno strumento, liberamente scaricabile e liberamente installabile, chiamato **Power BI Desktop**  
Qui il download: https://www.microsoft.com/en-us/download/details.aspx?id=58494   

### Cosa è Power BI Desktop
Power BI Desktop è un software di analisi dei dati che consente di creare report e dashboard interattivi. È progettato per integrarsi con una vasta gamma di origini dati, inclusi database, file di Excel e servizi cloud. In breve, Power BI Desktop è uno strumento facile e potente per costruire modelli dati, visualizzare e analizzare informazioni in modo intuitivo e significativo  

### Che cosa avviene "dietro le quinte"
Il file che è stato realizzato per studiare i vostri dati e produrne le analisi si aspetta di lavorare in questo percorso:   *C:\PowerBIGarmin*  
  
Quello che faremo sarà "scaricare" i dati dal sito Garmin per farli trovare allo strumento che potrà leggerli e produrne le analisi  
Quindi, **per prima cosa**, è necessario creare sul proprio disco C una cartella chiamata "PowerBIGarmin"  
Più in basso in questa pagina, nella sezione "Come poter fare le vostre analisi sui dati dei vostri allenamenti (= istruzioni)", trovate tutte le altre informazioni utili  

## Info per tecnici (= per chi conosce Power BI)
Il file ha, al momento, un'unica connessione verso il file CSV estratto dal portale (area riservata) di Garmin  
Di default si aspetta di trovarlo nella directory *C:\PowerBIGarmin*, nessuno vieta (naturalmente), di modificare il puntamento a piacere ("Transform Data" - "Data source settings")  

Al momento il modello dati costruito è molto semplice e consiste solo di due tabelle in relazione tra loro:
- Garmin: entità che contiene i dati scaricati dal sito Garmin con l'aggiunta di alcune misure calcolate
- dimDate: entità calendario, autocostruita, con un periodo dal 1/1/2022 al 31/12/2026

![Modello dati](../main/images/modellodati.png)  

## Come poter fare le vostre analisi sui dati dei vostri allenamenti (= istruzioni)
- scaricare il file PBIX da questo repository e memorizzarlo sul proprio PC, in una cartella dedicata (ad esempio: C:\PowerBIGarmin). Questo il file da scaricare: https://github.com/anbened/PowerBIGarmin/blob/main/file/PowerBIGarmin.pbix  
- andare sul sito Garmin, accedere alla propria area riservata e scaricare il file di tutte le attività
Istruzioni:
  - accedere a https://connect.garmin.com/
  - effettuare il login con le proprie credenziali
  - sulla spalla sinistra, sotto la voce "attività", selezionare "tutte le attività"    
    
  ![Tutte le attività](../main/images/tutteleattivita.png)  

  - una volta apparsa la videata con tutte le attività memorizzate, è necessario scorrerla verso il basso per fare in modo che vengano caricati tutti gli allenamenti fino alla data da cui volete iniziare a fare le vostre analisi (ad esempio: poichè io ho iniziato ad allenarmi, per questa stagione, il 10 ottobre... farò scorrere la videata verso il basso fino a che non verrà caricato il giorno 10 ottobre)
  - una volta a video tutti gli allenamenti che voglio analizzare premo, in alto a dx, "esporta csv"    
    
![Esporta csv](../main/images/esportacsv.png)
  
  - a questo punto nella cartella "downloads" del vostro PC avrete disponibile il file con i dati memorizzati da Garmin
  - questo file va copiato nella cartella scelta al punto 1 (ad esempio: C:\PowerBIGarmin)
  - a questo punto, nella cartella scelta, dovrete avere due file: il file "PowerBIGarmin.pbix" (che avete scaricato da questo repository) per poter fare le analisi e il file "Activities.csv" (che avete scaricato dal sito Garmin) con i dati dei vostri allenamenti    
    
![Folder dati](../main/images/folder.png)
  
- fare doppio click sul file "PowerBIGarmin.pbix" presente nella vostra cartella. A questo punto si aprirà a video lo strumento Power BI Desktop
- sullo strumento, cliccare il comando "Refresh" (oppure "Aggiorna") presente sulla barra orizzontale dei comandi per fare in modo che vengano caricati i vostri dati    
  
![Refresh](../main/images/refresh.png)  
  
- una volta caricati i vostri dati, selezionate in alto a sinistra (sul report che vedete a video), il periodo che volete analizzare (da quando... a quando)


![Periodo](../main/images/periodo.png)  

- buone analisi!

## Come utilizzare le analisi

- Come spiegato sopra, tramite il selettore delle date, è possibile scegliere il periodo di analisi che si vuole visualizzare  
- Su ogni report è possibile selezionare un qualsiasi elemento visuale per potersi focalizzare sullo stesso. Nell'immagine, ad esempio, viene selezionata la voce "Trail Running" all'interno della visualizzazione delle "Calorie per Attività". Una volta cliccata la voce, tutti gli altri elementi del report vengono automaticamente filtrati per quella selezione (ad esempio, in alto, il "Num Allenamenti" rappresenta solo quelli fatti per il "Trail Running"). Cliccando la medesima voce il focus (il filtro) viene disabilitato e la visualizzazione ritorna per tutte le voci  

![Selezione](../main/images/selezione.png)  
  
- Sulla parte bassa dello strumento sono presenti le linguette (i "tab") che permettono di spostarsi tra un report e un altro  
  
![Footer](../main/images/footer.png)  


## Esempi di analisi

Al momento il lavoro consiste in diversi report.  
Ogni suggerimento per arricchire questo lavoro, per renderlo più utile e fruibile, per correggere errori e/o imprecisioni è ben accetto!  
Alcuni esempi:  

### Report principale - Intro
![Report 1](../main/images/report1.png)
  
### Analisi trend di allenamento
![Report 2](../main/images/report2.png)
  
### Analisi mensile
![Report 3](../main/images/report3.png)
  
### Analisi settimanale
![Report 4](../main/images/report4.png)
  
### Analisi ore di allenamento
![Report 5](../main/images/report5.png)
  

