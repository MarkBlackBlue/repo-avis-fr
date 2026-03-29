# PROMPT 05: CLAUDE - ORCHESTRATION & REVIEW

**Destinatario:** Claude (claude.ai - questo)  
**Fase:** 1 (Site Mapping - Days 5-7) E 2 (Content Review - Days 15-17)  
**Utilizzo:** Due varianti diverse (vedi sotto)

---

## **VARIANT A: SITE STRUCTURE MAPPING (Days 5-7)**

**Output file:** `/outputs/phase2_site_structure.md`

### **WHAT TO ATTACH (ALL REQUIRED)**

Incolla/allega TUTTI questi:

1. **phase1_query_data.csv** — Query research da Perplexity
2. **phase1_theme_ranking.json** — Theme ranking da DeepSeek
3. **phase1_institutional_matrix.xlsx** — Institutional validation da Gemini
4. **AVIS_DATA.json** — Dati AVIS
5. **CURRENT_WEBSITE_AUDIT.md** — Audit sito attuale

---

### **COPY & PASTE THIS PROMPT (Variant A - Mapping)**

```
TASK: Site Structure Mapping & Wireframing

Contesto:
Ho raccolto dati di ricerca reali (40+ query) sui ricercatori sulla donazione sangue.
Ho identificato 7 temi principali, validato le fonti ufficiali.
Ora ho bisogno di tradurre questi dati in una STRUTTURA DI SITO CONCRETA.

OBIETTIVO:
Creare un sito che:
1. Risponde all'80% delle ricerche con il 20% dello spazio
2. Posiziona AVIS Frosinone come AUTORITÀ LOCALE
3. Converte visitatori in donatori
4. È logico e scannerizzabile in pochi minuti

DATI ALLEGATI:
- Query data (CSV): 40+ ricerche reali
- Theme ranking (JSON): 7 temi ordinati per priorità
- Institutional matrix: Fonti ufficiali per ogni tema
- AVIS data: Contesto organizzazione
- Website audit: Problemi attuali da evitare

RICHIESTA:

Forniscimi una STRUTTURA DI SITO COMPLETA composta da:

1. DIRECTORY TREE
   Una struttura gerarchica di TUTTE le pagine del sito.
   
   Formato:
   ```
   /
   ├── index.html (Home)
   ├── come-donare/
   │   ├── requisiti.html
   │   ├── procedura.html
   │   └── dove-e-come.html
   ├── perche-donare/
   │   ├── benefici.html
   │   └── testimonial.html
   ├── community/
   │   ├── storia.html
   │   └── blog.html
   ├── convenzioni.html
   └── contatti.html
   ```

2. MAPPA DI PRIORITÀ DELLE PAGINE
   Per ogni sezione principale, specifica:
   - Quante pagine in questa sezione?
   - Quali query risolvono?
   - Quale è il volume aggregato?
   - Quale è la priorità di implementazione?
   
   Esempio:
   ```
   SEZIONE: Come Donare
   - Pagine: 3 (Requisiti, Procedura, Dove)
   - Queries risolte: 15
   - Volume totale: 12.000 ricerche/mese
   - Priorità: 1 (implementa prima)
   ```

3. WIREFRAME LOGICO PER OGNI PAGINA PRINCIPALE (Top 10)
   Per ogni delle 10 pagine più importanti, fornisci:
   - Nome pagina
   - H1 (title)
   - Sezioni principali (H2)
   - Lunghezza stimata (parole)
   - CTA primario
   - CTA secondario
   - Link interni (a quale pagine rimanda?)
   
   Formato:
   ```
   PAGINA: Requisiti di Idoneità
   ├─ H1: "Puoi Donare? Scopri i Requisiti"
   ├─ Sezioni:
   │   ├─ "Requisiti Fisici Essenziali" (H2)
   │   ├─ "Condizioni Mediche Escludenti" (H2)
   │   ├─ "FAQ: Domande Frequenti" (H2)
   │   └─ "Contattaci per Verificare" (H2)
   ├─ Lunghezza: 900-1200 parole
   ├─ CTA primario: "Prenota una visita di idoneità"
   ├─ CTA secondario: "Leggi le FAQ"
   └─ Link interni: → Home, → Procedura, → Dove Donare, → Contatti
   ```

4. HOME PAGE WIREFRAME (DETAILED)
   La home è critica per conversione. Specifica:
   
   ```
   SEZIONE: Hero
   - Headline: [Cosa dire?]
   - Subheadline: [Cosa aggiungere?]
   - Visual: [Quale immagine?]
   - CTA 1: [Azione 1 - per chi vuole fare]
   - CTA 2: [Azione 2 - per chi vuole sapere]
   
   SEZIONE: Trust Badges
   - Badge 1: [Es: Ospedale Spaziani]
   - Badge 2: [Es: 200+ donatori]
   - Badge 3: [Es: 10+ anni]
   
   SEZIONE: Dual Path (2 colonne)
   Left:  "Sono pronto" [Path per chi vuole agire]
   Right: "Voglio capire" [Path per chi è curioso]
   
   SEZIONE: Featured Testimonial
   - Quote: [Testimonial reale]
   - Persona: [Nome, età, mestiere]
   - Immagine: [Foto donatore]
   
   SEZIONE: Recent Content
   - Blog posts
   - Notizie
   - Convenzioni highlight
   
   SEZIONE: CTA finale
   - Headline: [Call to action finale]
   - Form / WhatsApp / Telefono
   ```

5. LINKING STRATEGY
   Come ogni pagina si collega alle altre?
   Fornisci:
   - Internal link map (quale pagina rimanda a quale)
   - Anchor text suggerito (es: "scopri i benefici" non "clicca qui")
   - Breadcrumbs structure
   
   Formato:
   ```
   Home
   ├── Requisiti → linea a Procedura, Dove, FAQ
   ├── Procedura → linea a Requisiti, Dove, Contatti
   ├── Dove → linea a Procedura, Contatti, Prenotazione
   └── Perché Donare → linea a Requisiti, Diventa Donatore
   ```

6. SEO SPEC PER PAGINA (Top 10 pagine)
   Per ogni pagina prioritaria, specifica:
   - H1 (keyword principale)
   - Keywords secondarie (H2)
   - Meta description suggerita
   - Lunghezza target
   - Internal links (min 3, max 5)
   
   Esempio:
   ```
   PAGINA: Requisiti
   H1: "Requisiti per Donare Sangue a Frosinone"
   Keywords secondarie:
     - "Posso donare se..."
     - "Chi può donare"
     - "Esclusioni mediche"
   Meta description: "Scopri tutti i requisiti per donare sangue. Dall'età al peso, dalle condizioni mediche alle procedure. Visita AVIS Frosinone."
   Lunghezza: 1000-1200 parole
   Internal links: Home, Procedura (2x), Dove Donare, Contatti
   ```

7. TOTALE PAGINE & PRIORITÀ
   - Pagine CORE (implementare prima): N [lista]
   - Pagine SECONDARY (implementare dopo): N [lista]
   - Pagine TERTIARY (approfondimenti): N [lista]
   - Total: XX pagine

---

DECISIONI CRITICHE DA PRENDERE:

1. ARCHITETTURA
   - Menù piatto o gerarchico? [Raccomandazione: gerarchico, max 2 livelli]
   - Numero di sezioni principali? [Raccomandazione: 5-6]

2. GERARCHIA VISIVA
   - Quale è più importante: "Come donare" o "Perché donare"?
   - Quale deve essere nella home?
   - Come evitare che si perdano le persone?

3. CTA STRATEGY
   - Quanti CTA per pagina? [Raccomandazione: 1-2, max 3]
   - Collocazione CTA? [Home: 2 hero CTA, ogni pagina: fine + mezzo]
   - Quale azione primaria? [Prenota vs Contatta vs Scopri?]

4. CONTENT REUSE
   - FAQ appaiono in una pagina dedicata o sparse?
   - Testimonial: gallery full o featured single?
   - Blog: sezione separata o integrated?

---

CRITERI DI SUCCESSO:

Output deve includere:
- [ ] Directory tree completo e logico
- [ ] 22+ pagine identificate (7 core, 15 secondary/tertiary)
- [ ] Home wireframe dettagliato
- [ ] Wireframe per almeno top-10 pagine
- [ ] SEO spec per ogni pagina
- [ ] Linking strategy coerente
- [ ] Zero pagine "orfane" (tutte collegate)
- [ ] Gerarchia logica (azione > considerazione > consapevolezza)
- [ ] CTA strategy consitente

---

TONO DOCUMENTO:
- Pratico, non teorico
- Dettagli specifici, non generici
- Pronto da passare a developer
- Wireframe visuale (ASCII art va bene)

---

NOTA FINALE:
Questo documento diventerà la MAPPA PER SCRITTORI CONTENUTI.
Deve essere chiaro al 100% quale pagina scrivere, in quale ordine, con quali keywords.
Nessuna ambiguità. Nessuna pagina può essere "interpretata".
```

