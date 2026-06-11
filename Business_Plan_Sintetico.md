# Business Plan Sintetico — EMSy S.r.l.
**Bando FESR DGR 575/2025 — Sostegno alle startup innovative — Valle d'Aosta**
*Aggiornato: giugno 2026*

---

## 1. L'impresa

**EMSy S.r.l.** è una startup innovativa con sede operativa in Valle d'Aosta, iscritta alla sezione speciale del registro delle imprese ai sensi della L.R. 14/2011. L'azienda sviluppa strumenti software basati su intelligenza artificiale per la medicina d'emergenza preospedaliera — un settore ad alta criticità in cui ogni decisione clinica può fare la differenza tra la vita e la morte.

La piattaforma EMSy è già in produzione e conta oggi **oltre 400 utenti registrati in più di 50 paesi**, con **più di 1.000 consultazioni giornaliere** effettuate da medici di emergenza, infermieri del 118 e soccorritori professionali.

---

## 2. Il team

| Nome | Ruolo | Competenze |
|------|-------|------------|
| **Simon Grosjean** | Co-founder, CTO | Sviluppatore fullstack senior, architettura AI/LLM, Next.js, Python, LangChain. Firma la domanda FESR. |
| **Damiano Presciani** | Co-founder, Medical Director | Medico d'emergenza con esperienza operativa sul campo. Responsabile della validazione clinica di tutti i contenuti e dei modelli AI. |
| **Nicolò Balzani** | Co-founder, CPO | Progettista di prodotto. Responsabile UX, design dell'interfaccia e strategia di prodotto. |

Il team combina competenze tecniche avanzate (AI, sviluppo software, architetture cloud) con expertise medica specialistica diretta — una combinazione rara e critica per sviluppare strumenti clinici affidabili. Il profilo medico interno elimina la dipendenza da consulenze esterne per la validazione clinica e garantisce aderenza ai protocolli ERC/ILCOR aggiornati.

---

## 3. Il problema e la soluzione

### Il problema
L'operatore sanitario preospedaliero (medico 118, infermiere, soccorritore) lavora in condizioni estreme: ambiente remoto, stress elevato, tempi di decisione ridotti, spesso senza connettività stabile. Gli strumenti digitali disponibili non sono progettati per questo contesto e la letteratura scientifica più recente è inaccessibile sul campo in tempo reale.

Sul fronte della ricerca clinica, esiste un **gap specifico e documentato**: nessun modello predittivo ML prehospitaliero è stato validato su un sistema EMS medicalizzato europeo per la predizione dell'esito neurologico dell'arresto cardiaco extraospedaliero (OHCA). I modelli esistenti sono stati sviluppati su dati giapponesi o su dati raccolti dopo l'arrivo in ospedale — inutilizzabili sul territorio italiano.

### La soluzione
EMSy offre una piattaforma AI informativa ed educativa progettata specificamente per il contesto preospedaliero:

- **Interfaccia ottimizzata per il campo**: funziona con i guanti, sotto la pioggia, con bassa connettività, senza formazione tecnica avanzata
- **AI Assistant basato su letteratura scientifica aggiornata**: risponde in linguaggio naturale a domande cliniche, citando linee guida ERC/ILCOR, protocolli e farmaci
- **Sistema predittivo AI Data Expert** (sviluppo in corso): modelli ML su dati clinici reali per supportare decisioni in scenari ad alta complessità come l'OHCA
- **EMSy Events**: gestione sanitaria in tempo reale di eventi sportivi in ambiente alpino

---

## 4. Prodotti e stato di sviluppo

### Prodotto A — EMSy Platform (in produzione)
Piattaforma web e app mobile (iOS/Android) con:
- AI Assistant (RAG su Pinecone, multi-modello via OpenRouter)
- AI Coach con quiz clinici adattativi
- Calcolatori clinici e score validati (OHCA, trauma, cardiovascolare)
- EMSy Arena — simulazioni gamificate per formazione medica

**Stato:** in produzione. 400+ utenti, 50+ paesi, 1.000+ consultazioni/giorno.

### Prodotto B — EMSy AI Data Expert (cuore del Piano di sviluppo FESR)
Sistema multi-intelligenza multi-agente a moduli specializzati orchestrati da LangGraph:
- Modulo letteratura (attivo): LLM + RAG su letteratura medica
- Modulo predittivo (sviluppo Fase 1): ML classico su dati tabulari OHCA (XGBoost, SHAP explainability)
- Modulo segnali (sviluppo Fase 2): Deep Learning su segnali ECG/EEG
- Modulo di sintesi (integrazione Fase 2): LLM Reasoning per sintesi clinica contestualizzata

**Stato:** Modulo letteratura attivo. Moduli predittivo, segnali e sintesi da sviluppare nel Piano di sviluppo FESR.

### Prodotto C — EMSy Events (attivazione operativa nel Piano di sviluppo)
App mobile + centrale operativa web per gestione sanitaria in tempo reale durante eventi sportivi in montagna.

**Stato:** in fase di attivazione operativa con partner contrattuale VDA Trailers su GTC® (luglio 2026) e TORX® (settembre 2026).

