# PROMPT 03: GEMINI - INSTITUTIONAL VALIDATION

**Destinatario:** Gemini (gemini.google.com)  
**Fase:** 1 (Data Collection)  
**Giorno:** 4-5  
**Input file:** `/outputs/phase1_theme_ranking.json` (da DeepSeek)  
**Output file:** `/outputs/phase1_institutional_matrix.xlsx` (salva come markdown table)

---

## **WHAT TO ATTACH**

Incolla o allega:

1. **phase1_theme_ranking.json** — Output da DeepSeek (da `/outputs/`)

---

## **COPY & PASTE THIS ENTIRE PROMPT**

```
TASK: Institutional Validation & Official Sources Research

Contesto:
Ho identificato 7 temi principali che le persone cercano sulla donazione di sangue.
Ora devo validare che questi temi siano COERENTI con autorità ufficiali italiane
e trovare FONTI UFFICIALI che AVIS Frosinone può citare.

Scopo:
1. Verificare che i temi hanno fondamento nelle linee guida ufficiali
2. Trovare fonte ufficiale per ogni tema
3. Definire il messaggio UFFICIALE che AVIS dovrebbe usare

AUTORITÀ DI RIFERIMENTO (Italia):
- Ministero della Salute (www.salute.gov.it)
- Centro Nazionale Sangue (www.centronazionalesangue.it)
- AVIS Nazionale (www.avis.it)
- Decreto Ministeriale 2 novembre 2015 (D.M. 2 Nov 2015)

RICHIESTA:

Per OGNI tema del ranking allegato, fornisci:

1. VALIDAZIONE ISTITUZIONALE
   - Questo tema è supportato dalle linee guida ufficiali? (Sì / No)
   - Se Sì, quale autorità lo menziona?
   - Se No, è un tema comunque rilevante? (Sì / No)

2. FONTE UFFICIALE
   - Link diretto (se possibile)
   - Documento o pagina (specifica)
   - Citazione breve dalla fonte
   
3. MESSAGGIO UFFICIALE SUGGERITO
   - Come AVIS Frosinone dovrebbe comunica questo tema?
   - Basato su linee guida ufficiali
   - Tono: rassicurante, preciso, basato su fatti

4. DISCLAIMER O PRECISAZIONI
   - Ci sono disclaimers legali? (Es: "Consultare sempre il medico")
   - Ci sono eccezioni documentate?
   - Cosa AVIS NON dovrebbe dire (per non essere fuorviante)

OUTPUT RICHIESTO:

Formato: TABELLA MARKDOWN

| Tema | Validato? | Fonte Ufficiale | Link/Documento | Messaggio Suggerito | Note/Disclaimer |
|-----|-----------|---|---|---|---|
| [Nome tema] | Sì/No | Ministero / AVIS / CNS | [Link] | [Messaggio] | [Disclaimer] |
| ... | ... | ... | ... | ... | ... |

DETTAGLI COLONNA PER COLONNA:

**Tema:** [Nome dal ranking di DeepSeek]

**Validato?:** 
- Sì → Linee guida ufficiali supportano questo tema
- No → Non supportato ufficialmente (ma potrebbe essere rilevante)
- Parziale → Supportato con eccezioni

**Fonte Ufficiale:**
- Ministero della Salute
- Centro Nazionale Sangue
- AVIS Nazionale
- D.M. 2 Nov 2015
- (o combinazione di più fonti)

**Link/Documento:**
- URL diretto preferibilmente
- Se URL non reperibile, nome documento + riferimento capitolo
- Formato: "www.salute.gov.it/[pagina]" o "D.M. 2 Nov 2015, Art. X, comma Y"

**Messaggio Suggerito:**
- Come comunicare il tema per un sito no-profit
- 1-2 frasi
- Esempio per "Requisiti": 
  "Per donare sangue, devi avere tra i 18 e i 65 anni e pesare almeno 50 kg. 
   Il medico presso il centro trasfusionale valuterà la tua idoneità."

**Note/Disclaimer:**
- "Consultare sempre il medico presso il centro trasfusionale"
- "Valutazione medica necessaria"
- "Esenzioni possibili in base a valutazione clinica"

---

RICERCA SPECIALE - TEMA LOCALE:

Cercare anche:
- Se il Ministero della Salute riconosce ufficialmente AVIS come partner?
- Quale è il rapporto Ministero → AVIS Nazionale → AVIS locali?
- Che autorità ufficiale ha Frosinone per autorizzare le donazioni?
  (Es: ASL Lazio, Ospedale Spaziani, Centro Trasfusionale)

---

TONO:
- Preciso, citare fonti
- Se non trovi fonte ufficiale per un tema, sii trasparente
- Spiega discrepanze se tema popolare ma non documentato ufficialmente

NOTA FINALE:
La matrice che produci diventerà la BASE PER LA CREDIBILITÀ del nuovo sito AVIS.
Ogni pagina citerà la fonte ufficiale, così il sito stesso avrà AUTORITÀ.
Non improvvisare: ogni messaggio deve essere tracciabile a una fonte ufficiale.
```

