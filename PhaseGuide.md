# PHASE GUIDE: ESECUZIONE GIORNO PER GIORNO

**Per non perdere il filo conduttore, segui esattamente questa timeline.**

---

## **PRIMA DI INIZIARE (Day 0 - Oggi)**

### Checklist Pre-Lancio:
- [ ] Hai clonato questo repo
- [ ] Hai letto BRIEF.md (capire il "perché")
- [ ] Hai letto README.md (capire il "come")
- [ ] Hai accesso a: Perplexity, DeepSeek, Gemini, ChatGPT, Claude
- [ ] Hai accesso a avisfrosinone.it (per reference)
- [ ] Hai preparato: foto "un giorno col dono", dati AVIS disponibili
- [ ] Hai creato `/docs/attachments/` con file necessari

**Se manca qualcosa, STOP. Non procedere finché tutto è pronto.**

---

## **PHASE 1: DATA COLLECTION & MAPPING**

**Durata:** Settimana 1-2 (Days 1-10)  
**Output finale:** Struttura sito dettagliata + ranking priorità

---

### **DAY 1: Setup + Preparazione Documenti**

**Mattina (1 ora)**

1. **Crea file `/docs/attachments/AVIS_DATA.json`**
   - Compila con dati reali AVIS (vedi template in README.md)
   - Salva in repo
   - Commit: `git commit -m "Day1: AVIS base data compiled"`

2. **Crea file `/docs/attachments/PARTNER_LIST.md`**
   - Lista 15 convenzioni partner con: nome, tipo, sconto, stato attivo
   - Nota: marca quali sono "da verificare" (il focus della fase riordino)
   - Salva in repo
   - Commit: `git commit -m "Day1: Partner list documented"`

3. **Crea file `/docs/attachments/CURRENT_WEBSITE_AUDIT.md`**
   - Analisi veloce avisfrosinone.it (problemi, punti di forza, opportunità)
   - Vedi template in README.md
   - Salva in repo
   - Commit: `git commit -m "Day1: Current website audit completed"`

**Pomeriggio (1 ora)**

4. **Inzia FILE_LOG.md**
   - Aggiungi entry: data, giorno, checklist completato
   - Commit

**End of Day 1:** Preparazione completata. Repo pronto. 

---

### **DAY 2-3: PERPLEXITY - QUERY RESEARCH**

**When:** Day 2 mattina

**Task:** Raccogliere 40+ query sulla donazione con volumi mensili

**Step-by-step:**

1. **Apri Perplexity** (perplexity.ai)

2. **Copia prompt file completo** da `/prompts/prompt_01_perplexity.md`

3. **In Perplexity chat, incolla:**
   ```
   [Contenuto intero di prompt_01_perplexity.md]
   
   CONTESTO AGGIUNTIVO:
   [Contenuto di AVIS_DATA.json]
   [Contenuto di CURRENT_WEBSITE_AUDIT.md]
   ```

4. **Aspetta risposta** (5-15 minuti)

5. **Copia il CSV/tabella risultante** in `/outputs/phase1_query_data.csv`

6. **Valida i risultati:**
   - Apri Google Trends
   - Verifica 5-10 query random dal CSV vs Google Trends
   - Se volumetrie sono coerenti (±30%), va bene
   - Se diverse >50%, chiedere a Perplexity chiarimenti

7. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 2 - [Data]
   **Agente:** Perplexity  
   **Task:** Query research + volumi  
   **Status:** ✅ Completato  
   **Output:** /outputs/phase1_query_data.csv (40 query)  
   **Validazione:** Cross-check su Google Trends OK  
   **Note:** [eventuali note su discrepanze, outlier]  
   **Next:** Day 3 - Inviare dati a DeepSeek  
   ```

8. **Commit:**
   ```bash
   git add outputs/phase1_query_data.csv FILE_LOG.md
   git commit -m "Day2: Perplexity query research completed - 40 queries with volumes"
   git push
   ```

**End of Day 2-3:** CSV di 40 query pronti per fase successiva.

---

### **DAY 3-4: DEEPSEEK - PATTERN ANALYSIS**

**When:** Day 3 mattina (parallelo a validazione Perplexity)

**Task:** Analizzare query, identificare temi prioritari, ranking

**Step-by-step:**

1. **Apri DeepSeek** (deepseek.com)

2. **Copia prompt file** da `/prompts/prompt_02_deepseek.md`

3. **In DeepSeek chat, incolla:**
   ```
   [Contenuto intero di prompt_02_deepseek.md]
   
   DATI ALLEGATI (CSV Perplexity):
   [Incolla il CSV completo da /outputs/phase1_query_data.csv]
   
   CONTESTO:
   [AVIS_DATA.json]
   ```

4. **Aspetta risposta** (10-20 minuti)

5. **Copia output in `/outputs/phase1_theme_ranking.json`**
   - Formato: JSON con clustering temi, volumi totali per cluster, ranking

6. **Valida risultati:**
   - Leggi il ranking, verifica che ha senso logico
   - Es: "Requisiti" prima di "Tipi di donazione"? Sì, logico.
   - Se ranking sembra sbagliato, contatta DeepSeek con feedback

7. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 3 - [Data]
   **Agente:** DeepSeek  
   **Task:** Pattern analysis + theme clustering  
   **Status:** ✅ Completato  
   **Output:** /outputs/phase1_theme_ranking.json (7 temi identificati)  
   **Top-5 temi:**
   1. Requisiti di idoneità (8.500 ricerche/mese)
   2. Come e dove donare (3.200 ricerche/mese)
   ... [ecc]
   **Next:** Day 4 - Inviare ranking a Gemini  
   ```

8. **Commit:**
   ```bash
   git add outputs/phase1_theme_ranking.json FILE_LOG.md
   git commit -m "Day3: DeepSeek analysis - 7 themes identified and ranked"
   git push
   ```

**End of Day 3-4:** Ranking temi definitivo.

---

### **DAY 4-5: GEMINI - INSTITUTIONAL VALIDATION**

**When:** Day 4 mattina

**Task:** Validare temi vs autorità istituzionali + trovare fonti ufficiali

**Step-by-step:**

1. **Apri Gemini** (gemini.google.com)

2. **Copia prompt file** da `/prompts/prompt_03_gemini.md`

3. **In Gemini chat, incolla:**
   ```
   [Contenuto intero di prompt_03_gemini.md]
   
   TEMI DA VALIDARE (da DeepSeek):
   [Incolla il ranking JSON da /outputs/phase1_theme_ranking.json]
   ```

4. **Aspetta risposta** (10-20 minuti)

5. **Copia output in `/outputs/phase1_institutional_matrix.xlsx`** (o .md se markdown)
   - Formato: Tabella con colonne: Tema, Fonte Ufficiale, Link/Riferimento, Messaggio Suggerito, Note

6. **Valida risultati:**
   - Verificare che OGNI tema ha almeno una fonte ufficiale
   - Controllare link se possibile
   - Se manca fonte per tema importante, contatta Gemini

7. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 4 - [Data]
   **Agente:** Gemini  
   **Task:** Institutional validation + official sources  
   **Status:** ✅ Completato  
   **Output:** /outputs/phase1_institutional_matrix.xlsx  
   **Sources found:** 7/7 temi hanno fonte ufficiale  
   **Principali fonti:**
   - Ministero della Salute
   - Centro Nazionale Sangue
   - AVIS Nazionale
   **Next:** Day 5 - Inviare tutti i dati a Claude per mapping struttura  
   ```

8. **Commit:**
   ```bash
   git add outputs/phase1_institutional_matrix.xlsx FILE_LOG.md
   git commit -m "Day4: Gemini institutional validation - all themes sourced"
   git push
   ```

**End of Day 4-5:** Validazione istituzionale completata.

---

### **DAY 5-7: CLAUDE - SITE STRUCTURE MAPPING**

**When:** Day 5 pomeriggio

**Task:** Tradurre temi in struttura sito dettagliata + wireframe

**Step-by-step:**

1. **Apri Claude** (questo, claude.ai)

2. **Copia prompt file** da `/prompts/prompt_05_claude.md`

3. **In Claude chat, incolla:**
   ```
   [Contenuto intero di prompt_05_claude.md]
   
   ALLEGATI (in ordine):
   1. [AVIS_DATA.json]
   2. [CURRENT_WEBSITE_AUDIT.md]
   3. [CSV da Perplexity: /outputs/phase1_query_data.csv]
   4. [JSON da DeepSeek: /outputs/phase1_theme_ranking.json]
   5. [Matrice da Gemini: /outputs/phase1_institutional_matrix.xlsx]
   ```

4. **Aspetta risposta** (20-30 minuti, articolo lungo)

5. **Copia output in `/outputs/phase2_site_structure.md`**
   - Contiene: directory tree completo, wireframe logico, SEO spec per pagina

6. **Valida risultati:**
   - Leggi struttura, verifica che:
     * Home ha 2 CTA chiari (come donare / perché donare)
     * Requisiti prima di logistica
     * Blog integrato, non sepolto
     * Convenzioni visibili
     * CTA in ogni pagina

7. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 5-7 - [Data]
   **Agente:** Claude  
   **Task:** Site structure mapping + wireframe  
   **Status:** ✅ Completato  
   **Output:** /outputs/phase2_site_structure.md  
   **Structure overview:**
   - 1 Home (2 CTA)
   - 3 Sezioni principali (Come Donare, Perché Donare, Community)
   - 1 Sezione Convenzioni
   - 1 Sezione Chi Siamo
   - 1 Sezione Contatti
   - Total: 22 pagine prioritarie (7 immediate, 15 secondary)
   **Next:** Phase 2 - Content generation (ChatGPT)  
   ```

8. **Commit:**
   ```bash
   git add outputs/phase2_site_structure.md FILE_LOG.md
   git commit -m "Day5-7: Claude site mapping - complete structure + wireframes"
   git push
   ```

**End of Phase 1:** Tutta la struttura sito pronta, basata su dati reali.

---

## **PHASE 2: CONTENT GENERATION & REVIEW**

**Durata:** Settimana 2-3 (Days 8-18)  
**Output finale:** 20 pagine scritte, SEO-ready, strutturate

---

### **DAY 8-14: CHATGPT - CONTENT GENERATION**

**When:** Day 8 mattina

**Task:** Generare 20 pagine di contenuto basate su struttura sito

**Step-by-step (Batch Process):**

1. **Crea file `/outputs/phase2_content_pages/`** (cartella vuota)

2. **Per OGNI pagina prioritaria (vedi structure.md):**

   a. **Copia prompt file** da `/prompts/prompt_04_chatgpt.md`
   
   b. **Personalizza il prompt:**
      ```
      [Contenuto base di prompt_04_chatgpt.md]
      
      TEMA PAGINA: [Es: "Requisiti di idoneità"]
      QUERY TARGET: [Es: "Posso donare sangue se ho il diabete?"]
      VOLUME MENSILE: [Es: 180 ricerche/mese]
      
      CONTESTO:
      - Struttura sito: [Vedi /outputs/phase2_site_structure.md]
      - Fonte ufficiale: [Da matrice Gemini]
      - Tono: [Rassicurante, diretto, basato su fatti]
      ```
   
   c. **Invia a ChatGPT**
   
   d. **Aspetta risposta** (2-5 minuti per pagina)
   
   e. **Copia HTML in `/outputs/phase2_content_pages/NN_[tema].html`**
      - Es: `02_requisiti_diabete.html`
   
   f. **Aggiorna FILE_LOG.md** (end of day):
      ```markdown
      ## Day 8 - [Data]
      **Agente:** ChatGPT  
      **Task:** Content generation - batch 1 (pages 1-5)  
      **Pagine generate:**
      ✅ Home (CTA, hero, value prop)
      ✅ Requisiti (overview + checklist)
      ✅ Domande frequenti (requisiti medici)
      ✅ Procedura (timeline)
      ✅ Dove donare (mappa + orari)
      **Status:** 5/20 pagine  
      **Next:** Day 9 - Continua batch 2  
      ```

