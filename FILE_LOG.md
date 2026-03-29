# PROJECT LOG: AVIS FROSINONE DIGITAL AUTHORITY BUILD

**Inizio progetto:** 24 Marzo 2026  
**Target completamento:** 30 Aprile 2026  
**Manager:** Mark (AI Director)

---

## QUICK STATUS

| Fase | Task | Status | Progress | Target |
|------|------|--------|----------|--------|
| **Phase 1** | Data Collection & Mapping | ⏳ In Progress | 25% | Day 7 |
| **Phase 2** | Content Generation | ⏳ Upcoming | 0% | Day 17 |
| **Phase 3** | Technical Setup & Launch | ⏳ Upcoming | 0% | Day 30 |

---

## 🔄 DATA PIPELINE (Phase 1)

Perplexity → `/outputs/phase1_query_data.csv` ✅  
↓  
DeepSeek → `/outputs/phase1_theme_ranking.json` ✅  
↓  
Gemini → `/outputs/phase1_institutional_matrix.xlsx` ⏳  
↓  
Claude → `/outputs/phase2_site_structure.md` ⏳  

**Rule:** ogni step parte SOLO dopo validazione dello step precedente

---

## ⚠️ CRITICAL PATH

Perplexity → DeepSeek → Gemini → Claude  

Qualsiasi ritardo qui blocca tutto il progetto  
Buffer massimo per step: **24h**

---

## GIORNALE DETTAGLIATO

---

### Day 1 - 24 Marzo 2026

**Planned:**
- [ ] Creare AVIS_DATA.json
- [ ] Creare PARTNER_LIST.md
- [ ] Creare CURRENT_WEBSITE_AUDIT.md
- [ ] Setup repository
- [ ] First FILE_LOG.md entry

**Status:** ⏳ Pending  
**Agente:** N/A

**Output:**
- `/docs/attachments/AVIS_DATA.json`
- `/docs/attachments/PARTNER_LIST.md`
- `/docs/attachments/CURRENT_WEBSITE_AUDIT.md`

**Validation:**
- [ ] Tutti i file presenti
- [ ] JSON valido
- [ ] Markdown corretto

**Next:** Day 2

---

### Day 2 - 25 Marzo 2026

**Planned:**
- [x] Inviare prompt_01_perplexity.md
- [x] Raccogliere 40+ query
- [x] Validare su Google Trends
- [x] Salvare CSV

**Status:** ✅ Completed  
**Agente:** Perplexity

**Output:**
- `/outputs/phase1_query_data.csv`

**Formato:**
Query | Monthly Volume | Search Intent | Competition

**Validation:**
- [x] 40+ query presenti
- [x] Volumi coerenti
- [x] Intent classificati

**Notes:**
- Dataset pronto per analisi
- Nessun blocco

**Next:** Day 3 (DeepSeek)

---

### Day 3 - 26 Marzo 2026

**Input:**
- `/outputs/phase1_query_data.csv`

**Dependency:**
- Day 2 validato ✅

**Planned:**
- [ ] Inviare CSV a DeepSeek
- [ ] Clustering query
- [ ] Identificare 5-7 temi
- [ ] Ranking per volume

**Status:** ⏳ Pending  
**Agente:** DeepSeek

**Handoff:**
INPUT → `phase1_query_data.csv`  
OUTPUT → `phase1_theme_ranking.json`  

**Output:**
- `/outputs/phase1_theme_ranking.json`

**Validation:**
- [ ] 5-7 temi
- [ ] Ranking coerente
- [ ] Volumi aggregati

**Fail Condition:**
- Se clustering incoerente → rifare analisi

**Next:** Day 4

---

### Day 4 - 27 Marzo 2026

**Input:**
- `/outputs/phase1_theme_ranking.json`

**Dependency:**
- Day 3 completato

**Planned:**
- [ ] Validazione fonti istituzionali
- [ ] Associazione tema → fonte
- [ ] Creazione matrice

**Status:** ⏳ Pending  
**Agente:** Gemini

**Handoff:**
INPUT → `phase1_theme_ranking.json`  
OUTPUT → `phase1_institutional_matrix.xlsx`  

**Output:**
- `/outputs/phase1_institutional_matrix.xlsx`

**Formato:**
Tema | Fonte | Link | Messaggio | Note

**Validation:**
- [ ] Tutti i temi coperti
- [ ] Link verificati
- [ ] Coerenza messaggi

**Fail Condition:**
- Fonti non autorevoli → rifare

**Next:** Day 5

---

### Day 5-7 - 28-30 Marzo 2026

**Input:**
- Tutti gli output precedenti

**Dependency:**
- Day 4 completato

