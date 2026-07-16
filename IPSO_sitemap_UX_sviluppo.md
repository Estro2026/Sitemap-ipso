# IPSO — Sitemap, architettura UX e indicazioni di sviluppo

> Documento operativo per Claude Code.
> Usare questo file come **fonte di verità per architettura informativa, routing, modelli di contenuto e integrazioni**. La struttura indicata qui prevale sulle tassonomie e sui menu dei siti esistenti.

---

## 1. Scopo del progetto

Realizzare un ecosistema digitale unico per IPSO che:

- presenti con chiarezza l'Istituto e la Biosofia;
- orienti utenti freddi o semi-consapevoli verso il percorso più adatto;
- generi richieste di informazioni, colloqui orientativi, iscrizioni ai corsi e registrazioni agli eventi;
- consolidi il patrimonio editoriale e storico oggi distribuito su più siti;
- elimini, per quanto possibile, la frammentazione dell'esperienza digitale dei corsisti;
- permetta una crescita futura ordinata senza creare nuovi micrositi scollegati.

Il sito non deve apparire come un semplice catalogo di corsi. Deve essere percepito come il punto di riferimento IPSO per la relazione tra corpo, emozioni, mente e consapevolezza.

### Obiettivo primario

Generare lead qualificati e iscrizioni ai percorsi formativi.

### Obiettivi secondari

- rafforzare l'autorevolezza dell'Istituto;
- spiegare l'approccio somatorelazionale e la Biosofia;
- favorire la partecipazione a eventi e attività esperienziali;
- aumentare il traffico organico qualificato;
- preservare e rendere consultabile il patrimonio storico e culturale;
- offrire ai corsisti un accesso unico, semplice e accompagnato.

---

## 2. Decisioni architetturali principali

### 2.1 Un unico ecosistema, non una rete di micrositi

Tutti i contenuti pubblici devono convergere nel dominio principale. I domini esistenti devono diventare fonti di migrazione e, successivamente, gestire reindirizzamenti `301` pagina-per-pagina.

Non replicare nel nuovo sito la frammentazione attuale tra:

- `biosofia.it`;
- `sentirsivivi.it`;
- `ipsosmart.it`;
- `teoriapolivagale.it`.

### 2.2 Dominio principale: decisione da confermare

I documenti strategici indicano **IPSO come brand ombrello** e `biosofia.it` come dominio madre. Nel brief compare però anche il riferimento a un nuovo `istitutoipso.it`.

Fino alla decisione definitiva:

- usare nei prototipi e nel codice la variabile/configurazione `SITE_BASE_URL`;
- non hardcodare il dominio nei componenti;
- non impostare redirect definitivi;
- considerare `biosofia.it` come ipotesi di lavoro coerente con i documenti strategici, salvo nuova conferma del cliente.

### 2.3 Due ambienti percepiti come un unico servizio

L'ecosistema deve essere composto da:

1. **Sito pubblico**: identità, corsi, eventi, archivio, rete professionale e conversione.
2. **Area corsisti autenticata**: videolezioni, registrazioni, materiali, calendario, community, supporto e accesso ai test ECM.

I due ambienti devono condividere:

- identità visiva;
- account utente;
- navigazione coerente;
- tono di voce;
- sistema di supporto;
- URL appartenenti allo stesso dominio principale o a un suo sottodominio chiaramente riconoscibile.

### 2.4 Teoria Polivagale: non semplice landing isolata

Teoria Polivagale deve rimanere **interna alla sezione Formazione** e non diventare una voce autonoma del menu principale. Tuttavia, per quantità di contenuti, attività post-training, community e area riservata, deve essere progettata come un **hub verticale** con:

- landing pubblica di conversione;
- pagine di supporto dedicate;
- accesso diretto alla relativa area corsisti;
- community e post-training;
- collegamento alla rete degli operatori.

Quindi:

- **collocazione informativa**: `Formazione > Teoria Polivagale`;
- **autonomia UX**: sì, attraverso sotto-navigazione e dashboard dedicata;
- **autonomia di brand o dominio**: no, salvo decisione strategica successiva.

---

## 3. Utenti e percorsi principali

### 3.1 Utenti prospect

Profili principali:

- persone interessate a una crescita personale profonda;
- persone in transizione professionale;
- counselor, coach, educatori e professionisti della relazione d'aiuto;
- psicologi e professionisti già formati;
- operatori del benessere e delle discipline corporee;
- persone che si avvicinano per la prima volta a bioenergetica, consapevolezza corporea o Teoria Polivagale.

Percorso ideale:

`Scoperta → Comprensione → Fiducia → Contatto → Iscrizione`

### 3.2 Corsisti

Obiettivi principali:

- capire subito cosa fare dopo il login;
- accedere alla lezione o al live successivo;
- ritrovare video, materiali e registrazioni senza conoscere la piattaforma che li ospita;
- svolgere i test ECM con istruzioni chiare;
- ricevere supporto senza dover cercare tra email e siti diversi.

### 3.3 Ex corsisti e sostenitori

Obiettivi principali:

- accedere ai contenuti post-training;
- partecipare alla community;
- aggiornare il proprio profilo professionale, se previsto;
- trovare eventi e formazione continua;
- mantenere il rapporto con IPSO.

### 3.4 Redazione e segreteria

Obiettivi principali:

- aggiornare corsi, date, docenti, eventi e CTA senza interventi di sviluppo;
- pubblicare una sola volta le informazioni riutilizzate in più pagine;
- gestire lo stato delle iscrizioni;
- evitare duplicazioni e incongruenze;
- avere form e lead riconducibili a corso, evento e campagna di origine.

---

## 4. Navigazione globale

### 4.1 Header desktop

Ordine consigliato:

1. Logo IPSO — collegamento alla Home
2. Chi siamo
3. Formazione
4. Eventi
5. Archivio
6. Contatti
7. CTA primaria: **Area corsisti**

Elementi secondari in utility navigation o menu esteso:

- Rete professionale
- Newsletter
- Cerca

### 4.2 Header mobile

Nel menu mobile mostrare tutte le voci in questo ordine:

1. Chi siamo
2. Formazione
3. Eventi
4. Archivio
5. Rete professionale
6. Contatti
7. Newsletter
8. Area corsisti

La CTA Area corsisti deve essere visivamente distinta ma non deve coprire le altre azioni.

### 4.3 Footer

Il footer deve includere:

