# PROMPT 02: DEEPSEEK - PATTERN ANALYSIS & CLUSTERING

**Destinatario:** DeepSeek (deepseek.com)  
**Fase:** 1 (Data Collection)  
**Giorno:** 3-4  
**Input file:** `/outputs/phase1_query_data.csv` (da Perplexity)  
**Output file:** `/outputs/phase1_theme_ranking.json`

---

## **WHAT TO ATTACH**

Incolla o allega:

1. **phase1_query_data.csv** — Output da Perplexity (da `/outputs/`)
   - Se non l'hai ancora, ottienilo prima da Perplexity

---

## **COPY & PASTE THIS ENTIRE PROMPT**

```
TASK: Pattern Analysis & Theme Clustering

Contesto:
Ho una lista di 40+ query sulla donazione di sangue raccolte da Google.
Voglio capire i PATTERN logici dietro queste query.

Le query sono state divise in 4 categorie di intent:
- Consapevolezza (Chi è curioso)
- Considerazione (Chi vuole capire se può)
- Azione (Chi è pronto a fare)
- Locale (Specifico territorio)

RICHIESTA:
Analizza il CSV allegato e identifica i TEMI LOGICI sottostanti.

Un "TEMA" è un argomento ricorrente che racchiude multiple query correlate.

Esempio:
  Query: "posso donare diabete", "posso donare se assumo antibiotici", 
          "chi non può donare", "requisiti donazione"
  → TEMA: "Requisiti e esclusioni mediche"

ANALISI RICHIESTA:

1. CLUSTERING
   Per ogni TEMA che identifichi, fornisci:
   - Nome del tema
   - Query che vi appartengono (elenca almeno 3 query per tema)
   - Categoria intent prevalente (Consapevolezza / Considerazione / Azione / Locale)
   - Sottotemi (se il tema ha sub-cluster)
   
   Esempio JSON:
   {
     "theme_1": {
       "name": "Requisiti di idoneità",
       "queries": ["posso donare se...", "chi può donare", "requisiti donazione"],
       "monthly_volume": 8500,
       "intent_category": "Considerazione",
       "sub_themes": [
         "Malattie escludenti",
         "Farmaci incompatibili",
         "Condizioni fisiche",
         "Età e peso"
       ]
     },
     ...
   }

2. VOLUMETRIA AGGREGATA
   Per ogni tema, somma i volumi delle query che vi appartengono.
   Fornisci ranking per volume totale (decrescente).
   
   Esempio:
   Tema | Volume totale | N. query | % del totale
   Requisiti | 8.500 | 12 | 35%
   Logistica | 3.200 | 8 | 13%
   ...

3. PRIORITÀ PER CONVERSIONE
   Non solo volume, ma IMPORTANZA per conversione a donatore.
   
   Ranking logica:
   - Requisti (blocca azione se non resolved) = MASSIMA
   - Logistica (come e dove) = ALTA
   - Benefici (convincimento) = MEDIA
   - Tipi di donazione (approfondimento) = BASSA
   
   Fornisci ranking 1-N dove 1 = massima priorità per conversione.

4. GAPS & OPPORTUNITÀ
   Quali domande le persone cercano che NON hanno risposta chiara online?
   Quali sono le opportunità SEO per AVIS?
   
   Esempio: "Quanto si guadagna donando sangue?" 
   (è una paura comune ma non è quasi mai risolta online)

OUTPUT RICHIESTO:

Formato: JSON strutturato

{
  "analysis_date": "2026-03-26",
  "total_queries_analyzed": XX,
  "themes_identified": N,
  
  "themes": [
    {
      "rank": 1,
      "name": "[Nome tema]",
      "queries_count": N,
      "monthly_volume_total": XXXX,
      "volume_percentage": "XX%",
      "intent_category": "[Consapevolezza / Considerazione / Azione / Locale]",
      "conversion_priority": "MASSIMA / ALTA / MEDIA / BASSA",
      "sub_themes": ["...", "..."],
      "sample_queries": ["query1", "query2", "query3"],
      "seo_opportunity": "High / Medium / Low"
    },
    ... (ripeti per ogni tema, ordinato per volume decrescente)
  ],
  
  "gaps_and_opportunities": [
    {
      "gap": "[Domanda non risposta]",
      "volume_estimate": "N/A o numero",
      "why_important": "[Perché conversione sale se risposta chiara]",
      "avis_opportunity": "[Come AVIS può posizionarsi]"
    },
    ...
  ],
  
  "summary": {
    "total_themes": N,
    "top_3_themes": ["Tema1", "Tema2", "Tema3"],
    "total_volume": XXXXX,
    "notes": "..."
  }
}

REQUISITI PER ANALISI:

- Logico: Un tema deve avere minimo 3 query correlate
- Esclusioni: Evita micro-temi con 1-2 query (aggregate con temi affini)
- Coerenza: Se una query potrebbe stare in 2 temi, scegli il tema primario
- Quantità: Totale temi 5-7 (non più, non meno - consolidate quello che serve)

TONO:
- Analitico, non speculativo
- Spiega la logica del clustering
- Se una query è ambigua, nota il motivo
- Trasparenza su decisioni di categorizzazione

NOTA SPECIALE - TEMA LOCALE:
Identifica quante query sono specifiche di Frosinone/Lazio.
Questo determina quanto il sito locale può rankare per query locale.
Esempio: 8% delle query sono locale → sito locale rankherà per ~8% delle opportunità.
```