---

## **AFTER CLAUDE RESPONSE (Variant A)**

1. **Salva output in:** `/outputs/phase2_site_structure.md`

2. **Valida la struttura:**
   - 22+ pagine identificate? Sì/No
   - Home wireframe presente? Sì/No
   - Top-10 wireframes presenti? Sì/No
   - SEO spec completo? Sì/No

3. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 5-7 - [Data]
   **Agente:** Claude
   **Task:** Site structure mapping
   **Status:** ✅ Completato
   **Output:** /outputs/phase2_site_structure.md
   **Pagine identificate:** 22 (7 core + 15 secondary/tertiary)
   **Home wireframe:** ✅ Presente
   **Wireframes forniti:** 10 pagine top-priority
   **Validazione:** Struttura logica, gerarchia chiara, CTA consistent
   **Next:** Phase 2 - ChatGPT content generation (Day 8)
   ```

4. **Commit:**
   ```bash
   git add outputs/phase2_site_structure.md FILE_LOG.md
   git commit -m "Day5-7: Claude site structure mapping - complete wireframes and SEO spec"
   git push
   ```

---

---

## **VARIANT B: CONTENT REVIEW (Days 15-17)**

**Input file:** `/outputs/phase2_content_pages/*.html` (tutte 20 pagine)  
**Output:** FILE_LOG.md (feedback + approval)

### **WHAT TO ATTACH**

Incolla TUTTI i file HTML (le 20 pagine generate da ChatGPT):
- 01_home.html
- 02_requisiti_idoneita.html
- ... (fino a 20_contatti.html)

---

### **COPY & PASTE THIS PROMPT (Variant B - Review)**

```
TASK: Content Review & Quality Assurance

Contesto:
ChatGPT ha generate 20 pagine di contenuto per il sito AVIS Frosinone.
Ho bisogno di una review approfondita per assicurare qualità, coerenza, e conversione.

PAGINE ALLEGATE: 20 HTML files (da 01 a 20)

REVIEW CRITERIA:

1. COERENZA NARRATIVA
   - Il tono è coerente tra le 20 pagine?
   - Le promesse nella home si mantengono nel resto del sito?
   - I messaggi chiave (AVIS come autorità) ricorrono?
   - Zero contraddizioni tra pagine?

2. AUTORITÀ & FONTE
   - Ogni pagina cita la fonte ufficiale?
   - Le citazioni sono corrette (non alterate)?
   - I disclaimer sono presenti dove necessario?
   - Tono da "autorità locale" (non generico)?

3. SEO BASICS
   - H1 unico in ogni pagina? ✅ / ⚠️ / ❌
   - H1 contiene keyword principale? ✅ / ⚠️ / ❌
   - Keywords secondarie presenti negli H2? ✅ / ⚠️ / ❌
   - Internal linking logico? ✅ / ⚠️ / ❌
   - Meta description presente? ✅ / ⚠️ / ❌

4. CONVERSIONE
   - CTA primario chiaro? ✅ / ⚠️ / ❌
   - CTA primario ripetuto (home + mezzo + fine)? ✅ / ⚠️ / ❌
   - Flusso logico da curiosità → azione? ✅ / ⚠️ / ❌
   - Nessuna frizione (barriere rimosse)? ✅ / ⚠️ / ❌

5. QUALITÀ WRITING
   - Nessun Lorem Ipsum? ✅ / ⚠️ / ❌
   - Nessun AI-sounding text? ✅ / ⚠️ / ❌
   - Scansionabile in 3 minuti? ✅ / ⚠️ / ❌
   - Errori grammaticali? (Lista se sì)
   - Tono appropriato? ✅ / ⚠️ / ❌

6. LUNGHEZZA
   - Nessuna pagina è troppo corta (<300 parole)? ✅ / ⚠️ / ❌
   - Nessuna pagina è troppo lunga (>2000 parole)? ✅ / ⚠️ / ❌
   - Lunghezza proporzionale all'importanza? ✅ / ⚠️ / ❌

7. STRUTTURA HTML
   - Nessun tag malformato? ✅ / ⚠️ / ❌
   - Semantica HTML appropriata? ✅ / ⚠️ / ❌
   - CTA formattato come <a> o <button>? ✅ / ⚠️ / ❌

---

OUTPUT RICHIESTO:

Per OGNI pagina, fornisci:

```
PAGINA: [NN - Titolo]
Status: ✅ OK / 🔄 MINOR REVISION NEEDED / ❌ MAJOR REVISION NEEDED

Feedback:
- [Punto forte 1]
- [Punto forte 2]
- [Area di miglioramento 1 (se presente)]
- [Area di miglioramento 2 (se presente)]

Revisione suggerita:
- [Consiglio 1, se applicabile]
- [Consiglio 2, se applicabile]
- [... solo se necessario]

SEO Score: X/10
Quality Score: X/10
Overall: ✅ APPROVED / 🔄 MINOR CHANGES / ❌ REWRITE
```

---

SUMMARY A FINE REVIEW:

Fornisci anche un RIASSUNTO COMPLESSIVO:

```
REVIEW SUMMARY:
- Pagine OK al primo giro: X/20
- Pagine con minor revision: Y/20
- Pagine con major revision: Z/20
- Total rework needed: Z%
- Timeline impact: [None / +1 day / +2 days]

Top strengths:
1. [Cosa è andato bene]
2. [Cosa è andato bene]

Key issues (if any):
1. [Problema ricorrente]
2. [Problema ricorrente]

Recommendation:
[Proceed to revision / Proceed as-is / Redo certain pages]
```

---

CRITERI DI APPROVAZIONE:

Per procedere senza revision:
- ✅ 18/20 pagine ≥ 8/10 quality score
- ✅ Zero errori grammaticali critici
- ✅ Tono coerente
- ✅ CTA presenti e chiari
- ✅ Fonti ufficiali citate

Se fallisce uno di questi criteri:
- 🔄 Inviare feedback a ChatGPT per revision
- Aspettare versione 2
- Rereview
```

---

## **AFTER CLAUDE REVIEW (Variant B)**

1. **Estrai il feedback:**
   - Pagine OK: [lista]
   - Pagine da revisionare: [lista con feedback]

2. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 15 - [Data]
   **Agente:** Claude
   **Task:** Content review - batch 1 (pages 1-7)
   **Status:** ✅ Review completato
   **Output:** Feedback dettagliato per ogni pagina
   **Risultati:**
   ✅ Pagine OK (no revision): 5/7
   🔄 Pagine da revisionare: 2/7 (minor issues)
   **Principali feedback:**
   - [Feedback 1]
   - [Feedback 2]
   **Next:** Day 16 - Inviare feedback a ChatGPT per revision
   ```

3. **Invia feedback a ChatGPT:**
   ```
   "Ho ricevuto review della pagina [NN]. 
   Feedback: [Descrizione del problema da risolvere].
   Puoi riscrivere [quale sezione] incorporando questo?"
   ```

4. **Ricevi pagine riviste, salva in same `/outputs/phase2_content_pages/`**

5. **Commit:**
   ```bash
   git add outputs/phase2_content_pages/* FILE_LOG.md
   git commit -m "Day15-17: Content review complete - all 20 pages approved with minor revisions"
   git push
   ```

---

**Ready? Send the appropriate prompt variant to Claude.**

**Variant A (Days 5-7): Site Structure**  
**Variant B (Days 15-17): Content Review**
