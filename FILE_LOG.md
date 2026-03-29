# PROJECT LOG: AVIS FROSINONE DIGITAL AUTHORITY BUILD

**Inizio progetto:** 24 Marzo 2026  
**Target completamento:** 30 Aprile 2026  
**Manager:** Mark (AI Director)

---

## **QUICK STATUS**

| Fase | Task | Status | Progress | Target |
|------|------|--------|----------|--------|
| **Phase 1** | Data Collection & Mapping | ⏳ Upcoming | 0% | Day 7 |
| **Phase 2** | Content Generation | ⏳ Upcoming | 0% | Day 17 |
| **Phase 3** | Technical Setup & Launch | ⏳ Upcoming | 0% | Day 30 |

---

## **GIORNALE DETTAGLIATO**

### **Day 1 - 24 Marzo 2026**

**Planned:**
- [ ] Creare AVIS_DATA.json
- [ ] Creare PARTNER_LIST.md
- [ ] Creare CURRENT_WEBSITE_AUDIT.md
- [ ] Setup repository
- [ ] First FILE_LOG.md entry

**Status:** ⏳ Pending  
**Agente:** N/A (setup manuale)

**Output:**
- File: `/docs/attachments/AVIS_DATA.json` (da compilare)
- File: `/docs/attachments/PARTNER_LIST.md` (da compilare)
- File: `/docs/attachments/CURRENT_WEBSITE_AUDIT.md` (da compilare)

**Validation:**
- [ ] Tutti i file presenti
- [ ] JSON valido (test JSON validator)
- [ ] Markdown formattato correttamente

**Next:**
- Day 2: Perplexity query research

**Notes:**
- [Aspetta che Mark inizi il progetto]
- [Verifica accesso a tutti gli strumenti AI]
- [Sincronizza repo con GitHub]

---

### **Day 2 - 25 Marzo 2026**

**Planned:**
- [ ] Inviare prompt_01_perplexity.md a Perplexity
- [ ] Raccogliere 40+ query sulla donazione
- [ ] Validare su Google Trends
- [ ] Salvare CSV in /outputs/

**Status:** ⏳ Pending  
**Agente:** Perplexity

**Output:**
- File: `/outputs/phase1_query_data.csv` (da ricevere)
- Formato: CSV con colonne: Query | Monthly Volume | Search Intent | Competition

**Validation:**
- [ ] CSV ha 40+ righe
- [ ] Volumi ragionevoli (cross-check Google Trends)
- [ ] Intenti categorizzati correttamente

**Next:**
- Day 3: DeepSeek analysis

**Notes:**
- [Placeholder for Day 2 results]

---

### **Day 3 - 26 Marzo 2026**

**Planned:**
- [ ] Inviare phase1_query_data.csv a DeepSeek
- [ ] Analizzare pattern + clustering
- [ ] Identificare 5-7 temi prioritari
- [ ] Ranking per volume

**Status:** ⏳ Pending  
**Agente:** DeepSeek

**Output:**
- File: `/outputs/phase1_theme_ranking.json` (da ricevere)
- Formato: JSON con temi, sub-temi, volumi aggregati, ranking

**Validation:**
- [ ] 5-7 temi identificati
- [ ] Ranking logicamente coerente
- [ ] Volumi aggregati corretti

**Next:**
- Day 4: Gemini institutional validation

**Notes:**
- [Placeholder for Day 3 results]

---

### **Day 4 - 27 Marzo 2026**

**Planned:**
- [ ] Inviare ranking temi a Gemini
- [ ] Validare vs autorità istituzionali
- [ ] Trovare fonte ufficiale per ogni tema
- [ ] Compilare matrice: tema → fonte → messaggio

**Status:** ⏳ Pending  
**Agente:** Gemini

**Output:**
- File: `/outputs/phase1_institutional_matrix.xlsx` (da ricevere)
- Formato: Tabella con colonne: Tema | Fonte Ufficiale | Link | Messaggio Suggerito | Note

**Validation:**
- [ ] 7/7 temi hanno fonte
- [ ] Link verificati
- [ ] Messaggi coerenti con fonte

**Next:**
- Day 5: Claude site structure mapping

**Notes:**
- [Placeholder for Day 4 results]

---

### **Day 5-7 - 28-30 Marzo 2026**

**Planned:**
- [ ] Inviare tutti i dati a Claude
- [ ] Ricevere struttura sito completa
- [ ] Wireframe logico per ogni sezione
- [ ] SEO spec per pagina

**Status:** ⏳ Pending  
**Agente:** Claude

**Output:**
- File: `/outputs/phase2_site_structure.md` (da ricevere)
- Formato: Markdown con: directory tree, wireframe, SEO spec, CTA map

**Validation:**
- [ ] 22 pagine identificate (7 core, 15 secondary)
- [ ] Gerarchia logica
- [ ] CTA coerenti
- [ ] SEO base configurato

**Next:**
- Day 8: ChatGPT content generation (batch 1-5)

**Notes:**
- [Placeholder for Phase 1 completion]

---

## **PHASE 2: CONTENT GENERATION (Days 8-18)**

### **Day 8-14: Content Generation Batch**

| Batch | Pages | Status | Deadline |
|-------|-------|--------|----------|
| Batch 1 | 1-5 | ⏳ Pending | Day 9 |
| Batch 2 | 6-10 | ⏳ Pending | Day 11 |
| Batch 3 | 11-15 | ⏳ Pending | Day 13 |
| Batch 4 | 16-20 | ⏳ Pending | Day 14 |

