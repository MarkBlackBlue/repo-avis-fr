# PROMPT 04: CHATGPT - CONTENT GENERATION

**Destinatario:** ChatGPT (chatgpt.com)  
**Fase:** 2 (Content Generation)  
**Giorno:** 8-14 (ripetere 20 volte, 1 per pagina)  
**Input:** phase2_site_structure.md + dati pagina specifica  
**Output file:** `/outputs/phase2_content_pages/NN_[tema].html` (ripeti per ogni pagina)

---

## **WHAT TO ATTACH**

Prima di inviare questo prompt a ChatGPT:

1. **phase2_site_structure.md** — Struttura sito (da `/outputs/`, creato da Claude)
2. **Dati pagina specifica** — Vedi sezione PERSONALIZATION qui sotto

---

## **HOW TO USE THIS PROMPT**

**Questo prompt è un TEMPLATE.** Dovrai:

1. Copiare il prompt INTERO qui sotto
2. Personalizzare i campi [BRACKETED] per ogni pagina
3. Allegare il contenuto di phase2_site_structure.md
4. Inviare a ChatGPT
5. Ripetere 20 volte (una per ogni pagina)

**Ordine di esecuzione (vedi PHASE_GUIDE.md):**
- Batch 1 (5 pagine): Home, Requisiti, Procedura, Dove Donare, Perché Donare
- Batch 2 (5 pagine): Benefici, Tipi di Donazione, Diventa Donatore, Convenzioni, Contatti
- Batch 3 (10 pagine): Approfondimenti, FAQ, Blog, etc

---

## **PERSONALIZATION SECTION**

**Per ogni pagina, substituzione questi campi:**

```
[PAGINA_NUMERO] = 01, 02, 03... 20
[PAGINA_TITOLO] = Es: "Home", "Requisiti di Idoneità", etc
[PAGINA_DESCRIZIONE] = Es: "Pagina di benvenuto con CTA dual"
[QUERY_TARGET] = Es: "donare sangue Frosinone" (da CSV Perplexity)
[KEYWORD_PRINCIPALE] = Es: "Requisiti donazione sangue"
[KEYWORD_SECONDARIE] = Es: "Posso donare se...", "Chi può donare", etc
[VOLUME_RICERCHE] = Es: "8.500 ricerche/mese" (da CSV Perplexity)
[FONTE_UFFICIALE] = Es: "Ministero della Salute - D.M. 2 Nov 2015" (da matrice Gemini)
[TEMA_PRINCIPALE] = Es: "Requisiti di idoneità" (da ranking DeepSeek)
[TONO] = Es: "Rassicurante, diretto" / "Emozionale, motivazionale" / etc
[SEZIONE_HOME] = Sì / No (è nella home page?)
[CTA_PRIMARIO] = Es: "Prenota una donazione", "Scopri i benefici", etc
[CTA_SECONDARIO] = Es: "Leggi le FAQ", "Contattaci", etc
```

---

## **COPY & PASTE THIS ENTIRE PROMPT (then personalize)**

