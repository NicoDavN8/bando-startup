# Piano di Sviluppo — EMSy S.r.l.
**Bando FESR DGR 575/2025 — Sostegno alle startup innovative — Valle d'Aosta**
**Durata:** 18 mesi | **Budget totale:** €80.000 | **Contributo richiesto:** €56.000 (70%)
*Aggiornato: giugno 2026*

---

## 1. Sommario Esecutivo

**Titolo del progetto:** Sistema AI multi-agente per il supporto informativo all'emergenza preospedaliera in ambiente montano

**Finalità:** Sviluppare e validare sul campo, con operatori del soccorso valdostani, un sistema AI multi-agente a moduli specializzati integrati per il supporto informativo e formativo alla medicina d'urgenza preospedaliera in ambiente montano, includendo la prototipazione esplorativa di interfacce AR per la visualizzazione contestuale di informazioni cliniche in scenario.

Il Piano di sviluppo ha durata di 18 mesi e si articola in tre direttrici principali:
1. Sviluppo e validazione del sistema AI multi-agente (*AI Data Expert*) con moduli specializzati per letteratura scientifica, predizione clinica su dati reali e sintesi contestualizzata
2. Prototipazione esplorativa di interfaccia AR su display binoculare indossabile (XREAL 1S — display Micro-OLED binoculare per sviluppo e validazione dell'architettura visiva dell'interfaccia clinica)
3. Attivazione operativa della piattaforma in contesti reali valdostani con partner contrattualmente impegnati (GTC® e TORX® 2027)

Il progetto si inserisce nelle aree prioritarie della Smart Specialization Strategy (S3) regionale 2021-2027 e produce ricadute occupazionali, tecnologiche e sanitarie dirette sul territorio valdostano.

---

## 2. Contesto e Motivazione

### 2.1 Il problema clinico

L'operatore sanitario preospedaliero — medico del 118, infermiere di emergenza, soccorritore avanzato — opera in condizioni che nessun altro professionista sanitario affronta: ambiente remoto o ostile, stress decisionale estremo, tempi compressi, connettività instabile, spesso le mani occupate durante le manovre di soccorso.

In questo contesto, l'accesso alla letteratura medica aggiornata, ai protocolli operativi e agli strumenti di calcolo clinico è di fatto impossibile con gli strumenti digitali convenzionali. La conseguenza è una dipendenza dalla memoria individuale dell'operatore, con variabilità nella qualità delle cure inversamente proporzionale all'esperienza del singolo.

### 2.2 Il gap nella ricerca clinica

Sul fronte della ricerca, esiste un **gap specifico**: non sono disponibili modelli predittivi ML (Machine Learning — sistemi che apprendono dai dati per fare previsioni) validati sul contesto preospedaliero medicalizzato europeo per scenari ad alta complessità come l'arresto cardiaco extraospedaliero (OHCA — Out-of-Hospital Cardiac Arrest, arresto cardiaco fuori dall'ospedale). I modelli predittivi esistenti non sono sviluppati né calibrati per il sistema EMS italiano.

EMSy colma questo gap sviluppando un modello ML preospedaliero-only validato su dataset europei medicalizzati pubblici, con piena aderenza allo standard Utstein.

### 2.3 Il gap tecnologico nelle interfacce

Le interfacce digitali esistenti per il soccorso sono progettate per ambienti controllati. Nessuna piattaforma AI per la medicina d'emergenza ha progettato un'interfaccia ottimizzata per la realtà aumentata, con informazioni cliniche (dosaggi, score, risposte AI) visualizzate in overlay senza interrompere le manovre. EMSy introduce questo paradigma: il Piano di sviluppo prevede la prototipazione dell'interfaccia AR — progettazione dell'architettura visiva, test di leggibilità e validazione dell'esperienza utente — su display binoculare XREAL 1S (Micro-OLED, 1920×1200 per occhio, 52° campo visivo). Il prototipo sarà la base per il futuro deployment su dispositivi da campo.

### 2.4 La risposta di EMSy

EMSy è già in produzione con oltre 800 utenti registrati in più di 50 paesi e più di 2.000 consultazioni giornaliere. Il presente Piano di sviluppo rappresenta il salto evolutivo dalla piattaforma informativa esistente a un sistema AI predittivo e multi-modale, radicato nel contesto operativo valdostano.

