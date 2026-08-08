# Questionfisio

Applicazione web per la somministrazione di scale di valutazione clinica e il monitoraggio pre/post trattamento in fisioterapia e riabilitazione.

**🔗 App online:** https://TUOUSERNAME.github.io/questionfisio/

---

## Caratteristiche

- **Funziona offline** — una volta caricata, non serve connessione
- **Nessuna installazione** — si apre in Safari/Chrome e si aggiunge alla schermata Home
- **Dati locali** — tutto rimane sul dispositivo (localStorage), nessun server
- **Anti-bias di ancoraggio** — i punteggi sono nascosti al paziente durante la compilazione, e il form riparte sempre vuoto

---

## Scale incluse

### 🦵 Arto Inferiore
| Scala | Descrizione |
|---|---|
| **LEFS** | Lower Extremity Functional Scale (20 item, 0–80) |
| **HOOS-12** | Hip disability and Osteoarthritis Outcome Score (12 item) |
| **KOOS** | Knee injury and Osteoarthritis Outcome Score (42 item, 5 subscale) |
| **FAOS** | Foot and Ankle Outcome Score (42 item, 5 subscale) |
| **VISA-A** | Tendinopatia achillea (8 item, 0–100) |
| **VISA-P** | Tendinopatia rotulea (8 item, 0–100) |
| **VISA-H** | Tendinopatia prossimale ischiocrurali (8 item, 0–100) |
| **VISA-G** | Sindrome trocanterica / GTPS (8 item, 0–100) |

### 💪 Arto Superiore
| Scala | Descrizione |
|---|---|
| **QuickDASH** | Disabilities of Arm, Shoulder and Hand (11 item, 0–100) |

### 🦴 Rachide
| Scala | Descrizione |
|---|---|
| **Roland Morris** | Disabilità lombalgia (24 item, 0–24) |
| **NDI** | Neck Disability Index (10 item, 0–100%) |

### 🧠 Neurologiche
| Scala | Descrizione |
|---|---|
| **Berg Balance Scale** | Equilibrio funzionale (14 item, 0–56) |
| **FRAT** | Falls Risk Assessment Tool (Parte 1 + checklist) |
| **NPS** | Neuropathic Pain Scale (10 qualità del dolore) |
| **MIDAS** | Migraine Disability Assessment (giorni persi) |

### 🩺 Cliniche / Rischio
| Scala | Descrizione |
|---|---|
| **Wells DVT** | Probabilità pre-test trombosi venosa profonda |
| **FRAX** | Screening fattori di rischio frattura osteoporotica |
| **FIQR** | Revised Fibromyalgia Impact Questionnaire (21 item) |
| **POSAS 2.0** | Scar Assessment Scale — Osservatore + Paziente |
| **Flags LBP** | Red / Yellow / Blue flags nella lombalgia |
| **Edema** | Pitting score con riferimento visivo (1+ → 4+) |
| **Örebro ÖMPSQ-SF** | Screening rischio cronicizzazione (10 item, 1–100) |

### 📋 Generaliste
| Scala | Descrizione |
|---|---|
| **NRS** | Dolore a riposo + dolore durante movimenti specifici |
| **TSK-11** | Tampa Scale of Kinesiophobia |
| **SF-12** | Stato di salute — punteggi PCS e MCS |
| **Pain Drawing** | Mappa del dolore disegnabile su figura anteriore/posteriore |

### ⚙️ Personalizzate
- **Scala manuale** — qualsiasi punteggio inserito a mano
- **Misurazioni cliniche** — cm, mm, gradi (ROM), kg, N o unità personalizzata

---

## Funzionalità

### Fasi di trattamento
Sei fasi selezionabili (T0 pre-trattamento → T5) per ogni paziente e ogni scala.

### Anti-bias di ancoraggio
- I punteggi **non vengono mai mostrati** durante la compilazione
- Il form riparte **sempre vuoto**, anche se la scala è già stata compilata in quella fase
- Un toggle 🔒/🔓 nella scheda paziente permette al clinico di rivelare i punteggi solo quando serve

### Grafici pre/post
- Linea di andamento per ogni scala con delta vs T0
- Linee multiple per scale multidimensionali (SF-12 PCS/MCS, KOOS/FAOS 5 subscale, POSAS Osservatore/Paziente, NRS riposo + movimenti)
- Confronto visivo dei manichini per il Pain Drawing
- Pulsante **"Vedi questionario"** per il confronto item-per-item, con evidenziazione ⚠ delle risposte cambiate

### Export
- **PDF** — report completo con tabelle per fase e dettaglio item
- **CSV** — tutti i dati di tutti i pazienti
- **Backup JSON** — copia di sicurezza completa, ripristinabile

### Bibliografia
Ogni scala include un pannello espandibile con soglie di interpretazione, MCID, MDC e riferimenti bibliografici primari (fonti: Shirley Ryan AbilityLab RehabMeasures, MDCalc, koos.nu, posas.nl, ACI NSW).

---

## Installazione

Questionfisio è una **Progressive Web App**: si installa direttamente dal browser, senza App Store.

### iPad / iPhone (Safari)
1. Apri il link dell'app in **Safari** (non Chrome)
2. Tocca l'icona **Condividi** — il quadrato con la freccia verso l'alto
3. Scorri e tocca **Aggiungi alla schermata Home**
4. Tocca **Aggiungi**

### Android (Chrome)
Comparirà automaticamente una barra in basso con il pulsante **Installa**. In alternativa: menu ⋮ → **Installa app**.

### Computer (Chrome / Edge)
Comparirà l'icona di installazione ⊕ nella barra degli indirizzi, oppure appare la barra con **Installa** in basso.

Una volta installata, l'app funziona **completamente offline** grazie al service worker.

---

## Backup dei dati

I dati sono salvati nel browser del dispositivo. Safari può cancellarli se lo spazio si esaurisce o se svuoti la cache.

**Consiglio:** dopo ogni seduta usa **💾 Dati → Backup dati (JSON)** e salva il file su iCloud Drive o Google Drive.

---

## Note legali

Questo strumento è destinato a professionisti sanitari qualificati come supporto alla raccolta di outcome misurati dal paziente (PROM). Non sostituisce il giudizio clinico né costituisce dispositivo medico certificato.

Le scale incluse sono strumenti pubblicati in letteratura scientifica. Alcune (POSAS, KOOS, FAOS, HOOS) sono soggette a licenza per uso commerciale: consultare i rispettivi siti ufficiali per i termini d'uso.

---

## Sviluppo

Applicazione single-page in React, compilata in un unico file HTML autonomo.

```
Stack: React 18 + Recharts + Vite
Output: file HTML singolo (~890 KB) senza dipendenze esterne
Storage: localStorage del browser
```
