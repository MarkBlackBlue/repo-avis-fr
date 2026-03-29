# ORCHESTRATION GUIDE: Come usare i prompt file

**Leggi questo prima di inviare qualsiasi prompt a un agente.**

---

## **FLOW OVERVIEW**

```
Tu (bridge)
    ↓
Invia prompt_01 → Perplexity
    ↓
Ricevi output + salva in /outputs/
    ↓
Invia prompt_02 + output_01 → DeepSeek
    ↓
Ricevi output + salva in /outputs/
    ↓
Invia prompt_03 + output_02 → Gemini
    ↓
... e così via
```

**Ogni prompt è auto-contenuto.** Non dimenticare di allegare i dati del prompt precedente.

---

## **STEP-BY-STEP PER OGNI AGENTE**

### **Come inviare un prompt:**

1. **Apri il tool (Perplexity, DeepSeek, Gemini, ChatGPT, Claude)**

2. **Leggi la sezione "WHAT TO ATTACH" nel file prompt**
   - Es: "Attach: AVIS_DATA.json, CURRENT_WEBSITE_AUDIT.md"

3. **Prepara i file da allegare:**
   - Se il file è in `/docs/attachments/`, copia il contenuto
   - Se è output precedente in `/outputs/`, copia il CSV/JSON

4. **In chat del tool, copia il contenuto INTERO del file prompt**

5. **Aggiungi sezione "ATTACHMENTS:"** sotto il prompt:
   ```markdown
   ---
   ATTACHMENTS:
   
   [AVIS_DATA.json]
   (incolla contenuto file)
   
   [CURRENT_WEBSITE_AUDIT.md]
   (incolla contenuto file)
   ```

6. **Invia al tool**

7. **Aspetta risposta** (tempi variano da 5 minuti a 30 minuti)

8. **Copia COMPLETAMENTE la risposta**

9. **Incolla in nuovo file** in `/outputs/` (vedi istruzioni in ogni prompt file)

10. **Aggiorna FILE_LOG.md** con data, agente, deliverable, status

11. **Commit su Git:**
    ```bash
    git add outputs/[file] FILE_LOG.md
    git commit -m "Day X: [Agente] - [Deliverable]"
    git push
    ```

---

## **ORDINE ESATTO DEGLI AGENTI**

### **Fase 1: Data Collection (Days 1-7)**

```
Day 1: Setup (niente prompt)
    ↓
Day 2-3: prompt_01_perplexity.md → Perplexity
    ↓ (output: phase1_query_data.csv)
    ↓
Day 3-4: prompt_02_deepseek.md + output_01 → DeepSeek
    ↓ (output: phase1_theme_ranking.json)
    ↓
Day 4-5: prompt_03_gemini.md + output_02 → Gemini
    ↓ (output: phase1_institutional_matrix.xlsx)
    ↓
Day 5-7: prompt_05_claude.md + output_01 + output_02 + output_03 → Claude
    ↓ (output: phase2_site_structure.md)
```

**⚠️ ATTENZIONE:** Non saltare agenti. Ogni agente usa output del precedente.

---

### **Fase 2: Content Generation (Days 8-18)**

```
Day 8-14: prompt_04_chatgpt.md (ripeti 20 volte, 1 per pagina) → ChatGPT
    ↓ (output: phase2_content_pages/NN_[tema].html × 20)
    ↓
Day 15-17: prompt_05_claude.md (review version) + outputs_04 → Claude
    ↓ (feedback)
    ↓
Day 16-17: prompt_04_chatgpt.md (revision version) → ChatGPT
    ↓ (revised pages)
    ↓
Day 18: Compilazione manuale final_deliverable.md
```

---

## **DETTAGLI AGENTI**

### **AGENTE 1: PERPLEXITY (Query Research)**

**File:** `prompt_01_perplexity.md`  
**Quando:** Day 2-3  
**Input:** AVIS_DATA.json, CURRENT_WEBSITE_AUDIT.md  
**Output:** CSV con 40+ query + volumi  
**Tempo risposta:** 10-15 minuti  
**Salva come:** `/outputs/phase1_query_data.csv`

**Come usare:**
1. Apri perplexity.ai
2. Incolla prompt_01_perplexity.md
3. Sotto, copia AVIS_DATA.json e CURRENT_WEBSITE_AUDIT.md
4. Invia
5. Copia risposta in CSV file

---

### **AGENTE 2: DEEPSEEK (Pattern Analysis)**

**File:** `prompt_02_deepseek.md`  
**Quando:** Day 3-4  
**Input:** phase1_query_data.csv  
**Output:** JSON con temi ranked + volumi  
**Tempo risposta:** 15-20 minuti  
**Salva come:** `/outputs/phase1_theme_ranking.json`

**Come usare:**
1. Apri deepseek.com
2. Incolla prompt_02_deepseek.md
3. Sotto, copia il CSV da Perplexity
4. Invia
5. Copia risposta JSON

---

### **AGENTE 3: GEMINI (Institutional Validation)**

**File:** `prompt_03_gemini.md`  
**Quando:** Day 4-5  
**Input:** phase1_theme_ranking.json  
**Output:** Matrice tema → fonte ufficiale → messaggio  
**Tempo risposta:** 15-20 minuti  
**Salva come:** `/outputs/phase1_institutional_matrix.xlsx` (markdown table va bene)

**Come usare:**
1. Apri gemini.google.com
2. Incolla prompt_03_gemini.md
3. Sotto, copia il JSON da DeepSeek
4. Invia
5. Copia risposta in formato tabella markdown

