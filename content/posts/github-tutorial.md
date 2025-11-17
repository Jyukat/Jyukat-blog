---
date: '2025-11-16T16:32:55+01:00'
draft: false
title: 'Git & Github Tutorial per principianti'
categories: [tutorials]
tags: [git, github, guide]
cover:
    image: images/github-guide.webp
    hiddenInList: false
---

Sono da tantissimi anni che programmo a livello amatoriale per progetti personali molto piccoli,
 ma ormai da un paio di anni ho contribuito a sviluppare applicativi con un piccolo team di developer sparsi in Europa.

Non sapevo nulla di come gestire un progetto più ampio, da qui ho dovuto imparare ad usare Git e Github.

In questa guida mirata per principianti voglio farvi vedere le principali funzioni di Git.

## ❓ Cos'è Git

Git è un sistema di controllo versione distribuito e open source che traccia la cronologia delle modifiche ai file di un progetto.

Permette ai team di sviluppare in modo collaborativo, creando copie locali del codice su cui lavorare insieme, e di gestire le modifiche in modo efficiente tramite **snapshot** (istantanee) e **commit** (salvataggi). È ampiamente utilizzato nello sviluppo software per la sua **flessibilità**.

Una volta che avrete imparato ad usare Git anche per i vostri progetti personali
non ne farete a meno di usarlo!

**Iniziamo con il tutorial !**

## 🔧 1. Installazione di Git

Ovviamente dobbiamo avere Git installato sul nostro sistema:

Per prima cosa dovrete scaricalo da: [https://git-scm.com](https://git-scm.com), seguire l'istallazione passo-passo e assicurarsi di usare le impostazioni predefinite.

Una volta installato Git nel vostro computer aprite il vostro terminale e digitate il comando:

```bash
git --version
```

Se l'installazione è avvenuta con successo premendo INVIO il terminale mostrerà la versione di Git installata. Fatto questo adesso siamo pronti a configurare Git per poi creare una cartella per il vostro progetto.

## 🧱 2. Configurazione iniziale (una sola volta per PC)

Sempre nel vostro terminale digitate questi due comandi :

```bash
git config --global user.name "Tuo Nome"
git config --global user.email "tua.email@example.com"
```

> I comandi sopra elencati servono per identificarti nei commit. GitHub usa queste info per associare i commit al tuo profilo.

## 📁 3. Creare un nuovo progetto locale

```bash
mkdir mio-progetto
cd mio-progetto
git init
```

- `mkdir`: crea una cartella.
- `cd`: entra nella cartella.
- `git init`: trasforma la cartella in un **repository Git locale**.

## 🌐 4. Collegare il repository locale a GitHub

Vai su [https://github.com](https://github.com) (registrati se ancora non lo hai fatto) → crea un **nuovo repository** (es. `mio-progetto`). **Non aggiungere README** per ora.

Poi nel terminale:

```bash
git remote add origin https://github.com/tuonome/mio-progetto.git
```

- `git remote add`: collega il tuo progetto locale al repository su GitHub.
- `origin` è il nome standard del remoto (può essere qualsiasi nome, ma `origin` è la convenzione).

## ✍️ 5. Lavorare sul progetto e salvare i cambiamenti

### a. Controllare lo stato

```bash
git status
```

> Mostra quali file sono stati modificati, aggiunti o eliminati.

### b. Aggiungere i file alla "area di staging"

```bash
git add .
```

> Aggiunge **tutti** i file modificati o nuovi. Puoi anche usare `git add nomefile.txt` per aggiungere solo uno specifico file.

### c. Fai un commit (salvataggio definitivo)

```bash
git commit -m "Primo commit: aggiunto file iniziali"
```

> Crea una instantanea del progetto in questo momento. Il messaggio deve essere **chiaro e breve**.

## ☁️ 6. Caricare il progetto su GitHub

```bash
git branch -M main
git push -u origin main
```

- `git branch -M main`: rinomina il branch principale in `main` (GitHub usa questo nome).
- `git push -u origin main`: carica i commit su GitHub. La flag `-u` serve per collegare il branch locale al remoto (dopo il primo push basterà usare `git push`).

---

## 🔄 7. Scaricare aggiornamenti dal repository remoto

Se lavori da un altro PC o altri collaboratori hanno fatto modifiche:

```bash
git pull
```

> Scarica e **unisce** automaticamente le modifiche dal repository remoto al tuo progetto locale.

---

## 🌿 8. Lavorare con i branch (rami)

I branch servono per sviluppare funzionalità senza rovinare il codice principale.

### a. Creare un nuovo branch

```bash
git checkout -b nuova-funzionalita
```

> Crea e passa automaticamente al nuovo branch.

### b. Tornare al branch principale

```bash
git checkout main
```

### c. Unire un branch al main

```bash
git merge nuova-funzionalita
```

> **Unisce** le modifiche del branch `nuova-funzionalita` nel branch corrente (es. `main`).

---

## 🧹 9. Comandi utili extra

| Comando                                                 | Spiegazione                                                                                        |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `git log`                                               | Mostra la cronologia dei commit                                                                    |
| `git diff`                                              | Mostra le differenze tra file modificati ma non ancora commitati                                   |
| `git clone https://github.com/tuonome/mio-progetto.git` | Scarica un repository esistente da GitHub                                                          |
| `git reset --hard`                                      | Annulla **tutte** le modifiche locali non commitate (**attenzione: perdi il lavoro non salvato!**) |

---

## ✅ Flusso di lavoro tipico (riassunto)

```bash
git status
git add .
git commit -m "Descrizione chiara"
git push
```

## CONSIGLI PRATICI E ALTRI SPUNTI

- ### Commit frequenti: Fai commit piccoli e frequenti

- ### Messaggi descrittivi: Usa messaggi di commit chiari

- ### Pull prima del push: Sempre aggiornare prima di pushare

- ### Branch per feature: Usa branch separati per ogni feature

- ### Backup regolare: Pusha regolarmente su GitHub

## Video tutorial

{{< youtube jpOqT_JWric >}}
