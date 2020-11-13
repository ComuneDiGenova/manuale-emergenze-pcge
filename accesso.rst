Modalità di accesso
====================


Chi può avere accesso al sistema
---------------------------------
Le modalità di accesso attualmente previste dal sistema sono:

* **dipendente comunale**: *da rete interna*: avviene inserendo matricola e password comunali; *da rete esterna*: avviene inserendo le  credenziali SPID personali  
* **esterno**: avviene inserendo le credenziali SPID personali

Le matricola e/o le credenziali SPID sono il criterio con cui accedere all'appllicativo. 
Dopodichè per visualizzare le informazioni e/o inserire nuove informazioni è necessario essere abilitati
dall'amministratore di sistema della protezione civile. 

L'amministratore di sistema ha la possibilità di associare un dipendente comunale o un utente esterno a 
un determinato profilo utente all'interno del Sistema e questo determina cosa l'utente può fare o meno
sull'applicativo stesso.


Come accedere al sistema
--------------------------

L'applicativo realizzato è web-based per cui si accede al sistema semplicemente tramite un link

In particolare, esistono due versioni dell'applicativo:

* **versione in esercizio**  `https://emergenze.comune.genova.it <https://emergenze.comune.genova.it>`_ accessibile via internet e da usare solo in emergenza in seguito ad un avviso della Protezione Civile
* **versione di test**  `https://gestemert.comune.genova.it <https://gestemert.comune.genova.it>`_ accessibile solo da rete comunale e utilizzabile per test ed esercitazioni anche in tempo di pace


L'accesso avviene tramite un applicativo dei Sistemi Informativi del Comune di Genova denominato SIRAC SSO (Single Sign On authentication)
appositamente implementato per l'accesso agli applicativi che richiedano una doppia modalità di autenticazione. Per
maggiori informazioni circa il seguente applicativo si rimanda ai Sistemi Informativi (applicazionisit@comune.genova.it)


.. image::  img/modalita_accesso.png


* **dipendente comunale**: Cliccando sul tasto rosso a destra compare un'unica opzione su cui cliccare "Altre modalità di accesso" ed è quindi necessario inserire le proprie matricola e password comunali

* **esterno**: Cliccando sul tasto blu a sinistra si visualizzano i vari provider SPID tra cui scegliere quello con le proprie credenziali e si verrà re-indirizzati sul sito del provider su cui inserire utente e password

**Nella sola versione di test**, una volta inseriti questi dati si arriva ad una seconda pagina implementata dai Sistemi Informativi del Comune di Genova in cui inserire
mail, numero di telefono e indirizzo. **I dati in questione non servono in nessun modo al sistema quindi non è necessario
inserire dati personali.**


.. image::  img/dati_accesso.png

Al termine si verrà re-indirizzati verso l'applicativo e, se autorizzati, si vedrà la prima pagina dell'applicativo.

.. image::  img/dashboard.png

Se non autorizzati all'acceso è necessario contattare gli amministratori di sistema (adminemergenzepc@comune.genova.it) come illustrato
nelle :ref:`richiesta-accesso`.

In caso di problemi tecnici di accesso si invita invece a contattare i Sistemi Informativi via mail applicazionisit@comune.genova.it o telefono XXXXXX.


Profilo utente e attivazione notifiche telegram 
--------------------------------------------------------------

Si possono visualizzare le caratteristiche del proprio utente (livello di permessi) o altro accedendo all'apposito pulsante presente nella toolbar in alto a destra  cliccando sul proprio codice fiscale

.. image::  img/profilo0.PNG


Oltre a visualizzare i dati è anche possibile attivare il bot telegram denominato **Gestione emergenze comune di Genova** (@emergenze_genova_bot) che si può aggiungere sul proprio account telegram.

.. image::  img/profilo0.PNG


1) Per prima cosa è necessario installare il bot su telegram (cercare il titolo *Gestione emergenze comune di Genova* o direttamente il nome @emergenze_genova_bot

.. image::  img/ricerca_bot.jpg


2) Quini recuperare il proprio *telegram id* o *chat id*  tramite il bot stesso. Cliccare sul simbolo **/** o iniziare a digitare lo slash / e selezionare il comando telegram_id


.. image::  img/chat_id.PNG


Il bot restiruirà il proprio chat id

.. image::  img/chat_id2.PNG

3) a quel punto sul sistema emergenze inserire il proprio *telegram id* e attivare le notifiche

** Si noti che le notifiche di sistema sono inviate sulla base dello specifico profilo impostato dagli amministratori di sistema. 
Non è in nessun modo possibile modficare queste impostazioni.**

 