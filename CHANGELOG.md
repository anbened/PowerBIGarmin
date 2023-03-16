# Changelog

Tutte le **modifiche al progetto**, le **correzioni** più importanti, l'aggiunta di **nuove funzionalità** sono documentate in questo file

## 2023-03-17

Aggiunto nuovo report di **analisi su Training Effect**

Il report è composto, al momento, da tre elementi grafici che rappresentano:
- impatto attività su livello fitness aerobico
- cadenza di corsa media
- rapporto verticale medio
Tutti gli elementi grafici hanno anche la relativa analisi del trend nel tempo  
  
  
  
Aggiunto nuovo report di **analisi su Punteggio Allenamenti**

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

- Gestione delle colonne NON presenti sul file Activities.csv  
  
  
Può capitare, a seconda del tipo di sport praticato, che alcune colonne (come, ad esempio, la "Frequenza respiratoria media") non siano presenti sul set di dati 
che il sistema si aspetta di torvare per le sue elaborazioni. 
Con questa modifica il sistema ne verifica la presenza e, se necessario, le crea vuote per evitare che possano andare in errore istruzioni di analisi  
  
Per tecnici, le istruzioni sono aggiunte in linguaggio M sulle elaborazioni Power Query.  
Ad esempio:  
*#"Add Col Frequenza respiratoria media" = try Table.AddColumn(#"Renamed Columns2", "Frequenza respiratoria media", each null) otherwise #"Renamed Columns2",*  



  