---

### **AGENTE 4: CHATGPT (Content Generation)**

**File:** `prompt_04_chatgpt.md`  
**Quando:** Day 8-14 (ripetuto 20 volte)  
**Input:** phase2_site_structure.md + dati pagina specifica  
**Output:** HTML pagina (1 per iterazione)  
**Tempo risposta:** 2-5 minuti per pagina  
**Salva come:** `/outputs/phase2_content_pages/NN_[tema].html`

**Come usare (ripeti per OGNI pagina):**
1. Apri chatgpt.com
2. Incolla prompt_04_chatgpt.md
3. Personalizza: `[TEMA PAGINA]`, `[QUERY TARGET]`, etc
4. Sotto, copia la struttura rilevante da site_structure.md
5. Invia
6. Copia HTML risposta in nuovo file

**⚠️ Importante:** Numero file as `01_home.html`, `02_requisiti.html`, ... `20_contatti.html`

---

### **AGENTE 5: CLAUDE (Orchestration + Review)**

**File:** `prompt_05_claude.md` (versione mapping) + `prompt_05_claude_review.md` (versione review)  
**Quando:** Day 5-7 (mapping), Day 15-17 (review)  
**Input:** 
- Mapping: tutti gli output Phase 1 (CSV, JSON, matrice)
- Review: tutte le 20 pagine HTML
**Output:** 
- Mapping: site_structure.md
- Review: Feedback + approval
**Tempo risposta:** 30-45 minuti  
**Salva come:** 
- `/outputs/phase2_site_structure.md` (mapping)
- FILE_LOG.md (review feedback)

**Come usare:**
1. Apri claude.ai (questo)
2. Incolla prompt_05_claude.md (versione appropriata)
3. Sotto, copia TUTTI gli allegati richiesti
4. Invia
5. Copia risposta nel file appropriato

---

## **CHECKLIST PRIMA DI INVIARE PROMPT**

✅ **Prima di inviare qualsiasi prompt, verificare:**

- [ ] Ho aperto il tool corretto (Perplexity ≠ DeepSeek ≠ Gemini, etc)
- [ ] Ho copiato il file prompt COMPLETO (non solo il titolo)
- [ ] Ho allegato/incollato TUTTI i file richiesti in "WHAT TO ATTACH"
- [ ] Ho personalizzato i campi [BRACKETED] se richiesto
- [ ] Ho verificato che il prompt sia leggibile (non tagliato/corrotto)
- [ ] Ho preparato dove salvare l'output (cartella creata, nome file pronto)

✅ **Dopo aver ricevuto la risposta:**

- [ ] Ho copiato la RISPOSTA COMPLETA (non riassunto)
- [ ] Ho salvato il file nella cartella giusta `/outputs/`
- [ ] Ho verificato il formato (CSV, JSON, HTML, Markdown, etc)
- [ ] Ho aggiornato FILE_LOG.md con data, agente, status
- [ ] Ho fatto commit su Git

---

## **VALIDAZIONE DEI DATI**

### **Perplexity Output (CSV):**
- Deve avere almeno 40 righe
- Colonne: Query | Volume | Intent
- Volumi ragionevoli (da 50 a 10.000+ ricerche/mese)
- Cross-check con Google Trends

### **DeepSeek Output (JSON):**
- 5-7 temi identificati
- Ranking logico (Requisiti > Logistica > Benefici, etc)
- Volumi aggregati sono somma logica

### **Gemini Output (Matrice):**
- 7/7 temi hanno fonte ufficiale
- Link verificabili (non broken)
- Messaggi coerenti con fonte

### **ChatGPT Output (HTML):**
- 1 pagina per richiesta
- H1 unico
- Almeno 1 CTA
- No testo placeholder o Lorem Ipsum

### **Claude Output (Struttura):**
- Directory tree completo
- 22 pagine identificate
- Wireframe logico
- SEO spec per pagina

---

## **TROUBLESHOOTING**

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Agente dà risposta off-topic | Prompt non chiaro / contesto incompleto | Riscrivi prompt con allegati completi |
| Output è generico/AI-sounding | Prompt non personalizzato | Aggiungi brief AVIS-specific nel prompt |
| File size troppo grande | Troppi allegati | Spezza in 2-3 richieste separate |
| Agente dice "non posso" | Tool non supporta il task | Chiedi a tool diverso o riscrivi task |
| Output ha errori | Agente ha interpretato male | Dai feedback specifico con correzione |

---

## **QUICK REFERENCE: File Paths**

| Fase | Agente | Input | Output |
|------|--------|-------|--------|
| **1** | Perplexity | AVIS_DATA.json | `/outputs/phase1_query_data.csv` |
| **1** | DeepSeek | phase1_query_data.csv | `/outputs/phase1_theme_ranking.json` |
| **1** | Gemini | phase1_theme_ranking.json | `/outputs/phase1_institutional_matrix.xlsx` |
| **1** | Claude | Tutti output fase 1 | `/outputs/phase2_site_structure.md` |
| **2** | ChatGPT | site_structure.md × 20 | `/outputs/phase2_content_pages/*.html` |
| **2** | Claude | Tutte 20 HTML | FILE_LOG.md (feedback) |
| **3** | ChatGPT | Feedback Claude | `/outputs/phase2_content_pages/*.html` (revised) |
| **4** | - | Compilation | `/outputs/phase3_final_deliverable.md` |

---

**Ready?** Segui PHASE_GUIDE.md giorno per giorno. Non improvvisare.
