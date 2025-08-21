# EVO - Calcola Orario di Uscita 9h e 6h

Questo script Tampermonkey/Greasemonkey è progettato per il sistema di gestione delle presenze EVO (usato su `https://personale-unibo.hrgpi.it/`). Calcola automaticamente l'orario di uscita previsto per la giornata corrente, tenendo conto delle timbrature, della propria linea oraria e delle durate lavorative di 9 o 6 ore.

**(Versione Script: 1.0 - Ufficiale)**

## Caratteristiche

* **Calcolo Flessibile dell'Orario di Uscita tramite Switch:**
    * **Per 9 ore (9:00):** Determina l'orario di uscita necessario per completare le 9 ore di lavoro **nette**, a cui viene aggiunta la pausa pranzo di 10 minuti.
    * **Per 6 ore (6:00):** Determina l'orario di uscita necessario per completare le 6 ore di lavoro **nette**. Per questo calcolo, la pausa pranzo **non viene aggiunta**.
    * La modalità di calcolo (9:00 o 6:00) può essere selezionata tramite un **switch toggle compatto** e la tua scelta viene **salvata automaticamente** e ricaricata alla visita successiva della pagina.
* **Gestione Fascia Oraria di Ingresso:**
    * Include un **selettore a discesa** che permette di scegliere la fascia oraria desiderata per l'ingresso (`07:30 - 08:30`, `08:00 - 09:00`, `08:30 - 09:30`).
    * L'orario di ingresso considerato per entrambi i calcoli sarà il **maggiore** tra la prima timbratura di ingresso effettiva e il limite inferiore della fascia oraria selezionata.
    * La preferenza della fascia oraria viene **salvata automaticamente** e ricaricata alla visita successiva della pagina.
* **Gestione Timbrature Flessibile:** Supporta sia il formato standard `E HH:mm` / `U HH:mm` che il formato "Telelavoro" `E[HH:mm]` / `U[HH:mm]`.
* **Gestione Pausa Pranzo:** La pausa pranzo (10 minuti) viene aggiunta al calcolo solo nella modalità 9:00.
* **Visualizzazione Orario di Uscita Dedicata:** L'orario di uscita calcolato viene visualizzato in una **box dedicata e compatta** (`"Uscita: HH:mm"`) con uno sfondo grigio chiaro e un bordo sottile, posizionata in un blocco UI riorganizzato. L'orario è anche inserito come "pillola" nella cella della tabella EVO in corrispondenza del giorno corrente, sovrascrivendo qualsiasi contenuto precedente dello script.
* **Posizionamento Intuitivo:** Il selettore della fascia oraria, lo switch per la modalità di calcolo e la box dell'orario di uscita sono posizionati strategicamente in un **unico blocco UI compatto**, vicino ai controlli principali della pagina (come il bottone "Aggiorna").
* **Apparizione Condizionale:** Gli elementi UI dello script appaiono **esclusivamente sulla pagina "Cartellino"** del portale, evitando la loro visualizzazione su altre sezioni non pertinenti.

## Installazione e Aggiornamenti Automatici

Per installare lo script e assicurarti che si aggiorni automaticamente dal repository GitHub, segui i passaggi per il tuo browser:

### 1. Installare l'estensione Tampermonkey

Se non l'hai già fatto, installa l'estensione Tampermonkey nel tuo browser:

* **[Tampermonkey per Chrome](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)**
* **[Tampermonkey per Edge](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpbldmmepgdkmfapfmccmocdkf)**
* **[Tampermonkey per Firefox](https://addons.mozilla.org/it/firefox/addon/tampermonkey/)** (o Greasemonkey se preferisci)

### 2. Configurazione del Browser (Importante per l'esecuzione)

Per consentire l'esecuzione corretta dello script, potrebbero essere necessari alcuni passaggi di configurazione nel tuo browser:

#### Per Google Chrome:

1. Apri Chrome e digita `chrome://extensions/` nella barra degli indirizzi, poi premi Invio.
2. In alto a destra, attiva la **"Modalità sviluppatore"** (interruttore).
3. Individua Tampermonkey nell'elenco delle estensioni.
4. Clicca su **"Dettagli"** sotto Tampermonkey.
5. Assicurati che l'opzione **"Consenti script utente"** sia attiva.
6. Assicurati che l'opzione **"Consenti l'accesso agli URL del file"** sia attiva.

#### Per Microsoft Edge:

1. Apri Edge e digita `edge://extensions/` nella barra degli indirizzi, poi premi Invio.
2. In alto a destra, attiva la **"Modalità sviluppatore"** (interruttore). Potrebbe comparire un avviso di sicurezza nella parte superiore del browser; è normale quando si usa questa modalità.
3. Individua Tampermonkey nell'elenco delle estensioni.
4. Clicca su **"Dettagli"** sotto Tampermonkey.
5. Assicurati che l'opzione **"Consenti estensioni da altri archivi"** sia attiva.
6. **Assicurati che l'opzione "Consenti l'accesso agli URL del file" sia attiva.**

### 3. Installazione dello Script per Aggiornamenti Automatici

Ora che il tuo browser è configurato, puoi installare lo script:

[**Clicca qui per installare/aggiornare EVO - Calcola Orario di Uscita 9h e 6h**](https://github.com/stefano-salvatore7/evo-exit-time-calculator-900_600/raw/refs/heads/main/evo-exit-time-calculator_900-600.user.js)

* Dopo aver cliccato, Tampermonkey (o Greasemonkey) ti mostrerà il codice dello script e ti chiederà di **"Installa"** (se è la prima volta) o **"Aggiorna"** (se stai aggiornando una versione precedente). Conferma l'azione.

### 4. Verifica Aggiornamenti Automatici (Tampermonkey)

Una volta installato tramite il link RAW, Tampermonkey dovrebbe gestire automaticamente gli aggiornamenti. Puoi verificare le impostazioni:

* Clicca sull'icona di Tampermonkey nel tuo browser e seleziona **"Dashboard"**.
* Trova "EVO - Calcola Orario di Uscita 9h e 6h" nell'elenco.
* Verifica che la casella "Controlla aggiornamenti" sia spuntata. L'URL di aggiornamento dovrebbe essere corretto (quello RAW che hai usato per l'installazione).
* Tampermonkey controllerà periodicamente il repository per nuove versioni e ti notificherà se è disponibile un aggiornamento. Puoi anche forzare un controllo cliccando sull'icona delle frecce circolari (Aggiorna) accanto al nome dello script.

## Utilizzo

Una volta installato, lo script si attiverà automaticamente quando visiterai la pagina delle timbrature EVO su `https://personale-unibo.hrgpi.it/*`.

1. Naviga alla pagina delle timbrature (assicurati che sia la pagina "Cartellino").
2. Troverai un **selettore a discesa** per la "Linea oraria" e uno **switch toggle** ("9:00" / "6:00") posizionati strategicamente, insieme a una **box compatta per l'orario di uscita**, sotto al bottone "Aggiorna".
3. **Seleziona la fascia oraria** desiderata dal selettore e la **modalità di calcolo** desiderata (9:00 o 6:00) tramite lo switch.
4. L'orario di uscita calcolato apparirà automaticamente nella box dedicata e anche come "pillola" nella tabella in corrispondenza della data corrente.