- logo e payoff;
- contatti diretti;
- indirizzo e mappa;
- link principali;
- corsi attivi;
- eventi in evidenza;
- rete professionale;
- newsletter;
- social;
- privacy, cookie, termini, accessibilità e preferenze cookie;
- eventuali dati societari e amministrativi;
- collegamento Area corsisti.

### 4.4 Breadcrumb

Usare breadcrumb in tutte le pagine di secondo livello e nelle pagine di dettaglio.

Esempi:

- `Home > Formazione > Counseling Somatorelazionale`
- `Home > Eventi > Nome evento`
- `Home > Archivio > Articoli > Titolo articolo`
- `Home > Rete professionale > Nome professionista`

---

## 5. Sitemap generale

```text
/
├── chi-siamo/
│   ├── storia/
│   ├── biosofia-e-approccio-somatorelazionale/
│   ├── docenti/
│   │   └── [slug-docente]/
│   ├── organizzazione/
│   └── certificazioni-e-riconoscimenti/
│
├── formazione/
│   ├── counseling-somatorelazionale/
│   ├── pratica-bioenergetica/
│   ├── ipso-smart/
│   ├── teoria-polivagale/
│   │   ├── programma/
│   │   ├── docenti/
│   │   ├── testimonianze/
│   │   ├── community-e-post-training/
│   │   ├── faq/
│   │   └── iscrizione/
│   └── [slug-corso]/
│
├── eventi/
│   ├── in-programma/
│   ├── esperienze-immersive/
│   ├── eventi-aperti/
│   ├── passati/
│   └── [slug-evento]/
│
├── archivio/
│   ├── pubblicazioni/
│   ├── articoli/
│   ├── libri/
│   ├── riviste/
│   ├── video-e-audio/
│   ├── centro-documentazione-wilhelm-reich/
│   └── [tipologia]/[slug-contenuto]/
│
├── rete-professionale/
│   ├── counselor/
│   ├── psicoterapeuti/
│   ├── operatori-polivagali/
│   └── [slug-professionista]/
│
├── contatti/
├── prenota-colloquio/
├── newsletter/
├── cerca/
│
├── area-corsisti/                       [NOINDEX + autenticazione]
│   ├── login/
│   ├── recupera-accesso/
│   ├── dashboard/
│   ├── corsi/[slug-corso]/
│   │   ├── panoramica/
│   │   ├── moduli/
│   │   │   └── [slug-modulo]/[slug-lezione]/
│   │   ├── live-e-calendario/
│   │   ├── registrazioni/
│   │   ├── materiali/
│   │   ├── test-ecm/
│   │   ├── community/
│   │   └── assistenza/
│   ├── profilo/
│   └── supporto/
│
└── pagine-legali/
    ├── privacy-policy/
    ├── cookie-policy/
    ├── termini-e-condizioni/
    └── dichiarazione-di-accessibilita/
```

### Nota su categorie e sotto-pagine

Le pagine di categoria devono essere create solo quando hanno abbastanza contenuto da offrire valore autonomo. In fase iniziale, filtri e sezioni interne possono sostituire pagine troppo vuote.

Esempio: se esistono solo due esperienze immersive, usare il filtro nella pagina Eventi invece di creare una pagina sottile e poco utile.

---

## 6. Specifiche delle pagine pubbliche

## 6.1 Home

### Obiettivi

- comprendere chi è IPSO;
- comprendere cos'è la Biosofia;
- individuare rapidamente corsi ed eventi rilevanti;
- richiedere informazioni;
- accedere all'Area corsisti.

### Ordine delle sezioni

1. **Hero istituzionale**
   - logo IPSO;
   - payoff istituzionale;
   - video emozionale o visual ad alto impatto;
   - breve presentazione dell'Istituto;
   - CTA primaria: `Scopri la formazione`;
   - CTA secondaria: `Conosci IPSO`;
   - accesso Area corsisti sempre riconoscibile nell'header.

2. **Corsi attivi** — immediatamente sotto la hero
   - massimo 3–4 card prioritarie;
   - stato: iscrizioni aperte, prossima partenza, lista d'attesa, on demand;
   - data di partenza;
   - durata e modalità;
   - CTA diretta alla landing del corso;
   - dati gestiti da CMS, mai hardcodati.

3. **IPSO e Biosofia**
   - spiegazione sintetica e accessibile;
   - distinzione tra Istituto, approccio somatorelazionale e Biosofia;
   - CTA verso la pagina di approfondimento.

4. **Scegli il punto di ingresso**
   - `Cerco una formazione professionale`;
   - `Voglio fare un'esperienza o partecipare a un evento`;
   - `Voglio approfondire corpo, emozioni e relazione`.

5. **Differenzianti**
   - storia e continuità;
   - integrazione tra teoria ed esperienza;
   - lavoro personale e formazione professionale;
   - qualità e stabilità del corpo docente;
   - rete professionale;
   - rigore senza linguaggio eccessivamente accademico.

6. **Eventi in evidenza**
   - prossimo evento principale;
   - 2–3 eventi successivi;
   - CTA `Vedi tutti gli eventi`.

7. **Testimonianze**
   - studenti;
   - ex allievi;
   - professionisti;
   - preferire testimonianze specifiche e contestualizzate.

8. **Partnership e riconoscimenti**
   - loghi con testo alternativo;
   - collegamenti solo se aggiornati e autorizzati;
   - evitare una fascia di loghi priva di contesto.

9. **CTA finale**
   - titolo orientativo;
   - `Prenota un colloquio`;
   - `Richiedi informazioni`.

### Regole UX

- non sovraccaricare la hero con tutte le informazioni;
- i corsi attivi devono essere visibili senza lunga esplorazione;
- la Home deve offrire una mappa, non sostituire tutte le pagine interne;
- non usare slider automatici per corsi o contenuti principali;
- mantenere una CTA primaria coerente per sezione.

---

## 6.2 Chi siamo

### Obiettivo

Raccontare l'identità dell'Istituto e costruire fiducia.

### Pagina hub `/chi-siamo/`

Sezioni:

1. introduzione istituzionale;
2. storia in sintesi;
3. la Biosofia e l'approccio somatorelazionale;
4. missione, visione e principi;
5. corpo docente;
6. organizzazione;
7. certificazioni e riconoscimenti;
8. CTA verso Formazione ed Eventi.

### Sotto-pagine

#### `/chi-siamo/storia/`

- nascita;
- fondatori;
- evoluzione;
- timeline delle tappe principali;
- pubblicazioni e iniziative storiche correlate.

#### `/chi-siamo/biosofia-e-approccio-somatorelazionale/`