```
TASK: Content Generation - [PAGINA_TITOLO]

Contesto:
Sto ristrutturando il sito di AVIS Frosinone (associazione no-profit donazione sangue).
Il sito deve rispondere ai bisogni reali dei ricercatori (volumi di ricerca verificati)
e convertire visitatori in donatori.

PAGINA DA SCRIVERE:
- Numero: [PAGINA_NUMERO]/20
- Titolo: [PAGINA_TITOLO]
- Descrizione: [PAGINA_DESCRIZIONE]

RICERCA CHE GUIDA QUESTA PAGINA:
- Query target: "[QUERY_TARGET]"
- Keyword principale: [KEYWORD_PRINCIPALE]
- Keywords secondarie: [KEYWORD_SECONDARIE]
- Volume mensile ricerche: [VOLUME_RICERCHE]
- Autorità della fonte: [FONTE_UFFICIALE]

TEMA PRINCIPALE (da strategia sito):
- Tema: [TEMA_PRINCIPALE]
- Rank priorità: [1-7]

REQUISITI CONTENUTO:

1. TONO & VOCE
   - Tono richiesto: [TONO]
   - Pubblico: [Es: Chi non sa ancora / Chi è pronto a fare]
   - Punto di vista: [Es: Professionista / Peer / Autorità]
   
   IMPORTANTE: Non suonare "AI-generated". Scrivere come persona reale.

2. STRUTTURA HTML
   - Pagina deve usare HTML semantico
   - H1 unico (contiene keyword principale)
   - H2 per sottosezioni (contengono keywords secondarie)
   - Paragrafi sintetici (max 3-4 frasi)
   - Liste bullet dove appropriato
   - Nessun Lorem Ipsum

3. LUNGHEZZA & SCANSIONABILITÀ
   - Home page: 400-600 parole
   - Pagine informatiche: 800-1200 parole
   - Pagine transazionali: 300-500 parole
   
   - Usa spazi bianchi
   - Paragrafi brevi (2-3 frasi)
   - Bold su punti chiave
   - CTA ogni 3-4 sezioni

4. SEO BASICS
   - H1: Deve contenere [KEYWORD_PRINCIPALE]
   - Introduzione (prime 50 parole): Risponde direttamente alla query target
   - Keyword principale: Almeno 3x nel contenuto (naturale)
   - Keywords secondarie: Almeno 1x per keyword
   - Links interni: [vedi lista nel file structure]
   - Meta description: 150-160 caratteri (suggerisci alla fine)

5. CALL-TO-ACTION
   - CTA Primario: [CTA_PRIMARIO]
   - CTA Secondario: [CTA_SECONDARIO]
   - Placement: Fine pagina + almeno 1x nel mezzo
   - Formato: Button HTML con classe "cta-primary" o "cta-secondary"

6. FONTI & CREDIBILITÀ
   - Cita fonte ufficiale: [FONTE_UFFICIALE]
   - Formato citazione: "[Contenuto]" — Fonte: Ministero della Salute
   - Disclaimer se rilevante: "Consultare sempre il medico presso il centro trasfusionale"

7. IMMAGINI/MEDIA
   - Descrizione alt-text da usare (se foto disponibile)
   - Non includere tag <img>, ma put placeholder: <!-- [Foto descrizione] -->

8. LINK INTERNI
   - Collegare a altre pagine logicamente correlate
   - Anchor text descrittivo (es: "scopri i benefici" non "clicca qui")
   - Vedi structure file per mappa link raccomandata

---

RICHIESTA FINALE:

Scrivi il contenuto HTML COMPLETO per questa pagina.

Formato: HTML puro (non Markdown)

Struttura:
```html
<div class="page-content">
  <h1>[Keyword principale]</h1>
  
  <p>[Introduzione che risponde direttamente alla query target]</p>
  
  [Sezioni con H2, paragrafi, liste]
  
  <div class="cta-primary">
    <a href="[link]">[CTA_PRIMARIO]</a>
  </div>
  
  [Più sezioni]
  
  <div class="cta-secondary">
    <a href="[link]">[CTA_SECONDARIO]</a>
  </div>
  
  [Footer info: fonte ufficiale, disclaimer]
</div>
```

CHECKLIST FINALE (verifica prima di mandare HTML):

- [ ] H1 contiene [KEYWORD_PRINCIPALE]
- [ ] Prime 50 parole rispondono a query target
- [ ] Nessun Lorem Ipsum
- [ ] Almeno 2 CTA visibili
- [ ] Links interni coerenti con structure
- [ ] Disclaimer incluso se rilevante
- [ ] Tono coerente (non troppo formale, non troppo casual)
- [ ] Nessun errore grammaticale
- [ ] HTML semantico (no div nested assurdi)

---

CONTESTO AGGIUNTIVO:

AVIS Frosinone attualmente è "una delle associazioni" presso il centro trasfusionale.
L'obiettivo è farla diventare il partner primario.
Questo sito deve posizionarla come AUTORITÀ LOCALE sulla donazione.
Ogni pagina deve far sentire al visitatore che AVIS sa di cosa parla.

TARGET VISITATORE:
- [Es: Chi ha paura di donare] / [Es: Chi cerca dove donare]
- Primo contatto con donazione potrebbe essere contrastato
- La tua pagina deve eliminare barriere, non aggiungerne

---

TONALITÀ SPECIFICA PER [PAGINA_TITOLO]:

[Inserisci guida su tono specifico della pagina]
Esempio per Home: "Invitante, non troppo allarmistico, con urgenza sottile"
Esempio per FAQ: "Rassicurante, pratico, senza jargon medico"
Esempio per Requisiti: "Diretto, no sorprese, basato su fatti"

---

NOTA FINALE:
Non è una pagina generica. È una pagina che converte.
Chi la legge deve sentirsi: "Ok, sono in mani giuste, AVIS sa di cosa parla."
```

---