3. **Routine giornaliera (Days 8-14):**
   - Mattina: Invia 3-4 pagine a ChatGPT
   - Pomeriggio: Ricevi output, salva file
   - Sera: Aggiorna FILE_LOG.md, commit

4. **End of Day 14:**
   ```bash
   git status  # Verifica 20 file HTML in /outputs/phase2_content_pages/
   git add outputs/phase2_content_pages/* FILE_LOG.md
   git commit -m "Day8-14: ChatGPT content generation - 20 pages complete"
   git push
   ```

**End of Day 8-14:** 20 pagine generate.

---

### **DAY 15-17: CLAUDE - CONTENT REVIEW**

**When:** Day 15 mattina

**Task:** Revisionare tutte 20 pagine, feedback, coherence check

**Step-by-step:**

1. **Copia prompt file** da `/prompts/prompt_05_claude.md` (versione review)

2. **In Claude chat, incolla:**
   ```
   [Contenuto di prompt review]
   
   PAGINE DA REVISIONARE (allega tutte 20 HTML o spezzale in 3-4 batch):
   [Copia contenuto delle pagine]
   
   CHECKLIST DI REVIEW:
   - Coerenza narrativa tra pagine
   - Tono consistente
   - CTA chiari e coerenti
   - Zero contraddizioni
   - SEO base (keyword, H1, meta)
   - Link interni logici
   - No testi generici/AI-sounding
   ```

3. **Aspetta resposta** (30-45 minuti)

4. **Ricevi feedback:**
   - Quali pagine vanno bene
   - Quali need revision
   - Suggerimenti specifici per ogni pagina

5. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 15 - [Data]
   **Agente:** Claude  
   **Task:** Content review - batch 1 (pages 1-7)  
   **Risultati review:**
   ✅ 5 pagine OK (no changes)
   🔄 2 pagine need minor revision (tono, link)
   **Feedback:** [Riassunto punti critici]
   **Next:** Day 16 - Send feedback to ChatGPT for revisions  
   ```

6. **Day 16-17: Invia feedback a ChatGPT**
   ```
   Prompt: "Ho ricevuto feedback sulla review di [pagina]. 
   Problema: [descrizione].
   Soluzione: [come risolverlo].
   Riscrivimi il paragrafo/sezione."
   ```

7. **Ricevi pagine revisionat, salva in stesso `/outputs/phase2_content_pages/`**

8. **Commit:**
   ```bash
   git add outputs/phase2_content_pages/* FILE_LOG.md
   git commit -m "Day15-17: Content review - all 20 pages revised and approved"
   git push
   ```

**End of Day 15-17:** Tutte 20 pagine approvate e pronte.

---

### **DAY 18: FINAL DELIVERABLE**

**When:** Day 18 mattina

**Task:** Compilare documento finale per sviluppatore

**Step-by-step:**

1. **Crea file** `/outputs/phase3_final_deliverable.md`

2. **Contenuto:**
   ```markdown
   # DELIVERABLE FINALE: AVIS FROSINONE DIGITAL REBUILD
   ## Pronto per implementazione tecnica
   
   ### STRUTTURA SITO
   [Copia da /outputs/phase2_site_structure.md]
   
   ### CONTENUTI (20 PAGINE)
   [Indice delle 20 pagine HTML con link ai file]
   
   ### SPECIFICHE TECNICHE
   - Platform: [Webflow/WordPress/Custom]
   - CMS: [Quale]
   - Schema.org: FAQPage, LocalBusiness, Article (su ogni pagina)
   - Mobile: Responsive 100%
   - Performance: Target Lighthouse 80+
   
   ### SEO CHECKLIST
   - Meta title per ogni pagina
   - Meta description per ogni pagina
   - H1 unico per pagina
   - Internal linking: [mappa]
   - Sitemap ready: [XML template]
   
   ### LAUNCH CHECKLIST
   - [ ] Dominio pronto
   - [ ] Hosting setup
   - [ ] SSL configurato
   - [ ] CDN (opzionale)
   - [ ] Analytics setup
   - [ ] GSC verification
   - [ ] Monitoring attivo
   
   ### FILE ALLEGATI
   - /outputs/phase2_site_structure.md (wireframe + spec)
   - /outputs/phase2_content_pages/* (20 HTML files)
   - /outputs/phase1_query_data.csv (SEO keywords)
   - /outputs/phase1_institutional_matrix.xlsx (source references)
   ```

3. **Commit:**
   ```bash
   git add outputs/phase3_final_deliverable.md
   git commit -m "Day18: Final deliverable compiled - ready for dev team"
   git push
   ```

**End of Phase 2:** Contenuti pronti, nessuna modifica richiesta dall'utente finale.

---

## **PHASE 3: TECHNICAL SETUP & LAUNCH**

**Durata:** Settimana 3-4 (Days 19-30)  
**Chi:** Developer esterno (fuori scope questo repo)

**Mark's role:** Supervisionare, validare, approvare

---

### **DAY 19-28: DEVELOPER IMPLEMENTATION**

- Setup piattaforma
- Implementazione contenuti
- Schema.org configurazione
- Mobile testing
- Performance optimization

**Tu aggiorna FILE_LOG.md con:** data, status, blocchi eventuali

---

### **DAY 28-30: QA & LAUNCH**

- Final testing
- GSC setup
- DNS updates
- Monitoring attivo

**TARGET LAUNCH:** Day 30 (30 Aprile 2026)

---

## **TIMELINE COMPLETA (A COLPO D'OCCHIO)**

```
WEEK 1:
Day 1:    Setup + preparazione documenti
Day 2-3:  Perplexity (query research)
Day 3-4:  DeepSeek (analysis)
Day 4-5:  Gemini (validation)

WEEK 2:
Day 5-7:  Claude (site structure)
Day 8-14: ChatGPT (content generation)

WEEK 3:
Day 15-17: Claude (content review + revision)
Day 18:    Final deliverable compilation

WEEK 4:
Day 19-28: Developer (implementation)
Day 28-30: QA + Launch

TARGET: 30 Aprile 2026 (Day 30)
```

---

## **DAILY SYNC TEMPLATE**

**Copia e incolla questo template ogni giorno in FILE_LOG.md:**

```markdown
## Day X - [Data: DD Mese YYYY]

### Morning (9 AM)
**Planned:** [Cosa dovevi fare]
**Status:** [In progress / Completed / Blocked]
**Agente:** [Nome agente, se rilevante]

### Output
**File:** [Dove hai salvato il risultato]
**Lines of code / Words / Queries:** [Metrica rilevante]
**Quality check:** [OK / Needs revision / ...]

### Validation
**Validated against:** [Source/tool usato]
**Result:** [✅ OK / ⚠️ Minor issues / ❌ Major issues]

### Next
**Tomorrow:** [Cosa devi fare Day X+1]
**Blockers:** [Nessuno / Lista eventuali blocchi]

### Notes
[Osservazioni, insights, problemi incontrati, soluzioni trovate]
```

---

## **COSA FARE SE TI PERDI**

1. **Apri FILE_LOG.md** → vedi dove sei arrivato
2. **Leggi PHASE_GUIDE.md** → trova il giorno corrispondente
3. **Leggi il prompt file** → capisce che cosa devi fare
4. **Procedi come descritto**

Se ancora confuso:
- Contatta Mark
- Non procedere se in dubbio

---

**Sei pronto? Inizia da DAY 1. 🚀**