---

## 3. Obiettivi del Piano

### Obiettivo generale
Sviluppare e validare sul campo, con operatori del soccorso valdostani, un sistema AI multi-agente a moduli specializzati integrati per il supporto informativo e formativo alla medicina d'urgenza preospedaliera in ambiente montano, includendo la prototipazione esplorativa di interfacce AR per la visualizzazione contestuale di informazioni cliniche in scenario.

### Obiettivi specifici

| # | Obiettivo | Fase | Indicatore di risultato |
|---|-----------|------|------------------------|
| OS1 | Sviluppare il modulo ML predittivo OHCA (Modulo predittivo) | Fase 1 | AUC (Area Under the Curve — indicatore di accuratezza predittiva, da 0 a 1) ≥ 0.75 su validation set ROC Epistry v3 |
| OS2 | Attivare EMSy Events su eventi VDA 2027 | Fase 2 | Sistema attivo su GTC® e TORX® 2027, ≥500 atleti gestiti |
| OS3 | Rilasciare la Web App EMSy accessibile da browser mobile | Fase 1 | Web App live, testata su browser mobile iOS e Android |
| OS4 | Integrare i 3 moduli AI in architettura unificata LangGraph | Fase 2 | Sistema end-to-end testato su ≥100 casi clinici reali |

| OS5 | Validare il modello OHCA su dataset europei medicalizzati pubblici | Fase 2 | AUC validato su dataset europeo, report clinico prodotto |
| OS6 | Prototipare interfaccia AR su display XREAL 1S | Fase 2 | Prototipo funzionante con visualizzazione overlay clinica su display Micro-OLED binoculare |
| OS7 | Completare assessment tecnologico esterno | Fase 2 | Report di assessment consegnato entro mese 12 |
| OS8 | Certificare compliance GDPR del sistema PII | Fase 2 | Fascicolo documentale validato da consulente specializzato |

---

## 4. Architettura Tecnica del Sistema

### 4.1 AI Data Expert — Sistema multi-intelligenza a 3 moduli

Il cuore del Piano di sviluppo è l'*AI Data Expert*, un sistema che integra tre moduli AI specializzati orchestrati dal framework LangGraph (sistema software che coordina più agenti AI in sequenza logica, come un direttore d'orchestra). L'orchestratore analizza la domanda del clinico e attiva i moduli pertinenti, restituendo una risposta sintetica e contestualizzata.


```
                    OPERATORE SANITARIO
                    (medico 118, ricercatore)
                              |
                   [LangGraph Orchestrator]
                    Analizza la domanda e
                    attiva i moduli pertinenti
                        /           \
                       /             \
               MODULO 1          MODULO 2
               LLM + RAG         ML classico
               Letteratura       Dati OHCA
               scientifica       tabulari
                        \           /
                         \         /
                   [MODULO 3 — LLM Reasoning]
                    Sintesi clinica contestualizzata
                    in linguaggio naturale
```

**Modulo 1 — LLM + RAG** *(già attivo, da potenziare)*
LLM (Large Language Model — modello AI che comprende e genera testo in linguaggio naturale) + RAG (Retrieval-Augmented Generation — sistema che recupera informazioni da una base documentale prima di rispondere, garantendo risposte basate su fonti verificate). Ricerca semantica su base di conoscenza medica specializzata: linee guida ERC (European Resuscitation Council — Consiglio Europeo per la Rianimazione)/ILCOR (International Liaison Committee on Resuscitation — Comitato Internazionale di Collegamento sulla Rianimazione)/AHA (American Heart Association), protocolli 118, farmaci EMA/FDA, letteratura PubMed. Vector database Pinecone, routing multi-modello via OpenRouter (Anthropic Claude, Google Gemini, Meta Llama).

