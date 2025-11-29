---
date: '2025-11-28T14:47:40+01:00'
draft: false
title: 'Perché programmare in C/C++ oggi è spesso sconveniente'
categories: []
tags: []
cover:
  image: images/cpp-vs-electron.png
  hiddenInList: false
---


*Scopri perché programmare in C/C++ oggi è sconveniente. Memory safety, costi di sviluppo, toolchain complesse e boom delle app desktop Electron.*

---

Quando si parla di linguaggi di programmazione, **C e C++** sono sicuramente i primi a venire in mente a qualsiasi programmatore, essi occupano un posto speciale nei nostri cuori.

È veloce, potente, capace di tutto. Eppure, oggi più che mai, programmare app desktop in C++ può essere **frustrante**. Non perché il linguaggio sia *“sbagliato”*, ma perché il panorama tecnologico e l'industria sono cambiati totalmente: le esigenze di oggi richiedono <u>sicurezza</u>, <u>sviluppo rapido</u> e un ecosistema più orientato alla produttività che all’ottimizzazione estrema.

In questo articolo voglio esplorare alcuni motivi per cui C++ sta perdendo terreno, soprattutto nel mondo delle applicazioni desktop, e come questo vuoto sia stato riempito da strumenti come Electron, con tutti i suoi difetti e pregi.

---

## 1. **Il nodo principale: la sicurezza della memoria**

C e C++ concedono grandi poteri… e richiedono grande responsabilità e soprattutto molte competenze. La gestione della memoria è uno dei suoi punti di forza, e purtroppo anche il suo tallone d’Achille.

### **Buffer overflow, use-after-free, memory leak…**

Sono da anni che programmatori hanno a che vedere con bug fixing critici, questo perchè quando si programma in C/C++ e facile cadere in errori soprattutto quando mancano certe accortezze e si è distratti.

Sono problemi noti da decenni, e continuano a tormentarci. Qualsiasi programmatore C++ sa che basta una distrazione:

- Un `delete` mancante

- Un puntatore non inizializzato

- Un array riempito oltre i suoi limiti

In questo post non entro nei dettagli, altrimenti l'articolo sarebbe noioso e troppo tecnico, magari affronterò l'argomento più avanti in un altro post.

### **Gli strumenti moderni non sono sufficienti**

È vero: C++ ha smart pointer, RAII, librerie di alto livello, e gli standard recenti hanno introdotto pratiche più sicure. Ma il linguaggio rimane strutturalmente non memory-safe.

Non esiste un *garbage collector*.  

Non esistono *controlli automatici dei limiti*.  

Non esiste un *modello di memoria intrinsecamente sicuro*.

Certo, puoi programmare “in modo sicuro”, ma richiede disciplina, esperienza, analisi statica e test approfonditi. Ed è qui che i linguaggi moderni prendono il largo.

---

## 2. **Il confronto con i linguaggi memory-safe**

Oggi linguaggi come **Rust**, **Go**, **C#** o **Java** offrono una sicurezza maggiore. Rust, in particolare, ha dimostrato che *(non sempre)* è possibile ottenere prestazioni che si avvicinano al C++ *senza* sacrificare la sicurezza della memoria.

Le aziende anche quelle senza scopo di lucro, stanno iniziando a rendersi conto dei costi del C++:

- continue patch per problemi di memoria

- vulnerabilità ripetute

- tempi di sviluppo solitamente più lunghi

Tant’è che persino Mozilla, Microsoft, Amazon e Google stanno adottando Rust in componenti critici.

Questo non significa però che il C++ sia un linguaggio da buttare, diciamo che forse è meglio passare a uno standard che introduca la memory-safe, un esempio lampante sotto gli occhi di tutti è il **Kernel Linux**, che dall' inizio del 2025 sta cominciando a convertire e ad implementare patch in **Rust**.

> Ovviamente Rust comporta anch'esso delle problematiche note; i disservizi di CLOUDFLARE che hanno colpito quasi tutto internet a Novembre del 2025, sono stati causati da poche righe di codice Rust.
> 
> Per piu dettagli a riguardo visitate leggete questo [articolo](https://www.miamammausalinux.org/2025/11/il-post-mortem-del-disastro-cloudflare-ci-parla-di-rust-errori-banali-e-illusioni-sulla-sicurezza/)

---

## 3. **Il paradosso delle app desktop moderne**

Mentre i linguaggi nativi lottano con problemi strutturali, il mondo delle app desktop ha preso una direzione completamente diversa: **l’adozione massiva di Electron**.

Electron, nel bene e nel male, ha cambiato il mercato.

### **Perché Electron ha vinto**

- La stessa codebase per Windows, macOS e Linux

- Utilizzo esclusivo di tecnologie Web

- Debug semplice

- Librerie infinite

- UI più facile da costruire rispetto a toolkit nativi complessi

E così, applicazioni come *VS Code, Discord, Spotify, Netflix, Telegram, ChatGPT* e molti altri hanno dominato il panorama desktop… pur essendo essenzialmente **browser** mascherati da app.

### **Il problema secondo me: Electron è pesante**

Bella quella ragazza conosciuta in discoteca, faceva buio ed era truccatissima, poi ci sei andato a letto e al mattino successivo si sveglia presentandosi come UGINA FANTOZZI !

Più o meno Electron è questo.

Applicazioni che potrebbero pesare pochi megabyte diventano facilmente:

- centinaia di MB sul disco

- centinaia di MB di RAM

- lente a partire

- voraci di risorse

Paradossalmente, molti sviluppatori evitano C++ più che altro perché è difficile e richiedono skill e preparazione, non per i problemi legati alla memory safe… e finiscono con l'usare framework che sprecano risorse.

---

## 4. **C++ può ancora avere un ruolo?**

Assolutamente sì, soprattutto dove servono:

- prestazioni estreme

- controllo totale del sistema

- latenza ridotta

- compatibilità con codice storico

- sviluppo di motori grafici, giochi, sistemi embedded (es: aduino), driver

Ma per molte applicazioni moderne — soprattutto desktop — il costo di usarlo è spesso superiore ai benefici.

La tendenza attuale è chiara:

- i nuovi progetti lo usano sempre meno

- l’industria si sposta verso linguaggi memory-safe

- il mondo consumer preferisce applicazioni cross-platform veloci da sviluppare

C++ svolgerà sempre un ruolo importante, ma non è più il linguaggio “universale” di una volta.

---

## **Conclusione**

Programmare in C++ oggi non è “sbagliato”, ma spesso diventa sconveniente quando si considerano sicurezza, tempi di sviluppo e gestione della memoria. Se da un lato abbiamo un linguaggio potente ma potenzialmente pericoloso, dall'altro abbiamo framework come **Electron** che risolve i problemi di produttività a scapito dell’efficienza o linguaggi come **Rust** che gestiscono meglio la memoria, ma non sono immuni a <u>cattive condotte di programmazione</u>.

Il futuro probabilmente troverà un equilibrio: linguaggi come Rust si faranno strada, e i toolkit nativi moderni torneranno ad essere competitivi. Nel frattempo, dobbiamo accettare che l’evoluzione del software passa anche attraverso compromessi: non sempre i più eleganti, ma quelli che permettono di costruire prodotti più rapidamente e in modo più sicuro.

In fondo, la programmazione non è solo questione di linguaggi: è questione di scelte, ed esigenze reali.