---

## 5. Mercato di riferimento

Il mercato target primario è il **sistema di emergenza medica preospedaliera europeo**, composto da:
- Sistemi 118/SAMU/REGA (medici, infermieri, operatori)
- Organizzazioni di volontariato del soccorso (Croce Rossa, ANPAS, Misericordie)
- Strutture di formazione continua per operatori del soccorso
- Organizzatori di eventi sportivi in ambienti estremi (trail running, sci alpinismo, arrampicata)

La piattaforma è già presente in **50+ paesi** a meno di 2 anni dal lancio, con trazione organica senza investimenti marketing strutturati — dimostrazione di un bisogno reale e di un prodotto che risponde efficacemente.

---

## 6. Partnership e radicamento territoriale

### Partner contrattuali (contratti firmati)
- **UTMB Italia** — partner per validazione clinica della piattaforma in contesti di medicina d'emergenza ad alta complessità (trail running in alta quota, condizioni estreme)
- **VDA Trailers** — partner per attivazione operativa di EMSy Events su Gran Trail Courmayeur GTC® e TORX® with Kailas 2026, entrambi eventi valdostani di rilevanza internazionale con Piano Sanitario approvato dall'AUSL Valle d'Aosta

### Collaborazioni operative in Valle d'Aosta
- **Valpelline** — collaborazione con i volontari del soccorso locale, documentata da rapporto economico formale. Testimonianza diretta del radicamento operativo sul territorio valdostano.

### Sovvenzioni e programmi startup internazionali (già ricevute)
- **Amazon AWS Activate** — crediti cloud per sviluppo AI (SageMaker, Lambda, S3)
- **NVIDIA Startup Program** — crediti GPU per training modelli Deep Learning

Il riconoscimento da parte di Amazon e NVIDIA attraverso i rispettivi programmi startup valida la qualità tecnologica del progetto a livello internazionale.

---

## 7. Tecnologia e innovazione

**Stack tecnologico:**
Next.js/TypeScript, PostgreSQL/Prisma, Pinecone (vector DB), LangChain/LangGraph, OpenRouter (multi-LLM), Python FastAPI, Capacitor (iOS/Android), AWS, Google Cloud.

**Compliance e sicurezza:**
La piattaforma gestisce dati clinici sensibili con un sistema di anonimizzazione PII a 3 layer indipendenti già in produzione (regex medico-italiano + modello NER clinico OpenMed 66M parametri + system prompt GDPR), con tutta l'infrastruttura localizzata in regioni EU (Google Cloud `europe-west1`, Vercel EU). Nessun dato grezzo lascia l'Unione Europea.

**Posizionamento normativo:**
EMSy è uno strumento informativo ed educativo per professionisti sanitari. Non è classificato come Software as a Medical Device (SaMD) e non richiede marcatura CE ai sensi del Reg. UE 2017/745. Classificazione EU AI Act: rischio limitato (Art. 50) — obbligo di trasparenza già rispettato.

---

## 8. Sostenibilità finanziaria

EMSy adotta un modello freemium con livelli di accesso differenziati. L'infrastruttura è interamente cloud-based con costi variabili proporzionali alla crescita degli utenti. I costi fissi mensili attuali (infrastruttura + LLM) sono contenuti e coperti dall'operatività corrente.

Il progetto FESR consente di accelerare lo sviluppo dell'AI Data Expert — il modulo a maggior valore aggiunto — senza compromettere la sostenibilità operativa della piattaforma esistente. Il contributo FESR atteso di **€52.800** (70% su €80.000) copre il 65% dei costi totali del Piano di sviluppo, con un cofinanziamento EMSy di €27.200 (30%) già pianificato.

La sostenibilità finanziaria a lungo termine è rafforzata dall'accordo di finanziamento ponte con **Banca Sella + Alpifidi** (€24.000 a 5 anni, garanzia MCC), cumulabile con il contributo FESR.

---

## 9. Impatto occupazionale e ricadute sul territorio

Il Piano di sviluppo prevede:
- **Inserimento di 1 nuovo collaboratore** (Co.Co.Co) per 18 mesi — profilo junior, primo accesso al mercato del lavoro nel settore AI/tecnologia in Valle d'Aosta
- **Valorizzazione delle competenze dei 3 soci fondatori** residenti e operativi sul territorio valdostano
- **Attivazione operativa della piattaforma** su eventi di rilevanza internazionale con ricaduta diretta sulla sicurezza sanitaria in Valle d'Aosta (GTC® e TORX®)
- **Prototipazione tecnologia AR** (RealWear Navigator 520) per applicazioni future nel soccorso alpino valdostano

Il progetto si inserisce coerentemente nelle tre aree della Smart Specialization Strategy (S3) regionale 2021-2027:
- **Montagna intelligente** — AI applicata a contesti operativi alpini
- **Montagna di eccellenza** — innovazione nella sicurezza e medicina d'emergenza
- **Montagna sostenibile** — infrastruttura software-first, zero emissioni dirette

---

*Documento interno EMSy S.r.l. — Aggiornato giugno 2026 — Non diffondere*
