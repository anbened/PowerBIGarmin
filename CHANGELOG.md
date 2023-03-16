# Changelog

Tutte le **modifiche al progetto**, le **correzioni** più importanti, l'aggiunta di **nuove funzionalità** sono documentate in questo file

## 2023-03-16

- Gestione delle colonne NON presenti sul file Activities.csv  
  
  
Può capitare, a seconda del tipo di sport praticato, che alcune colonne (come, ad esempio, la "Frequenza respiratoria media") non siano presenti sul set di dati 
che il sistema si aspetta di torvare per le sue elaborazioni. 
Con questa modifica il sistema ne verifica la presenza e, se necessario, le crea vuote per evitare che possano andare in errore istruzioni di analisi  
  
Per tecnici, le istruzioni sono aggiunte in linguaggio M sulle elaborazioni Power Query.  
Ad esempio:  
*#"Add Col Frequenza respiratoria media" = try Table.AddColumn(#"Renamed Columns2", "Frequenza respiratoria media", each null) otherwise #"Renamed Columns2",*  



  