## **AFTER CHATGPT RESPONSE**

1. **Copia TUTTA la risposta HTML**

2. **Salva in file:** `/outputs/phase2_content_pages/NN_[TEMA].html`
   - Formato filename: `01_home.html`, `02_requisiti.html`, etc.
   - NN = numero pagina (01-20)
   - [TEMA] = tema breve (max 2-3 parole, lowercase, underscore)

   Esempio completi:
   - `01_home.html`
   - `02_requisiti_idoneita.html`
   - `03_procedura.html`
   - `04_dove_donare.html`
   - `05_perche_donare.html`
   - etc.

3. **Valida HTML:**
   - Apri il file in browser
   - Verifica rendering (nessun errore)
   - Test link (if localhost setup)
   - Altrimenti, usa W3C HTML validator online

4. **Aggiorna FILE_LOG.md:**
   ```markdown
   ## Day 8 (es) - [Data]
   **Agente:** ChatGPT
   **Task:** Content generation - Batch 1
   **Pagine generate:**
   ✅ 01_home.html - 520 parole - OK
   ✅ 02_requisiti_idoneita.html - 950 parole - OK
   ✅ 03_procedura.html - 890 parole - OK
   ✅ 04_dove_donare.html - 620 parole - OK
   ✅ 05_perche_donare.html - 780 parole - OK
   **Status:** 5/20 completate
   **Quality check:** [Nessun problema / Minor notes]
   **Next:** Day 9 - Batch 2
   ```

5. **Commit su Git:**
   ```bash
   git add outputs/phase2_content_pages/*.html FILE_LOG.md
   git commit -m "Day8: ChatGPT content batch 1 - 5 pages generated (home, requisiti, procedura, dove, perche)"
   git push
   ```

---

## **EXPECTED OUTPUT FORMAT**

ChatGPT dovrebbe darti HTML strutturato tipo:

```html
<div class="page-content">
  <h1>Requisiti per Donare Sangue a Frosinone</h1>
  
  <p>Vuoi donare il tuo sangue ma non sai se puoi? Scopri i requisiti esatti che AVIS Frosinone verifica prima di ogni donazione.</p>
  
  <h2>Requisiti Fisici Essenziali</h2>
  <ul>
    <li><strong>Età:</strong> Tra 18 e 65 anni</li>
    <li><strong>Peso:</strong> Almeno 50 kg</li>
    <li><strong>Emoglobina:</strong> Verificata dal medico</li>
  </ul>
  
  [... più sezioni ...]
  
  <div class="cta-primary">
    <a href="/prenota.html">Prenota una Donazione</a>
  </div>
  
  <p><em>Fonte: Ministero della Salute - D.M. 2 Novembre 2015</em></p>
</div>
```

---

## **TIPS FOR QUALITY**

- **Non usare:** "Lorem ipsum", template generico, buzzword vuote
- **Usa:** Dati reali (volumi ricerca), cite fonti, risponde query diretta
- **Tono:** Come se parlassi a amico curioso (non professore, non venditore)
- **Length:** Non troppo lungo (scansionare in 3 minuti)

---

## **TROUBLESHOOTING**

**ChatGPT dà risposta troppo generica:**
- Chiedi: "Personalizza per AVIS Frosinone, aggiungi dettagli locali"
- Riscrivi prompt con più dettagli AVIS-specific

**HTML ha errori:**
- Chiedi di riparare: "Valida il tuo HTML con W3C validator"

**Content troppo lungo:**
- Chiedi di condensare: "Mantieni massimo 1000 parole, rimuovi ripetizioni"

**Tono è sbagliato:**
- Descrivi il tono: "Meno formale, più amichevole"
- Dai esempio: "Come se parlassi a un amico che ha paura di donare"

---

## **MASTER FILE: PAGINE DA SCRIVERE (20 total)**

Ordine consigliato:

**Core Pages (always):**
1. Home
2. Requisiti di idoneità
3. Procedura di donazione
4. Dove e come donare
5. Perché donare

**Second Wave:**
6. Benefici della donazione
7. Tipi di donazione
8. Diventa donatore
9. Convenzioni
10. Contatti

**Tertiary/Approfondimenti:**
11-20. FAQ, Blog posts, Testimonianze, Donna e donazione, etc
      (Vedi phase2_site_structure.md per lista completa)

---

**Ready? Start with Batch 1. Copy prompt, personalize, send to ChatGPT.**

**REPEAT THIS PROCESS 20 TIMES (one for each page).**
