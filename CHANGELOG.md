# Changelog

Tutte le **modifiche al progetto**, le **correzioni** più importanti, l'aggiunta di **nuove funzionalità** sono documentate in questo file


## 2023-03-19

### Aggiunto nuovo elemento grafico su report Calorie

Efficienza dell'allenamento: Calcola l'efficienza dell'allenamento dividendo le calorie bruciate per la durata dell'allenamento (in minuti). Questo fornisce un'idea di quante calorie vengono bruciate al minuto in ogni allenamento.  
  
  
## 2023-03-18  

### Correzione grafico **Frequenza Cardiaca Media**  
In giornate con più di un allenamento, il valore veniva espresso come somma delle frequenze cardiache medie (non aveva alcun senso)
Adesso, per ogni giornata, il valore espresso è il massimo valore tra i valori medi registrati negli allenamenti della giornata  
  
Ad esempio, con dati simili a:  
17/03 ore 10:00 - 133 bpm  
17/03 ore 15:00 - 142 bpm  
  
Prima: FC media = 275 bpm  
Adesso: FC media = 142 bpm  
  
  
   
### Aggiunto nuovo elemento grafico su **report Punteggio Allenamenti**  
Un secondo elemento grafico, con una differente formula di calcolo basata su pesi specifici associati a ogni attributo, è stato aggiunto al report  
L'idea resta quella di poter capire, tramite il trend esposto dai grafici, se si è in crescita, decrescita o stazionari  
  
  
### Aggiunto nuovo report di **analisi Calorie**  
  
### Aggiunto nuovo report di analisi **Frequenza Cardiaca**  
  
  
## 2023-03-17

### Aggiunto nuovo report di **analisi su Training Effect**

Il report è composto, al momento, da tre elementi grafici che rappresentano:
- impatto attività su livello fitness aerobico
- cadenza di corsa media
- rapporto verticale medio
Tutti gli elementi grafici hanno anche la relativa analisi del trend nel tempo  
  
  
  
### Aggiunto nuovo report di **analisi su Punteggio Allenamenti**

Il report è composto, al momento, da un singolo elemento grafico che rappresenta un punteggio relativo ad ogni allenamento, insieme alla relativa analisi del trend nel tempo
Il punetggio viene calcolato tramite una formula che tiene conto della velocità media, del dislivello, della durata, della frequenza cardiaca media e delle calorie bruciate

Per fare il calcolo, le misure sono espresse nelle seguenti unità di misura:
- Durata: secondi
- Velocità media: chilometri all'ora (km/h)
- Dislivello: metri
- Frequenza cardiaca media: battiti al minuto (bpm)
- Calorie bruciate: calorie

Attenzione: la formula utilizzata è solo un esempio e potrebbe non essere adatta a personali esigenze specifiche

## 2023-03-16

### Gestione delle colonne NON presenti sul file Activities.csv  
    
  
Può capitare, a seconda del tipo di sport praticato, che alcune colonne (come, ad esempio, la "Frequenza respiratoria media") non siano presenti sul set di dati 
che il sistema si aspetta di torvare per le sue elaborazioni. 
Con questa modifica il sistema ne verifica la presenza e, se necessario, le crea vuote per evitare che possano andare in errore istruzioni di analisi  
  
Per tecnici, le istruzioni sono aggiunte in linguaggio M sulle elaborazioni Power Query.  
Ad esempio:  
*#"Add Col Frequenza respiratoria media" = try Table.AddColumn(#"Renamed Columns2", "Frequenza respiratoria media", each null) otherwise #"Renamed Columns2",*  



  
