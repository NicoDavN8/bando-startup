# Business Plan Sintetico — EMSy S.r.l.
**Bando FESR DGR 575/2025 — Sostegno alle startup innovative — Valle d'Aosta**
*Aggiornato: giugno 2026*

**Titolo progetto:** Sistema AI multi-agente per il supporto informativo all'emergenza preospedaliera in ambiente montano

**Finalità:** Sviluppare e validare sul campo, con operatori del soccorso valdostani, un sistema AI multi-agente a moduli specializzati integrati per il supporto informativo e formativo alla medicina d'urgenza preospedaliera in ambiente montano, includendo la prototipazione esplorativa di interfacce AR per la visualizzazione contestuale di informazioni cliniche in scenario.

---

## 1. L'impresa

**EMSy S.r.l.** è una startup innovativa con sede operativa in Valle d'Aosta, iscritta alla sezione speciale del registro delle imprese dedicata alle startup innovative ai sensi dell'art. 25 del D.L. 179/2012 (conv. L. 221/2012). L'azienda sviluppa strumenti software basati su intelligenza artificiale per la medicina d'emergenza preospedaliera — un settore ad alta criticità in cui ogni decisione clinica può fare la differenza tra la vita e la morte.

La piattaforma EMSy è già in produzione e conta oggi **oltre 800 utenti registrati in più di 50 paesi**, con **più di 2.000 consultazioni giornaliere** effettuate da medici di emergenza, infermieri del 118 e soccorritori professionali.

---

## 2. Il team

| Nome | Ruolo | Competenze |
|------|-------|------------|
| **Simon Grosjean** | Co-founder, CTO, Presidente CDA | Medico del 118 e ideatore del progetto. Progettista del prodotto e sviluppatore fullstack (AI/LLM, Next.js, Python, LangChain). Firma la domanda FESR. |
| **Damiano Presciani** | Co-founder, Medical Director | Medico del 118 con esperienza operativa sul campo. Ideatore di EMSy Events. Responsabile della validazione clinica di tutti i contenuti e dei modelli AI. |
| **Nicolò Balzani** | Co-founder, CPO | Responsabile marketing, comunicazione e gestione operativa del progetto. Referente societario per il bando FESR. |

Il team unisce competenze rare: Simon combina la pratica clinica diretta sul campo come medico 118 con le capacità tecniche per tradurla in architetture AI funzionanti. Damiano garantisce la validazione medica dei contenuti e ha ideato la verticalizzazione sugli eventi sportivi. Nicolò coordina la strategia di mercato e la gestione operativa del progetto. La presenza di due medici d'emergenza nel team fondatore elimina la dipendenza da consulenze cliniche esterne e garantisce aderenza costante ai protocolli ERC/ILCOR aggiornati.

---

## 3. Il problema e la soluzione

### Il problema
L'operatore sanitario preospedaliero (medico 118, infermiere, soccorritore) lavora in condizioni estreme: ambiente remoto, stress elevato, tempi di decisione ridotti, spesso senza connettività stabile. Gli strumenti digitali disponibili non sono progettati per questo contesto e la letteratura scientifica più recente è inaccessibile sul campo in tempo reale.

Sul fronte della ricerca clinica, esiste un **gap specifico**: non sono disponibili modelli predittivi validati sul contesto preospedaliero medicalizzato europeo per scenari ad alta complessità come l'arresto cardiaco extraospedaliero (OHCA). I modelli predittivi esistenti non sono sviluppati né calibrati per il sistema EMS italiano.

### La soluzione
EMSy è una **piattaforma SaaS acquistabile online**, progettata specificamente per i professionisti dell'emergenza preospedaliera. Offre un ambiente integrato di supporto alla formazione e all'aggiornamento continuo, accessibile da Web App in qualsiasi momento — anche sul campo.

Il cuore della piattaforma è una **RAG proprietaria** (sistema di recupero e generazione aumentata) alimentata da letteratura scientifica medica aggiornata, linee guida ERC/ILCOR e protocolli operativi. La knowledge base si arricchisce continuamente con nuovi dati scientifici validati dal team medico interno.

Funzionalità principali:
- **Chat AI clinica**: il professionista pone domande in linguaggio naturale e riceve risposte contestualizzate con riferimenti bibliografici precisi
- **AI Coach**: percorsi formativi con quiz adattativi per il mantenimento delle competenze
- **Calcolatori clinici**: score e algoritmi validati (OHCA, trauma, cardiovascolare) utilizzabili direttamente sul campo
- **EMSy Events**: modulo per la gestione sanitaria in tempo reale di eventi sportivi in ambiente alpino
- **AI Data Expert** (sviluppo in corso): sistema multi-agente per analisi predittiva su dati clinici complessi

---

## 4. Prodotti e stato di sviluppo

### Prodotto A — EMSy Platform (in produzione)
Piattaforma Web App (PWA — Progressive Web App, accessibile da browser mobile senza installazione) con:
- AI Assistant (RAG — Retrieval-Augmented Generation, sistema che recupera documenti scientifici prima di rispondere — su Pinecone, multi-modello via OpenRouter)
- AI Coach con quiz clinici adattativi
- Calcolatori clinici e score validati (OHCA — Out-of-Hospital Cardiac Arrest, arresto cardiaco extraospedaliero; trauma, cardiovascolare)
- EMSy Arena — simulazioni gamificate per formazione medica

**Stato:** in produzione. 800+ utenti, 50+ paesi, 2.000+ consultazioni/giorno.

