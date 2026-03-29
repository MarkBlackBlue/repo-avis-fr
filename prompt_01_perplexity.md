# PROMPT 01: PERPLEXITY - QUERY RESEARCH

**Destinatario:** Perplexity (perplexity.ai)  
**Fase:** 1 (Data Collection)  
**Giorno:** 2-3  
**Output file:** `/outputs/phase1_query_data.csv`

---

## **WHAT TO ATTACH**

Incolla o allega questi documenti PRIMA di inviare il prompt:

1. **AVIS_DATA.json** — Dati AVIS (da `/docs/attachments/`)
2. **CURRENT_WEBSITE_AUDIT.md** — Audit sito attuale (da `/docs/attachments/`)

Se non li hai ancora, prepara velocemente:
```json
{
  "organization": "AVIS Comunale di Frosinone",
  "territory": "Frosinone, Lazio, Italy",
  "current_donors": 40,
  "monthly_donations": 10
}
```

---

## **COPY & PASTE THIS ENTIRE PROMPT**

```
TASK: Query Research - Donazione Sangue (Italia + Local)

Sono il director di una strategia digitale per AVIS Frosinone, 
un'associazione no-profit che promuove la donazione di sangue 
nel territorio di Frosinone (Lazio, Italia).

Ho bisogno di scoprire ESATTAMENTE cosa cercano le persone quando 
cercano informazioni sulla donazione di sangue.

RICHIESTA:
Forniscimi un elenco COMPLETO di query che le persone cercano su Google 
riguardante la donazione di sangue. Dividi le query per CATEGORIA di intento.

CATEGORIE RICHIESTE:

1. CONSAPEVOLEZZA (Chi non sa ancora ed è curioso)
   - Query generiche sulla donazione
   - Benefici della donazione
   - Importanza della donazione
   - Informazioni sulla sicurezza
   Esempio: "donazione sangue benefici", "perché donare sangue", "importanza donazione"

2. CONSIDERAZIONE (Chi vuole capire se PUÒ)
   - Requisiti medici
   - Esclusioni (malattie, farmaci, etc)
   - Domande su condizioni specifiche
   Esempio: "posso donare se ho il diabete", "requisiti donazione sangue", 
   "chi può donare sangue"

3. AZIONE (Chi è pronto a fare)
   - Località: dove donare nel territorio
   - Orari e prenotazioni
   - Procedura pratica
   - Iscriversi/contatti
   Esempio: "dove donare sangue Frosinone", "centri trasfusionali Frosinone", 
   "come prenotare donazione"

4. LOCALE (Specifico per Frosinone e provincia)
   - Query con "Frosinone", "Frosinone provincia", "Cassino", "Sora"
   - Ricerca AVIS specificamente
   - Ospedali della zona
   Esempio: "donare sangue Frosinone", "AVIS Frosinone", "ospedale Spaziani donazione"

OUTPUT RICHIESTO:
Forniscimi una TABELLA CSV con le seguenti colonne:

Query | Monthly Search Volume (Italia) | Category | Search Intent | Competition Level | Lokale?

Dove:
- Query: la query di ricerca esatta
- Monthly Search Volume: stima volume ricerche mensili (USA Google Trends, SemRush data pubblica, Ahrefs)
- Category: Una delle 4 categorie sopra
- Search Intent: navigazionale / informazionale / transazionale / commerciale
- Competition Level: basso / medio / alto (stima SEO difficulty)
- Lokale?: sì / no

QUANTITÀ: Almeno 30-40 query totali (distribuito tra categorie)

VALIDAZIONE:
- Usa SOLO fonti pubbliche (Google Trends, Ahrefs free, Moz, Answer The Public)
- Se un volume non è tracciabile con certezza, metti "N/A" e nota motivo
- Le query devono essere REALI (non inventate)

TONO:
- Dati precisi, non speculazioni
- Spiega come hai trovato il volume (fonte)
- Se mancano dati, sii trasparente

ORDINA PER:
1. Volume (decrescente)
2. Categoria (Azione > Considerazione > Consapevolezza > Locale)

EXTRA:
- Nota se vedi gap o query non coperte da siti attuali
- Nota se vedi trend interessanti (query in crescita, etc)
```

---

## **AFTER YOU GET THE RESPONSE**

1. **Copia TUTTA la risposta di Perplexity** (non riassunto)

2. **Salva in file:** `/outputs/phase1_query_data.csv`
   - Se Perplexity dà tabella markdown, convertila in CSV standard
   - Separa con virgola o tab

3. **Valida il CSV:**
   - Apri Google Trends (trends.google.com)
   - Confronta 5-10 query random dal CSV vs Google Trends
   - Se volumi sono ±30%, accettabile
   - Se diversi >50%, contatta Perplexity per chiarimenti

4. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 2 - [Data]
   **Agente:** Perplexity
   **Task:** Query research + volume research
   **Status:** ✅ Completato
   **Output file:** /outputs/phase1_query_data.csv
   **Queries raccolte:** 40+ (spec: XX per categoria)
   **Validazione:** Cross-check Google Trends OK (±30% margine)
   **Note:** [Eventuali osservazioni]
   **Next:** Day 3 - Inviare dati a DeepSeek
   ```

5. **Commit su Git:**
   ```bash
   git add outputs/phase1_query_data.csv FILE_LOG.md
   git commit -m "Day2: Perplexity query research - 40+ queries with monthly volumes"
   git push
   ```

---

## **EXPECTED OUTPUT FORMAT**

Perplexity dovrebbe darti qualcosa come:

| Query | Monthly Volume | Category | Intent | Competition | Locale? |
|-------|---|---|---|---|---|
| donazione sangue benefici | 3,200 | Consapevolezza | Informazionale | Medio | No |
| posso donare se diabetico | 890 | Considerazione | Informazionale | Basso | No |
| dove donare sangue Frosinone | 120 | Azione | Navigazionale | Basso | Sì |
| AVIS Frosinone | 45 | Locale | Navigazionale | Basso | Sì |
| ... | ... | ... | ... | ... | ... |

---

## **TROUBLESHOOTING**

**Perplexity dice "non posso":**
- Chiedi di usare fonte pubblica (Google Trends)
- Spiega che basta stima, non dato esatto
- Riscrivi: "Dammi una lista qualitativa ordinata per importanza"

**Volumi sembra troppo alto/basso:**
- Cross-check con Google Trends personalmente
- Se davvero wrong, chiedi a Perplexity source

**Output manca categoria:**
- Chiedi di splitare per categoria come richiesto
- Fornisci gli esempi di query

---

## **NOTES FOR MARK**

- Questo è il primo passo critico
- Qualità di questo CSV determina tutto il resto
- Non procedere a Day 3 se CSV non convincente
- Se Perplexity output è generico, riscrivi prompt con dettagli AVIS-specific

---

**Ready to send to Perplexity? Copy the prompt above into perplexity.ai chat.**