- definizione della Biosofia;
- relazione tra corpo, emozioni, mente e consapevolezza;
- radici teoriche;
- principi metodologici;
- cosa distingue IPSO;
- collegamenti a corsi, eventi e archivio.

#### `/chi-siamo/docenti/`

- griglia filtrabile per area e corso;
- fotografia professionale;
- ruolo;
- breve bio;
- corsi ed eventi collegati.

Ogni docente deve avere una sola scheda riutilizzata in tutte le pagine.

#### `/chi-siamo/organizzazione/`

- direzione;
- comitato direttivo;
- comitato scientifico;
- segreteria;
- aree operative;
- governance.

#### `/chi-siamo/certificazioni-e-riconoscimenti/`

- accreditamenti;
- affiliazioni;
- riconoscimenti istituzionali;
- spiegazione sintetica del valore di ciascun riconoscimento;
- data di aggiornamento.

---

## 6.3 Formazione

### Obiettivo

Permettere all'utente di confrontare l'offerta e scegliere il percorso più adatto.

### Pagina hub `/formazione/`

Sezioni:

1. introduzione all'approccio formativo IPSO;
2. corsi con iscrizioni aperte;
3. tutti i percorsi;
4. orientamento alla scelta;
5. confronto sintetico tra percorsi;
6. testimonianze;
7. FAQ generali;
8. CTA colloquio orientativo.

### Filtri consigliati

- stato: aperto, prossima edizione, lista d'attesa, on demand;
- modalità: presenza, online, ibrido, residenziale;
- durata: breve, annuale, pluriennale;
- finalità: professionale, specializzazione, crescita personale, aggiornamento;
- area: counseling, bioenergetica, Teoria Polivagale, relazione d'aiuto.

I filtri devono aggiornare l'URL con query leggibili e condivisibili.

### Percorsi da prevedere

- Counseling Somatorelazionale;
- Pratica Bioenergetica;
- IPSO Smart;
- Teoria Polivagale;
- altri corsi, master, seminari e percorsi futuri.

---

## 6.4 Template landing page corso

Ogni corso usa lo stesso modello dati e una struttura flessibile. La pagina deve sostenere traffico organico, campagne Google Search e campagne Meta senza creare copie non governate.

### Struttura

1. **Hero**
   - nome del corso;
   - tipologia;
   - sottotitolo;
   - breve descrizione;
   - CTA primaria;
   - eventuale CTA secondaria `Scarica il programma`;
   - stato iscrizioni.

2. **Barra informazioni principali**
   - data di partenza;
   - durata;
   - modalità;
   - sede;
   - investimento;
   - eventuali crediti o riconoscimenti.

3. **A chi è rivolto**
   - profili;
   - prerequisiti;
   - criteri di ammissione;
   - indicazioni per capire se il corso è adatto.

4. **Perché scegliere il percorso**
   - differenzianti specifici;
   - risultati realistici;
   - nessuna promessa assoluta.

5. **Struttura e programma**
   - moduli;
   - ore;
   - attività esperienziali;
   - live, registrazioni e lavoro individuale;
   - materiali inclusi.

6. **Metodo formativo**
   - equilibrio tra teoria, esperienza, supervisione e lavoro personale;
   - modalità di accompagnamento.

7. **Numeri e risultati**
   - solo dati verificati;
   - anno di riferimento visibile;
   - evitare contatori generici senza fonte.

8. **Corpo docente**
   - schede riutilizzabili;
   - ruolo nel corso;
   - mini bio;
   - eventuale video.

9. **Partnership e riconoscimenti**

10. **Testimonianze**
    - video o testo;
    - nome, ruolo e corso frequentato;
    - consenso alla pubblicazione.

11. **Sbocchi professionali**
    - opportunità realistiche;
    - quadro normativo e limiti espressi con chiarezza;
    - rete professionale collegata.

12. **FAQ specifiche**

13. **CTA finale**
    - `Prenota un colloquio orientativo`;
    - `Richiedi informazioni`;
    - `Iscriviti` quando il flusso è effettivamente disponibile.

### CTA sticky

Su mobile prevedere una CTA sticky discreta con l'azione primaria del corso. Non mostrare più di un'azione contemporaneamente.

### Campagne

Per campagne pubblicitarie:

- usare la landing corso canonica quando possibile;
- personalizzare headline o blocchi tramite parametri/configurazione, senza duplicare l'intero contenuto;
- se serve una landing separata `/lp/[campagna]/`, impostare canonical verso la pagina corso o `noindex` in base alla strategia SEO;
- preservare UTM e sorgente nei form.

---

## 6.5 Teoria Polivagale — hub pubblico

### URL radice

`/formazione/teoria-polivagale/`

### Ruolo

Essere contemporaneamente:

- pagina di presentazione e conversione;
- porta d'ingresso alla formazione;
- punto di riferimento per programma, docenti, testimonianze e post-training;
- accesso all'Area corsisti;
- collegamento alla community e alla rete degli operatori.

### Sotto-navigazione locale

- Panoramica
- Programma
- Docenti
- Testimonianze
- Community e post-training
- FAQ
- Iscrizione
- Area corsisti

La sotto-navigazione deve essere contestuale alla sezione e non aggiungere voci al menu principale globale.

### Contenuti pubblici

- spiegazione accessibile della Teoria Polivagale;
- autorevolezza scientifica senza sovraccarico accademico;
- struttura del Foundation;
- durata, ore live e registrate, calendario, modalità;
- docenti;
- partnership;
- testimonianze;
- attività post-training;
- community;
- operatori polivagali collegati alla Rete professionale;
- FAQ su accessi, registrazioni, materiali ed ECM;
- CTA di iscrizione o lista d'attesa.

### Regola di contenuto

Non duplicare l'elenco degli operatori in due database. La pagina Teoria Polivagale deve mostrare una vista filtrata del modello `Professional`, con filtro `specializzazione = teoria-polivagale`.

---

## 6.6 Eventi

### Obiettivi

- registrarsi a un evento;
- iscriversi alla newsletter;
- scoprire corsi e contenuti collegati.

### Pagina hub `/eventi/`

1. evento principale in evidenza;
2. calendario o lista degli eventi in programma;
3. filtri;
4. esperienze immersive;
5. eventi aperti;
6. archivio eventi passati;
7. newsletter;
8. percorsi formativi correlati.

### Categorie

- residenziali;
- ritiri;
- weekend esperienziali;
- conferenze;
- open day;
- incontri divulgativi;
- seminari;
- presentazioni dei corsi;
- convegni.

### Template evento