**Planned:**
- [ ] Struttura sito
- [ ] Wireframe logico
- [ ] SEO spec
- [ ] CTA map

**Status:** ⏳ Pending  
**Agente:** Claude

**Handoff:**
INPUT → dataset completo  
OUTPUT → `phase2_site_structure.md`  

**Output:**
- `/outputs/phase2_site_structure.md`

**Validation:**
- [ ] 22 pagine definite
- [ ] Gerarchia chiara
- [ ] CTA coerenti
- [ ] SEO base OK

**Fail Condition:**
- Struttura confusa → revisione

**Next:** Phase 2

---

## PHASE 2: CONTENT GENERATION (Days 8-18)

### Day 8-14: Content Generation

| Batch | Pages | Status | Deadline |
|------|------|--------|----------|
| Batch 1 | 1-5 | ⏳ | Day 9 |
| Batch 2 | 6-10 | ⏳ | Day 11 |
| Batch 3 | 11-15 | ⏳ | Day 13 |
| Batch 4 | 16-20 | ⏳ | Day 14 |

**Agente:** ChatGPT

**Output:**
`/outputs/phase2_content_pages/NN_[tema].html`

---

### Day 15-17: Review

**Agenti:** Claude + ChatGPT

**Planned:**
- [ ] Review completo
- [ ] Fix contenuti
- [ ] Approval finale

**Criteria:**
- Coerenza
- SEO
- CTA
- No testo artificiale

---

### Day 18: Final Deliverable

**Output:**
- `/outputs/phase3_final_deliverable.md`

**Validation:**
- [ ] Completo
- [ ] Nessun placeholder
- [ ] Pronto sviluppo

---

## PHASE 3: TECHNICAL (Days 19-30)

| Task | Owner | Status | Deadline |
|------|------|--------|----------|
| Setup | Dev | ⏳ | Day 20 |
| Content | Dev | ⏳ | Day 24 |
| Schema | Dev | ⏳ | Day 26 |
| Mobile | Dev | ⏳ | Day 27 |
| Performance | Dev | ⏳ | Day 28 |
| QA | Mark + Dev | ⏳ | Day 29 |
| Launch | Mark + Dev | ⏳ | Day 30 |

---

## MASTER CHECKLIST

### Phase 1
- [x] Perplexity (query)
- [ ] DeepSeek (temi)
- [ ] Gemini (fonti)
- [ ] Claude (struttura)

### Phase 2
- [ ] 20 pagine
- [ ] Review completa
- [ ] Deliverable

### Phase 3
- [ ] Dev
- [ ] QA
- [ ] Launch

---

## KPI TRACKING

### Phase 1
- [x] 40+ query
- [ ] 5-7 temi
- [ ] Fonti validate
- [ ] Struttura sito

### Phase 2
- [ ] 20 pagine
- [ ] 100% approvate
- [ ] SEO ready

### Phase 3
- [ ] Sito live
- [ ] Lighthouse 80+
- [ ] Schema OK
- [ ] Mobile OK

---

## BLOCKERS & ISSUES

| Data | Issue | Severity | Status | Resolution |
|------|------|----------|--------|------------|
| - | - | - | - | - |

---

## LESSONS LEARNED

(Aggiornare durante il progetto)

---

## TIMELINE
### Day 4 - 27 Marzo 2026

**Input:**
- `/outputs/phase1_theme_ranking.json`

**Dependency:**
- Day 3 completato ✅

**Planned:**
- Validazione fonti istituzionali
- Associazione tema → fonte
- Creazione matrice

**Status:** ✅ Completed

**Agente:** Gemini

**Handoff:**
INPUT → `phase1_theme_ranking.json`
OUTPUT → `phase1_institutional_matrix.md`

**Output:**
- `/outputs/phase1_institutional_matrix.md`

**Validation:**
- Tutti i 7 temi coperti
- Fonti ufficiali validate (Ministero, AVIS Nazionale, CNS, ASL Frosinone)
- Link verificati
- Messaggi compliant
- Note legali incluse

**Notes:**
- 7 temi validati con fonti istituzionali
- Ricerca speciale su riconoscimento AVIS completata
- 5 domande strategiche per Fase 2 identificate

**Next:** Day 5-7 (Claude - struttura sito)

### Day 5-7 - 28-30 Marzo 2026
**Agente:** Claude
**Task:** Site structure & wireframes
**Status:** ✅ Completed
**Output:** `/outputs/phase2_site_structure.md`
**Pagine definite:** 26 (10 CORE + 9 SECONDARY + 7 TERTIARY)
**Note:** Struttura gerarchica, SEO spec, linking strategy completi
**Next:** Phase 2 - ChatGPT content generation (Day 8-14)