---

## **AFTER YOU GET THE RESPONSE**

1. **Copia TUTTA la risposta di Gemini** (la tabella completa)

2. **Salva in file:** `/outputs/phase1_institutional_matrix.xlsx`
   - Se Gemini dà markdown table, salvala come `.md` va bene
   - Se è già in forma table, convertila in CSV o lasciala markdown

3. **Valida i risultati:**
   - Verifica che OGNI tema ha almeno una fonte
   - Controlla se link sono validi (click su 2-3 link random)
   - Se link è rotto, annota in note "link verificare"

4. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 4 - [Data]
   **Agente:** Gemini
   **Task:** Institutional validation + official sources
   **Status:** ✅ Completato
   **Output file:** /outputs/phase1_institutional_matrix.xlsx (or .md)
   **Temi validati:** 7/7
   **Fonti principali:**
   - Ministero della Salute: N temi
   - Centro Nazionale Sangue: N temi
   - AVIS Nazionale: N temi
   - D.M. 2 Nov 2015: N temi
   **Link verificati:** Sì, X link cross-checked
   **Note:** [Eventuali osservazioni su temi particolari]
   **Next:** Day 5 - Inviare tutti i dati a Claude per site structure mapping
   ```

5. **Commit su Git:**
   ```bash
   git add outputs/phase1_institutional_matrix.xlsx FILE_LOG.md
   git commit -m "Day4: Gemini institutional validation - all 7 themes sourced from official authorities"
   git push
   ```

---

## **EXPECTED OUTPUT STRUCTURE**

Gemini dovrebbe darti tabella tipo:

| Tema | Validato? | Fonte Ufficiale | Link/Documento | Messaggio Suggerito | Note |
|---|---|---|---|---|---|
| Requisiti di idoneità | Sì | Ministero della Salute + D.M. 2 Nov 2015 | www.salute.gov.it/donazione + Art. 3 D.M. | "Devi avere 18-65 anni, pesare ≥50kg. Il medico valuta la tua idoneità." | Valutazione medica obbligatoria |
| Come e dove donare | Sì | Centro Nazionale Sangue + AVIS Nazionale | www.centronazionalesangue.it/strutture | "Puoi donare presso il centro trasfusionale dell'Ospedale Spaziani o altri centri autorizzati." | Prenotazione consigliata |
| Benefici della donazione | Parziale | AVIS Nazionale (marketing) | www.avis.it/benefici | "La donazione regolare aiuta a monitorare la tua salute e salva vite." | Non scientificamente comprovato |
| ... | ... | ... | ... | ... | ... |

---

## **TROUBLESHOOTING**

**Gemini non trova fonte ufficiale:**
- Chiedi "Quale è la fonte più autorevole disponibile?"
- Accettare AVIS Nazionale se Ministero non disponibile
- Nota: "Fonte non ufficiale ma comunemente citata"

**Link è rotto:**
- Chiedi "Dammi URL alternativo o documento specifico"
- Riscrivi come "D.M. 2 Nov 2015, Art. X"

**Messaggio suggerito è generico:**
- Chiedi di essere più specifico
- "Aggiungi numeri, date, o dettagli da documento ufficiale"

**Disclaimer incompleto:**
- Aggiungi manualmente: "Consultare medico presso centro trasfusionale"
- Nota: "Disclaimer legale standard"

---

## **NOTES FOR MARK**

- Questa matrice è **CRITICA** per credibilità sito
- Ogni pagina sito citerà la fonte ufficiale
- Se tema NON ha fonte ufficiale → potrebbe non meritar intera pagina
- Usare questa matrice come **Template Copy** per scrittori contenuti

---

**Ready to send to Gemini? Copy the prompt above into gemini.google.com chat.**