- titolo;
- categoria;
- data e ora, con fuso orario;
- modalità e luogo;
- stato: aperto, completo, lista d'attesa, concluso;
- descrizione;
- programma;
- relatori collegati al modello Docente/Persona;
- quota o gratuità;
- disponibilità posti;
- CTA registrazione;
- istruzioni dopo l'iscrizione;
- eventi, corsi e articoli correlati.

### Eventi passati

Gli eventi passati non devono sparire automaticamente. Devono:

- passare nello stato `concluso`;
- mantenere valore storico e SEO quando hanno contenuti utili;
- mostrare registrazioni, materiali o sintesi, se disponibili;
- sostituire la CTA di registrazione con `Scopri i prossimi eventi`.

---

## 6.7 Archivio

### Obiettivo

Preservare il patrimonio storico e culturale costruito negli anni senza trasformare la navigazione principale in un elenco enciclopedico.

### Pagina hub `/archivio/`

- ricerca full-text;
- filtri per tipologia, tema, autore, anno e formato;
- collezioni in evidenza;
- ultimi contenuti;
- percorsi guidati per utenti non specialisti;
- newsletter;
- corsi ed eventi correlati.

### Tipologie

- pubblicazioni;
- articoli;
- libri;
- riviste;
- video;
- audio;
- dispense pubbliche;
- bibliografie;
- materiali di ricerca;
- contenuti storici;
- Centro di documentazione Wilhelm Reich;
- Anima e Corpo.

### Regole di migrazione

Per ogni contenuto assegnare uno stato:

- `MIGRARE`: contenuto valido e utile;
- `AGGIORNARE`: contenuto valido ma con dati obsoleti;
- `FONDERE`: duplicato da unire a una pagina principale;
- `ARCHIVIARE`: valore storico, non prioritario nella navigazione;
- `NON INDICIZZARE`: utile solo a utenti specifici o con qualità insufficiente;
- `ELIMINARE + 301`: privo di valore autonomo ma con URL esistente;
- `ELIMINARE + 410`: contenuto definitivamente rimosso e senza equivalente.

### Ricerca e filtri

- filtri accessibili anche da tastiera;
- URL aggiornato a ogni filtro;
- pulsante `Azzera filtri`;
- messaggio chiaro quando non esistono risultati;
- paginazione o caricamento progressivo accessibile;
- non indicizzare combinazioni infinite di filtri.

---

## 6.8 Rete professionale

### URL

`/rete-professionale/`

### Posizionamento nella navigazione

Non è una priorità commerciale primaria. Inserirla nella utility navigation, nel footer e nei collegamenti contestuali di Chi siamo, corsi e Contatti.

### Contenuti

- counselor;
- psicoterapeuti;
- operatori polivagali;
- eventuali altre qualifiche approvate.

### Filtri

- tipologia professionale;
- specializzazione;
- regione/provincia/città;
- modalità online/in presenza;
- lingue;
- disponibilità, solo se mantenuta aggiornata.

### Scheda professionista

- nome e fotografia;
- qualifica dichiarata;
- percorso IPSO completato;
- anno o edizione, se autorizzato;
- specializzazioni;
- località;
- modalità di lavoro;
- contatti professionali;
- sito esterno;
- disclaimer sul ruolo di IPSO;
- data dell'ultimo aggiornamento.

### Requisiti di governance

- consenso esplicito alla pubblicazione;
- processo di revisione e scadenza periodica;
- possibilità per il professionista di richiedere aggiornamento o rimozione;
- nessuna informazione sanitaria o personale non necessaria;
- evitare che IPSO sembri garantire prestazioni individuali non verificate.

---

## 6.9 Contatti

### Obiettivi

- richiedere informazioni;
- prenotare un colloquio;
- entrare in contatto con l'Istituto;
- indirizzare correttamente la richiesta alla segreteria.

### Struttura

1. introduzione;
2. scelta del motivo del contatto;
3. form contestuale;
4. prenotazione colloquio;
5. recapiti diretti;
6. orari segreteria;
7. sede e mappa;
8. riferimenti amministrativi;
9. FAQ essenziali.

### Motivi del contatto

- informazioni su un corso;
- colloquio orientativo;
- iscrizione o pagamenti;
- eventi;
- area corsisti e problemi di accesso;
- partnership e istituzioni;
- amministrazione;
- altro.

La selezione deve:

- aggiornare i campi del form;
- aggiungere automaticamente il contesto alla richiesta;
- indirizzare la notifica al destinatario corretto;
- non costringere l'utente a conoscere la struttura interna di IPSO.

### Form

Campi minimi:

- nome;
- cognome;
- email;
- telefono facoltativo salvo colloquio;
- motivo del contatto;
- corso/evento di interesse, se pertinente;
- messaggio;
- consenso privacy;
- consenso marketing separato e facoltativo.

---

## 7. Area corsisti: architettura UX

## 7.1 Principio guida

L'utente deve percepire un unico ambiente. Le etichette di navigazione devono descrivere l'attività dell'utente, non il fornitore tecnologico.

Usare:

- `Videolezioni`;
- `Registrazioni dei live`;
- `Materiali`;
- `Test ECM`;
- `Community`;
- `Assistenza`.

Non usare come voci principali:

- `Vimeo`;
- `Promate`;
- `Spazio Iris`;
- nomi di plugin o servizi tecnici.

Il nome della piattaforma esterna può essere mostrato soltanto quando serve per trasparenza o supporto.

## 7.2 Dashboard corsista

Dopo il login mostrare, in ordine:

1. saluto e contesto;
2. `Riprendi da dove hai lasciato`;
3. prossima attività live con data, ora e link;
4. corsi attivi;
5. attività da completare;
6. nuovi materiali o registrazioni;
7. stato ECM, se disponibile;
8. accesso alla community;
9. contatto assistenza.

### Card corso

Ogni card deve mostrare:

- nome del corso;
- edizione;
- progresso;
- prossima attività;
- CTA `Vai al corso`;
- eventuale avviso importante.

## 7.3 Navigazione interna al corso

Ordine consigliato:

1. Panoramica
2. Moduli
3. Live e calendario
4. Registrazioni
5. Materiali
6. Test ECM
7. Community
8. Assistenza

Su mobile usare una navigazione compatta ma sempre riconoscibile. Evitare menu nascosti in icone non etichettate.

## 7.4 Pagina lezione

- titolo e posizione nel percorso;
- video incorporato;
- trascrizione o sottotitoli, quando disponibili;
- materiali allegati;
- durata;
- stato completamento;
- lezione precedente/successiva;
- eventuali note personali;
- contatto assistenza contestuale.