**Modulo 2 — ML su dati strutturati** *(sviluppo Fase 1 — priorità principale)*
Modello predittivo XGBoost/Random Forest (algoritmi di Machine Learning ad alto rendimento su dati strutturati) addestrato su dati tabulari OHCA secondo standard Utstein (standard internazionale per la raccolta uniforme di dati sull'arresto cardiaco). Dataset primario: ROC Epistry v3 (120.000 casi, BioLINCC). Servito da microservizio Python FastAPI. SHAP values (SHapley Additive exPlanations — metodo per spiegare il contributo di ogni variabile alla singola predizione) obbligatori per ogni predizione.

**Modulo 3 — LLM Reasoning** *(integrazione Fase 2)*
Modulo di sintesi: riceve gli output dei Moduli 1-2 e genera una risposta clinica unica, contestualizzata e azionabile. Parzialmente presente nell'architettura attuale, da completare e integrare.

### 4.2 Interfaccia AR — Prototipazione su XREAL 1S

Il piano di sviluppo FESR include la fase di prototipazione dell'interfaccia AR di EMSy: progettazione dell'architettura visiva, test di leggibilità in overlay e validazione dell'esperienza utente clinica.

Lo strumento utilizzato per questa fase è l'**XREAL 1S** — display binoculare Micro-OLED (1920×1200 per occhio, 52° campo visivo, 700 nit) connesso alla workstation di sviluppo. Il dispositivo permette a Simon di vedere direttamente in AR come appaiono le informazioni cliniche sovrapposte alla visuale reale, iterare rapidamente sul layout, testare la leggibilità dei componenti (score OHCA, dosaggi farmacologici, risposte AI) e validare la UX con gli altri membri del team.

Questa fase produce i design pattern, le specifiche di interazione e i criteri di UX che guideranno il futuro deployment dell'interfaccia su dispositivi da campo. La separazione tra fase di prototipazione (sviluppo iterativo su display consumer di alta qualità) e fase di deployment (hardware certificato per uso operativo) è la prassi standard nello sviluppo di interfacce per ambienti critici.

### 4.3 Stack tecnologico

| Layer | Tecnologia | Stato |
|-------|-----------|-------|
| Frontend web | Next.js 15 + TypeScript | In produzione |
| Backend API | Next.js API Routes + Python FastAPI | In produzione + da sviluppare |
| Database | PostgreSQL + Prisma (Neon hosted) | In produzione |
| Vector DB | Pinecone | In produzione |
| AI Orchestrazione | LangChain + LangGraph | In produzione (da estendere) |
| LLM routing | OpenRouter (multi-model) | In produzione |
| ML service | Python FastAPI + XGBoost | Da sviluppare |
| Web App | PWA (Progressive Web App — applicazione web fruibile da browser mobile senza installazione) | Da sviluppare |
| AR interface | XREAL SDK + adattamento UI | Da sviluppare |
| Cloud compute | AWS SageMaker + NVIDIA credits | Crediti disponibili |
| Privacy/GDPR | OpenMed NER (Named Entity Recognition — riconoscimento automatico di entità sensibili nel testo) + pipeline PII (Personally Identifiable Information — dati personali identificabili) | In produzione |
| Server dedicato | Server GPU on-premise h24 per inferenza LLM locale | Da acquistare Fase 1 |

---

## 5. Piano di Lavoro

### FASE 1 — Mesi 1-6 | Budget: €27.210

#### Obiettivi Fase 1
- Costruire le fondamenta del sistema ML (Modulo 2)
- Sviluppare e testare il modulo EMSy Events in preparazione all'attivazione operativa (Fase 2)
- Rilasciare la Web App accessibile da browser mobile

#### Work Breakdown Structure — Fase 1

**WP1.1 — Data Foundation e ML Service (mesi 1-3)**
- Definizione schema dati Utstein e struttura database DuckDB per dataset clinici
- Accesso e validazione dataset ROC Epistry v3 (BioLINCC)
- Sviluppo endpoint upload CSV con validazione colonne Utstein
- Pipeline di anonimizzazione e validazione all'ingestion
- Setup microservizio Python FastAPI (`emsy-ml-service/`)
- *Responsabile:* Collaboratore Co.Co.Co + Simon

**WP1.2 — Modulo 2: Training e inference OHCA (mesi 2-4)**
- Feature engineering su variabili preospedaliere Utstein
- Training modello XGBoost/Random Forest su ROC Epistry v3
- Endpoint `/predict` (variabili → probabilità CPC 1-2)
- Endpoint `/explain` (SHAP waterfall per singola predizione)
- Endpoint `/stats` (statistiche descrittive, distribuzioni)
- Benchmark contro score esistenti (CAHP, R-EDByUS)
- *Responsabile:* Collaboratore Co.Co.Co + Simon + Damiano (validazione clinica)

**WP1.3 — EMSy Events: sviluppo e preparazione modulo (mesi 3-6)**
- Finalizzazione modulo gestione emergenze in tempo reale
- Sviluppo dashboard centrale operativa web per coordinamento sanitario eventi
- Test interno del sistema su scenari simulati
- Integrazione con infrastruttura VDA Trailers in preparazione alle edizioni 2027
- Definizione protocolli operativi con Damiano per attivazione in gara
- *Responsabile:* Simon + Nicolò (coordinamento operativo) + Damiano (protocolli)

**WP1.4 — Web App EMSy: rilascio pubblico accessibile da mobile (mesi 1-3)**
- Sviluppo e ottimizzazione interfaccia Web App (PWA) per browser mobile (iOS Safari, Android Chrome)
- Ottimizzazione UX (User Experience — esperienza utente) per uso su smartphone in condizioni di campo
- Test di compatibilità cross-browser e cross-device
- Rilascio pubblico accessibile via URL senza necessità di installazione
- *Responsabile:* Simon + Nicolò

#### Milestone Fase 1

| Milestone | Mese | Indicatore |
|-----------|------|------------|
| M1.1 | Mese 2 | Pipeline ingestion dati Utstein operativa |
| M1.2 | Mese 3 | Microservizio ML endpoint `/predict` attivo |
| M1.3 | Mese 3 | Web App live e accessibile da browser mobile iOS e Android |
| M1.4 | Mese 4 | Modello OHCA trainato: AUC ≥ 0.75 su validation set |
| M1.5 | Mese 5 | Modulo EMSy Events completato e testato internamente |
| M1.6 | Mese 6 | Protocolli operativi Events validati con Damiano — sistema pronto per attivazione in gara |

#### Budget Fase 1

| Voce | Importo |
|------|---------|
| Co.Co.Co (€1.800 × 6 mesi) | €10.800 |
| Prestazioni soci | €5.320 |
| Spese generali (15% × €10.800) | €1.620 |
| Hardware (Server GPU €10.000 + 2× XREAL 1S €918 — quota ammortamento 18/60) | €3.275 |
| Software / Licenze LLM (€800 × 6 mesi) | €4.800 |
| Margine di riserva Fase 1 | €1.395 |
| **Totale Fase 1** | **€27.210** |

---

### FASE 2 — Mesi 7-18 | Budget: €52.790

#### Obiettivi Fase 2
- Integrare i 3 moduli AI in architettura unificata
- Validare il modello OHCA su dataset europei medicalizzati pubblici
- Prototipare l'interfaccia AR su XREAL 1S
- Attivare operativamente EMSy Events su GTC® (luglio 2027) e TORX® (settembre 2027)
- Espandere a un secondo dominio clinico
- Completare assessment tecnologico e compliance GDPR

#### Work Breakdown Structure — Fase 2

**WP2.1 — Integrazione LangGraph multi-modulo (mesi 7-10)**
- Sviluppo tool LangGraph: `query_dataset`, `predict_ohca`, `explain_prediction`, `generate_chart`
- Aggiornamento classifier per routing automatico (domande analitiche vs. letteratura)
- Integrazione Modulo 3 (LLM Reasoning): sintesi output ML + RAG in risposta unica
- Test end-to-end sistema integrato su casi clinici documentati
- *Responsabile:* Collaboratore Co.Co.Co + Simon

**WP2.2 — Validazione clinica modello OHCA su dataset europei pubblici (mesi 8-12)**
- External validation modello OHCA su holdout set ROC Epistry v3 e dataset secondari (WACAR Mendeley, 814 casi; DCAPS Korea, 36k casi)
- Calcolo AUC su dataset europei medicalizzati
- Calibrazione modello e implementazione guardrail (confidence intervals — intervalli di confidenza, warning campioni piccoli, k-anonymity)
- Confronto performance vs. score clinici esistenti
- Produzione report di validazione clinica
- Test di usabilità della piattaforma EMSy con operatori sanitari durante eventi e manifestazioni sportive in montagna (non deployment istituzionale 118 per motivi burocratici)
- Coinvolgimento di esperto esterno per validazione clinica indipendente
- *Responsabile:* Damiano (Medical Director) + esperto clinico esterno (validatore) + Collaboratore Co.Co.Co

**WP2.3 — Prototipo interfaccia AR su XREAL 1S (mesi 9-14)**
- Setup XREAL 1S e ambiente di sviluppo AR (XREAL SDK)
- Progettazione architettura visiva: layout overlay clinico, gerarchia informativa, leggibilità in AR
- Adattamento interfaccia EMSy per display binoculare (componenti ridotti, alta leggibilità, contrasto ottimizzato)
- Test di validazione UX con Simon e Damiano su scenari simulati
- Documentazione tecnica del prototipo e specifiche per futuro deployment su dispositivi da campo
- *Responsabile:* Simon + Nicolò (coordinamento)

**WP2.4 — Espansione secondo dominio clinico (mesi 14-18)**
- Adattamento architettura ML a dataset STEMI o trauma preospedaliero
- Identificazione e coinvolgimento ≥1 partner clinico validatore
- Primo modello funzionante su secondo dominio
- *Responsabile:* Damiano + Collaboratore Co.Co.Co

**WP2.5 — EMSy Events: attivazione operativa GTC® e TORX® 2027 (mesi 7-11)**
- Coordinamento finale con VDA Trailers per GTC® (luglio 2027) e TORX® with Kailas (settembre 2027)
- Attivazione sistema Events in condizioni reali di gara
- Raccolta dati sanitari de-identificati per validazione sistema
- Report post-evento con metriche operative (atleti gestiti, interventi, performance sistema)
- *Responsabile:* Nicolò (coordinamento operativo) + Damiano (protocolli clinici) + Simon (supporto tecnico)

**WP2.6 — Assessment tecnologico esterno (mesi 8-12)**
- Selezione esperto esterno indipendente (≥5 anni esperienza in technology assessment o gestione startup innovative nel settore AI/medicale)
- Affidamento formale incarico
- Conduzione assessment e produzione report
- *Responsabile:* Simon (coordinamento) + esperto esterno

**WP2.7 — Compliance GDPR: validazione e certificazione (mesi 10-14)**
- Incarico a consulente specializzato GDPR per validazione sistema PII
- Produzione fascicolo documentale: diagramma architetturale, versioni esatte componenti, risultati validazione su campione rappresentativo
- Data retention policy formalizzata
- DPA Google Cloud e region pinning documentati
- *Responsabile:* Nicolò (coordinamento) + consulente esterno

#### Milestone Fase 2

| Milestone | Mese | Indicatore |
|-----------|------|------------|
| M2.1 | Mese 8 | EMSy Events attivo su GTC® (luglio 2027) — report post-evento |
| M2.2 | Mese 9 | Sistema 3 moduli integrato in LangGraph — test end-to-end completato |
| M2.3 | Mese 10 | Prototipo AR: overlay clinico funzionante su display XREAL 1S — UX validata |
| M2.4 | Mese 10 | EMSy Events attivo su TORX® (settembre 2027) — report post-evento |
| M2.5 | Mese 11 | Modello OHCA validato su dataset europei medicalizzati — AUC documentato |
| M2.6 | Mese 12 | Assessment tecnologico esterno completato — report consegnato |
| M2.7 | Mese 14 | Fascicolo GDPR validato da consulente |
| M2.8 | Mese 18 | Secondo dominio clinico attivo — ≥1 partner validatore identificato |

#### Budget Fase 2

| Voce | Importo |
|------|---------|
| Co.Co.Co (€1.800 × 12 mesi) | €21.600 |
| Prestazioni soci | €10.680 |
| Spese generali (15% × €21.600) | €3.240 |
| Software / Licenze LLM (€800 × 12 mesi) | €9.600 |
| Assessment tecnologico | €4.500 |
| Margine di riserva Fase 2 (spese legali certificazioni EU ~€1.000 + consulenza Dott. Carenzo ~€1.500 + ricerca medica/test eventi ~€670) | €3.170 |
| **Totale Fase 2** | **€52.790** |

---

## 6. Deliverables Finali

| # | Deliverable | Fase | Metrica di verifica |
|---|-------------|------|-------------------|
| D1 | Modulo ML predittivo OHCA (Modulo predittivo) — MVP | 1 | AUC ≥ 0.75; SHAP su 100% predizioni |
| D2 | EMSy Events attivo su GTC® e TORX® 2027 | 2 | Sistema live; dati su ≥500 atleti; report post-evento |
| D3 | Web App EMSy accessibile da browser mobile | 1 | Web App live, ottimizzata per mobile, accessibile senza installazione |
| D4 | Sistema AI Data Expert integrato (3 moduli) | 2 | Test su ≥100 casi clinici reali documentati |
| D5 | Validazione clinica OHCA su dataset europei medicalizzati pubblici | 2 | AUC su dataset europeo; report di validazione |
| D6 | Prototipo interfaccia AR su display XREAL 1S | 2 | Overlay clinico funzionante, architettura visiva documentata |
| D7 | Assessment tecnologico esterno | 2 | Report consegnato entro mese 12 |
| D8 | Fascicolo GDPR validato | 2 | Audit completato; data retention policy formalizzata |

---

## 7. Team e Competenze

### Soci fondatori

| Nome | Ruolo nel Piano | Ore/mese | Competenze specifiche |
|------|----------------|----------|----------------------|
| **Simon Grosjean** | Ideatore del progetto, sviluppo architettura AI, LangGraph, ML service, AR SDK | ~15 h/mese | Medico del 118, fullstack senior, Python ML, LangChain/LangGraph |
| **Damiano Presciani** | Validazione clinica modelli, protocolli operativi, standard Utstein | ~8 h/mese | Medico del 118, ideatore di EMSy Events, EMS medicalizzato, standard Utstein, OHCA |
| **Nicolò Balzani** | Marketing, comunicazione, gestione operativa del progetto, referente societario FESR | ~4 h/mese | Coordinamento operativo, marketing, comunicazione, compliance |

### Collaboratore Co.Co.Co

Sviluppatore AI junior (profilo studente universitario, nessun altro impiego), inserito per la durata del Piano (18 mesi). Mansioni: sviluppo microservizio ML FastAPI, pipeline dati, integrazione LangGraph, test. Sede operativa in Valle d'Aosta, max 20% smart working.

### Esperti esterni

- **Esperto assessment tecnologico:** profilo TBD, ≥5 anni esperienza in technology assessment o incubatori/startup innovative nel settore AI/medicale (da identificare entro avvio Piano, incarico entro mese 6)
- **Consulente GDPR:** specialista in compliance dati sanitari, validazione sistema PII (Personally Identifiable Information), redazione fascicoli tecnici
- **Dott. Luca Carenzo** — Anestesista-rianimatore, esperto in medicina d'emergenza ed elisoccorso (HEMS — Helicopter Emergency Medical Services). Validatore clinico esterno indipendente: testerà la piattaforma EMSy in contesti reali, fornirà feedback clinico qualificato e potrà produrre pubblicazioni scientifiche o presentazioni a convegni medici sull'efficacia del sistema. Incarico previsto in Fase 2, finanziato dal margine di riserva.

---

## 8. Gestione dei Rischi

| Rischio | Probabilità | Impatto | Mitigazione |
|---------|-------------|---------|-------------|
| Dataset ROC Epistry v3 non disponibile nei tempi | Media | Alto | Dataset WACAR (Mendeley, 814 casi) e DCAPS Korea (36k) già scaricabili come alternativa per avvio training |
| AUC < 0.75 al primo training | Media | Medio | Feature engineering iterativo; possibilità di abbassare soglia a 0.70 con motivazione clinica; Damiano disponibile per revisione variabili |
| Difficoltà integrazione SDK XREAL | Bassa | Medio | SDK ben documentato; fallback su WebXR browser-based come alternativa |
| Scostamento costi LLM oltre budget | Bassa | Basso | Crediti AWS Activate e NVIDIA coprono i picchi iniziali; server GPU on-premise riduce dipendenza da API cloud; margine di riserva €4.565 disponibile |
| Mancata disponibilità Dott. Carenzo per test | Bassa | Medio | Identificare in anticipo un secondo profilo clinico alternativo di pari livello |
| Indisponibilità dataset secondari per validazione | Bassa | Medio | Dataset WACAR (Mendeley) e DCAPS Korea già scaricabili come alternativa; holdout ROC Epistry v3 garantisce validazione minima |

---

## 9. Compliance Normativa

### GDPR (Reg. UE 2016/679)
Sistema di anonimizzazione PII già in produzione con architettura a 3 layer indipendenti. Tutta l'infrastruttura in regioni EU. Nel Piano: validazione formale da consulente specializzato e produzione fascicolo documentale completo.

### EU AI Act (Reg. UE 2024/1689)
EMSy è classificato come strumento informativo ed educativo per professionisti sanitari. Rischio limitato (Art. 50): obbligo di trasparenza verso l'utente che il sistema è AI-assistito. Già rispettato nell'interfaccia corrente.

### DNSH — Do No Significant Harm
Il progetto è software-first: nessuna produzione manifatturiera, nessuna emissione diretta. Hardware acquistato da fornitori certificati RoHS (Direttiva 2011/65/UE) e WEEE (Direttiva 2012/19/UE). Il Server GPU dedicato è certificato Energy Star e conforme agli standard Ecodesign (ESPR); il display XREAL 1S è certificato CE e RoHS.

### ESPR — Ecodesign for Sustainable Products (Reg. UE 2024/1781)
L'hardware acquistato nel Piano è certificato Ecodesign, condizione per l'ottenimento della **premialità +5 punti** prevista dal bando.

---

## 10. Coerenza con la S3 Valle d'Aosta 2021-2027

La Smart Specialization Strategy (S3) regionale 2021-2027 individua tre aree di specializzazione intelligente su cui concentrare gli investimenti FESR per rafforzare la competitività del sistema produttivo e dell'ecosistema innovativo valdostano. Il Piano di sviluppo EMSy si inserisce coerentemente in tutte e tre le aree, con contributi specifici e misurabili.

---

### Montagna intelligente
*Digitalizzazione, intelligenza artificiale e tecnologie avanzate applicate al contesto alpino*

La S3 identifica nella digitalizzazione e nell'AI una leva strategica per valorizzare le specificità del territorio montano, in settori in cui la Valle d'Aosta può sviluppare vantaggi competitivi rispetto ad altri contesti.

**Come EMSy contribuisce:**
- L'AI Data Expert è un sistema progettato esplicitamente per le criticità del contesto alpino: funziona con connettività ridotta o instabile, è ottimizzato per l'uso con i guanti, in condizioni meteo avverse, da parte di operatori sotto stress
- Il sistema multi-agente integra intelligenza artificiale avanzata (LLM, ML predittivo) in un contesto operativo — il soccorso in montagna — in cui nessun prodotto analogo esiste oggi sul mercato
- La prototipazione dell'interfaccia AR su display binoculare XREAL 1S introduce un paradigma di visualizzazione uomo-AI inedito per la medicina d'emergenza alpina, con design patterns trasferibili in futuro su dispositivi da campo per il soccorso alpino e speleologico valdostano (SAVALP)
- Il sistema raccoglie e analizza dati clinici provenienti da interventi reali in ambiente montano, creando un patrimonio informativo unico per la ricerca applicata al territorio

---

### Montagna di eccellenza
*Qualità della vita, sicurezza, sanità e servizi ad alto valore aggiunto*

La S3 punta a consolidare la Valle d'Aosta come territorio di eccellenza nei servizi alla persona, con particolare attenzione alla sicurezza in montagna e alla qualità del sistema sanitario territoriale.

**Come EMSy contribuisce:**
- Valle d'Aosta è sede del sistema di emergenza territoriale 118 e del Corpo Valdostano di Soccorso Alpino e Speleologico (SAVALP): un ecosistema di eccellenza operativa che EMSy valorizza portando innovazione tecnologica dove l'expertise umana è già alta
- Il Piano di sviluppo prevede la validazione clinica del modello OHCA su dataset europei medicalizzati pubblici — un contributo scientifico concreto alla medicina d'urgenza preospedaliera europea, prodotto in Valle d'Aosta
- L'attivazione di EMSy Events su GTC® (Gran Trail Courmayeur, oltre 2.000 atleti da 50+ paesi) e TORX® with Kailas 2027 porta innovazione sanitaria diretta su eventi di rilevanza internazionale che si svolgono sul territorio valdostano, con Piano Sanitario approvato dall'AUSL Valle d'Aosta
- La piattaforma migliora la qualità e l'uniformità delle cure preospedaliere, riducendo la variabilità clinica legata all'esperienza del singolo operatore — un impatto diretto sulla sicurezza di residenti e turisti in Valle d'Aosta
- Il progetto crea occupazione qualificata nel settore AI/tecnologia in Valle d'Aosta, un profilo professionale ancora raro sul territorio

---

### Montagna sostenibile
*Transizione ecologica, efficienza energetica e modelli produttivi a basso impatto ambientale*

La S3 promuove modelli di sviluppo economico compatibili con la fragilità dell'ecosistema alpino, privilegiando tecnologie a basso impatto ambientale e processi produttivi dematerializzati.

**Come EMSy contribuisce:**
- Il modello di business è interamente **software-first e cloud-based**: nessuna produzione manifatturiera, nessuna supply chain fisica, zero emissioni operative dirette legate allo sviluppo del prodotto
- L'infrastruttura cloud (Vercel EU, Neon, AWS) è ospitata in data center con certificazioni di efficienza energetica, localizzati in regioni EU con mix energetico a basse emissioni
- L'hardware acquistato nel Piano (Server GPU dedicato, XREAL 1S) è conforme agli standard **RoHS/WEEE**; il Server GPU è certificato **Energy Star** e **Ecodesign (ESPR, Reg. UE 2024/1781)** — condizione per l'ottenimento della premialità +5 punti prevista dal bando
- La piattaforma distribuisce conoscenza clinica in modalità digitale, eliminando la necessità di spostamenti fisici per la formazione continua degli operatori del soccorso (ECM digitale), con ricaduta diretta sulla riduzione delle emissioni legate alla mobilità formativa
- Il sistema di anonimizzazione PII a 3 layer garantisce che nessun dato sanitario grezzo lasci l'Unione Europea, in linea con i principi di sovranità digitale europea promossi dalla strategia GAIA-X

---

## 11. Assessment Tecnologico

Come previsto dall'Art. 12 dell'Avviso, il Piano di sviluppo include un **assessment tecnologico obbligatorio** condotto da esperto esterno indipendente con almeno 5 anni di esperienza documentata in assessment tecnologico, gestione di startup innovative o incubatori nel settore AI o medicale.

**Tempistica:** affidamento formale entro mese 8, assessment completato entro mese 12.

**Oggetto dell'assessment:**
- Valutazione dell'architettura tecnica del sistema AI Data Expert
- Analisi del posizionamento competitivo rispetto alla letteratura scientifica internazionale
- Verifica della coerenza tra deliverables realizzati e Piano approvato
- Raccomandazioni per la fase di scale-up successiva al Piano

**Budget:** €4.500 (con margine del 20% per eventuale scostamento senza necessità di autorizzazione preventiva, ai sensi dell'Art. 10, comma 7 dell'Avviso).

---

## 12. Obblighi Post-Finanziamento

EMSy si impegna al rispetto di tutti gli obblighi previsti dall'Avviso:

| Obbligo | Modalità di adempimento |
|---------|------------------------|
| IBAN dedicato | Apertura conto dedicato al progetto entro concessione contributo |
| Contabilità separata | Tutte le spese esclusivamente su IBAN dedicato, con CUP su ogni documento |
| Rapportini orari | Fogli presenza mensili per Co.Co.Co e soci, controfirmati |
| Max 20% smart working | Presenza fisica documentata in VdA per ≥80% delle ore rendicontate |
| Hardware in VdA | Server GPU e XREAL 1S rimangono presso sede VdA per 3 anni post-progetto |
| Assessment entro anno 1 | Pianificato entro mese 12 (vedi sezione 11) |
| DNSH | Hardware certificato RoHS/WEEE/Ecodesign (vedi sezione 9) |

---

*Documento interno EMSy S.r.l. — Aggiornato giugno 2026 — Non diffondere*
