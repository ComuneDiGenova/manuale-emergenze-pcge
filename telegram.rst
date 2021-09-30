Funzionalità Telegram
==========================

Per utilizzare le funzionalità del Bot Telegram **Gestione emergenze comune di Genova** (@emergenze_genova_bot) è necessario essere un utente del Sistema Emergenze ed avere un profilo assegnato. 
Inoltre è necessario attivare le notifiche Telegram secondo quanto indicato nel capitolo `Profilo utente e attivazione notifiche telegram <accesso.html#profilo-utente-e-attivazione-notifiche-telegram>`__

Tramite il bot Telegram è possibile ricevere notifiche dal Sistema Emergenze, ad esempio in caso di apertura di un nuovo evento, di assegnazione di un incoarico/presidio alla propria squadra, ecc. Inoltre è anche possibile interagire direttamente con il Sistema Emergenze ad esempio segnalando la propria presenza alla Centrale Operativa, accettando o rifiutando un incarico assegnato alla propria squadra, inserendo la lettura di una mira o inviando una comunicazione alla Centrale.


Comandi Telegram
-------------------------------------------
Una volta installato il bot su Telegram è possibile accedere ai diversi comandi sviluppati. La lista dei comandi disponibili è accessibile cliccando sul pulsante **Menu** nella barra degli strumenti dell'applicazione Telegram oppure digitando il simbolo slash **/**

.. image:: img/barra_t.png
  :align: center

I comandi disponibili sono:

* **/start** - avvia il bot per la prima volta e viene automaticamente lanciato all'installazione del bot
* **/help** - restituisce un messaggio con una breve descrizione dei comandi del bot
* **/telegram_id** - restituisce il proprio codice identificativo Telegram. Questo codice univoco deve essere inserito nel Sistema per consentire l'attiovazione delle notifiche
* **/sito** - restituisce il link web al Portale di Sistema Emergenze
* **/registra_presenza** - consente all'utente di registrare a sistema la propria presenza ad inizio turno (per maggiori dettagli si veda il paragrafo :ref:`registra-presenza`)
* **/registra_uscita** - consente all'utente di registrare a sistema la fine del proprio turno (per maggiori dettagli si veda il paragrafo :ref:`registra-presenza`)
* **/inserisci_mira** - consente di inserire il valore della lettura di una mira (per maggiori dettagli si veda il paragrafo :ref:`lettura-mira`)
* **/comunicazione** - consente di inviare una comunicazione (testo ed eventuali immagini) relativa a una segnalazione alla Centrale operativa (per maggiori dettagli si veda il paragrafo :ref:`comunicazioni`)

.. image:: img/comandi_t_cut.png
  :align: center
  
I comandi possono essere lanciati con tre modalità:

* cliccando sul comando desiderato dalla lista dei comandi che si ottiene con il pulsante **Menu**
* cliccando sul comando desiderato dalla lista dei comandi che si ottiene digitando il simbolo **/**
* digitando il nome del comando preceduto da simbolo slash **/**

.. image:: img/comandi_t2.png
  :align: center

Funzioni Telegram
-------------------------------------------

.. _registra-presenza:

