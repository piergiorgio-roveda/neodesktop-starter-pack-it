---
name: init
description: "Prima configurazione del neoDesktop. USE WHEN: l'utente lancia /init, oppure è la prima sessione e CLAUDE.md contiene ancora segnaposto [...]. Intervista l'utente, compila CLAUDE.md e context/_profilo.md nella lingua di lavoro, prepara lo spazio e manda il primo messaggio a Piergiorgio."
---

# /init — prima configurazione del tuo neoDesktop

Si lancia **una volta**, all'inizio. Trasforma lo scheletro (con i segnaposto `[...]`)
nel neoDesktop personale dell'utente, spiegando ogni passo mentre lo fa. L'utente sta
alla tastiera; tu lo guidi.

## Principio

Non scaricare nulla e non fare magie: **costruisci e racconta**. Spiega a parole semplici
cosa stai facendo e perché, un passo alla volta. L'utente non è necessariamente tecnico.

## Lingua di lavoro

Questo è uno spazio bilingue. La lingua non è decisa in anticipo: la **raccogli**
nell'intervista (campo `[LINGUA]`) e da quel momento governa tutto.

- **Conduci l'intervista** nella lingua in cui l'utente ti scrive; appena hai confermato
  `[LINGUA]`, prosegui tutta l'interazione in quella lingua.
- **Scrivi tutti i file in `[LINGUA]`.** Sia quelli che compili (`CLAUDE.md`,
  `context/_profilo.md`, il primo messaggio a PJ), sia i quattro **file-guida statici** che
  il template porta già scritti in italiano (`communications/_README.md`,
  `communications/_needs.md`, `context/clients/_README.md`, `context/projects/_README.md`):
  questi vanno **ri-renderizzati** nella lingua scelta (step 5 e 6). Non lasciare prosa in
  una lingua diversa da quella scelta.
- In `CLAUDE.md` non ti limiti a sostituire i segnaposto: **rendi la prosa** (titoli,
  testo delle sezioni, regole) in `[LINGUA]`. I **token fissi** restano invariati e non si
  traducono mai — gli slug dei comandi (`/init`, `/message-to-pj`, `/message-from-pj`), i
  valori `direction` (`to-pj` / `from-pj`), il nickname `PJ`. Si localizza solo la prosa
  attorno (es. "il canale con Piergiorgio (PJ)").

## Procedura

0. **Prima configurazione o rilancio?** Prima di ogni altra cosa, controlla se i file del
   template — anzitutto `CLAUDE.md` — contengono ancora segnaposto `[...]`. Se **ci sono**
   segnaposto residui, è la prima configurazione: prosegui dallo step 1. Se **non** ce ne
   sono più, lo spazio è **già configurato**: non rifare l'init da capo (vedi "Dopo /init"),
   salta al ramo di aggiornamento del profilo.
1. **Benvenuto.** In 2-3 frasi, spiega cos'è questo spazio: una cartella + documenti che
   descrivono come lavora + un agente che li legge. Niente gergo.
2. **Intervista.** Una domanda alla volta, con calma. Raccogli: nome e come preferisce
   essere chiamato; professione e dominio; **lingua di lavoro** (`[LINGUA]` — chiedila
   presto, così il resto dell'intervista e tutti i file la rispettano); 1-3 workflow
   ricorrenti (cosa entra, cosa esce, dove rallenta); strumenti che usa oggi. Se ha già
   risposto a queste domande via email a Piergiorgio, parti da quelle e chiedi solo conferma.
3. **Compila `CLAUDE.md`.** Sostituisci ogni segnaposto `[...]` con le risposte e **rendi la
   prosa in `[LINGUA]`** (vedi sezione "Lingua di lavoro"). Mostra il risultato e chiedi
   conferma prima di salvare. Verifica che non resti alcun `[...]` residuo.
4. **Compila `context/_profilo.md`.** Scrivi il profilo in prosa breve, in `[LINGUA]`.
5. **Spiega la memoria, e ri-renderizza le sue guide.** Mostra `context/clients/` e
   `context/projects/`: qui nasceranno un file per cliente e per progetto, man mano. Non
   crearne ora a vuoto. Traduci in `[LINGUA]` i due file-guida statici
   `context/clients/_README.md` e `context/projects/_README.md` (sono in italiano nel
   template): rendi la prosa, lascia invariati i nomi di file e cartella.
6. **Spiega il canale con PJ, e ri-renderizza le sue guide.** Mostra `/message-to-pj` e
   `/message-from-pj` e a cosa servono. Traduci in `[LINGUA]` `communications/_README.md` e
   `communications/_needs.md` (in italiano nel template): **rendi la prosa ma lascia
   invariati i token fissi** — i nomi dei campi del frontmatter (`direction`, `status`,
   `date`, `type`, `reply_to`), i valori `to-pj`/`from-pj`/`unread`/`read`/`answered`, e il
   blocco YAML di esempio. Si traduce solo il testo attorno.
7. **Primo messaggio a PJ.** Crea un messaggio `to-pj` di "setup completato", così
   Piergiorgio sa che sei partito e prepara i primi aggiornamenti. Procedi così:
   - **Crea il file** in `communications/` con nome `<YYYY-MM-DD>-to-pj-<slug>.md` (data di
     oggi in ISO `YYYY-MM-DD`; `<slug>` = breve slug descrittivo **in `[LINGUA]`**, es.
     `setup-completato` / `setup-complete` — è prosa, non un token fisso), seguendo lo schema di
     `communications/_README.md`. Il frontmatter è:

     ```
     ---
     direction: to-pj
     status: unread
     date: <YYYY-MM-DD>
     ---
     ```

     Niente campo `type`: non è una domanda. Sotto il blocco, scrivi in `[LINGUA]` un breve
     riepilogo del profilo (nome, professione/dominio, lingua, i workflow ricorrenti
     raccolti) — quel tanto che basta a PJ per orientarsi.
   - **Invia il messaggio.** Aggiungi *solo questo file* allo stage (`git add` del percorso
     del messaggio, non `git add -A`) e fai un commit locale con un messaggio descrittivo.
   - **Sincronizza, best-effort.** Tenta `git push`. Se riesce, il messaggio è arrivato a PJ.
     Se **fallisce** — tipicamente perché il repo non ha ancora un remote configurato (è il
     caso normale al primo avvio) — **degrada con grazia**: il commit locale è comunque fatto,
     quindi spiega all'utente che il messaggio è salvato in locale e che la sincronizzazione
     con Piergiorgio avverrà non appena il remote sarà configurato. Non è un errore da
     correggere: è lo stato atteso del primo run.
8. **Chiusura.** Di' che è tutto pronto e che può iniziare a usare il suo Claude facendo
   domande sul suo lavoro.

## Dopo /init

Questa skill non serve più una volta che la configurazione è completa. Il segnale concreto
è l'**assenza di segnaposto `[...]`** nei file del template (vedi step 0): se non ce ne sono
più, lo spazio è già configurato.

Se l'utente rilancia `/init` su uno spazio già configurato, **non resettare nulla**.
Riconoscilo apertamente e proponi semmai di **aggiornare il profilo**:

- chiedi cosa è cambiato (nuovo dominio, nuovi workflow, strumenti diversi, lingua);
- riscrivi **solo le parti toccate** di `CLAUDE.md` e ricompila `context/_profilo.md`,
  mantenendo `[LINGUA]` come lingua di lavoro corrente;
- non ricreare i file di scaffolding né sovrascrivere il lavoro esistente. Un nuovo
  messaggio a PJ qui è facoltativo: mandalo solo se l'aggiornamento è sostanziale.
