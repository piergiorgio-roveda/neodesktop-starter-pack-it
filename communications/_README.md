# Comunicazioni con Piergiorgio (PJ)

Il canale asincrono tra te e Piergiorgio. Ogni messaggio è un file in questa cartella,
scambiato con `git push` / `git pull`. Si gestisce con i comandi `/message-to-pj` e
`/message-from-pj` — di norma non serve toccare i file a mano.

## Formato di un messaggio

Nome file: `<YYYY-MM-DD>-<direction>-<slug>.md` — es. `2026-06-30-from-pj-benvenuto.md`.

Ogni file inizia con un piccolo blocco YAML (il frontmatter, tra due righe `---`).
Esempio pronto da copiare e incollare:

```yaml
---
direction: from-pj
status: unread
date: 2026-06-30
type: question
reply_to: 2026-06-29-to-pj-domanda-export.md
---
```

Sotto il blocco c'è il testo del messaggio, in markdown libero.

### I campi

| Campo | Obbligatorio | Valori | Significato |
|---|---|---|---|
| `direction` | sì | `to-pj` \| `from-pj` | `to-pj` = da te verso Piergiorgio; `from-pj` = da Piergiorgio verso te. Questi token sono **fissi**, non si traducono. |
| `status` | sì | `unread` \| `read` \| `answered` | stato di lettura / risposta (vedi sotto). |
| `date` | sì | data ISO `YYYY-MM-DD` | data del messaggio, es. `2026-06-30`. |
| `type` | no | `question` | presente **solo** se il messaggio aspetta una risposta; altrimenti si omette. |
| `reply_to` | no | nome di un file | il file a cui questo messaggio risponde; presente **solo** nelle risposte. |

## Stati

- `unread` — appena arrivato, non ancora letto dal destinatario.
- `read` — letto dal destinatario.
- `answered` — era una domanda (`type: question`) e la risposta è stata scritta; il file
  della risposta la collega tramite `reply_to`.

### Chi cambia gli stati

Per la transizione di stato ogni messaggio è "di competenza" del lato che lo riceve:

- **Messaggi `from-pj`** (da Piergiorgio verso te): li gestisci tu con `/message-from-pj`.
  Il comando li porta da `unread` a `read`; se è una domanda e scrivi la risposta, la
  domanda passa ad `answered`.
- **Messaggi `to-pj`** (da te verso Piergiorgio): li transiziona **Piergiorgio dal suo
  lato** — li legge in geoDesktop e li porta a `read`. Se una tua `to-pj` era una domanda
  (`type: question`), torna ad `answered` quando `/message-from-pj` riceve la risposta di
  Piergiorgio: il comando riconosce il `reply_to` che punta alla tua domanda e la marca
  `answered`.

## `_needs.md`

Il file `_needs.md` raccoglie i bisogni che emergono mentre lavori: cose che vorresti
fare e che l'agente non sa ancora coprire. Di norma è **l'agente** ad annotarli lì in
automatico (è una regola del `CLAUDE.md`); puoi comunque aggiungerne a mano quando vuoi.
Piergiorgio li legge e ti prepara aggiornamenti mirati.
