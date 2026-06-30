---
name: message-from-pj
description: "Legge i messaggi di Piergiorgio (PJ) e gestisce le risposte. USE WHEN: l'utente lancia /message-from-pj, o chiede se ci sono novità/messaggi da Piergiorgio. Sincronizza, mostra i non letti, li marca letti e guida la risposta alle domande di PJ."
---

# /message-from-pj — leggere Piergiorgio e rispondere

**Lingua.** Queste istruzioni si rivolgono a te, l'agente. Mostra, riassumi i messaggi e
dialoga con l'utente **nella lingua del suo profilo** (`[LINGUA]` in `CLAUDE.md` /
`context/_profilo.md`). Restano **fissi** in ogni lingua i token tecnici: lo slug del
comando e i valori `direction` (`to-pj` / `from-pj`).

## Procedura

1. **Sincronizza.** Prova `git pull` **best-effort** per scaricare gli eventuali nuovi
   messaggi di Piergiorgio. Se manca il remote (repo non ancora collegato a GitHub),
   **non è un errore**: prosegui leggendo i file `from-pj` già presenti in locale e
   avvisa che la sincronizzazione con PJ partirà quando il remote sarà configurato.
2. **Trova i non letti.** Cerca in `communications/` i file `direction: from-pj` con
   `status: unread`. Se non ce ne sono, dillo e fermati.
3. **Mostra.** Presenta ogni messaggio non letto in modo leggibile (data + contenuto),
   nella lingua del profilo.
4. **Classifica ogni messaggio** in uno dei tre casi e gestiscilo:
   - **(a) Risposta di PJ a una tua domanda** — il `from-pj` ha un campo `reply_to` che
     punta a un tuo `to-pj` con `type: question`. È PJ che risponde: marca il `from-pj`
     a `status: read` e porta il `to-pj` originale (la tua domanda) a `status: answered`,
     chiudendo il thread. Mostra la risposta accanto alla domanda.
   - **(b) Domanda di PJ** — il `from-pj` ha `type: question`. Marca a `status: read`.
     Poi **proponi** di rispondere, ma **non forzare** la risposta nello stesso run: se
     l'utente vuole rispondere ora, vai allo step 5; se preferisce rinviare, lascia il
     messaggio a `read` — risponderà più avanti rilanciando il comando, e la domanda
     resta riconoscibile come ancora aperta.
   - **(c) Comunicazione semplice** — nessun `type: question`. Marca a `status: read`,
     non serve altro.
5. **Comporre la risposta a una domanda di PJ** (solo se l'utente sceglie di rispondere
   ora — caso (b)). Guida l'utente a comporre la risposta nella lingua del profilo. Crea
   un nuovo file `to-pj` (nome `<YYYY-MM-DD>-to-pj-<slug>.md`) con frontmatter:
   - `direction: to-pj`
   - `status: unread`
   - `date:` la data di oggi in ISO `YYYY-MM-DD`
   - `reply_to: <nome-file-della-domanda-from-pj>`

   Poi porta il messaggio originale di Piergiorgio (la domanda `from-pj`) a
   `status: answered`.
6. **Invia.** `git add` dei **soli file modificati o creati** (path espliciti, mai
   `-A`): gli stati aggiornati e l'eventuale risposta. `git commit` con messaggio chiaro.
   Quindi prova `git push` **best-effort**: se riesce, conferma; se manca il remote,
   l'aggiornamento resta valido in locale e raggiungerà PJ alla prossima sincronizzazione
   — avvisa e prosegui senza trattarlo come errore.

## Note

- Non scrivere tu i messaggi `from-pj`: li scrive Piergiorgio dal suo lato. Tu ne cambi
  solo lo `status` (`unread` → `read`, e `answered` quando è una domanda a cui hai
  risposto).
- Mantieni il collegamento domanda↔risposta con `reply_to`, così il thread resta
  leggibile in entrambe le direzioni.