Registra Presenza
''''''''''''''''''''''''''''''''''''''''''''''
La funzionalità **Registra presenza** consente all'utente di indicare l'inizio e la fine del proprio turno. 

Il comando **/registra_presenza**, disponibile nella lista dei comandi, consente di indicare l'inizio del proprio turno. Il comando restituisce all'utente un messaggio in cui viene chiesto di specificare la durata del turno, l'utente dovrà quindi cliccare sul bottone corrispondente al numero di ore del turno

.. image:: img/presenza_durata.png
  :align: center
  
Una volta indicata la durata del proprio turno, il bot restituisce un messaggio di avvenuta registrazione della presenza e l'indicazione dell'orario presunto di fine turno

.. image:: img/presenza_ok.png
  :align: center
  
.. warning:: Qualora fosse già stata indicata la propria presenza tramite il comando **/registra_presenza**, il bot restituirà un messaggio che informa l'utente che la presenza è già stata registrata.

Il comando **/registra_uscita**, disponibile nella lista dei comandi, consente di indicare la fine del proprio turno. Il comando restituisce all'utente un messaggio in cui viene chiesto di confermare la chiusura del turno

.. image:: img/registra_uscita.png
  :align: center

.. warning:: Qualora fosse già stata indicata la fine del proprio turno tramite il comando **/registra_uscita**, il bot restituirà un messaggio che informa l'utente che non risulta a sistema un tunro attivo.

A partire da 10 minuti prima dell'ora presunta di fine turno, l'utente riceverà una notifica automatica di remind sul bot per ricordare di utilizzare il comando **/registra_uscita** per indicare la fine del turno. L'utente riceverà una notifica ogni 10 minuti finchè non verrà chiuso il turno

Ricezione della presenza sul Sistema Emergenze 
*************************************************

Quando l'operatore registra la propria presenza tramite il comando **/registra_presenza** del bot Telegram, i dettagli del suo turno saranno visibili sulla pagina web **Utenti presenti** del Sistema Emergenze. Oltre ai dati dell'utente (matricola/CF, nome e cognome) sono indicati anche data e ora di inizio turno e la durata del turno. Gli utenti del Sistema con profilo **Amministratore** possono dalla pagina **Utenti presenti**:

* chiudere il turno di un operatore utilizzando il bottone **Termina Turno** 
* modificare i dettagli (inizio e durata) del turno di un operatore utilizzando il bottone **Modifica Turno**

.. image:: img/presenti.png
  :align: center
  
Quando il turno di un operatore viene terminato, utilizzando il comando **/registra_uscita** del bot Telegram o dall'Amministratore di Sistema, i dettagli del turno appena chiuso saranno visibili nella pagina web **Storico utenti presenti** del Sistema Emergenze.

La presenza degli operatori è visibile anche sulla pagina web **Gestione squadre**. Nella tabella delle squadre attive o attivabili, la colonna **Telegram** indica se il Capo squadra ha registrato la propria presenza:

* icona X arancione = è stato assegnato un Capo squadra ma non ha registrato la propria presenza
* icona V verde = è stato assegnato un Capo squadra e ha registrato la propria presenza
* - = non è stato assegnato un Capo squadra

.. image:: img/presenza_squadre.png
  :align: center

Accettazione/rifiuto incarichi interni, presidi e incarichi
''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

Durante la gestione di una segnalazione registrata sul Sistema Emergenze, l'ente che ne detiene la titolarità ha la possibilità di assegnare incarichi interni e presidi fissi alle squadre attivabile o incarichi a Direzioni, Municipi, Distretti di PM e Unità Operative Esterne. Questa funzione gestisce anche l'accettazione o il rifiuto di presidi fissi assegnati a una squdara indipendentemente da una segnalazione.

* Quando viene assegnato un **incarico interno o un presidio fisso** il Sistema Emergenze **invierà una notifica sul bot Telegram** a tutti gli operatori facenti parte della **squadra** a cui è stato assegnato l'incarico interno/presidio fisso. In questo caso è possibile per gli operatori gestire l'accettazione o il rifiuto dell'incarico/presidio direttamente dal bot Telegram.
* Quando viene assegnato un **presidio mobile** il Sistema Emergenze **invierà una notifica sul bot Telegram** a tutti gli operatori facenti parte della **squadra** a cui è stato assegnato il presidio mobile. In questo caso viene solamente inviata la notifica e **non è possibile** per gli operatori gestire l'accettazione del presidio direttamente dal bot Telegram.
* Quando viene assegnato un **incarico** il Sistema Emergenze **invierà una notifica sul bot Telegram** ai contatti registrati a sistema per la notifica degli incarichi a Direzioni, Municipi, Distretti di PM e Unità Operative Esterne. In questo caso viene solamente inviata la notifica e **non è possibile** per gli operatori gestire l'accettazione o il rifiuto dell'incarico direttamente dal bot Telegram.

Accettazione/rifiuto incarichi interni
***************************************

In caso di assegnazione di un incarico interno a una squadra, tutti gli operatori facenti parte della squadra riceveranno una notifica di assegnazione incarico sul bot Telegram con indicato:

* il numero della segnalazione a cui fa riferimento l'incarico
* il nome della squadra di appartenenza
* i dettagli dell'incarico (breve descrizione operativa)
* le istruzioni per accettare o rifiutare l'incarico
* una mappa con la geolocalizzazione dell'incarico

.. image:: img/notifica_inc_int.png
  :align: center
  

L'operatore può **accettare** l'incarico con due modalità:

* cliccando sul comando **/accetto** direttamente dal messaggio di notifica ricevuto
* digitando il comando **/accetto** nell'area di testo di Telegram

La funzione di accettazione dell'incarico assegnato è composta dai seguenti step:

* comando **/accetto** - restiruisce un messaggio sul bot in cui viene chiesto all'operatore di indicare tra quanti minuti sarà sul posto.
* invio del messaggio da parte dell'operatore con indicazione il numero di minuti espresso in cifre (es. 20). **NB.** Se il numero di minuti viene espresso in caratteri (es. venti) il bot restituirà un messaggio di errore e sarà necessario indicare nuovamente i minuti in cifre.
* indicazione da parte dell'operatore se la presa in carico è regolare o parziale cliccando sui bottoni che compaiono nella barra degli strumenti di telegram

Conclusi questi tre step, l'operatore riceverà un messaggio di riepilogo con quanto indicato negli step recedenti e le istruzioni per chiudere l'incarico una volta completato

.. image:: img/accetto_inc_int.png
  :align: center
  
.. warning:: Per sua natura il bot Telegram consente di eseguire le sole operazioni che sono state sviluppate per il bot stesso, è quindi fondamentale per il corretto funzionamento del bot rispettare e seguire tutti i passaggi sopra indicati e nell'ortdine indicato per poter eseguire correttamente la funzione di accettazione dell'incarico. Qualora non venissero esguiti tutti gli step, la funzione non viene terminata e quindi l'accettazione non viene registrata dal sistema e tutti gli altri comandi/funzioni del bot non potranno essere utilòizzati fino al completamento della funzione di accettazione dell'incarico.

L'operatore può successivamente **chiudere** l'incarico con due modalità:

* cliccando sul comando **/chiudo** direttamente dal messaggio di notifica ricevuto terminata la funzione di accettazione dell'incarico
* digitando il comando **/chiudo** nell'area di testo di Telegram

La funzione di chiusura dell'incarico assegnato è composta dai seguenti step:

* comando **/chiudo** - restiruisce un messaggio sul bot in cui viene chiesto all'operatore di indicare una nota di chiusura
* invio del messaggio da parte dell'operatore con un breve testo di nota per la chiusura

.. image:: img/chiudo_inc_int.png
  :align: center
  
Oltre ad accettare/chiudere l'incarico è possibile anche dal bot telegram **rifiutare** l'incarico.

L'operatore può **rifiutare** l'incarico con due modalità:

* cliccando sul comando **/rifiuto** direttamente dal messaggio di notifica ricevuto all'assegnazione dell'incarico
* digitando il comando **/rifiuto** nell'area di testo di Telegram

La funzione di rifiuto dell'incarico assegnato è composta dai seguenti step:

* comando **/rifiuto** - restiruisce un messaggio sul bot in cui viene chiesto all'operatore di indicare una motivazione per il rifiuto
* invio del messaggio da parte dell'operatore con un breve testo di motivazione per il rifiuto

.. image:: img/rifiuto_inc_int.png
  :align: center
  

.. warning:: I comandi **/accetto, /chiudo e /rifiuto** funzionano solo se l'operatore è parte di una squadra e se a quella squadra è stato assegnato un incarico. Quando l'operatore lancia uno di questi comandi il bot verifica se l'operatore è inserito in una squadra e se ad essa è assegnato un incarico interno, qualora queste condizioni non fossero verificate, il bot restituisce un messaggio di errore.


Accettazione presidio fisso
***************************************

In caso di assegnazione di un presidio fisso a una squadra, tutti gli operatori facenti parte della squadra riceveranno una notifica di assegnazione presidio sul bot Telegram con indicato:

* il numero della segnalazione a cui fa riferimento il presidio
* il nome della squadra di appartenenza
* i dettagli del presidio (breve descrizione operativa)
* le istruzioni per accettare il presidio (nel caso dei presidi non è previsto il rifiuto)
* una mappa con la geolocalizzazione del presidio

.. image:: img/notifica_pres_fis.png
  :align: center
  

L'operatore può **accettare** il presidio fisso con due modalità:

* cliccando sul comando **/presidio** direttamente dal messaggio di notifica ricevuto
* digitando il comando **/presidio** nell'area di testo di Telegram

La funzione di accettazione del presidio assegnato è composta dai seguenti step:

* comando **/presidio** - restiruisce un messaggio sul bot in cui viene chiesto all'operatore di indicare tra quanti minuti sarà sul posto.
* invio del messaggio da parte dell'operatore con indicazione il numero di minuti espresso in cifre (es. 20). **NB.** Se il numero di minuti viene espresso in caratteri (es. venti) il bot restituirà un messaggio di errore e sarà necessario indicare nuovamente i minuti in cifre.

Conclusi questi due step, l'operatore riceverà un messaggio di riepilogo con quanto indicato negli step recedenti e le istruzioni per chiudere il presidio una volta completato

.. image:: img/accetto_pres_fis.png
  :align: center
  
.. warning:: Per sua natura il bot Telegram consente di eseguire le sole operazioni che sono state sviluppate per il bot stesso, è quindi fondamentale per il corretto funzionamento del bot rispettare e seguire tutti i passaggi sopra indicati e nell'ortdine indicato per poter eseguire correttamente la funzione di accettazione dell'incarico. Qualora non venissero esguiti tutti gli step, la funzione non viene terminata e quindi l'accettazione non viene registrata dal sistema e tutti gli altri comandi/funzioni del bot non potranno essere utilòizzati fino al completamento della funzione di accettazione dell'incarico.

L'operatore può successivamente **chiudere** il presidio con due modalità:

* cliccando sul comando **/stop** direttamente dal messaggio di notifica ricevuto terminata la funzione di accettazione del presidio
* digitando il comando **/stop** nell'area di testo di Telegram

La funzione di chiusura del presidio assegnato è composta dai seguenti step:

* comando **/stop** - restiruisce un messaggio sul bot in cui viene chiesto all'operatore di indicare una nota di chiusura
* invio del messaggio da parte dell'operatore con un breve testo di nota per la chiusura

.. image:: img/chiudo_pres_fis.png
  :align: center
  

.. warning:: I comandi **/presidio e /stop** funzionano solo se l'operatore è parte di una squadra e se a quella squadra è stato assegnato un presidio. Quando l'operatore lancia uno di questi comandi il bot verifica se l'operatore è inserito in una squadra e se ad essa è assegnato un presidio fisso, qualora queste condizioni non fossero verificate, il bot restituisce un messaggio di errore.


.. _lettura-mira:

Inserimento lettura mire
'''''''''''''''''''''''''''''''''''''''''''''''

.. _comunicazioni:

Comunicazioni con la centrale operativa
'''''''''''''''''''''''''''''''''''''



