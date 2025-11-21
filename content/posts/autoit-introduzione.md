---
date: '2025-11-20T23:00:19+01:00'
draft: false
title: 'AutoIt v3: il “piccolo grande” linguaggio per Windows'
categories: []
tags: []
cover:
  image: images/autoit.webp
  hiddenInList: false
---


*Una guida rapida per scoprire di cosa si tratta, perché può tornarti utile e come scrivere il tuo primo programma in meno di cinque minuti o imparare a programmare.*

---

### Cosa è AutoIt v3?

AutoIt è un linguaggio di scripting, nato per automatizzare Windows. Con il tempo è cresciuto e si evoluto alla versione v3, diventando un vero e proprio linguaggio di programmazione **general-purpose**, pur rimanendo estremamente **leggero** e **facile da apprendere**.  
La sintassi ricorda il BASIC: poche righe per fare quello che con C/C++ faresti con dozzine di righe di codice, senza bisogno di runtime aggiuntivi o IDE particolari.

Il mio corso Autoit per principianti:
{{< youtube 7Zkf_Fnjpao >}}

---

### Vale la pena conoscerlo?

Risposta rapida? Sì.
Qui sotto elencherò i 6 motivi per impararlo.

1. **BASIC-like**: se hai mai scritto una macro o smanettato con VB, ti sentirai a casa, la sintassi è semplice e permissiva, adatta per chi vuole imparare a programmare.

2. **Automazione di Windows**: può cliccare, digitare, spostare finestre, compilare moduli, persino installare software senza intervento dell'utente.

3. **Compilazione nativa**: un file sorgente `.au3` si trasforma in un `.exe` standalone con un semplice comando.

4. **Creazione di GUI**: crea finestre, bottoni e input-box con poche istruzioni.

5. **Potente ma minuscolo**: l’intero ambiente pesa meno di 1 MB, non lascia tracce e funziona sulle versioni di Windows da XP fino a Windows 11.

6. **Community e UDF**: esistono centinaia di librerie scritte dagli utenti (User Defined Functions) per gestire reti, PDF, Excel, hardware, giochi…  

---

### Primi passi: installazione

- Scarica il pacchetto ufficiale da [autoitscript.com](https://www.autoitscript.com/site/autoit/downloads/)  
- Lancia il setup: installerà l’interprete, il compilatore **Aut2Exe** e l’editor base **SciTE** già configurato
- Per un esperienza migliore consiglio di scaricare anche il setup completo di [SciTE per Autoit](https://www.autoitscript.com/site/autoit-script-editor/)  

Finito! Non serve riavviare, non servono dipendenze esterne.

---

### Il tuo primo script “Hello, World!”

Apri SciTE, crea un nuovo file e salvalo con nome `test.au3`.  
Digita:

```autoit
; Il mio primo script AutoIt
MsgBox(0, "AutoIt v3", "Hello, World!")
```

Spieghiamo la riga:  

- `;` è un commento (ignorato dal motore)  
- `MsgBox(flag, titolo, testo)` mostra una MessageBox, il flag `0` significa “solo il pulsante OK”  

Salva il file sorgente premento **CTRL+S**
Premi **F5** (o clicca “Tools → Go”).  
Congratulazioni, hai appena scritto ed eseguito il tuo primo programma AutoIt!

## Prossimi passi

- **Leggi l’help**: F1 in SciTE apre la *bibbia* di AutoIt (funzioni, flag, esempi di codice).  
- **Gioca con Send() e MouseMove()** per automatizzare il tuo primo “robot” che riempie un form.  
- **Esplora le UDF**: visita il forum ufficiale e dai un occhiata alle librerie per Excel, Selenium, dispositivi, ecc.

---

### Conclusione

AutoIt v3 è come avere un **assistente digitale personale**, ma è anche molto di più di questo, si tratta ormai di un vero e proprio linguaggio di programmazione tascabile, potente e immediato.

Io per esempio ho creato un Password manager **open source** usando interamente Autoit:

Provalo!
- Codice sorgente: [Open Password Manager (OPM)](https://github.com/Jyukat/Open-Password-Manager.git)
- File eseguibile: [Release](https://github.com/Jyukat/Open-Password-Manager/releases/download/release/Open.Password.Manager.Exe)

Che tu debba automatizzare installazioni, creare utility aziendali o semplicemente divertirti con la programmazione, AutoIt ti permette di **passare dall’idea al risultato in poche righe**.

Adesso la prossima volta che ti trovi a ripetere a lavoro 50 volte le stesse azioni col mouse e tastiera, ricorda che potresti farle fare ad Autoit mentre ti prendi un caffè.

---

### Fonti e approfondimenti:  
Sito ufficiale Autoit :
> https://www.autoitscript.com/site/

Il mio corso Autoit su Youtube:
{{< youtube 7Zkf_Fnjpao >}}