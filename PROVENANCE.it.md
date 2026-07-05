# PROVENANCE — neodesktop-starter-pack-it

> [!IMPORTANT]
> **Non fare `git push` su questo repository pubblico.** È il *modello* condiviso di tutti,
> non il tuo spazio di lavoro. Per adottare il tuo neoDesktop:
> 1. Crea un repository **tuo e privato** e **clona/ricostruisci** questo pack dentro di esso
>    (non "Fork": un fork su GitHub resta **pubblico** — i tuoi dati finirebbero esposti).
> 2. Personalizzalo con `/init` **sul tuo repo privato**.
> 3. Quando vuoi attivare il canale, **aggiungi `piergiorgio-roveda` come collaboratore alla
>    TUA repo privata** — non chiedere accesso a questa.

Questo documento racconta **da dove viene** questo starter-pack, **cosa contiene ogni file**
e **come puoi ricostruirlo da solo**. È pensato per essere letto con calma — anche con
l'aiuto del tuo assistente AI — prima di decidere se e come adottarlo.

Lo trovi insieme ai file del **repo pubblico**
https://github.com/piergiorgio-roveda/neodesktop-starter-pack-it, ed è disponibile anche in
**PDF** (vedi sotto), così puoi leggerlo senza scaricare nulla.

---

## 1. Perché esiste questo documento

Un neoDesktop è uno spazio di lavoro fatto di **cartelle e documenti di testo** che
descrivono come lavori, più un agente AI (Claude Code) che li legge e lavora dentro al tuo
processo. Niente app, niente abbonamento: file tuoi, sul tuo computer.

C'è però un dettaglio delicato. Questi file **parlano all'agente**: il `CLAUDE.md` è il suo
"contratto", le skill in `.claude/skills/` sono procedure che l'agente esegue. Sono testo
innocuo — non lanciano nulla da soli — ma **un buon assistente AI, se vede arrivare da fuori
dei file che istruiscono un agente, ti avvisa**: «attenzione, questi documenti pilotano me;
sei sicuro della loro provenienza?». È il suo sistema immunitario che funziona, ed è giusto
così.

Per questo lo starter-pack **non ti viene spinto addosso**. È pubblico, ispezionabile,
versionato, e soprattutto: questo documento ti permette di **costruirtelo da solo**, così
**l'autore dei tuoi file sei tu** — non una fonte esterna che si auto-installa. L'agente che
ti aiuta sta eseguendo le *tue* istruzioni, non quelle di uno sconosciuto. L'allarme non
scatta perché non c'è nulla di cui allarmarsi.

C'è anche un'inversione che vale la pena notare: quando vorrai attivare il canale di
assistenza, **sei tu a creare un repository privato e a invitare Piergiorgio** come
collaboratore. Non è lui che entra nel tuo spazio: sei tu che apri la porta, quando e se
vuoi.

## 2. I tre strati: modello, agente, neoDesktop

Per capire bene cos'hai davanti, conviene tenere separate tre cose che spesso si confondono in
una sola.

- **Il modello** è la testa che ragiona — Opus, Sonnet, e fuori da Anthropic GPT, Gemini e
  altri. Lo costruiscono e lo migliorano i grandi laboratori; cambia in fretta, ed è uguale
  per tutti.
- **L'agente** sono le mani e gli occhi — il software che mette quella testa a lavorare sui
  tuoi file: Claude Code, Cowork, oppure Codex di OpenAI. Anche questo te lo dà un fornitore,
  ed è identico per chiunque lo installi.
- **Il neoDesktop** è la **tua conoscenza e il tuo metodo** — i tuoi progetti, le tue regole,
  le decisioni prese e il perché, il modo in cui fai le cose. Questo strato non ha un
  fornitore: sei tu. È l'unico davvero tuo, e l'unico che **cresce** mentre lavori.

I primi due te li danno già fatti e cambiano in fretta; il terzo lo costruisci e resta.
**Questo starter-pack è il punto di partenza del terzo strato**: lo scheletro del tuo
neoDesktop, da riempire con il tuo lavoro. Il modello e l'agente li porti tu (qui, Claude
Code); il neoDesktop lo rendi tuo con `/init` e con l'uso quotidiano.

## 3. Dove trovare e come leggere questo documento

Con ogni probabilità stai leggendo il **PDF**, che ti è arrivato **prima ancora del repo**.
Ecco i **due indirizzi da cui parte tutto** — sono la cosa più importante di questa pagina:

> ### Repo pubblico
>
> **https://github.com/piergiorgio-roveda/neodesktop-starter-pack-it**
>
> ### Sorgente di questo documento (Markdown)
>
> **https://github.com/piergiorgio-roveda/neodesktop-starter-pack-it/blob/master/PROVENANCE.it.md**

Da lì in poi:

- **Il PDF**, scaricabile da questo indirizzo (Google Drive, accessibile a chiunque abbia il
  link): https://drive.google.com/file/d/1b_Vcumax_HnJvGRzYTIp3rTHA28lqInM/view?usp=sharing —
  è autosufficiente: contiene tutto ciò che serve per capire e ricostruire il pacchetto,
  anche senza aprire il repo.
- **Con l'aiuto del tuo assistente AI**, dandolo in pasto al tuo Claude Code (o a un altro
  LLM) per farti spiegare, tradurre o guidare passo-passo: è scritto apposta per essere
  leggibile sia da te sia da un agente.

Leggilo come una mappa: prima il *perché* (questa parte), poi il *cosa* (la mappa di
provenienza), infine il *come* (la guida costruttiva).

## 4. A cosa serve — due usi

Questo documento serve a **due** scopi, che corrispondono a **due strade diverse e
alternative**. Sono davvero separate: scegline una, non ti servono entrambe.

1. **Clonare, e capire ogni file.** Questa strada **usa il repo**: cloni o scarichi
   `neodesktop-starter-pack-it`, e la *mappa di provenienza* (sezione 6) ti dice, file per
   file, cosa fa e perché c'è. Ti serve a ispezionare con cognizione ciò che hai scaricato.
2. **Ricostruire da zero, senza toccare il repo.** Questa strada **non usa il repo**: parti da
   una cartella vuota e la *guida costruttiva* (sezione 7) ti accompagna a ricreare lo stesso
   spazio passo-passo, insieme al tuo Claude Code. Niente `git clone`, niente `git pull`,
   nessun download. La guida è **autosufficiente**: tutto ciò che serve per costruire i file è
   già scritto qui dentro, in questo documento (o nel suo PDF). **Non devi leggere il repo per
   ricostruirlo** — al massimo puoi *sbirciare* il testo canonico di un file nel browser se ti
   fa piacere confrontare, ma è un extra facoltativo, mai un passaggio richiesto.

Le due strade arrivano allo stesso punto. In entrambi i casi, alla fine lancerai `/init`, che
rende lo spazio **tuo** (profilo, lingua, workflow). Non devi scegliere subito: puoi leggere,
capire, e decidere dopo.

## 5. Adozione senza fretta, e gli issue pubblici

**Non c'è alcuna fretta.** Anche se più avanti sarà utile attivare la condivisione del repo e
fare pratica con i messaggi (`/message-to-pj`, `/message-from-pj`), **non è necessario
farlo subito**: prenditi il tempo per capire e approfondire ogni aspetto. Lo scopo di questo
documento è proprio toglierti la pressione — adotti quando ti senti pronto.

**Per i dubbi, usa gli issue del repo pubblico.** Su
`github.com/piergiorgio-roveda/neodesktop-starter-pack-it`, nella scheda **Issues**, puoi
aprire una domanda o un suggerimento. Funziona così:

- apri un nuovo issue, scegli il tipo (domanda o suggerimento), scrivi con parole tue;
- Piergiorgio risponde lì, e così lo starter-pack migliora per tutti — le domande di uno
  aiutano i successivi.

⚠️ **Gli issue sono pubblici per loro natura**: chiunque può leggerli. È un bene per il
rodaggio collettivo, ma tienilo presente. **Se preferisci non esporti**, scrivi a Piergiorgio
**in privato** (email o messaggio diretto): nessun problema, la porta privata resta sempre
aperta.

---

## 6. Mappa di provenienza — ogni file, cosa fa, perché

Tutti i file derivano dal **template neoDesktop**, lo scheletro comune da cui parte ogni
spazio. Sono **testo semplice** (Markdown e qualche file di configurazione): leggibili,
modificabili, senza formati chiusi. I **segnaposto** sono parole in maiuscolo tra parentesi
quadre — `[NOME]`, `[LINGUA]`, … — che `/init` compila durante la prima intervista.

### Documenti di base

