# Usare Claude Code e Claude Cowork sulla stessa cartella

Il tuo neoDesktop è una cartella di file di testo sul tuo computer. Claude Code (il terminale) e Claude Cowork (l'app Desktop, con i Project) sono due modi diversi di lavorare su quella cartella, ma solo se **entrambi puntano davvero alla stessa cartella sul disco**. Se non lo fanno, uno dei due lavora alla cieca su file che non vede.

## Il problema tipico

Se apri Claude Cowork, crei un Project e **alleghi dei file** (PDF, documenti) direttamente in chat, quei file restano dentro il Project, non sul tuo disco. Sono contesto per quella conversazione, non file veri dentro la tua cartella neoDesktop. Se poi apri un terminale nella stessa cartella e lanci Claude Code, non li troverà: legge solo ciò che è fisicamente su disco.

## Come collegarli correttamente

1. **Parti dalla cartella, non dalla chat.** Crea (o apri) la cartella del tuo neoDesktop sul disco, ad esempio `~/neodesktop` o la cartella del tuo progetto.
2. **Apri un terminale in quella cartella** e lancia `claude` (Claude Code). Da qui in poi è questa la cartella che condividerai con Cowork.
3. **Metti i file dentro la cartella**, non in chat. Un PDF, un documento, un'immagine: trascinali nella cartella con il Finder o Esplora risorse, non caricarli come allegato di una conversazione.
4. **In Claude Cowork, collega la cartella come spazio di lavoro locale**, non come allegato di singoli file. È l'opzione che dà a Cowork accesso reale al filesystem della cartella, non solo al testo di un file caricato.
5. Da questo momento, Code e Cowork leggono e scrivono negli **stessi file**. Modifichi un documento dal Finder, o lo aggiorna uno dei due strumenti: l'altro lo vede.

## Cosa resta separato

Una cosa non si condivide mai tra Code e Cowork: **la cronologia della chat**. Sono due conversazioni distinte, ciascuna con la propria memoria. Quello che uno dei due "sa" da una conversazione non passa automaticamente all'altro: passa solo se lo scrivi in un file dentro la cartella. Se vuoi che un'informazione sia disponibile a entrambi, il posto giusto non è dirla in chat: è scriverla in un file del tuo neoDesktop.

È, in fondo, lo stesso principio di sempre: il tuo neoDesktop è la cartella, non la conversazione. Qualsiasi agente che la legge, terminale o app desktop, vede la stessa conoscenza, perché sta nei file, non in una chat che scompare.