---

## **AFTER YOU GET THE RESPONSE**

1. **Copia TUTTA la risposta di DeepSeek** (il JSON completo)

2. **Salva in file:** `/outputs/phase1_theme_ranking.json`
   - Deve essere JSON valido (test su jsonlint.com se dubbio)

3. **Valida il JSON:**
   ```bash
   # Se hai Python:
   python -m json.tool phase1_theme_ranking.json > /dev/null
   # Se valido, nessun errore
   ```

4. **Valida la logica:**
   - Leggi i 7 temi
   - Verifica che ranking sia logico
   - Es: "Requisiti" prima di "Tipi di donazione"? Sì
   - Se ordine sembra sbagliato, contatta DeepSeek

5. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 3 - [Data]
   **Agente:** DeepSeek
   **Task:** Pattern analysis + theme clustering
   **Status:** ✅ Completato
   **Output file:** /outputs/phase1_theme_ranking.json
   **Temi identificati:** 7 (opzione: elencare i nomi)
   **Top-3 temi (per volume):**
   1. [Nome] - XXXXX ricerche/mese
   2. [Nome] - XXXXX ricerche/mese
   3. [Nome] - XXXXX ricerche/mese
   **Validazione:** JSON valido, logica coerente
   **Note:** [Eventuali osservazioni]
   **Next:** Day 4 - Inviare ranking a Gemini
   ```

6. **Commit su Git:**
   ```bash
   git add outputs/phase1_theme_ranking.json FILE_LOG.md
   git commit -m "Day3: DeepSeek analysis - 7 themes identified and ranked"
   git push
   ```

---

## **EXPECTED OUTPUT STRUCTURE**

DeepSeek dovrebbe darti JSON tipo:

```json
{
  "analysis_date": "2026-03-26",
  "total_queries_analyzed": 42,
  "themes_identified": 7,
  
  "themes": [
    {
      "rank": 1,
      "name": "Requisiti di idoneità",
      "queries_count": 12,
      "monthly_volume_total": 8500,
      "volume_percentage": "35%",
      "intent_category": "Considerazione",
      "conversion_priority": "MASSIMA",
      "sub_themes": ["Malattie escludenti", "Farmaci incompatibili", "Condizioni fisiche"],
      "sample_queries": [
        "posso donare se ho il diabete",
        "chi può donare sangue",
        "requisiti donazione"
      ],
      "seo_opportunity": "High"
    },
    {
      "rank": 2,
      "name": "Come e dove donare",
      "queries_count": 8,
      "monthly_volume_total": 3200,
      ...
    },
    ...
  ],
  
  "gaps_and_opportunities": [
    {
      "gap": "Quanto si guadagna donando sangue?",
      "volume_estimate": "N/A (non searchable)",
      "why_important": "Paura comune ma non documentata",
      "avis_opportunity": "Sfatare il mito con pagina FAQ dedicata"
    }
  ]
}
```

---

## **TROUBLESHOOTING**

**DeepSeek dice "non posso fare clustering":**
- Chiedi di raggruppare le query manualmente per tema logico
- Fornisci esempi di tema (vedi prompt)

**JSON non valido:**
- Chiedi di formattare come JSON valido
- Dai link a JSON validator

**Temi troppi (>7):**
- Chiedi di consolidare micro-temi
- "Potete aggregare temi minori in macro-temi?"

**Ranking non logico:**
- Contestare l'ordine con motivazione
- "Requisiti dovrebbe essere #1, perché blocca azione"

---

## **NOTES FOR MARK**

- Questo clustering è fondamentale per struttura sito
- Se temi non convincenti, redo prima di procedere
- 7 temi è il sweet spot (5-9 è range, 7 è target)
- Priorities conversion userai per decidere quali pagine mettere nella home

---

**Ready to send to DeepSeek? Copy the prompt above into deepseek.com chat.**
