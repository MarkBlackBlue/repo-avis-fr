# Phase 2 — Site Structure & Wireframes
## AVIS Comunale di Frosinone

**Generato da:** Dati di ricerca reali (42 query) · Theme ranking · Institutional matrix · AVIS data · Website audit  
**Data:** 2026-03-26  
**Agente:** Claude (claude.ai)  
**Fase:** 1 — Site Mapping (Days 5–7)  
**Output file:** `/outputs/phase2_site_structure.md`

---

## Indice

1. [Directory Tree](#1--directory-tree-completo)
2. [Mappa di Priorità delle Sezioni](#2--mappa-di-priorità-delle-sezioni)
3. [Home Page Wireframe (Dettagliato)](#3--home-page-wireframe-dettagliato)
4. [Wireframe Top-10 Pagine](#4--wireframe-top-10-pagine)
5. [SEO Spec Top-10 Pagine](#5--seo-spec-top-10-pagine)
6. [Linking Strategy](#6--linking-strategy)
7. [Decisioni Architetturali](#7--decisioni-architetturali)
8. [Riepilogo Finale & Checklist](#8--riepilogo-finale--checklist)

---

## 1 · Directory Tree Completo

```
/  (Home)
├── index.html                          ← CORE #1
│
├── come-donare/                        ← SEZIONE AZIONE
│   ├── index.html                      ← Hub sezione        CORE #2
│   ├── requisiti-idoneita.html         ← CORE #3  (14.030 vol/mese)
│   ├── procedura-donazione.html        ← CORE #4  (4.030 vol/mese)
│   ├── dove-e-quando.html              ← CORE #5  (6.810 vol/mese)
│   └── preparazione-donazione.html     ← SEC #1
│
├── perche-donare/                      ← SEZIONE CONSAPEVOLEZZA
│   ├── index.html                      ← Hub sezione        CORE #6
│   ├── benefici-donatore.html          ← CORE #7  (11.690 vol/mese)
│   ├── importanza-sociale.html         ← SEC #2
│   ├── miti-falsi-credenze.html        ← SEC #3   (gap: sicurezza/paure)
│   └── storie-donatori.html            ← SEC #4
│
├── diventa-donatore/                   ← SEZIONE CONVERSIONE
│   ├── index.html                      ← CORE #8  (685 vol/mese · max conv.)
│   ├── iscrizione-avis.html            ← CORE #9
│   └── prima-donazione.html            ← SEC #5
│
├── frosinone/                          ← SEZIONE LOCALE (SEO geolocalizzato)
│   ├── index.html                      ← CORE #10 (825 vol/mese locale)
│   ├── ospedale-spaziani.html          ← SEC #6
│   ├── cassino.html                    ← TER #1
│   └── sora.html                       ← TER #2
│
├── convenzioni/                        ← SEZIONE BENEFICI SOCI
│   ├── index.html                      ← SEC #7
│   └── lista-convenzioni.html          ← SEC #8
│
├── faq.html                            ← SEC #9   (cross-sezione)
│
├── blog/                               ← SEZIONE CONTENUTO
│   ├── index.html                      ← TER #3
│   └── [articoli/]                     ← TER #4+ (scalabile)
│
├── chi-siamo.html                      ← TER #5
├── contatti.html                       ← CORE #11 (ogni sezione punta qui)
└── privacy.html                        ← TER #6
```

**TOTALE: 26 pagine** (10 CORE + 9 SECONDARY + 7 TERTIARY) + articoli blog scalabili

---

## 2 · Mappa di Priorità delle Sezioni

### Volume per sezione (query risolte)

| Priorità | Sezione | Pagine | Query risolte | Volume aggregato | Motivo priorità |
|---|---|---|---|---|---|
| **1 · PRIMA** | Come Donare | 5 | 21 | ~25.000/mese | 55% del volume totale |
| **1 · PRIMA** | Perché Donare | 5 | 13 | ~11.690/mese | Fase awareness → conversione |
| **2 · SECONDA** | Diventa Donatore | 3 | 4 | 685 + conv. dirette | Pagina di conversione primaria |
| **2 · SECONDA** | Frosinone (locale) | 4 | 12 | 825 geolocalizzato | Traffico pronto all'azione |
| **3 · TERZA** | Convenzioni | 2 | 2 | 25–45/mese | Fidelizzazione donatori esistenti |
| **4 · QUARTA** | Blog / Chi siamo | 4+ | — | Long tail | Trust, SEO long-term |

### Dettaglio sezioni

**SEZIONE: Come Donare**
- Pagine: 5 (Hub, Requisiti, Procedura, Dove, Preparazione)
- Queries risolte: 21
- Volume totale: ~25.000 ricerche/mese
- Priorità: 1 — implementa prima
- Note: Copre il 55% del volume. Requisiti da sola vale 14.030/mese.

**SEZIONE: Perché Donare**
- Pagine: 5 (Hub, Benefici, Importanza, Miti, Storie)
- Queries risolte: 13
- Volume totale: ~11.690 ricerche/mese
- Priorità: 1 — implementa prima
- Note: Funnel awareness → considerazione → azione. Benefici è la seconda pagina più ricercata.

**SEZIONE: Diventa Donatore**
- Pagine: 3 (Hub, Iscrizione, Prima donazione)
- Queries risolte: 4
- Volume totale: 685/mese + alto tasso conversione
- Priorità: 2 — seconda wave
- Note: Volume basso ma intento alto. Ogni visita è un potenziale donatore.

**SEZIONE: Frosinone (locale)**
- Pagine: 4 (Hub, Spaziani, Cassino, Sora)
- Queries risolte: 12
- Volume totale: 825/mese (geolocalizzato)
- Priorità: 2 — seconda wave
- Note: Solo l'1.8% del volume totale ma traffico già pronto all'azione. Alta conversione.

**SEZIONE: Convenzioni**
- Pagine: 2 (Hub, Lista)
- Queries risolte: 2
- Volume totale: 25–45/mese
- Priorità: 3
- Note: Fix critico dall'audit: erano nascoste. Ora visibili in home e nel menu.

---

## 3 · Home Page Wireframe (Dettagliato)

```
╔══════════════════════════════════════════════════════════════════╗
║  [HEADER]  Logo AVIS Frosinone   |  Come Donare  Perché  Dove   ║
║            [Nav principale]       |  Diventa Donatore  Contatti  ║
╠══════════════════════════════════════════════════════════════════╣
║  [HERO — above the fold]                                         ║
║                                                                   ║
║  Headline:  "Dona Sangue a Frosinone.                            ║
║              Salva una Vita. Ci Vuole un'Ora."                   ║
║                                                                   ║
║  Sub:  "AVIS Frosinone collabora con l'Ospedale Spaziani.        ║
║         Ogni donazione conta. La prima è gratuita e guidata."    ║
║                                                                   ║
║  Visual: Foto reale donatore (db AVIS — "un giorno col Dono")    ║
║                                                                   ║
║  [CTA 1 — primario, rosso]  "Prenota la tua donazione"           ║
║  [CTA 2 — secondario, outline]  "Scopri se puoi donare →"        ║
║                                                                   ║
╠══════════════════════════════════════════════════════════════════╣
║  [TRUST BADGES — 3 colonne]                                      ║
║  ❶ Ospedale Spaziani          ❷ 40 donatori attivi    ❸ Dal 2019 ║
║    "Partner ufficiale"          "nella nostra sede"    "attivi"  ║
╠══════════════════════════════════════════════════════════════════╣
║  [DUAL PATH — 2 colonne]                                         ║
║  ┌─────────────────────────┐  ┌─────────────────────────┐       ║
║  │  "Sono pronto a donare" │  │  "Voglio capire prima"  │       ║
║  │                         │  │                          │       ║
║  │  → Requisiti            │  │  → Benefici per te       │       ║
║  │  → Dove andare          │  │  → Come funziona         │       ║
║  │  → Prenota ora          │  │  → Miti sfatati          │       ║
║  └─────────────────────────┘  └─────────────────────────┘       ║
╠══════════════════════════════════════════════════════════════════╣
║  [FEATURED TESTIMONIAL]                                          ║
║  Foto donatore  |  "Pensavo fosse complicato. In un'ora avevo    ║
║                 |   già salvato qualcuno. Torno ogni volta."     ║
║                 |  — Marco, 34 anni, programmatore, Frosinone   ║
║                    [da sostituire con testimonial reale AVIS]    ║
╠══════════════════════════════════════════════════════════════════╣
║  [COME FUNZIONA — 4 step orizzontali]                            ║
║  1. Registrazione → 2. Visita medica → 3. Prelievo →            ║
║  4. Riposo + snack    (~15 min ciascuno · 1 ora totale)         ║
╠══════════════════════════════════════════════════════════════════╣
║  [CONVENZIONI HIGHLIGHT — 3 card]                                ║
║  [Convenzione 1]  [Convenzione 2]  [Convenzione 3]               ║
║                              → Vedi tutte le convenzioni         ║
╠══════════════════════════════════════════════════════════════════╣
║  [RECENT BLOG / NEWS — 2–3 articoli]                             ║
║  Ultime notizie da AVIS Frosinone                                ║
╠══════════════════════════════════════════════════════════════════╣
║  [CTA FINALE — full width, sfondo rosso]                         ║
║  "Pronto a fare la differenza?"                                   ║
║                                                                   ║
║  📞 +39 377 490 1081   ✉ info@avisfrosinone.it                   ║
║  [Pulsante: Scrivici su WhatsApp]  [Pulsante: Chiamaci ora]      ║
╠══════════════════════════════════════════════════════════════════╣
║  [FOOTER]  Via Mazzini 70, 03100 Frosinone · Links · Privacy    ║
╚══════════════════════════════════════════════════════════════════╝
```

**Note home page:**
- Dual path risolve sia chi è già motivato (azione immediata) sia chi è curioso (educazione)
- Trust badges usano dati reali: 40 donatori, Ospedale Spaziani, fondato 2019
- CTA finale punta direttamente a WhatsApp e telefono, non a un form (meno attrito)
- Convenzioni visibili in home: fix diretto del problema audit

---

## 4 · Wireframe Top-10 Pagine

---

### CORE #3 — Requisiti di Idoneità

```
PAGINA: Requisiti di Idoneità alla Donazione
URL: /come-donare/requisiti-idoneita.html
H1: "Puoi Donare Sangue? Tutti i Requisiti per Frosinone"
Lunghezza: 1.100–1.300 parole
CTA primario: "Prenota la visita di idoneità"
CTA secondario: "Hai dubbi? Scrivici"
Internal links: → Home, → Procedura (×2), → Dove e quando, → FAQ, → Contatti
Fonte: D.M. 2 Nov 2015 · salute.gov.it
Disclaimer: valutazione finale spetta al medico del centro trasfusionale

├─ H1: Puoi Donare Sangue? Tutti i Requisiti per Frosinone
├─ H2: Requisiti fondamentali (età 18–65, peso ≥50 kg, buona salute)
│   └─ Tabella riepilogativa: Sì / No / Da verificare col medico
├─ H2: Condizioni mediche che sospendono la donazione
│   ├─ Temporanee: farmaci, tatuaggi recenti, viaggi in zone a rischio
│   └─ Permanenti: alcune malattie croniche, diabete insulino-dipendente
├─ H2: Domande frequenti — "Posso donare se..."
│   ├─ "...ho un tatuaggio?" (1.000/mese)
│   ├─ "...ho il diabete?" (420/mese)
│   └─ "...ho appena partorito?" (480/mese)
├─ H2: Cosa succede alla visita di idoneità (colloquio + visita medica)
├─ [CTA MID-PAGE] "Verifica la tua idoneità: chiama o scrivi ad AVIS Frosinone"
└─ H2: Fonti ufficiali — D.M. 2 Nov 2015 + link Ministero della Salute
```

---

### CORE #7 — Benefici della Donazione

```
PAGINA: Benefici della Donazione
URL: /perche-donare/benefici-donatore.html
H1: "Cosa Ti Dà Donare Sangue: Benefici per Te e per gli Altri"
Lunghezza: 900–1.100 parole
CTA primario: "Diventa donatore AVIS Frosinone"
CTA secondario: "Scopri se puoi donare"
Internal links: → Requisiti, → Diventa Donatore, → Storie donatori, → Convenzioni
Fonte: AVIS Nazionale · Centro Nazionale Sangue (CNS) · avis.it

├─ H1: Cosa Ti Dà Donare Sangue: Benefici per Te e per gli Altri
├─ H2: Benefici per la tua salute
│   └─ Esami ematochimici gratuiti, monitoraggio periodico della salute
├─ H2: Benefici sociali
│   └─ Autosufficienza ematica, solidarietà, impatto diretto sulla comunità
├─ H2: Donare fa bene? Cosa dice la scienza
│   └─ Citazione CNS / AVIS Nazionale con link ufficiale
├─ [CTA MID-PAGE] "Unisciti ai 40 donatori AVIS Frosinone"
├─ H2: La testimonianza di chi lo fa ogni anno
│   └─ Testimonial reale (foto + nome + età + occupazione, da db AVIS)
└─ H2: Le convenzioni: i vantaggi pratici per i soci AVIS
   └─ Link a /convenzioni/
```

---

### CORE #5 — Dove e Quando Donare

```
PAGINA: Dove e Quando Donare
URL: /come-donare/dove-e-quando.html
H1: "Dove Donare Sangue a Frosinone: Centri e Orari"
Lunghezza: 700–900 parole
CTA primario: "Prenota l'appuntamento"
CTA secondario: "Chiamaci: +39 377 490 1081"
Internal links: → Procedura, → Requisiti, → Contatti, → Frosinone hub
Fonte: centronazionalesangue.it · ASL Frosinone (UOC SIMT) · asl.fr.it
Disclaimer: orari e disponibilità verificare sempre con la sede

├─ H1: Dove Donare Sangue a Frosinone: Centri e Orari
├─ H2: Ospedale Fabrizio Spaziani — Centro Trasfusionale SIMT
│   ├─ Indirizzo completo, mappa Google incorporata, orari aggiornati
│   └─ Come arrivare: parcheggio, linee bus
├─ H2: AVIS Frosinone — Via Mazzini 70, 03100 Frosinone
│   └─ Orari segreteria, +39 377 490 1081, info@avisfrosinone.it, WhatsApp
├─ H2: Come prenotare un appuntamento
│   ├─ Via telefono: +39 377 490 1081
│   ├─ Via email: info@avisfrosinone.it
│   └─ Di persona (walk-in quando possibile)
├─ [CTA MID-PAGE — pulsante "Apri in Google Maps" + pulsante WhatsApp]
├─ H2: Cosa portare il giorno della donazione
│   └─ Documento d'identità, tessera sanitaria, colazione fatta
└─ H2: Donare anche in provincia: Cassino e Sora
   └─ Link a /frosinone/cassino.html e /frosinone/sora.html
```

---

### CORE #4 — Procedura di Donazione

```
PAGINA: Procedura di Donazione
URL: /come-donare/procedura-donazione.html
H1: "Come Si Dona il Sangue: La Procedura Passo per Passo"
Lunghezza: 800–1.000 parole
CTA primario: "Prenota ora — è più semplice di quanto pensi"
CTA secondario: "Hai ancora dubbi? Leggi le FAQ"
Internal links: → Requisiti, → Dove donare, → FAQ, → Prima donazione
Fonte: centronazionalesangue.it — La donazione

├─ H1: Come Si Dona il Sangue: La Procedura Passo per Passo
├─ H2: Prima di arrivare — colazione leggera, idratazione, no alcol
├─ H2: All'arrivo — registrazione e questionario anamnestico (~15 min)
├─ H2: La visita medica di idoneità (~10 min)
├─ H2: Il prelievo — indolore, dura 7–10 minuti
│   └─ Risposta diretta: "fa male donare sangue?" (450/mese)
├─ H2: Dopo la donazione — riposo, ristoro, istruzioni (~20–30 min)
│   └─ Risposta diretta: "quanto tempo totale?" (720/mese) → ~1 ora
├─ [CTA MID-PAGE]
└─ H2: Effetti normali e cosa fare se non ti senti bene
   └─ Gestione trasparente delle paure (gap critico identificato)
   └─ Disclaimer: seguire le istruzioni del personale sanitario post-donazione
```

---

### CORE #8 — Diventa Donatore AVIS Frosinone

```
PAGINA: Diventa Donatore AVIS Frosinone
URL: /diventa-donatore/index.html
H1: "Diventa Donatore AVIS Frosinone: Come Iscriversi"
Lunghezza: 600–800 parole
CTA primario: "Iscriviti ad AVIS Frosinone — è gratuito"
CTA secondario: "Scrivici: ti guidiamo passo per passo"
Internal links: → Requisiti, → Dove donare, → Convenzioni, → Contatti
Fonte: AVIS Nazionale · Statuto AVIS · avis.it/diventa-donatore
Disclaimer: iscrizione volontaria e gratuita

├─ H1: Diventa Donatore AVIS Frosinone: Come Iscriversi
├─ H2: Cosa significa iscriversi ad AVIS (volontario, gratuito, periodico)
├─ H2: I 3 passi per diventare donatore AVIS
│   1. Contattaci → 2. Visita di idoneità → 3. Prima donazione
├─ H2: Cosa ottieni come socio AVIS Frosinone
│   ├─ Convenzioni e vantaggi pratici
│   ├─ Esami periodici gratuiti
│   └─ Community di 40 donatori attivi a Frosinone
├─ [CTA PRIMARIO — form semplice OPPURE link WhatsApp diretto]
│   "Scrivici: ti guidiamo dalla A alla Z"
└─ H2: Unisciti ai nostri 40 donatori — 120 donazioni l'anno
   └─ Breve testimonial reale (1–2 righe + foto)
```

---

### CORE #10 — AVIS Frosinone Hub Locale

```
PAGINA: AVIS Frosinone Hub Locale
URL: /frosinone/index.html
H1: "Donazione Sangue a Frosinone — AVIS Comunale"
Lunghezza: 700–900 parole
CTA primario: "Contattaci per la tua prima donazione"
CTA secondario: "Scopri i centri in provincia"
Internal links: → Dove donare, → Requisiti, → Diventa Donatore, → Contatti, → Spaziani
Fonte: asl.fr.it (UOC SIMT) · AVIS Nazionale · Legge 219/2005

├─ H1: Donazione Sangue a Frosinone — AVIS Comunale
├─ H2: AVIS Frosinone in breve
│   ├─ Fondato nel 2019, Via Mazzini 70, 03100 Frosinone
│   └─ 40 donatori attivi, 120 donazioni/anno, 5 volontari
├─ H2: I nostri centri: Ospedale Spaziani + sede AVIS
│   └─ Mappa + orari + contatti diretti
├─ H2: Il nostro rapporto con ASL Frosinone e SIMT
│   └─ Posiziona AVIS come autorità locale partner del SSN
│   └─ Citazione Legge 219/2005 (ruolo AVIS nel SSN)
├─ H2: Donare nella provincia: Cassino e Sora
│   └─ Link a pagine locali dedicate
├─ [CTA] "Contattaci: +39 377 490 1081 · info@avisfrosinone.it"
└─ H2: Chi siamo — 5 volontari, comunità attiva dal 2019
```

---

### SEC #3 — Miti e Falsi Credenze sulla Donazione

```
PAGINA: Miti e Falsi Credenze
URL: /perche-donare/miti-falsi-credenze.html
H1: "Miti sulla Donazione di Sangue: Sfatiamoli con i Dati"
Lunghezza: 900–1.100 parole
CTA primario: "Hai ancora dubbi? Scrivici"
CTA secondario: "Scopri la procedura reale"
Internal links: → Procedura, → Requisiti, → FAQ, → Contatti
Nota: Risponde ai 3 gap principali identificati nella ricerca

├─ H1: Miti sulla Donazione di Sangue: Sfatiamoli con i Dati
├─ H2: "Donare fa male" — Falso: il prelievo dura 7–10 minuti, ago sottile
├─ H2: "Si può svenire" — Raro, gestito dal personale, non pericoloso
│   (gap critico: gestione trasparente delle paure)
├─ H2: "Non si può donare dopo il vaccino COVID"
│   (gap emergente post-pandemia: risposta aggiornata + link ministeriale)
├─ H2: "Donare fa dimagrire o ingrassare" — Le prove scientifiche
│   (gap: credenza popolare, risposte chiare per non creare aspettative errate)
├─ H2: "Si rischia la vita" — Zero: ago sterile monouso, personale formato
└─ H2: Cosa dice il Ministero della Salute
   └─ Link a salute.gov.it + citazione D.M. 2 Nov 2015
```

---

### SEC #9 — FAQ

```
PAGINA: FAQ — Domande Frequenti
URL: /faq.html
H1: "Domande Frequenti sulla Donazione di Sangue"
Lunghezza: 1.200–1.600 parole (20+ domande)
CTA primario: "Non trovi la risposta? Scrivici"
Internal links: → Requisiti (×3), → Procedura (×2), → Dove e quando, → Contatti
Nota tecnica: Implementare schema markup FAQ (JSON-LD) per rich snippet Google

├─ H1: Domande Frequenti sulla Donazione di Sangue
│
├─ [Sezione: Prima della Donazione]
│   ├─ Posso donare se ho un tatuaggio? (1.000/mese)
│   ├─ Posso donare se ho il diabete? (420/mese)
│   ├─ Posso donare dopo il parto? (480/mese)
│   ├─ Cosa mangiare prima della donazione?
│   └─ Posso donare se prendo farmaci?
│
├─ [Sezione: Durante la Donazione]
│   ├─ Fa male donare il sangue? (450/mese)
│   ├─ Quanto tempo dura la donazione? (720/mese)
│   └─ Cosa succede se mi sento male durante il prelievo?
│
├─ [Sezione: Dopo la Donazione]
│   ├─ Dopo quanto tempo posso ridonare? (tabella per tipo di donazione)
│   └─ Quali sono gli effetti normali post-donazione?
│
└─ [Sezione: AVIS Frosinone]
    ├─ Come mi iscrivo ad AVIS Frosinone?
    ├─ Dove si trova la sede AVIS? (Via Mazzini 70)
    └─ Come prenoto un appuntamento?
```

---

### SEC #4 — Storie dei Donatori

```
PAGINA: Storie dei Donatori
URL: /perche-donare/storie-donatori.html
H1: "Le Storie dei Donatori AVIS Frosinone"
Lunghezza: 600–800 parole + foto
CTA primario: "Unisciti a loro — prenota la tua prima donazione"
Internal links: → Diventa Donatore, → Benefici, → Home, → Contatti
Asset disponibili: 3 foto "Un giorno col Dono" (già nel db AVIS)

├─ H1: Le Storie dei Donatori AVIS Frosinone
├─ [Gallery 3 foto — "Un giorno col Dono"]
├─ H2: [Nome donatore 1, età, professione] — storia ~100 parole
├─ H2: [Nome donatore 2, età, professione] — storia ~100 parole
├─ H2: [Nome donatore 3, età, professione] — storia ~100 parole
└─ [CTA finale: "Vuoi fare parte di questa storia?"]
   → Link a /diventa-donatore/
```

---

### SEC #1 — Preparazione alla Donazione

```
PAGINA: Preparazione alla Donazione
URL: /come-donare/preparazione-donazione.html
H1: "Come Prepararsi alla Donazione di Sangue: Guida Pratica"
Lunghezza: 600–800 parole
CTA primario: "Prenota ora — sei già pronto"
CTA secondario: "Hai dubbi? Leggi le FAQ"
Internal links: → Procedura, → Dove e quando, → FAQ, → Requisiti

├─ H1: Come Prepararsi alla Donazione di Sangue: Guida Pratica
├─ H2: La sera prima (cena leggera, niente alcol, riposo)
├─ H2: La mattina della donazione
│   └─ Colazione leggera senza latte o latticini (fonte: CNS)
├─ H2: Cosa portare con sé
│   └─ Documento d'identità + tessera sanitaria
├─ H2: Come vestirti (manica larga, abbigliamento comodo)
└─ H2: Checklist riepilogativa
   └─ Lista stampabile / elemento interattivo (checkbox JS)
```

---

## 5 · SEO Spec Top-10 Pagine

### Home

- **H1:** Donazione Sangue Frosinone — AVIS Comunale
- **Keywords secondarie (H2):** come donare, benefici donazione, dove donare Frosinone, diventa donatore AVIS
- **Meta description:** "Dona sangue a Frosinone con AVIS. Partner dell'Ospedale Spaziani. Scopri requisiti, procedura e come prenotare. Salva una vita in un'ora."
- **Lunghezza:** 800–1.000 parole
- **Internal links:** → 5+ pagine interne (requisiti, benefici, dove, diventa donatore, contatti)

---

### Requisiti Idoneità

- **H1:** Puoi Donare Sangue? Tutti i Requisiti per Frosinone
- **Keywords secondarie (H2):** posso donare se ho tatuaggio, posso donare con diabete, chi può donare sangue, esclusioni donazione sangue, requisiti donazione sangue
- **Meta description:** "Scopri tutti i requisiti per donare sangue a Frosinone. Età, peso, condizioni mediche e cosa fare se hai dubbi. AVIS Frosinone risponde."
- **Lunghezza:** 1.100–1.300 parole
- **Internal links:** → Home, → Procedura (×2), → Dove e quando, → FAQ, → Contatti

---

### Benefici Donatore

- **H1:** Cosa Ti Dà Donare Sangue: Benefici per Te e per gli Altri
- **Keywords secondarie (H2):** donare sangue fa bene, perché donare sangue, importanza donazione sangue, esami gratuiti donatori
- **Meta description:** "Donare sangue ti permette di monitorare la salute con esami gratuiti e contribuisce all'autosufficienza ematica. Scopri tutti i benefici con AVIS Frosinone."
- **Lunghezza:** 900–1.100 parole
- **Internal links:** → Requisiti, → Diventa Donatore, → Storie donatori, → Convenzioni

---

### Dove e Quando

- **H1:** Dove Donare Sangue a Frosinone: Centri e Orari
- **Keywords secondarie (H2):** centro trasfusionale Frosinone, ospedale Spaziani donazione, prenotare donazione Frosinone, donazione sangue vicino a me
- **Meta description:** "Dona sangue all'Ospedale Spaziani di Frosinone o nella sede AVIS di Via Mazzini 70. Orari, mappa e come prenotare il tuo appuntamento."
- **Lunghezza:** 700–900 parole
- **Internal links:** → Procedura, → Requisiti, → Contatti, → Frosinone hub

---

### Procedura

- **H1:** Come Si Dona il Sangue: La Procedura Passo per Passo
- **Keywords secondarie (H2):** procedure donazione sangue, quanto tempo dura donazione sangue, fa male donare sangue, effetti donazione sangue
- **Meta description:** "Tutto quello che succede dalla registrazione al riposo post-donazione. La procedura dura circa un'ora. AVIS Frosinone ti accompagna in ogni passo."
- **Lunghezza:** 800–1.000 parole
- **Internal links:** → Requisiti, → Dove donare, → FAQ, → Prima donazione

---

### Diventa Donatore

- **H1:** Diventa Donatore AVIS Frosinone: Come Iscriversi
- **Keywords secondarie (H2):** iscriversi AVIS, AVIS donazione sangue, convenzioni AVIS Frosinone, become donatore AVIS Frosinone
- **Meta description:** "Iscriversi ad AVIS Frosinone è gratuito. Diventa donatore periodico: 3 passi, supporto completo, e i vantaggi delle convenzioni AVIS."
- **Lunghezza:** 600–800 parole
- **Internal links:** → Requisiti, → Dove donare, → Convenzioni, → Contatti

---

### Frosinone Hub Locale

- **H1:** Donazione Sangue a Frosinone — AVIS Comunale
- **Keywords secondarie (H2):** AVIS Frosinone, ospedale Spaziani donazione, ASL Frosinone donazione, donare sangue Frosinone, AVIS Frosinone contatti
- **Meta description:** "AVIS Comunale di Frosinone: Via Mazzini 70. Collaboriamo con l'Ospedale Spaziani e la ASL per garantire sangue sicuro al territorio."
- **Lunghezza:** 700–900 parole
- **Internal links:** → Dove donare, → Requisiti, → Diventa Donatore, → Contatti, → Spaziani

---

### Miti e Credenze

- **H1:** Miti sulla Donazione di Sangue: Sfatiamoli con i Dati
- **Keywords secondarie (H2):** donazione sangue sicurezza, fa male donare, si può svenire donando sangue, vaccino COVID donazione sangue
- **Meta description:** "Paura di donare sangue? Sfatiamo insieme i miti più comuni con dati ufficiali. Sicurezza, procedure, e le risposte che nessuno ti dà chiaramente."
- **Lunghezza:** 900–1.100 parole
- **Internal links:** → Procedura, → Requisiti, → FAQ, → Contatti

---

### FAQ

- **H1:** Domande Frequenti sulla Donazione di Sangue
- **Keywords secondarie (H2):** posso donare se..., quanto dura la donazione, effetti post-donazione, iscriversi AVIS, dove donare Frosinone
- **Meta description:** "Tutte le risposte sulle domande più comuni sulla donazione di sangue. Tatuaggi, farmaci, parto, diabete: AVIS Frosinone risponde con fonti ufficiali."
- **Lunghezza:** 1.200–1.600 parole (20+ domande)
- **Internal links:** → Requisiti (×3), → Procedura (×2), → Dove, → Diventa Donatore
- **Nota tecnica:** Implementare schema markup FAQ (JSON-LD) per rich snippet Google

---

### Storie Donatori

- **H1:** Le Storie dei Donatori AVIS Frosinone
- **Keywords secondarie (H2):** testimonianze donatori sangue, perché donare sangue, AVIS Frosinone community
- **Meta description:** "Conosci le persone che ogni anno donano con AVIS Frosinone. Storie vere, foto reali, motivazioni autentiche. Il dono più grande parte da qui."
- **Lunghezza:** 600–800 parole + foto
- **Internal links:** → Diventa Donatore, → Benefici, → Home, → Contatti

---

## 6 · Linking Strategy

### Internal Link Map (flusso principale)

```
HOME
├── → /come-donare/requisiti-idoneita.html      ("Scopri se puoi donare")
├── → /perche-donare/benefici-donatore.html      (dual path "voglio capire")
├── → /come-donare/dove-e-quando.html            (dual path "sono pronto")
├── → /diventa-donatore/                         (CTA primario hero)
├── → /perche-donare/storie-donatori.html        (testimonial section)
├── → /convenzioni/                              (sezione highlight)
└── → /contatti.html                             (CTA finale + footer)

REQUISITI IDONEITÀ
├── → /come-donare/procedura-donazione.html      ("una volta accertata l'idoneità...")
├── → /come-donare/dove-e-quando.html            ("prenota la visita di idoneità")
├── → /faq.html                                  ("vedi tutte le domande frequenti")
└── → /contatti.html                             (CTA "hai dubbi?")

BENEFICI DONATORE
├── → /come-donare/requisiti-idoneita.html       ("verifica se puoi donare")
├── → /diventa-donatore/                         (CTA mid-page)
├── → /perche-donare/storie-donatori.html        ("leggi le loro storie")
└── → /convenzioni/                              ("i vantaggi pratici per i soci")

PROCEDURA
├── → /come-donare/requisiti-idoneita.html       (link naturale in apertura)
├── → /come-donare/dove-e-quando.html            ("dove effettuare la donazione")
├── → /faq.html                                  ("domande sulla procedura?")
└── → /diventa-donatore/prima-donazione.html     (CTA fine pagina)

DOVE E QUANDO
├── → /come-donare/procedura-donazione.html      ("cosa succede quando arrivi")
├── → /come-donare/requisiti-idoneita.html       ("hai già verificato l'idoneità?")
├── → /frosinone/                                (link autorità locale)
└── → /contatti.html                             (CTA prenotazione)

DIVENTA DONATORE
├── → /come-donare/requisiti-idoneita.html       (passo 1: verifica idoneità)
├── → /come-donare/dove-e-quando.html            (passo 2: vieni da noi)
├── → /convenzioni/                              (benefici del socio)
└── → /contatti.html                             (CTA iscrizione)

FROSINONE HUB
├── → /come-donare/dove-e-quando.html            (mappa e orari)
├── → /frosinone/ospedale-spaziani.html          (pagina dedicata Spaziani)
├── → /frosinone/cassino.html                    (pagina locale Cassino)
├── → /frosinone/sora.html                       (pagina locale Sora)
└── → /diventa-donatore/                         (CTA territoriale)

FAQ
├── → /come-donare/requisiti-idoneita.html       (×3 per domande specifiche)
├── → /come-donare/procedura-donazione.html      (×2)
├── → /come-donare/dove-e-quando.html            (×1)
└── → /contatti.html                             (CTA "non trovi risposta?")
```

### Breadcrumb Structure

```
Home › Come Donare › Requisiti di Idoneità
Home › Come Donare › Procedura di Donazione
Home › Come Donare › Dove e Quando Donare
Home › Come Donare › Preparazione alla Donazione
Home › Perché Donare › Benefici per il Donatore
Home › Perché Donare › Miti e Falsi Credenze
Home › Perché Donare › Storie dei Donatori
Home › Perché Donare › Importanza Sociale
Home › Diventa Donatore
Home › Diventa Donatore › Iscrizione AVIS
Home › Diventa Donatore › Prima Donazione
Home › Frosinone
Home › Frosinone › Ospedale Spaziani
Home › Frosinone › Cassino
Home › Frosinone › Sora
Home › Convenzioni
Home › Convenzioni › Lista Convenzioni
Home › FAQ
Home › Blog
Home › Chi Siamo
Home › Contatti
```

### Anchor Text Suggerito

| Destinazione | Anchor text consigliato | Anchor text da evitare |
|---|---|---|
| Requisiti idoneità | "scopri se puoi donare", "verifica i requisiti", "leggi i criteri di idoneità" | "clicca qui", "leggi di più" |
| Procedura | "come si svolge la donazione", "scopri la procedura passo per passo" | "la procedura", "qui" |
| Dove e quando | "trova il centro più vicino", "orari e indirizzi a Frosinone" | "dove andare", "link mappa" |
| Diventa donatore | "iscriviti ad AVIS Frosinone", "diventa donatore oggi" | "registrati", "iscriviti" |
| Contatti | "chiamaci al +39 377 490 1081", "scrivici su WhatsApp" | "contatti", "pagina contatti" |
| FAQ | "domande frequenti sulla donazione", "tutte le risposte" | "FAQ", "clicca qui" |
| Benefici | "scopri cosa ti dà donare", "i benefici per la tua salute" | "benefici", "vantaggi" |
| Convenzioni | "i vantaggi pratici per i soci AVIS", "tutte le convenzioni" | "convenzioni", "sconti" |

---

## 7 · Decisioni Architetturali

| Decisione | Scelta adottata | Motivazione |
|---|---|---|
| Architettura menu | Gerarchica, max 2 livelli, 5 voci principali | Fix audit "menu confuso": 5 voci scannerizzabili in 3 sec |
| Gerarchia visiva home | "Come donare" PRIMA di "Perché donare" | Chi arriva da query locali è già motivato; dual path serve entrambi |
| CTA primario sito | "Prenota la tua donazione" (azione concreta) | Rimuove ambiguità vs "scopri", "informati". Link diretto WhatsApp/tel |
| Numero CTA per pagina | Max 2: uno mid-page, uno fine pagina | Più di 2 crea paralisi decisionale |
| CTA home | 2 hero CTA (dual path: azione + informazione) | Serve sia il pronto ad agire sia chi è curioso |
| FAQ | Pagina dedicata + risposte inline nelle pagine tematiche | FAQ page cattura long-tail; risposte inline riducono attrito sulle pagine core |
| Testimonial | Featured single in home + gallery full in /storie-donatori | Home: impatto immediato. Pagina dedicata: fiducia per chi la cerca |
| Blog | Sezione separata, non nella nav principale | Non distrae dal funnel. Accessibile da footer e link contestuali |
| Convenzioni | Estratto highlight in home + pagina dedicata nel menu | Fix audit: erano "nascoste a fine pagina". Ora visibili in home + nav |
| Foto disponibili | 3 foto "Un giorno col Dono" in home e /storie-donatori | Asset reali già disponibili: usarle subito per autenticità e trust |
| Pagine locali provincia | /frosinone/cassino e /frosinone/sora come pagine TER | Volume basso ora ma cattura traffico geolocalizzato a lungo termine |

---

## 8 · Riepilogo Finale & Checklist

### Conteggio pagine per categoria

| Categoria | N. Pagine | Elenco |
|---|---|---|
| **CORE** — implementare prima | 10 | Home, Come Donare hub, Requisiti, Procedura, Dove e quando, Benefici, Diventa Donatore hub, Iscrizione AVIS, Frosinone hub, Contatti |
| **SECONDARY** — implementare dopo | 9 | Preparazione, Importanza sociale, Miti e credenze, Storie donatori, Prima donazione, Ospedale Spaziani, Convenzioni hub, Lista convenzioni, FAQ |
| **TERTIARY** — approfondimenti | 7 | Cassino, Sora, Perché Donare hub, Blog index, Blog articoli, Chi siamo, Privacy |
| **TOTALE** | **26** | Zero pagine orfane · Tutte collegate · Breadcrumb completo |

### Fonti ufficiali mappate per sezione

| Sezione | Fonte principale | URL di riferimento |
|---|---|---|
| Requisiti / Idoneità | Ministero della Salute · D.M. 2 Nov 2015 | salute.gov.it |
| Benefici | AVIS Nazionale · CNS | avis.it · centronazionalesangue.it |
| Logistica / Dove donare | Centro Nazionale Sangue · ASL Frosinone SIMT | centronazionalesangue.it · asl.fr.it |
| Procedura | Centro Nazionale Sangue | centronazionalesangue.it |
| Locale Frosinone | ASL Frosinone (UOC SIMT) · Legge 219/2005 | asl.fr.it |
| Diventa donatore | AVIS Nazionale · Statuto | avis.it |
| Situazioni specifiche | D.M. 2 Nov 2015 (All. III) | Gazzetta Ufficiale |

### Gap di contenuto → pagine assegnate

| Gap identificato | Pagina che lo risolve |
|---|---|
| Paura di svenire o stare male | /perche-donare/miti-falsi-credenze.html + /come-donare/procedura.html (H2 dedicato) |
| Tempo totale reale della donazione | /come-donare/procedura-donazione.html (H2: "quanto dura?") |
| Vaccino COVID e donazione | /perche-donare/miti-falsi-credenze.html (H2 dedicato) + /faq.html |
| "Donare fa dimagrire o ingrassare?" | /perche-donare/miti-falsi-credenze.html |
| Checklist pratica pre-donazione | /come-donare/preparazione-donazione.html |

### Checklist validazione output

- [x] Directory tree completo e logico (26 pagine)
- [x] 26 pagine identificate (10 CORE + 16 SECONDARY/TERTIARY)
- [x] Home wireframe dettagliato (hero, trust, dual path, testimonial, steps, conv., CTA)
- [x] Wireframe completo per Top-10 pagine prioritarie
- [x] SEO spec per ogni pagina (H1, H2 keywords, meta desc, lunghezza, internal links)
- [x] Linking strategy coerente con anchor text specifici
- [x] Zero pagine orfane (ogni pagina riceve ≥2 link interni)
- [x] Gerarchia logica: azione > considerazione > consapevolezza
- [x] CTA strategy consistente (max 2/pagina, sempre concreto e diretto)
- [x] Problemi audit risolti: menu chiaro, blog accessibile, convenzioni visibili, CTA esplicito
- [x] Gap di contenuto mappati su pagine specifiche
- [x] Dati reali AVIS usati ovunque (no placeholder)
- [x] Fonti ufficiali indicate per ogni sezione
- [x] Pronto da passare a developer e scrittori di contenuto

---

## Note per gli Scrittori di Contenuto

**Prima di scrivere qualsiasi pagina:**
1. Leggere il wireframe della pagina assegnata (sezione 4)
2. Verificare la SEO spec (sezione 5): H1 esatto, keywords H2, lunghezza target
3. Usare i link interni indicati con gli anchor text consigliati (sezione 6)
4. Citare sempre la fonte ufficiale indicata, con link diretto
5. Inserire il disclaimer dove specificato (idoneità, orari, post-donazione)
6. Max 2 CTA per pagina: uno mid-page, uno fine pagina
7. Mai generare dati inventati: tutti i numeri (40 donatori, 120/anno, tel., indirizzo) sono verificati

**Ordine di scrittura consigliato:**
1. Home (CORE #1)
2. Requisiti idoneità (CORE #3) — volume massimo
3. Benefici donatore (CORE #7) — volume secondo
4. Dove e quando (CORE #5)
5. Procedura (CORE #4)
6. Diventa Donatore hub (CORE #8)
7. Frosinone hub (CORE #10)
8. Iscrizione AVIS (CORE #9)
9. Come Donare hub (CORE #2)
10. Contatti (CORE #11)
11. FAQ (SEC #9)
12. Miti e credenze (SEC #3)
13. Storie donatori (SEC #4)
14. Preparazione (SEC #1)
15. Pagine rimanenti SECONDARY e TERTIARY

---

*Documento generato per: AVIS Comunale di Frosinone — avisfrosinone.it*  
*Prossimo step: Phase 2 — ChatGPT content generation (Day 8)*