## 7.5 Onboarding primo accesso

Prevedere un onboarding breve:

1. conferma o creazione della password unica;
2. verifica del profilo;
3. presentazione della dashboard;
4. spiegazione di dove trovare video, materiali, live ed ECM;
5. test rapido di riproduzione video;
6. conferma dei canali di assistenza.

Non mostrare un tutorial generico lungo. Usare indicazioni contestuali e ripetibili.

## 7.6 Comunicazioni

Ogni email deve:

- usare lo stesso naming del portale;
- contenere un link profondo alla pagina esatta;
- evitare istruzioni che cambiano a seconda della piattaforma;
- non chiedere all'utente di cercare manualmente il contenuto;
- indicare chiaramente data, ora, fuso e azione richiesta;
- includere un contatto assistenza coerente.

---

## 8. Integrazione di Vimeo, Promate e altri servizi

## 8.1 Architettura raccomandata

```text
Utente
  ↓
Account IPSO unico / Identity Provider
  ↓
Area corsisti IPSO
  ├── LMS o layer applicativo: iscrizioni, moduli, progressi, materiali
  ├── Vimeo: hosting video incorporato nel portale
  ├── Calendario/live: link e promemoria centralizzati
  ├── Community: stesso account o SSO
  └── Promate/Spazio Iris: test e adempimenti ECM
```

## 8.2 Single Sign-On

### Obiettivo

Un solo account IPSO per accedere all'intero ecosistema.

### Requisiti

- autenticazione basata su standard, preferibilmente `OIDC/OAuth 2.0` o `SAML 2.0`;
- ruoli: corsista, alumni/sostenitore, docente, staff, amministratore;
- un utente può avere più ruoli e più corsi;
- recupero password centralizzato;
- revoca accessi e scadenze gestite in un solo punto;
- log accessi e audit per le funzioni sensibili;
- provisioning automatico degli utenti nei servizi esterni quando supportato.

### Verifica obbligatoria con Promate/Spazio Iris

Prima di scegliere l'implementazione, chiedere al fornitore:

1. supporta SAML o OpenID Connect?
2. espone API per creare utenti e iscriverli ai corsi?
3. supporta link firmati o accessi temporanei?
4. dispone di webhook o API per esito test, completamento e attestati?
5. consente personalizzazione del dominio e dell'interfaccia?
6. consente deep link diretti al corso o al test?
7. consente incorporamento sicuro oppure lo vieta?
8. quali dati devono restare nel sistema ECM per obblighi normativi?

Non promettere un login unico completo finché queste risposte non sono confermate.

## 8.3 Vimeo

Usare Vimeo come infrastruttura invisibile di hosting:

- incorporare i video direttamente nelle pagine lezione;
- configurare privacy e limitazione dell'incorporamento al dominio IPSO;
- non chiedere ai corsisti un account Vimeo;
- usare il Player SDK, se necessario, per registrare avanzamento e completamento nel LMS;
- mostrare sottotitoli, trascrizioni e controlli accessibili;
- non esporre URL pubblici dei video nei contenuti del CMS;
- verificare che il piano Vimeo in uso supporti le impostazioni richieste.

## 8.4 Promate / Spazio Iris

Promate deve essere considerato il sistema specialistico per gli adempimenti ECM, non il centro dell'esperienza corsista.

### Scenario ideale

- accesso tramite SSO;
- apertura del test ECM direttamente dalla dashboard;
- ritorno automatico al portale;
- sincronizzazione di stato e attestato.

### Scenario transitorio se SSO/API non sono disponibili

- il corsista accede prima al portale IPSO;
- la dashboard mostra una card `Test ECM` con stato e scadenza;
- prima del passaggio esterno appare una schermata breve con:
  - cosa sta per aprire;
  - perché è necessario;
  - quali credenziali usare;
  - pulsante `Apri il test ECM`;
  - link immediato all'assistenza;
- il link deve puntare direttamente al corso/test, non alla homepage di Promate;
- al ritorno nel portale, l'utente deve ritrovare il contesto;
- non incorporare il login esterno in un iframe senza approvazione tecnica e test completi su cookie, sicurezza e accessibilità.

## 8.5 Community e area sostenitori

La community deve utilizzare lo stesso account IPSO. Se resta su uno strumento esterno:

- richiedere SSO;
- usare deep link;
- mantenere header o identità riconoscibile;
- evitare una nuova password separata;
- applicare ruoli e scadenze coerenti con il corso o lo status alumni.

## 8.6 Livelli di soluzione

### Livello A — raccomandato

Portale IPSO + identità unica + LMS + Vimeo incorporato + SSO/API con Promate + community con stesso account.

### Livello B — transitorio accettabile

Portale IPSO + identità unica per area corsisti e community + Vimeo incorporato + handoff guidato a Promate con seconda autenticazione solo per ECM.

### Livello C — non sufficiente come soluzione finale

Una pagina con soli link a Vimeo, Promate e aree esterne. Riduce poco la frammentazione e non risolve il problema principale.

---

## 9. Modelli di contenuto per lo sviluppo

Usare modelli strutturati e relazioni, non pagine composte interamente da campi rich-text.

## 9.1 `Course`

Campi minimi:

```yaml
id:
slug:
title:
short_title:
subtitle:
summary:
course_type:
areas: []
audiences: []
status: open | upcoming | waitlist | closed | on_demand | archived
start_date:
end_date:
duration_label:
total_hours:
modality: in_person | online | hybrid | residential
location:
price:
price_notes:
accreditations: []
registration_url:
primary_cta_label:
secondary_cta_label:
program_download:
featured_image:
hero_video:
benefits: []
requirements: []
modules: []
teachers: []
partners: []
testimonials: []
faqs: []
professional_outcomes: []
related_events: []
related_archive_items: []
seo_title:
seo_description:
canonical_url:
updated_at:
```

## 9.2 `Event`

```yaml
id:
slug:
title:
summary:
event_type:
status: open | sold_out | waitlist | closed | past
start_datetime:
end_datetime:
timezone:
modality:
venue:
address:
price:
capacity:
registration_url:
registration_deadline:
speakers: []
program: []
related_courses: []
related_archive_items: []
recording_url:
materials: []
seo_title:
seo_description:
```

## 9.3 `Person`

Un solo modello per docenti, relatori e governance.

```yaml
id:
slug:
name:
roles: []
short_bio:
full_bio:
photo:
cv_file:
areas: []
courses: []
events: []
organization_roles: []
external_links: []
```

## 9.4 `Professional`

Può estendere `Person` ma deve avere workflow e consensi separati.

