---
name: message-to-pj
description: "Scrive un messaggio asincrono a Piergiorgio (PJ). USE WHEN: l'utente lancia /message-to-pj, o dice che vuole scrivere/chiedere qualcosa a Piergiorgio. Raccoglie il messaggio in modo interattivo, lo formatta in communications/ e lo invia via git."
---

# /message-to-pj — scrivere a Piergiorgio

Canale asincrono verso Piergiorgio. Il messaggio diventa un file in `communications/`,
che lui legge quando sincronizza il repo.

**Lingua.** Queste istruzioni si rivolgono a te, l'agente. Dialoga con l'utente **nella
lingua del suo profilo** (`[LINGUA]` in `CLAUDE.md` / `context/_profilo.md`): domande,
conferme e spiegazioni vanno in quella lingua. Restano invece **fissi** in ogni lingua i
token tecnici — lo slug del comando, il valore `direction: to-pj` e il token `to-pj` nel
nome del file: non si traducono.

## Procedura

1. **Chiedi cosa vuole dire.** Se non l'ha già scritto, fagli raccontare il messaggio a
   parole sue. Aiutalo a renderlo chiaro, senza snaturarlo.
2. **Capisci il tipo.** È una **domanda** (aspetta risposta) o una **comunicazione**
   (informa e basta)? Questo decide se il file porta il campo `type: question`.
3. **Scrivi il file.** In `communications/`, nome `<YYYY-MM-DD>-to-pj-<slug>.md`, con il
   blocco YAML del formato definito in `communications/_README.md`:
   - `direction: to-pj`
   - `status: unread`
   - `date:` la data di oggi in ISO `YYYY-MM-DD`
   - `type: question` **solo** se è una domanda (altrimenti ometti il campo)

   Sotto il blocco YAML c'è il corpo del messaggio.
4. **Mostra e conferma.** Fai vedere il messaggio formattato e chiedi conferma.
5. **Invia.** `git add` del **solo file appena scritto** (path esplicito, mai `-A`), poi
   `git commit` con un messaggio chiaro. Quindi prova `git push` **best-effort**:
   - se il push riesce, conferma che il messaggio è partito;
   - se fallisce perché manca il remote (il repo non è ancora collegato a GitHub),
     **non è un errore**: il commit locale è valido e regge. Avvisa l'utente che il
     messaggio è salvato in locale e raggiungerà Piergiorgio appena il remote sarà
     configurato e partirà la sincronizzazione.

   Se l'utente non ha familiarità, spiega in una riga che stai "spedendo" il messaggio.

## Note

- Un file = un messaggio. Non accumulare più messaggi nello stesso file.
- **Stati di un `to-pj`.** Una volta inviato, gli stati del tuo `to-pj`
  (`unread` → `read`) li transiziona **Piergiorgio dal suo lato** quando lo legge: non
  toccarli tu. L'unica eccezione è la chiusura del thread di una **domanda** `to-pj`:
  quando arriva la risposta di PJ (un `from-pj` con `reply_to` al tuo `to-pj`), è
  `/message-from-pj` a portare il `to-pj` originale a `answered`.
- Non toccare i messaggi `from-pj`: quelli si gestiscono con `/message-from-pj`.