| File | Cosa fa | Perché c'è |
|---|---|---|
| `README.md` | Il punto d'ingresso del repo, in italiano (la versione inglese vive nel repo gemello `neodesktop-starter-pack-en`). Spiega cos'è e il flusso di adozione self-service. | È la prima cosa che si legge atterrando sul repo pubblico. |
| `CLAUDE.md` | Il **contratto** dell'agente: chi sei, come lavori, e le regole che segue sempre. L'agente lo legge a ogni sessione. Contiene segnaposto (`[NOME]`, `[PROFESSIONE]`, `[DOMINIO]`, `[LINGUA]`, `[WORKFLOW]`, `[STRUMENTI]`, `[TONO]`). | È il cuore del metodo: un prompt scritto una volta vale come un contratto stabile, così non ripeti le stesse istruzioni ogni volta. |
| `PROVENANCE.it.md` | Questo documento. | Permette di capire e ricostruire il pacchetto in autonomia. |

### Configurazione del repo

| File | Cosa fa | Perché c'è |
|---|---|---|
| `.gitignore` | Elenca i file che Git ignora: roba di sistema/editor (`.DS_Store`, `Thumbs.db`, `.vscode/`) e gli **override personali** dell'agente (`.claude/settings.local.json`). | Tiene il repo pulito e impedisce che impostazioni locali e personali finiscano nella storia condivisa. |
| `.gitattributes` | Una riga: `* text=auto eol=lf`. Normalizza i fine-riga dei file a LF. | Evita differenze spurie tra Windows e Mac/Linux: la storia del repo resta pulita. |

> **Nota importante — un file che *non* c'è: `.claude/settings.json`.** Di proposito **non**
> esiste nel pacchetto. Quel file serve a dire all'agente quali comandi può eseguire senza
> chiederti conferma (ad esempio i comandi Git). Riceverlo "già pronto" da fuori
> significherebbe **pre-autorizzare** comandi prima del tuo consenso — esattamente il tipo di
> cosa che, vista da un agente prudente, somiglia a un raggiro. Perciò il pacchetto **non lo
> include**: sarà `/init` a **proportene la creazione in chiaro**, spiegandoti cosa concedi, e
> solo **dopo un tuo sì esplicito** (vedi la skill `init`). Se rifiuti, l'agente continuerà a
> chiederti conferma comando per comando: funziona lo stesso.

### Le skill — i comandi dell'agente (`.claude/skills/`)

Ogni skill è un file `SKILL.md` che definisce un comando. I nomi dei comandi
(`/init`, `/message-to-pj`, `/message-from-pj`), il nickname `PJ` e i token tecnici dei
messaggi (`to-pj`, `from-pj`, i campi del frontmatter) sono **fissi**: non si traducono mai,
nemmeno nella versione in un'altra lingua.

| File | Comando | Cosa fa |
|---|---|---|
| `.claude/skills/init/SKILL.md` | `/init` | La **prima configurazione**, da lanciare una volta. Ti dà il benvenuto, ti intervista (nome, professione, dominio, **lingua di lavoro**, workflow ricorrenti, strumenti), compila `CLAUDE.md` e `context/_profilo.md` nella tua lingua, ri-rende nella tua lingua i file-guida, **ti chiede il consenso per i permessi Git** (e solo allora scrive `.claude/settings.json`), e manda il primo messaggio a Piergiorgio. |
| `.claude/skills/message-to-pj/SKILL.md` | `/message-to-pj` | Scrive un messaggio **verso** Piergiorgio: lo raccoglie con te, lo formatta come file in `communications/` e lo invia via Git (best-effort: se manca ancora il collegamento a GitHub, resta salvato in locale). |
| `.claude/skills/message-from-pj/SKILL.md` | `/message-from-pj` | Legge i messaggi **da** Piergiorgio: sincronizza, mostra i non letti, li marca letti e ti guida a rispondere alle sue domande, tenendo il filo domanda↔risposta. |

### La memoria (`context/`)

| File | Cosa fa | Perché c'è |
|---|---|---|
| `context/_profilo.md` | Il tuo profilo in prosa breve: chi sei, come lavori, strumenti, tono preferito. Nel template ha i **segnaposto**, che **`/init` compila** durante l'intervista — non si scrive a mano. | L'agente lo legge per risponderti già nel modo giusto. |
| `context/clients/_README.md` | Guida della cartella clienti: un file per cliente, **man mano** che servono (non crearne a vuoto). | Spiega come cresce la memoria sui clienti senza riempirla di file vuoti. |
| `context/projects/_README.md` | Guida della cartella progetti: un file per progetto, man mano. | Idem, per i progetti. |

### Il canale con Piergiorgio (`communications/`)