```yaml
id:
person_id:
professional_types: []
specializations: []
city:
province:
region:
country:
works_online:
languages: []
contact_email:
phone:
website:
profile_status: draft | pending | published | expired
consent_date:
last_verified_at:
```

## 9.5 `ArchiveItem`

```yaml
id:
slug:
title:
content_type: article | book | journal | video | audio | publication | bibliography | document
summary:
body:
authors: []
published_date:
historical_date:
topics: []
media_file:
external_url:
cover_image:
rights_notes:
related_courses: []
related_events: []
seo_title:
seo_description:
indexing: index | noindex
```

## 9.6 `Testimonial`

```yaml
id:
quote:
video_url:
person_name:
person_role:
course_id:
edition:
consent_confirmed:
featured:
```

## 9.7 `PartnerOrRecognition`

```yaml
id:
name:
type: partner | accreditation | affiliation | recognition
logo:
url:
description:
valid_from:
valid_to:
verified_at:
```

## 9.8 `FAQ`

Le FAQ devono essere riutilizzabili e associate a:

- corso;
- evento;
- contatti;
- area corsisti;
- metodo;
- ECM.

---

## 10. Mappa delle fonti e migrazione dei contenuti

Questa tabella indica **dove recuperare i contenuti esistenti**. Non migrare automaticamente testi e dati senza revisione editoriale.

| Area nuova | Fonte primaria | Fonti secondarie | Azione |
|---|---|---|---|
| Identità IPSO, promessa, missione, vision, posizionamento | `Brand Identity.pdf` | `ipso_strategia_obiettivi.pdf`, `biosofia.it > La Biosofia e l'Istituto` | Riscrivere e uniformare |
| Storia dell'Istituto | `biosofia.it > La Biosofia e l'Istituto` | `Brand Identity.pdf`, pagine storiche e archivio | Verificare date e governance prima della pubblicazione |
| Biosofia | `biosofia.it > La Biosofia e l'Istituto` | `ipso_architettura_brand.pdf`, `ipso_sito_web.pdf` | Sintetizzare per il pubblico e mantenere una versione estesa |
| Approccio somatorelazionale | `biosofia.it` — pagine Biosofia, Counseling e Bioenergetica | Brand Identity e documenti strategici | Fondere, eliminando ripetizioni e linguaggio obsoleto |
| Missione, visione e principi | `Brand Identity.pdf` | `ipso_strategia_obiettivi.pdf` | Usare come base editoriale, non copiare meccanicamente |
| Governance e organizzazione | `biosofia.it > La Biosofia e l'Istituto` | CV e documenti interni | Aggiornare con il cliente |
| Docenti IPSO | `biosofia.it` — pagina Istituto, pagine corso e CV | `teoriapolivagale.it > Corpo docenti`, `ipsosmart.it > Il programma`, `sentirsivivi.it` relatori | Creare un solo database persone e deduplicare |
| Certificazioni e riconoscimenti | pagine corso su `biosofia.it` | loghi e riferimenti presenti negli altri siti | Verificare validità, denominazioni e autorizzazioni |
| Counseling Somatorelazionale | `biosofia.it > Corso di Counseling` | `sentirsivivi.it > Corpo Mente Relazione`, documenti strategici | Costruire landing nuova e migrare solo dati verificati |
| Pratica Bioenergetica | `biosofia.it > Corso per Insegnanti di Pratica Bioenergetica` | `sentirsivivi.it > Risvegliare l'Energia` | Fondere presentazione, programma, docenti e FAQ |
| IPSO Smart | `ipsosmart.it` — Home e Il programma | pagina di sintesi su `biosofia.it` | Migrare integralmente, aggiornare ed eliminare il microsito |
| Teoria Polivagale | `teoriapolivagale.it` — intero sito | pagina Teoria Polivagale su `biosofia.it`, eventi collegati su `sentirsivivi.it` | Trasformare in hub pubblico + area corsisti; non ridurre a una singola pagina povera |
| Programma Teoria Polivagale | `teoriapolivagale.it > Struttura/Programma` | materiali didattici approvati | Verificare ore, durata, edizione e calendario |
| Docenti Teoria Polivagale | `teoriapolivagale.it > Corpo docenti` | pagine evento e materiali corso | Collegare al database unico persone |
| Testimonianze Teoria Polivagale | `teoriapolivagale.it > Testimonianze dei corsisti` | nuovi video e survey | Migrare con consenso e contesto |
| Community e post-training | `teoriapolivagale.it > Post training / Comunità Polivagale Italiana` | area sostenitori attuale | Ridisegnare accessi e ruoli; non pubblicare contenuti riservati |
| Operatori Polivagali | `teoriapolivagale.it > Elenco operatori polivagali` | dati aggiornati degli iscritti | Importare nel modello Rete professionale con consenso |
| Eventi in programma | `sentirsivivi.it` | eventi presenti su `biosofia.it` e `teoriapolivagale.it` | Migrare in un solo calendario |
| Eventi passati e convegni | `sentirsivivi.it > Eventi passati` | `biosofia.it > Eventi, News, Convegni`, canale video | Conservare come archivio editoriale, eliminando duplicati |
| FAQ corsi e segreteria | `sentirsivivi.it > Domande frequenti` | pagine corso e email ricorrenti della segreteria | Riorganizzare per contesto e riscrivere |
| Attestati, diplomi, convenzioni, tirocinio, pagamenti | `sentirsivivi.it > Segreteria` e pagine specifiche su `biosofia.it` | documenti interni | Collocare in area supporto o pagine amministrative, non nel menu principale |
| Pubblicazioni e libri | `biosofia.it > Pubblicazioni` | Centro W. Reich, Anima e Corpo | Migrare nell'Archivio con metadati strutturati |
| Video, audio e testi | `biosofia.it > Media` | YouTube e contenuti evento di `sentirsivivi.it` | Catalogare e collegare a temi, corsi ed eventi |
| Centro di documentazione Wilhelm Reich | `biosofia.it` | inventari e documenti interni | Creare collezione dedicata nell'Archivio |
| Psicoterapeuti e counselor di riferimento | `biosofia.it > Psicoterapeuti di riferimento` e `Counselor di riferimento` | aggiornamenti diretti | Migrare nella Rete professionale con verifica e consenso |
| Partnership | loghi e pagine corso dei quattro siti | documenti strategici | Creare database unico, rimuovere partner non più attivi |
| Contatti e sede | `biosofia.it > Contatti` | footer degli altri siti | Definire un'unica versione aggiornata |
| Privacy e pagine legali | versione più recente validata dal consulente | pagine legali dei siti esistenti | Non fondere automaticamente; revisione legale obbligatoria |
| Area corsisti e materiali | aree riservate attuali, Vimeo, Promate/Spazio Iris | tutorial esistenti | Inventariare, classificare per corso/modulo e migrare soltanto nel nuovo ambiente autenticato |