**Agente:** ChatGPT

**Output location:** `/outputs/phase2_content_pages/NN_[tema].html`

**Daily log template:**
```markdown
### Day X - [Data]
**Batch:** [N]
**Pages generated:** X-Y
**Status:** [X/5 completate]
**Validation:** [Quick QA]
**Next:** [Quale batch domani]
**Issues:** [Nessuno / Lista problemi]
```

---

### **Day 15-17: Content Review**

**Planned:**
- [ ] Revisionare tutte 20 pagine
- [ ] Feedback per ogni pagina
- [ ] Identificare pagine che need revision
- [ ] Inviare feedback a ChatGPT
- [ ] Ricevere pagine riviste
- [ ] Final approval

**Status:** ⏳ Pending  
**Agente:** Claude (review) + ChatGPT (revision)

**Review criteria:**
- Coerenza narrativa
- Tono consistente
- CTA chiari
- Zero contraddizioni
- SEO base OK
- Link interni logici
- No AI-sounding text

**Output:**
- Updated files in `/outputs/phase2_content_pages/`
- Tutte pagine con ✅ approval

**Next:**
- Day 18: Final deliverable

**Notes:**
- [Placeholder for review results]

---

### **Day 18: Final Deliverable**

**Planned:**
- [ ] Compilare `/outputs/phase3_final_deliverable.md`
- [ ] Includere tutta la struttura
- [ ] Includere indice delle 20 pagine
- [ ] Spec tecniche complete
- [ ] SEO checklist
- [ ] Launch checklist

**Status:** ⏳ Pending  
**Agente:** N/A (compilation)

**Output:**
- File: `/outputs/phase3_final_deliverable.md`
- Ready for developer pickup

**Validation:**
- [ ] Documento completo
- [ ] Tutti i file linkati correttamente
- [ ] Nessun placeholder vuoto

**Next:**
- Phase 3: Developer implementation (Days 19-28)

**Notes:**
- [Placeholder for deliverable]

---

## **PHASE 3: TECHNICAL SETUP (Days 19-30)**

**Responsabile:** Developer esterno  
**Mark's role:** Supervision + approval

| Task | Owner | Status | Deadline |
|------|-------|--------|----------|
| Platform setup | Dev | ⏳ | Day 20 |
| Content implementation | Dev | ⏳ | Day 24 |
| Schema.org config | Dev | ⏳ | Day 26 |
| Mobile testing | Dev | ⏳ | Day 27 |
| Performance optimization | Dev | ⏳ | Day 28 |
| QA + final testing | Mark + Dev | ⏳ | Day 29 |
| Launch | Mark + Dev | ⏳ | Day 30 |

**Notes:**
- [Update progressivamente con status da developer]

---

## **MASTER CHECKLIST**

### Phase 1: Data Collection ✅ / ⏳ / ❌
- [ ] Day 1-2: Setup + Perplexity (40 query)
- [ ] Day 3-4: DeepSeek (5-7 temi ranked)
- [ ] Day 4-5: Gemini (temi validati)
- [ ] Day 5-7: Claude (struttura sito)

### Phase 2: Content Generation ✅ / ⏳ / ❌
- [ ] Day 8-14: ChatGPT (20 pagine)
- [ ] Day 15-17: Claude review + revision
- [ ] Day 18: Final deliverable

### Phase 3: Technical ✅ / ⏳ / ❌
- [ ] Day 19-28: Developer implementation
- [ ] Day 28-30: QA + Launch

---

## **KPI TRACKING**

### Phase 1 Success Metrics
- [ ] 40+ query raccolte
- [ ] 5-7 temi identificati
- [ ] 100% temi validati con fonte
- [ ] Struttura sito completa

### Phase 2 Success Metrics
- [ ] 20 pagine scritte
- [ ] 100% pagine approvate (no revision needed)
- [ ] Tutte pagine SEO-ready
- [ ] CTA coerenti in 20/20

### Phase 3 Success Metrics
- [ ] Sito live
- [ ] Lighthouse score 80+
- [ ] Schema.org valid 100%
- [ ] Responsive mobile 100%
- [ ] GSC setup + indexed

---

## **BLOCKERS & ISSUES**

| Data | Issue | Severity | Status | Resolution |
|------|-------|----------|--------|------------|
| - | - | - | - | - |

---

## **LESSONS LEARNED**

(Aggiorna mentre procedi)

---

## **TIMELINE OVERVIEW**

```
Mar 24-30 (Week 1): Phase 1 - Data Collection
  Day 1:   Setup
  Day 2-3: Perplexity
  Day 3-4: DeepSeek  
  Day 4-5: Gemini
  Day 5-7: Claude mapping

Mar 31 - Apr 6 (Week 2): Phase 2 - Content
  Day 8-14: ChatGPT content gen
  Day 15-17: Claude review + revision
  Day 18: Final deliverable

Apr 7-13 (Week 3): Phase 3 - Technical
  Day 19-28: Developer implementation
  Day 28-30: QA + Launch

TARGET LAUNCH: 30 Aprile 2026
```

---

**Last updated:** [Aggiorna ogni giorno]  
**Next review:** [Prossimo checkpoint]