| File | Cosa fa | Perché c'è |
|---|---|---|
| `communications/_README.md` | Definisce il **formato dei messaggi**: nome file (`<data>-<direction>-<slug>.md`), il blocco YAML in testa (`direction`, `status`, `date`, `type`, `reply_to`), gli stati (`unread` → `read` → `answered`) e chi li cambia. | È la specifica condivisa che fa funzionare lo scambio asincrono in modo prevedibile. |
| `communications/_needs.md` | Un quaderno dei **bisogni emersi**: cose che vorresti fare e che l'agente non sa ancora coprire. Di solito è l'agente ad annotarle (è una regola del `CLAUDE.md`). | Alimenta gli aggiornamenti mirati: Piergiorgio legge e prepara miglioramenti su misura. |

---

## 7. Guida costruttiva — ricostruire il repo da zero

Questa sezione ti accompagna a **ricreare lo stesso spazio senza scaricare il repo**. L'idea:
apri il tuo Claude Code in una cartella vuota e, seguendo questi passi, **tu e il tuo agente
scrivete insieme** i file. Alla fine avrai uno spazio equivalente — e `/init` lo renderà tuo.

Questa guida è **autosufficiente**: i passi qui sotto contengono tutto ciò che serve, e **non
richiedono di aprire il repo**. Se — e solo se — vuoi confrontare un file che hai scritto con
il suo "testo canonico", puoi **leggerlo nel browser** sul repo pubblico (GitHub mostra ogni
file senza bisogno di clonare): resta un riferimento facoltativo, non un download e non un
passaggio obbligato della ricostruzione.

### Prerequisiti

- **Visual Studio Code** con l'estensione **Claude Code** installata.
- **Git** installato (per salvare la storia dei file; il collegamento a GitHub può arrivare
  dopo).
- Una **cartella vuota** sul tuo computer, che diventerà il tuo neoDesktop.

### I passi

1. **Apri la cartella vuota** in VS Code e avvia Claude Code al suo interno.
2. **Crea i due file di configurazione del repo:**
   - `.gitattributes` con l'unica riga `* text=auto eol=lf`.
   - `.gitignore` che ignori `.DS_Store`, `Thumbs.db`, `.vscode/` e `.claude/settings.local.json`.
3. **Crea `CLAUDE.md`, il contratto.** Chiedi al tuo agente di scrivere un documento con
   queste sezioni, lasciando i segnaposto tra parentesi quadre da compilare dopo:
   - intestazione `neoDesktop — [NOME]` e una nota che spiega che è il contratto, leggibile e
     modificabile;
   - **Chi sono**: `[NOME]`, `[PROFESSIONE]`, `[DOMINIO]`, `[LINGUA]`;
   - **Come lavoro**: `[WORKFLOW]` (uno per riga) e `[STRUMENTI]`;
   - **Le regole che l'agente segue sempre**: parlare in `[LINGUA]`; tenere il tono `[TONO]`;
     mantenere i file leggibili e tuoi; chiedere quando manca una decisione invece di
     inventare; **annotare in `communications/_needs.md` i bisogni** che non sa ancora coprire;
   - **Come è organizzato lo spazio**: una mappa di `context/` e `communications/`;
   - **Il canale con Piergiorgio (PJ)**: i comandi `/message-to-pj` e `/message-from-pj`, con
     i messaggi scambiati via `git push` / `git pull`.
4. **Crea la memoria (`context/`):**
   - `context/_profilo.md`: un profilo breve con i segnaposto `[NOME]`, `[PROFESSIONE]`,
     `[DOMINIO]`, `[LINGUA]`, `[WORKFLOW]`, `[STRUMENTI]`, `[TONO]`.
   - `context/clients/_README.md` e `context/projects/_README.md`: due brevi guide che dicono
     «un file per cliente / per progetto, man mano che servono — non crearne a vuoto».
5. **Crea il canale (`communications/`):**
   - `communications/_README.md`: descrivi il formato dei messaggi — nome file
     `<YYYY-MM-DD>-<direction>-<slug>.md`; il blocco YAML con `direction` (`to-pj`/`from-pj`,
     fissi), `status` (`unread`/`read`/`answered`), `date`, `type` (`question`, solo se
     aspetta risposta), `reply_to` (solo nelle risposte); e chi cambia gli stati (ognuno
     gestisce i messaggi che riceve).
   - `communications/_needs.md`: un quaderno vuoto dei bisogni, con un esempio commentato.