---

## 11. Problemi di contenuto da risolvere prima della migrazione

### 11.1 Data di fondazione e timeline

Le fonti utilizzano riferimenti differenti, tra cui radici dal 1974, fondazione dal 1990 e oltre trent'anni di attività. Definire con il cliente:

- data ufficiale di fondazione dell'Istituto;
- data di origine del gruppo o della tradizione precedente;
- formulazione da usare in Home, storia e dati numerici.

### 11.2 Direzione e governance

Le fonti non sono pienamente allineate su direzione, leadership e composizione degli organi. Creare un documento master approvato prima di pubblicare le schede.

### 11.3 Dati dei corsi

Non considerare affidabili come dati permanenti:

- date di partenza;
- numero dell'edizione;
- durata;
- ore;
- prezzi;
- crediti ECM;
- disponibilità posti;
- partner;
- nomi dei docenti per singola edizione.

Devono essere campi CMS aggiornabili, con data di revisione.

### 11.4 Teoria Polivagale

Verificare e uniformare:

- durata indicata come 9 o 10 mesi;
- monte ore indicato in modo differente;
- composizione dei moduli;
- regole di accesso alle registrazioni;
- durata dell'accesso ai materiali;
- requisiti ECM;
- differenza tra corsisti, operatori, alumni e sostenitori.

### 11.5 Duplicati

Non migrare più versioni dello stesso contenuto. Definire una pagina canonica e reindirizzare tutte le vecchie URL equivalenti.

---

## 12. Strategia URL e redirect

### 12.1 Regole URL

- lowercase;
- parole separate da trattini;
- niente date nell'URL salvo contenuti editoriali che lo richiedano;
- niente nomi tecnici di CMS;
- niente ID numerici visibili;
- slug stabili anche quando cambia l'edizione del corso;
- edizioni gestite come dati, non come nuove pagine duplicate.

### 12.2 Redirect tra domini

Indicazioni di massima:

```text
sentirsivivi.it/                         → <dominio>/eventi/
ipsosmart.it/                            → <dominio>/formazione/ipso-smart/
teoriapolivagale.it/                     → <dominio>/formazione/teoria-polivagale/
```

Tuttavia, non usare solo redirect generici. Creare una matrice completa:

```csv
old_domain,old_path,new_url,http_status,content_action,notes
```

Ogni pagina di valore deve puntare al contenuto nuovo equivalente.

### 12.3 Regole tecniche

- usare `301` per migrazioni definitive;
- preservare i parametri UTM quando pertinenti;
- evitare catene di redirect;
- aggiornare link interni e canonical;
- mantenere attivi dominio, DNS e certificati dei vecchi siti per i redirect;
- monitorare errori `404` e correggere le destinazioni;
- generare una pagina `404` utile con ricerca, corsi ed eventi.

---

## 13. SEO e indicizzazione

### 13.1 Sitemap XML

Generare sitemap separate:

```text
/sitemap-pages.xml
/sitemap-courses.xml
/sitemap-events.xml
/sitemap-archive.xml
/sitemap-people.xml
/sitemap-professionals.xml
```

Escludere:

- area corsisti;
- login;
- risultati di ricerca interna;
- filtri e combinazioni di query non strategiche;
- landing pubblicitarie `noindex`;
- materiali riservati.

### 13.2 Dati strutturati

Implementare quando i dati sono disponibili:

- `EducationalOrganization` o `Organization`;
- `Course` e `CourseInstance`;
- `Event`;
- `Person`;
- `Article`, `Book`, `VideoObject` e `AudioObject`;
- `BreadcrumbList`;
- `FAQPage` soltanto per FAQ realmente visibili nella pagina.

### 13.3 Collegamenti interni

Ogni pagina deve portare a una successiva azione coerente:

- articoli → corsi, eventi, newsletter;
- corsi → colloquio, iscrizione, eventi introduttivi;
- eventi → corsi e approfondimenti;
- docenti → corsi, eventi e pubblicazioni;
- archivio → contenuti correlati e percorsi;
- rete professionale → approfondimenti e formazione continua.

### 13.4 Contenuti migrati

- conservare titolo, autore e data quando corretti;
- impostare canonical nuovi;
- non cambiare URL senza redirect;
- non pubblicare contenuti duplicati provenienti da domini diversi;
- mantenere il valore storico senza far apparire come attuali date, offerte o iscrizioni concluse.

---

## 14. Accessibilità, performance e comportamento responsive

### Accessibilità

- obiettivo minimo WCAG 2.2 livello AA;
- navigazione completa da tastiera;
- focus visibile;
- gerarchia heading corretta;
- etichette esplicite nei form;
- errori associati ai campi;
- contrasto adeguato;
- testi alternativi significativi;
- sottotitoli e trascrizioni per i video;
- nessun contenuto essenziale affidato solo a colore o animazione;
- rispetto di `prefers-reduced-motion`;
- evitare autoplay con audio.

### Performance

- immagini responsive e formati moderni;
- lazy loading sotto la piega;
- poster statico per i video in hero;
- non caricare player Vimeo multipli prima dell'interazione;
- componenti e script di terze parti caricati solo quando necessari;
- caching delle pagine pubbliche;
- font ottimizzati;
- nessun carosello pesante per contenuti principali.

### Responsive

Testare almeno:

- mobile 320–430 px;
- tablet portrait e landscape;
- desktop standard;
- desktop ampio.

Non limitarsi a ridurre le dimensioni: riorganizzare priorità, CTA, tabelle, filtri e sotto-navigazioni.

---

## 15. Form, CRM e tracciamento conversioni

### 15.1 Dati da acquisire

Ogni lead deve contenere:

- pagina di origine;
- corso o evento di interesse;
- campagna/UTM;
- tipo di richiesta;
- consenso privacy;
- consenso marketing separato;
- data e ora;
- eventuale appuntamento prenotato.

### 15.2 Eventi analytics minimi

```text
course_view
course_cta_click
orientation_booking_start
orientation_booking_complete
info_form_start
info_form_submit
event_view
event_registration_click
event_registration_complete
newsletter_submit
student_login_success
lesson_start
lesson_complete
ecm_handoff_click
support_request_submit
```

Non inviare dati personali negli eventi analytics.