### Prodotto B — EMSy AI Data Expert (cuore del Piano di sviluppo FESR)
Sistema AI (Intelligenza Artificiale) multi-agente a moduli specializzati orchestrati da LangGraph (framework che coordina più agenti AI in sequenza logica):
- Modulo letteratura (attivo): LLM (Large Language Model — modello AI per comprensione e generazione di testo) + RAG su letteratura medica
- Modulo predittivo (sviluppo Fase 1): ML (Machine Learning — apprendimento automatico) classico su dati tabulari OHCA (XGBoost, SHAP — SHapley Additive exPlanations, sistema di spiegabilità delle predizioni)
- Modulo di sintesi (integrazione Fase 2): LLM Reasoning per sintesi clinica contestualizzata

**Stato:** Modulo letteratura attivo. Moduli predittivo e sintesi da sviluppare nel Piano di sviluppo FESR.

### Prodotto C — EMSy Events (attivazione operativa nel Piano di sviluppo)
Web App + centrale operativa web per gestione sanitaria in tempo reale durante eventi sportivi in montagna.

**Stato:** in fase di preparazione per attivazione operativa con partner contrattuale VDA Trailers su GTC® (luglio 2027) e TORX® with Kailas (settembre 2027).

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
- **VDA Trailers** — partner per attivazione operativa di EMSy Events su Gran Trail Courmayeur GTC® e TORX® with Kailas 2027, entrambi eventi valdostani di rilevanza internazionale con Piano Sanitario approvato dall'AUSL Valle d'Aosta
### Esperti esterni pianificati (Fase 2)
- **Esperto clinico esterno (validazione indipendente)** — Anestesista-rianimatore con esperienza in medicina d'emergenza ed elisoccorso (HEMS). Previsto per test della piattaforma in contesti reali durante eventi e manifestazioni, con possibilità di produrre pubblicazioni scientifiche. Incarico da formalizzare in Fase 2.

### Collaborazioni operative in Valle d'Aosta
- **Valpelline** — collaborazione con i volontari del soccorso locale, documentata da rapporto economico formale. Testimonianza diretta del radicamento operativo sul territorio valdostano.

### Sovvenzioni e programmi startup internazionali (già ricevute)
- **Amazon AWS Activate** — crediti cloud per sviluppo AI (SageMaker, Lambda, S3)
- **NVIDIA Startup Program** — crediti GPU per inferenza e training modelli ML/LLM

Il riconoscimento da parte di Amazon e NVIDIA attraverso i rispettivi programmi startup valida la qualità tecnologica del progetto a livello internazionale.

---

## 7. Tecnologia e innovazione

**Stack tecnologico:**
Next.js/TypeScript, PostgreSQL/Prisma, Pinecone (vector DB), LangChain/LangGraph, OpenRouter (multi-LLM), Python FastAPI, AWS, Google Cloud.

**Compliance e sicurezza:**
La piattaforma gestisce dati clinici sensibili con un sistema di anonimizzazione PII a 3 layer indipendenti già in produzione (regex medico-italiano + modello NER clinico OpenMed 66M parametri + system prompt GDPR), con tutta l'infrastruttura localizzata in regioni EU (Google Cloud `europe-west1`, Vercel EU). Nessun dato grezzo lascia l'Unione Europea.

**Posizionamento normativo:**
EMSy è uno strumento informativo ed educativo per professionisti sanitari. Non è classificato come Software as a Medical Device (SaMD) e non richiede marcatura CE ai sensi del Reg. UE 2017/745. Classificazione EU AI Act: rischio limitato (Art. 50) — obbligo di trasparenza già rispettato.

---

## 8. Sostenibilità finanziaria

EMSy adotta un modello freemium con livelli di accesso differenziati. L'infrastruttura è interamente cloud-based con costi variabili proporzionali alla crescita degli utenti. I costi fissi mensili attuali (infrastruttura + LLM) sono contenuti e coperti dall'operatività corrente.

Il progetto FESR consente di accelerare lo sviluppo dell'AI Data Expert — il modulo a maggior valore aggiunto — senza compromettere la sostenibilità operativa della piattaforma esistente. Il contributo FESR atteso di **€56.000** (70% su €80.000) copre il 70% dei costi totali del Piano di sviluppo, con un cofinanziamento EMSy di €24.000 (30%) già pianificato.

La sostenibilità finanziaria a lungo termine è supportata dalla crescita organica della base utenti e dall'espansione del modello SaaS a livello europeo, con il contributo FESR che accelera lo sviluppo dei moduli a maggior valore aggiunto senza impattare l'operatività corrente.

---

## 9. Impatto occupazionale e ricadute sul territorio

Il Piano di sviluppo prevede:
- **Inserimento di 1 nuovo collaboratore** (Co.Co.Co) per 18 mesi — profilo junior, primo accesso al mercato del lavoro nel settore AI/tecnologia in Valle d'Aosta
- **Valorizzazione delle competenze dei 3 soci fondatori** residenti e operativi sul territorio valdostano
- **Attivazione operativa della piattaforma** su eventi di rilevanza internazionale con ricaduta diretta sulla sicurezza sanitaria in Valle d'Aosta (GTC® e TORX®)
- **Prototipazione interfaccia AR** (display binoculare XREAL 1S, Micro-OLED) per progettazione dell'overlay clinico — base per future applicazioni nel soccorso alpino valdostano
- **Acquisizione server GPU dedicato con schede video** per inferenza LLM (Large Language Model) on-premise h24, riducendo la dipendenza da servizi cloud esterni

Il progetto si inserisce coerentemente nelle tre aree della Smart Specialization Strategy (S3) regionale 2021-2027:
- **Montagna intelligente** — AI applicata a contesti operativi alpini
- **Montagna di eccellenza** — innovazione nella sicurezza e medicina d'emergenza
- **Montagna sostenibile** — infrastruttura software-first, zero emissioni dirette

---

*Documento interno EMSy S.r.l. — Aggiornato giugno 2026 — Non diffondere*