6. **Crea le skill (`.claude/skills/`).** Una skill è semplicemente un file di testo:
   `<nome>/SKILL.md`, con un breve frontmatter (`name`, `description` con il relativo
   `USE WHEN`) e la procedura. Il tuo agente le scrive come **qualsiasi altro documento** —
   non serve che il comando esista già, né alcuno strumento speciale: stai solo scrivendo del
   Markdown. Ricorda che i nomi dei comandi e i token `to-pj`/`from-pj`/`PJ` sono **fissi**:
   - **`init/SKILL.md`** (`/init`): benvenuto → intervista (raccogli **presto** la `[LINGUA]`)
     → compila `CLAUDE.md` e `context/_profilo.md` nella lingua scelta → ri-rendi nella stessa
     lingua i file-guida → **chiedi il consenso per i permessi Git e, solo se acconsente,
     scrivi `.claude/settings.json`** (vedi passo 7) → manda il primo messaggio a PJ → chiudi.
   - **`message-to-pj/SKILL.md`** (`/message-to-pj`): raccogli il messaggio, capisci se è una
     domanda (`type: question`) o una comunicazione, scrivilo in `communications/` col
     formato concordato, mostra e conferma, poi invia con `git add` del **solo** file +
     `git commit` + `git push` best-effort.
   - **`message-from-pj/SKILL.md`** (`/message-from-pj`): `git pull` best-effort, trova i
     `from-pj` `unread`, mostrali, classifica (risposta a una tua domanda / domanda di PJ /
     comunicazione), aggiorna gli stati e guida l'eventuale risposta, mantenendo il legame
     `reply_to`.
7. **Lascia i permessi a `/init`, non al seed.** **Non** creare `.claude/settings.json` a
   mano adesso. Sarà `/init`, durante la configurazione, a spiegarti quali permessi Git
   concedi e a scrivere quel file **solo dopo il tuo sì**. Così nessun permesso è
   pre-concesso da una fonte esterna: lo decidi tu, in chiaro.
8. **Inizializza Git e fai il primo commit.** `git init`, poi metti in stage i file che hai
   creato (con percorsi espliciti) e fai un commit iniziale. Il collegamento a un repository
   remoto può arrivare quando vorrai.
9. **Lancia `/init`** — la skill che hai appena scritto al passo 6. Qui si chiude il
   *bootstrap*, e vale la pena dirlo chiaramente perché sembra un paradosso e non lo è: per
   **avere** il comando `/init` non ti serviva già il comando `/init`. Al passo 6 il tuo agente
   ha scritto `init/SKILL.md` come **semplice file di testo** — e scrivere un file non richiede
   nessuna skill preesistente. Una volta salvato quel file, Claude Code **scopre** la skill
   dalla cartella `.claude/skills/` e ti mette a disposizione il comando `/init`. Prima il file
   (scritto dall'agente), poi il comando (che quel file abilita): nessun uovo-gallina. Se il
   comando non compare subito, chiudi e riapri Claude Code (o ricarica la finestra di VS Code):
   le skill vengono lette all'avvio della sessione. Poi lancialo: ti intervista e trasforma lo
   scheletro nel tuo spazio personale, nella tua lingua. Da qui in poi è tuo.

### Verifica

Hai finito quando: non resta nessun segnaposto `[...]` dopo `/init`; esistono `CLAUDE.md`,
`PROVENANCE.it.md` (questo documento, se lo vuoi tenere), le tre skill, e le cartelle
`context/` e `communications/` con le loro guide; e **non** è presente `.claude/settings.json`
finché non l'hai concesso tu.

---

## Una nota finale

Questo pacchetto è volutamente piccolo e trasparente. Se qualcosa non torna, o se hai un'idea
per migliorarlo, apri un issue (pubblico) o scrivi in privato. Non c'è un modo "giusto" di
andare di fretta: c'è solo il tuo ritmo.

## Una nota su geoDesktop

Un'ultima cosa, per non fare confusione con i nomi. **geoDesktop** è il neoDesktop di
Piergiorgio: il suo spazio personale, ottimizzato per la sua professione — il GIS — e per il
suo lavoro da libero professionista. È un neoDesktop come quello che costruirai tu, solo più
maturo, cresciuto in mesi di lavoro.

Ha però anche un secondo ruolo: è il **"fratello maggiore"** che seguirà tutti i nuovi
neoDesktop che nascono — incluso il tuo. Non con una connessione diretta dentro il tuo spazio
(quella non c'è, e non ci sarà), ma attraverso il **sistema di messaggi** che metterai in
piedi quando vorrai (`/message-to-pj` e `/message-from-pj`): tu mandi un bisogno o una
domanda, Piergiorgio — affiancato da geoDesktop — prepara un aggiornamento mirato e te lo
rimanda. Ognuno resta a casa propria; a viaggiare sono solo i messaggi.

E sì: **questo documento l'ha scritto proprio geoDesktop.** Consideralo un assaggio di cosa
diventa un neoDesktop quando lo si vive per un po'.