### 15.3 Conferme

Dopo l'invio:

- mostrare una pagina o uno stato di conferma chiaro;
- indicare tempi e modalità di risposta;
- inviare email coerente con il motivo del contatto;
- proporre una sola azione successiva pertinente.

---

## 16. Regole di design e tono applicate all'architettura

### Tono

- profondo senza essere ermetico;
- caldo senza essere informale;
- autorevole senza essere accademico;
- diretto senza essere aggressivamente commerciale.

### Da evitare

- linguaggio terapeutico o clinico non necessario;
- promesse trasformative assolute;
- tono new age o spiritualista;
- motivazionalismo aggressivo;
- sovraccarico teorico;
- CTA ripetute senza gerarchia;
- menu costruiti sulla struttura interna dell'organizzazione;
- nomi delle piattaforme tecniche come categorie UX.

### Da privilegiare

- chiarezza;
- profondità;
- concretezza;
- credibilità;
- umanità;
- competenza;
- orientamento progressivo.

---

## 17. Indicazioni specifiche per Claude Code

1. Non creare pagine statiche duplicate per docenti, partner, testimonianze, corsi o eventi.
2. Costruire componenti collegati a modelli dati riutilizzabili.
3. Separare contenuto, presentazione e configurazione.
4. Non hardcodare date, prezzi, stato iscrizioni, URL di registrazione o dominio.
5. Usare route dinamiche per corsi, eventi, docenti, archivio e professionisti.
6. Prevedere stati vuoti, errore, loading, evento concluso, corso chiuso e lista d'attesa.
7. Implementare breadcrumb e dati strutturati attraverso componenti condivisi.
8. Prevedere autorizzazioni per le route private.
9. Marcare tutte le route private come `noindex` e impedirne l'accesso senza sessione valida.
10. Non mostrare contenuti riservati nel sorgente delle pagine pubbliche.
11. Creare un componente unico per CTA corso con varianti configurabili.
12. Creare un componente unico per form contatti che accetti il contesto della pagina.
13. Creare un componente unico per card corso e card evento.
14. Consentire filtri accessibili e URL condivisibili.
15. Preparare una struttura per redirect e importazione dei contenuti legacy.
16. Tutti i link esterni devono indicare chiaramente quando portano fuori dall'ambiente IPSO.
17. Non incorporare Promate in iframe finché non sono stati verificati compatibilità, sicurezza e cookie.
18. Per Vimeo usare embed protetti e caricamento differito.
19. Non costruire un secondo menu globale per Teoria Polivagale: usare una sotto-navigazione locale.
20. Mantenere un'unica Area corsisti globale, con dashboard personalizzata per corsi e ruoli.

---

## 18. Criteri di accettazione UX e sviluppo

Il lavoro è accettabile quando:

- un nuovo visitatore comprende chi è IPSO e trova i corsi attivi dalla Home;
- la Biosofia è spiegata senza costringere l'utente a leggere contenuti specialistici lunghi;
- ogni corso ha una pagina coerente e completa;
- Teoria Polivagale è interna alla Formazione ma possiede un hub adeguato alla sua complessità;
- eventi futuri e passati sono gestiti dallo stesso modello;
- l'Archivio è ricercabile e filtrabile;
- docenti, partner e testimonianze non sono duplicati;
- la Rete professionale riusa un unico database;
- l'Area corsisti mostra video e materiali senza richiedere un login Vimeo;
- l'accesso ECM è guidato e diretto;
- il sistema è predisposto al SSO senza prometterlo prima della verifica con Promate;
- tutte le informazioni variabili sono gestibili da CMS;
- ogni vecchia pagina rilevante ha una destinazione di migrazione;
- il sito è navigabile da tastiera e responsive;
- form e CTA conservano il contesto di provenienza;
- le route private non sono indicizzate né accessibili pubblicamente.

---

## 19. Decisioni aperte da chiudere con il cliente

1. dominio definitivo: `biosofia.it` o nuovo dominio istituzionale;
2. payoff definitivo;
3. data ufficiale di fondazione e formulazione della timeline;
4. direzione e governance aggiornate;
5. elenco definitivo dei corsi al lancio;
6. dati attuali di ogni corso: date, ore, prezzi, crediti e docenti;
7. validità di certificazioni, affiliazioni e partnership;
8. sistema CRM e strumento di prenotazione colloqui;
9. requisiti di iscrizione e pagamento;
10. ruoli esatti di corsista, alumni, sostenitore e operatore;
11. durata dell'accesso ai materiali dopo il corso;
12. disponibilità di SSO/API da parte di Promate/Spazio Iris;
13. strumento futuro per community e post-training;
14. possibilità di sincronizzare esiti ECM e attestati;
15. contenuti dell'Archivio da indicizzare integralmente;
16. consensi e processo di aggiornamento della Rete professionale;
17. piano Vimeo attuale e funzioni disponibili;
18. migrazione degli account e delle credenziali esistenti;
19. responsabilità editoriale per aggiornare corsi, eventi e profili;
20. policy di assistenza e tempi di risposta ai corsisti.

---

## 20. Fonti analizzate

### Documenti forniti

- `ipso_strategia_obiettivi.pdf`
- `ipso_architettura_brand.pdf`
- `ipso_sito_web.pdf`
- `Brand Identity.pdf`

### Siti esistenti

- `biosofia.it` — identità, approccio, formazione storica, pubblicazioni, media, rete professionale e contatti;
- `sentirsivivi.it` — eventi, seminari, presentazioni, convegni, FAQ e contenuti di segreteria;
- `ipsosmart.it` — presentazione e programma IPSO Smart;
- `teoriapolivagale.it` — formazione, programma, docenti, testimonianze, operatori, community, post-training e aree riservate;
- Vimeo — hosting e riproduzione video;
- Promate / Spazio Iris — contenuti e test ECM.

---

## 21. Output richiesto a Claude Code

Produrre, nell'ordine:

1. file di configurazione delle route;
2. sitemap visuale e navigazione desktop/mobile;
3. schema dei modelli dati;
4. wireframe strutturale delle pagine hub;
5. template pagina corso;
6. template pagina evento;
7. architettura dell'Area corsisti;
8. prototipo del dashboard Teoria Polivagale;
9. matrice redirect iniziale;
10. elenco delle integrazioni con stato `confermato`, `da verificare`, `non disponibile`;
11. lista finale di domande bloccanti, senza inventare dati mancanti.

Non procedere con integrazioni reali, autenticazione o migrazione massiva prima che le decisioni aperte siano state confermate.
