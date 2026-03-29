# AVIS FROSINONE - DIGITAL AUTHORITY BUILD

**Repository per la ristrutturazione digitale di avisfrosinone.it**

Questo repository contiene tutta l'orchestrazione di agenti AI per costruire un sito moderno, autoritario e orientato alla conversione di nuovi donatori.

---

## **QUICK START (Leggi prima di tutto)**

1. **Leggi BRIEF.md** → Capisce l'obiettivo complessivo
2. **Segui PHASE_GUIDE.md** → Step-by-step di cosa fare ogni giorno
3. **Usa i file in /prompts/** → Copia-incolla i prompt nei rispettivi agenti AI
4. **Aggiorna FILE_LOG.md** → Documenta i risultati (diario)
5. **Consulta /docs/** → Riferimenti, template, formati

---

## **STRUTTURA DIRECTORY**

```
AVIS-FROSINONE-DIGITAL/
│
├── BRIEF.md                          # ← LEGGI PRIMA: strategia + obiettivi
├── README.md                         # ← Sei qui
├── PHASE_GUIDE.md                    # ← Come procedere passo-passo
├── FILE_LOG.md                       # ← Aggiorna quotidianamente (TUO DIARIO)
│
├── /prompts/                         # ← File prompt pronti per agenti AI
│   ├── 00_ORCHESTRATION.md           # ← LEGGI: Come usare gli agenti
│   ├── prompt_01_perplexity.md       # ← Prompt per Perplexity (ricerca)
│   ├── prompt_02_deepseek.md         # ← Prompt per DeepSeek (analisi)
│   ├── prompt_03_gemini.md           # ← Prompt per Gemini (validazione)
│   ├── prompt_04_chatgpt.md          # ← Prompt per ChatGPT (contenuti)
│   └── prompt_05_claude.md           # ← Prompt per Claude (review)
│
├── /docs/                            # ← Documentazione di supporto
│   ├── site-structure-template.md    # ← Template struttura sito
│   ├── content-checklist.md          # ← Checklist qualità contenuti
│   ├── seo-technical-spec.md         # ← Spec tecniche SEO
│   └── attachments/                  # ← Cartella per file da allegare ai prompt
│       ├── CURRENT_WEBSITE_AUDIT.md  # ← Analisi sito attuale
│       ├── AVIS_DATA.json            # ← Dati AVIS (da compilare)
│       └── PARTNER_LIST.xlsx         # ← Elenco convenzioni (da allegare)
│
├── /outputs/                         # ← Cartella dove salvi i risultati da agenti
│   ├── phase1_query_data.csv         # ← Output Perplexity
│   ├── phase1_theme_ranking.json     # ← Output DeepSeek
│   ├── phase1_institutional_matrix.xlsx  # ← Output Gemini
│   ├── phase2_site_structure.md      # ← Output Claude
│   ├── phase2_content_pages/         # ← 20 pagine da ChatGPT
│   │   ├── 01_home.html
│   │   ├── 02_requisiti.html
│   │   ├── 03_procedura.html
│   │   └── ... (altre 17)
│   └── phase3_final_deliverable.md   # ← Output finale: sito pronto per dev
│
├── /archive/                         # ← Storico di versioni precedenti
│   └── (vuoto per ora)
│
└── .gitignore                        # ← File Git (ignora privati)
```

---

## **COME USARE QUESTO REPO**

### **Regola 1: File Log è il tuo diario**

Ogni volta che ottieni un output da un agente:
1. Salva il file in `/outputs/`
2. Aggiorna `FILE_LOG.md` con: data, agente, deliverable, note
3. Commit su Git: `git commit -m "Day 2: Perplexity query research completed"`

```markdown
# Esempio entry in FILE_LOG.md
## Day 2 - 24 Marzo 2026
**Agente:** Perplexity  
**Task:** Query research + volumi  
**Status:** ✅ Completato  
**Output file:** /outputs/phase1_query_data.csv  
**Note:** 40 query raccolte, valori verificati su Google Trends  
**Next:** Inviare dati a DeepSeek  
```

### **Regola 2: Seguire l'ordine in PHASE_GUIDE.md**

Non saltare fasi. Se sembra inefficiente, è perché:
- Ogni fase dipende dal dato della precedente
- Saltare genera errori che costano 2x tempo dopo

### **Regola 3: Allegare documento di contesto**

Quando chiedi qualcosa a un agente:
1. Leggi quali doc servono nel prompt file
2. Preparali in `/docs/attachments/`
3. Incolla il contenuto nella richiesta all'agente (o allega file se agente lo supporta)

Esempio:
```
Prompt Perplexity include:
  ❌ "Ricerca le query sulla donazione"
  ✅ "Ricerca le query sulla donazione in Italia per il territorio di Frosinone
      Contesto: AVIS Frosinone è associazione no-profit con 40 donatori attuali
      Allegato: /docs/attachments/AVIS_DATA.json"
```

### **Regola 4: Validare sempre prima di procedere**

Se agente ti dà output sospetto:
- Chiedi spiegazione
- Confronta con fonte esterna (Google Trends, Ahrefs pubblico, etc)
- Se non convince, risotti il prompt con dettagli nuovi

### **Regola 5: Mantieni Git pulito**

```bash
# Ogni sera:
git add .
git commit -m "Day X: [Phase] [Deliverable] [Status]"
git push

# Esempio:
git commit -m "Day 3: Phase1 - Query data collected, validated with Google Trends"
```

---

## **FILE DOCUMENTO CHE DEVI PREPARARE SUBITO**

### **1. `/docs/attachments/AVIS_DATA.json`**

Compila con dati reali su AVIS Frosinone:

```json
{
  "organization": {
    "name": "AVIS Comunale di Frosinone",
    "founded": 2019,
    "address": "Via Mazzini 70, 03100 Frosinone",
    "phone": "+39 377 4901081",
    "email": "info@avisfrosinone.it",
    "current_donors": 40,
    "monthly_donations": 10,
    "yearly_donations": 120
  },
  "partnership": {
    "hospital": "Ospedale Fabrizio Spaziani",
    "blood_center": "Centro Trasfusionale - Frosinone",
    "partner_status": "One of several voluntary associations",
    "target_partner_status": "Official primary partner"
  },
  "territory": {
    "primary_region": "Frosinone, Lazio, Italy",
    "secondary_locations": ["Cassino", "Sora"],
    "target_population": "~75,000 (Frosinone city)"
  },
  "volunteers": {
    "staff_count": 8,
    "staff_active": true
  }
}
```

### **2. `/docs/attachments/PARTNER_LIST.xlsx` o `.md`**

Lista completa convenzioni attuali:

```markdown
| Partner | Tipo | Sconto | Attivo? | Contatto | Note |
|---------|------|--------|--------|----------|------|
| Seeweb | Servizi di Cloud Computing | 0% | SI | Fornitore dello spazio WEB/Cloud |
| Duferco | Vendita Energia elettrica e Gas | 0% ! SI ! partner associato |
| ACI Frosinone ! Servizi Automobilistici | da ridefinire | SI | Partner da contattare |
| Atletica Frosinone | Sport | da ridefinire | SI | Partner da contattare |
| Banca Popolare del Cassinate | Servizi bancari | da ridefinire | SI | Partner da contattare |
| Beatyyful Medical SpA | Servizi sanitari | da ridefinire | SI | Partner da contattare |
| Campioni gomme | Fornitura Pneumatici | da ridefinire | SI | Partner da contattare |
| Croce Rossa Italiana | Servizi sanitari ed ambulanze | da ridefinire | SI | Partner da contattare | Farmacia Mastrangeli | Farmacie | da ridefinire | SI | Partner da contattare |
| Finelli srl | Mobili per ufficio | da ridefinire | SI | Partner da contattare |
| Folgore | Servizio protezione anticendio | da ridefinire | SI | Partner da contattare |
| Fotomania Fotografia | Studio fotografico | da ridefinire | SI | Partner da contattare |
| Geom. Carlo Pavia | Studio geometra | da ridefinire | SI | Partner da contattare |
| Geslan | Servizi sanitari | da ridefinire | SI | Partner da contattare |
| L'auto accessorio | Servizi per auto | da ridefinire | SI | Partner da contattare |
| Localraise | Agenzia marketing | da ridefinire | SI | Partner da contattare |
| Logyc | -- | da ridefinire | SI | Partner da contattare |
| Maceroni | Studio dentistico | da ridefinire | SI | Partner da contattare |
| Musical Goggi | Vendita strumenti musicali | da ridefinire | SI | Partner da contattare |
| OMEC | servizi di noleggio professionale alle imprese| da ridefinire | SI | Partner da contattare | Ortopedia italia | Sanitaria | da ridefinire | SI | Partner da contattare |
| Otovision ! Ottico | da ridefinire | SI | Partner da contattare |
| Peronti | Officina meccanica | da ridefinire | SI | Partner da contattare |
| Real Caffé | Vendita caffé | da ridefinire | SI | Partner da contattare |
| Seti | Impianti elettrici industriali e civili| da ridefinire | SI | Partner da contattare |
| Veronese |  Sicurezza sul lavoro | da ridefinire | SI | Partner da contattare |
| ... | ... | ... | ... | ... | ... |
```

### **3. `/docs/attachments/CURRENT_WEBSITE_AUDIT.md`**

Analisi veloce del sito attuale (riempi tu, basato su quello che hai visto):

```markdown
# Website Audit: avisfrosinone.it

## Problemi trovati:
- Menu confuso: "La Donazione" e "Comunicazione" separati
- Blog sepolto in "Comunicazione > Info AVIS"
- Convenzioni nascoste a fine pagina
- No CTA chiaro per "diventa donatore"
- Testi lunghi e poco scannerizzabili
- Nessun testimonial visibile
- No video

## Punti di forza:
- Contenuto tecnico completo
- Info preliminari ben dettagliate
- FAQ su requisiti
- Mappa centri trasfusionali

## Opportunità:
- Foto reali già disponibili (3 foto "un giorno col dono")
- Database di donatori attuali per testimonial
- Dati AVIS verificabili
```

---

## **COME COPIARE I PROMPT AGLI AGENTI**

### **Per Perplexity (perplexity.ai)**
1. Apri https://perplexity.ai
2. Copia contenuto completo da `prompt_01_perplexity.md`
3. Incolla in chat
4. Se prompt dice "Allegare [file]", copia il contenuto di quel file nel messaggio
5. Premi invio, aspetta risposta
6. Copia risposta in `/outputs/phase1_query_data.csv` (o .json se diverso)
7. Aggiorna FILE_LOG.md

### **Per DeepSeek (deepseek.com)**
1. Apri https://deepseek.com (o app)
2. Copia contenuto da `prompt_02_deepseek.md`
3. Allega il CSV da Perplexity (incolla contenuto nel messaggio)
4. Aspetta risposta
5. Salva output in `/outputs/phase1_theme_ranking.json`

### **Per Gemini (gemini.google.com)**
1. Apri https://gemini.google.com
2. Copia contenuto da `prompt_03_gemini.md`
3. Includi il ranking da DeepSeek
4. Aspetta risposta
5. Salva output in `/outputs/phase1_institutional_matrix.xlsx` (copia in formato markdown)

### **Per ChatGPT (chatgpt.com)**
1. Apri https://chatgpt.com
2. Copia contenuto da `prompt_04_chatgpt.md` 
3. Includi la struttura sito da Claude
4. PER OGNI PAGINA, ripeti il prompt con i dati specifici della pagina
5. Salva ogni pagina in `/outputs/phase2_content_pages/NN_[nome_pagina].html`

### **Per Claude (questo, claude.ai)**
1. Apri https://claude.ai
2. Copia contenuto da `prompt_05_claude.md`
3. Allega dati da Perplexity, DeepSeek, Gemini
4. Aspetta risposta
5. Salva in `/outputs/phase2_site_structure.md`

---

## **METRICHE DI SUCCESSO PER OGNI FASE**

### Phase 1: Data Collection (Week 1-2)
- ✅ Perplexity: 40+ query raccolte con volumi verificati
- ✅ DeepSeek: 5-7 temi identificati con ranking numerico
- ✅ Gemini: Fonte ufficiale per ogni tema
- ✅ Claude: Struttura sito completa con wireframe logico

**Quality Gate:** Tutti e 4 gli output devono essere coerenti (non contraddizioni)

### Phase 2: Content Generation (Week 2-3)
- ✅ ChatGPT: 20 pagine scritte, SEO-ready, strutturate
- ✅ Claude: Review completata, feedback incorporati
- ✅ Tutti i link interni coerenti
- ✅ Zero broken links

**Quality Gate:** Almeno 15/20 pagine devono passare review al primo giro

### Phase 3: Technical Setup (Week 3-4)
- ✅ Sito implementato
- ✅ Schema.org validato
- ✅ Responsive mobile 100%
- ✅ Form funzionante
- ✅ Google Search Console setup

**Quality Gate:** Lighthouse score ≥80 mobile

---

## **COSA FARE SE QUALCOSA VA STORTO**

| Problema | Soluzione |
|----------|-----------|
| Agente dà risposta generica | Riscrivi prompt con più context. Allega documenti specifici. |
| Output ha errori | Chiedi al medesimo agente di revisionare. Fornisci fonte autorità. |
| Timeline slittarà | Update PHASE_GUIDE.md con nuove date. Comunica al team. |
| File troppo grande | Spezzalo in 2. Allega pezzi diversi a prompt diversi. |
| Non sai se proseguire | Contatta Mark. Non andare avanti se in dubbio. |

---

## **CHECKLIST GIORNALIERA**

```
Ogni mattina:
☐ Leggi FILE_LOG.md (ricordati dove sei arrivato)
☐ Apri il prompt file del giorno (vedi PHASE_GUIDE.md)
☐ Allega documenti necessari
☐ Invia a agente AI
☐ Aspetta risposta (da 5 minuti a 30 minuti)
☐ Copia output in /outputs/
☐ Aggiorna FILE_LOG.md
☐ Commit su Git
☐ Leggi le prossime istruzioni in PHASE_GUIDE.md

Ogni sera:
☐ git push (sincronizza repo)
☐ Valida che tutto sia committato
```

---

## **CONTATTI RAPIDI**

| Ruolo | Nome | Contatto | Ruolo |
|---|---|---|---|
| **Director** | Mark | Questo repo | Decisioni, escalation |
| **Repository** | GitHub | (URL da aggiungere) | Sincronizzazione |
| **Agenti** | Perplexity, DeepSeek, Gemini, ChatGPT, Claude | (URL già note) | Esecuzione task |

---

## **VERSIONE E CHANGELOG**

**Versione corrente:** 1.0  
**Ultimo aggiornamento:** 21 Marzo 2026

### Changelog:
- v1.0: Struttura iniziale, prompt pronti, guida completa

---

## **NOTE FINALI**

### ⚠️ Importante:
- **Non modificare i prompt di base** senza approvazione Mark
- **Sempre validare** output con fonte indipendente (Google Trends, Ahrefs pubblico, etc)
- **Git commit quotidianamente** — questo repo è la memoria del progetto

### 💡 Suggerimenti:
- Mantieni sezioni `/prompts/` e `/outputs/` sempre pulite
- Se crei nuovi file di supporto, mettili in `/docs/`
- Se scopri nuovi tool utili, documentalo in README update

### 🎯 Ricorda:
- L'obiettivo non è "fare tanti prompt", è **trasformare AVIS Frosinone in autorità locale**
- Ogni phase costruisce sulla precedente
- Qualità > velocità

---

**Pronto a iniziare?**  
→ Leggi PHASE_GUIDE.md domani mattina  
→ Day 1: Prepara /docs/attachments/ (AVIS_DATA.json, ecc)  
→ Day 2: Invia primo prompt a Perplexity

**Buona fortuna. 🚀**
