# neoDesktop — [NOME]

> Questo file è il **contratto** del tuo agente: chi sei, come lavori, e le regole che
> segue ogni volta, senza che tu le ripeta. È scritto in linguaggio leggibile: puoi
> aprirlo e modificarlo quando vuoi.
>
> I segnaposto sono parole in maiuscolo tra parentesi quadre — `[NOME]`, `[PROFESSIONE]`,
> `[LINGUA]` — e li compila `/init` durante la prima intervista. `/init` scrive tutto il
> file nella tua lingua di lavoro, quella che indichi in `[LINGUA]`.

## Chi sono

- Nome: [NOME]
- Professione: [PROFESSIONE]
- Dominio / settore: [DOMINIO]
- Lingua di lavoro: [LINGUA]

## Come lavoro

I workflow che ripeto più spesso (cosa entra, cosa esce, dove rallenta) — uno per riga:

- [WORKFLOW]

Strumenti che uso oggi:

- [STRUMENTI]

## Le regole che l'agente segue sempre

- Parlami sempre in [LINGUA].
- Tieni il tono che preferisco — [TONO] — per esempio risposte brevi e concrete, senza giri di parole.
- I file restano leggibili e miei: niente formati chiusi, niente magie nascoste.
- Quando non sai qualcosa, o serve una mia decisione, chiedimelo — non inventare.
- Quando emerge un bisogno che non sai ancora coprire, annotalo tu in
  `communications/_needs.md`: così Piergiorgio può preparare un aggiornamento mirato.

## Come è organizzato questo spazio (la memoria)

- `context/` — la mia memoria di lavoro.
  - `context/_profilo.md` — chi sono e come lavoro.
  - `context/clients/` — un file per cliente (nascono man mano).
  - `context/projects/` — un file per progetto (nascono man mano).
- `communications/` — il canale con Piergiorgio (vedi sotto).

## Il canale con Piergiorgio (PJ)

Piergiorgio mi segue nel tempo. La comunicazione è asincrona e passa da
`communications/`:

- `/message-to-pj` — scrivo un messaggio a Piergiorgio.
- `/message-from-pj` — leggo le sue risposte e rispondo alle sue domande.

I messaggi sono file in `communications/`, scambiati con `git push` / `git pull`.
