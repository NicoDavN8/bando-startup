# Piano di Sviluppo — EMSy S.r.l.
**Bando FESR DGR 575/2025 — Sostegno alle startup innovative — Valle d'Aosta**
**Durata:** 18 mesi | **Budget totale:** €80.000 | **Contributo richiesto:** €52.800 (70%)
*Aggiornato: giugno 2026*

---

## 1. Sommario Esecutivo

**Titolo del progetto:** Sistema AI multi-agente per il supporto informativo all'emergenza preospedaliera in ambiente montano

**Finalità:** Sviluppare e validare sul campo, con operatori del soccorso valdostani, un sistema AI multi-agente a moduli specializzati integrati per il supporto informativo e formativo alla medicina d'urgenza preospedaliera in ambiente montano, includendo la prototipazione esplorativa di interfacce hands-free per l'operatività in scenario.

Il Piano di sviluppo ha durata di 18 mesi e si articola in tre direttrici principali:
1. Sviluppo e validazione del sistema AI multi-agente (*AI Data Expert*) con moduli specializzati per letteratura scientifica, predizione clinica su dati reali, analisi di segnali biomedici e sintesi contestualizzata
2. Prototipazione esplorativa di interfaccia hands-free su dispositivo AR indossabile (RealWear Navigator 520) per l'operatività in scenario di soccorso
3. Attivazione operativa della piattaforma in contesti reali valdostani con partner contrattualmente impegnati (GTC® e TORX® 2026)

Il progetto si inserisce nelle aree prioritarie della Smart Specialization Strategy (S3) regionale 2021-2027 e produce ricadute occupazionali, tecnologiche e sanitarie dirette sul territorio valdostano.

---

## 2. Contesto e Motivazione

### 2.1 Il problema clinico

L'operatore sanitario preospedaliero — medico del 118, infermiere di emergenza, soccorritore avanzato — opera in condizioni che nessun altro professionista sanitario affronta: ambiente remoto o ostile, stress decisionale estremo, tempi compressi, connettività instabile, spesso le mani occupate durante le manovre di soccorso.

In questo contesto, l'accesso alla letteratura medica aggiornata, ai protocolli operativi e agli strumenti di calcolo clinico è di fatto impossibile con gli strumenti digitali convenzionali. La conseguenza è una dipendenza dalla memoria individuale dell'operatore, con variabilità nella qualità delle cure inversamente proporzionale all'esperienza del singolo.

### 2.2 Il gap nella ricerca clinica

Sul fronte della ricerca, esiste un **gap specifico**: non sono disponibili modelli predittivi ML validati sul contesto preospedaliero medicalizzato europeo per scenari ad alta complessità come l'arresto cardiaco extraospedaliero (OHCA — Out-of-Hospital Cardiac Arrest). I modelli predittivi esistenti non sono sviluppati né calibrati per il sistema EMS italiano.

EMSy colma questo gap sviluppando un modello ML preospedaliero-only validato su dati del sistema 118 italiano, con piena aderenza allo standard Utstein.

### 2.3 Il gap tecnologico nelle interfacce

Le interfacce digitali esistenti per il soccorso sono progettate per ambienti controllati. Nessuna piattaforma AI per la medicina d'emergenza offre oggi un'interfaccia operativa in realtà aumentata, hands-free, utilizzabile durante le manovre di rianimazione cardiopolmonare o di gestione del trauma. EMSy introduce questo paradigma tramite la prototipazione su RealWear Navigator 520.

### 2.4 La risposta di EMSy

EMSy è già in produzione con oltre 400 utenti registrati in più di 50 paesi e più di 1.000 consultazioni giornaliere. Il presente Piano di sviluppo rappresenta il salto evolutivo dalla piattaforma informativa esistente a un sistema AI predittivo e multi-modale, radicato nel contesto operativo valdostano.

---

## 3. Obiettivi del Piano

### Obiettivo generale
Sviluppare e validare sul campo, con operatori del soccorso valdostani, un sistema AI multi-agente a moduli specializzati integrati per il supporto informativo e formativo alla medicina d'urgenza preospedaliera in ambiente montano, includendo la prototipazione esplorativa di interfacce hands-free per l'operatività in scenario.

### Obiettivi specifici

| # | Obiettivo | Fase | Indicatore di risultato |
|---|-----------|------|------------------------|
| OS1 | Sviluppare il modulo ML predittivo OHCA (Modulo predittivo) | Fase 1 | AUC ≥ 0.75 su validation set ROC Epistry v3 |
| OS2 | Attivare EMSy Events su eventi VDA 2026 | Fase 1 | Sistema attivo su GTC® e TORX®, ≥500 atleti gestiti |
| OS3 | Rilasciare app mobile su App Store e Google Play | Fase 1 | App live su entrambi gli store |
| OS4 | Integrare i 4 moduli AI in architettura unificata LangGraph | Fase 2 | Sistema end-to-end testato su ≥100 casi clinici reali |
| OS5 | Validare il modello OHCA su dati 118 italiani | Fase 2 | AUC validato su dataset europeo, report clinico prodotto |
| OS6 | Prototipare interfaccia AR hands-free su RealWear | Fase 2 | Prototipo funzionante con navigazione vocale su RealWear Navigator 520 |
| OS7 | Completare assessment tecnologico esterno | Fase 2 | Report di assessment consegnato entro mese 12 |
| OS8 | Certificare compliance GDPR del sistema PII | Fase 2 | Fascicolo documentale validato da consulente specializzato |

---

## 4. Architettura Tecnica del Sistema

### 4.1 AI Data Expert — Sistema multi-intelligenza a 4 moduli

Il cuore del Piano di sviluppo è l'*AI Data Expert*, un sistema che integra quattro moduli AI specializzati orchestrati dal framework LangGraph. L'orchestratore analizza la domanda del clinico e attiva i moduli pertinenti, restituendo una risposta sintetica e contestualizzata.

```
                    OPERATORE SANITARIO
                    (medico 118, ricercatore)
                              |
                   [LangGraph Orchestrator]
                    Analizza la domanda e
                    attiva i moduli pertinenti
                   /          |          \
                  /           |           \
          MODULO 1        MODULO 2      MODULO 3
          LLM + RAG       ML classico   Deep Learning
          Letteratura     Dati OHCA     Segnali ECG/EEG
          scientifica     tabulari
                  \           |           /
                   \          |          /
                   [MODULO 4 — LLM Reasoning]
                    Sintesi clinica contestualizzata
                    in linguaggio naturale
```

**Modulo 1 — LLM + RAG** *(già attivo, da potenziare)*
Ricerca semantica su base di conoscenza medica specializzata: linee guida ERC/ILCOR/AHA, protocolli 118, farmaci EMA/FDA, letteratura PubMed. Vector database Pinecone, routing multi-modello via OpenRouter (Anthropic Claude, Google Gemini, Meta Llama).

**Modulo 2 — ML su dati strutturati** *(sviluppo Fase 1 — priorità principale)*
Modello predittivo XGBoost/Random Forest addestrato su dati tabulari OHCA secondo standard Utstein. Dataset primario: ROC Epistry v3 (120.000 casi, BioLINCC). Servito da microservizio Python FastAPI. SHAP values obbligatori per ogni predizione (explainability clinica).

**Modulo 3 — Deep Learning su segnali** *(sviluppo Fase 2)*
Analisi di segnali biomedici grezzi: ECG waveform per predizione efficacia defibrillazione, EEG post-ROSC per predizione esito neurologico. Framework PyTorch, compute su crediti NVIDIA/AWS già ricevuti.

**Modulo 4 — LLM Reasoning** *(integrazione Fase 2)*
Modulo di sintesi: riceve gli output dei Moduli 1-3 e genera una risposta clinica unica, contestualizzata e azionabile. Parzialmente presente nell'architettura attuale, da completare e integrare.

### 4.2 Interfaccia AR hands-free — RealWear Navigator 520

Il RealWear Navigator 520 è un dispositivo di realtà aumentata indossabile progettato per operatori in ambienti difficili: è certificato IP66 (impermeabile, resistente a polvere), funziona a comandi vocali in ambienti rumorosi, e monta un display davanti all'occhio che non ostruisce la visuale.

Per il contesto del soccorso preospedaliero:
- L'operatore indossa il dispositivo durante l'intervento
- Tramite comandi vocali accede alle funzionalità di EMSy
- Il display mostra dosaggi, score clinici e risposte dell'AI senza interrompere le manovre

Il Piano di sviluppo prevede la prototipazione dell'interfaccia EMSy ottimizzata per RealWear: schermo ridotto, navigazione vocale, UX semplificata per condizioni di stress, integrazione con l'AI Assistant tramite SDK RealWear.

### 4.3 Stack tecnologico

| Layer | Tecnologia | Stato |
|-------|-----------|-------|
| Frontend web | Next.js 15 + TypeScript | In produzione |
| Backend API | Next.js API Routes + Python FastAPI | In produzione + da sviluppare |
| Database | PostgreSQL + Prisma (Neon hosted) | In produzione |
| Vector DB | Pinecone | In produzione |
| AI Orchestrazione | LangChain + LangGraph | In produzione (da estendere) |
| LLM routing | OpenRouter (multi-model) | In produzione |
| ML service | Python FastAPI + XGBoost/PyTorch | Da sviluppare |
| Mobile | Capacitor (iOS + Android) | In sviluppo |
| AR interface | RealWear SDK + adattamento UI | Da sviluppare |
| Cloud compute | AWS SageMaker + NVIDIA credits | Crediti disponibili |
| Privacy/GDPR | OpenMed NER + pipeline PII | In produzione |

---

## 5. Piano di Lavoro

### FASE 1 — Mesi 1-6 | Budget: €27.210

#### Obiettivi Fase 1
- Costruire le fondamenta del sistema ML (Modulo 2)
- Attivare EMSy Events su eventi valdostani reali
- Rilasciare l'app mobile su store ufficiali

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

**WP1.3 — EMSy Events: attivazione operativa VDA 2026 (mesi 1-2)**
- Finalizzazione modulo gestione emergenze in tempo reale
- Integrazione con infrastruttura VDA Trailers per GTC® (10-12 luglio 2026)
- Attivazione operativa TORX® with Kailas (11-20 settembre 2026)
- Raccolta dati sanitari de-identificati per validazione sistema
- *Responsabile:* Simon + Nicolò (UX) + Damiano (protocolli)

**WP1.4 — App mobile iOS/Android: rilascio pubblico (mesi 1-3)**
- Finalizzazione build Capacitor iOS/Android
- Revisione Apple App Store + Google Play Store
- Rilascio versione 1.0 pubblica
- *Responsabile:* Simon + Nicolò

#### Milestone Fase 1

| Milestone | Mese | Indicatore |
|-----------|------|------------|
| M1.1 | Mese 2 | Pipeline ingestion dati Utstein operativa |
| M1.2 | Mese 3 | Microservizio ML endpoint `/predict` attivo |
| M1.3 | Mese 3 | App mobile live su App Store e Google Play |
| M1.4 | Mese 4 | Modello OHCA trainato: AUC ≥ 0.75 su validation set |
| M1.5 | Mese 5 | EMSy Events attivo su GTC® (luglio 2026) |
| M1.6 | Mese 6 | EMSy Events attivo su TORX® (settembre 2026) |

#### Budget Fase 1

| Voce | Importo |
|------|---------|
| Co.Co.Co (€1.800 × 6 mesi) | €10.800 |
| Prestazioni soci (33% del totale) | €5.320 |
| Spese generali (15% × €10.800) | €1.620 |
| Hardware (acquisto MBP + RealWear — quota 18/60) | €1.500 |
| Software / Licenze LLM (€800 × 6 mesi) | €4.800 |
| Margine di riserva Fase 1 | €3.170 |
| **Totale Fase 1** | **€27.210** |

---

### FASE 2 — Mesi 7-18 | Budget: €52.790

#### Obiettivi Fase 2
- Integrare i 4 moduli AI in architettura unificata
- Validare il modello OHCA su dati 118 italiani
- Prototipare l'interfaccia AR hands-free
- Espandere a un secondo dominio clinico
- Completare assessment tecnologico e compliance GDPR

#### Work Breakdown Structure — Fase 2

**WP2.1 — Integrazione LangGraph multi-modulo (mesi 7-10)**
- Sviluppo tool LangGraph: `query_dataset`, `predict_ohca`, `explain_prediction`, `generate_chart`
- Aggiornamento classifier per routing automatico (domande analitiche vs. letteratura)
- Integrazione Modulo 4 (LLM Reasoning): sintesi output ML + RAG in risposta unica
- Test end-to-end sistema integrato su casi clinici documentati
- *Responsabile:* Collaboratore Co.Co.Co + Simon

**WP2.2 — Validazione clinica modello OHCA su dati 118 (mesi 8-12)**
- Accesso e preparazione dataset 118 proprietario (centinaia di casi, sistema EMS europeo medicalizzato)
- External validation modello OHCA: calcolo AUC su dati italiani
- Calibrazione modello e implementazione guardrail (confidence intervals, warning campioni piccoli, k-anonymity)
- Confronto performance vs. score clinici esistenti
- Produzione report di validazione clinica
- *Responsabile:* Damiano (Medical Director) + Collaboratore Co.Co.Co

**WP2.3 — Prototipo interfaccia AR hands-free (mesi 9-14)**
- Setup SDK RealWear Navigator 520 e ambiente di sviluppo
- Adattamento interfaccia EMSy per display AR (schermo ridotto, alta leggibilità)
- Implementazione navigazione a comandi vocali
- Test operativi in scenario simulato di soccorso
- Documentazione tecnica del prototipo
- *Responsabile:* Simon + Nicolò (UX AR)

**WP2.4 — Modulo 3: Deep Learning su segnali ECG/EEG (mesi 10-16)**
- Accesso dataset I-CARE/PhysioNet (EEG post-ROSC, 607-1.020 casi)
- Accesso dataset Cardially Brescia (ECG OHCA italiano, 260 casi)
- Training modelli PyTorch su GPU (crediti NVIDIA/AWS SageMaker)
- Integrazione come modulo aggiuntivo in LangGraph
- *Responsabile:* Collaboratore Co.Co.Co + Simon

**WP2.5 — Espansione secondo dominio clinico (mesi 14-18)**
- Adattamento architettura ML a dataset STEMI o trauma preospedaliero
- Identificazione e coinvolgimento ≥1 partner clinico validatore
- Primo modello funzionante su secondo dominio
- *Responsabile:* Damiano + Collaboratore Co.Co.Co

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
| M2.1 | Mese 9 | Sistema 4 moduli integrato in LangGraph — test end-to-end completato |
| M2.2 | Mese 10 | Prototipo AR hands-free: navigazione vocale funzionante su RealWear |
| M2.3 | Mese 11 | Modello OHCA validato su dati 118 italiani — AUC documentato |
| M2.4 | Mese 12 | Assessment tecnologico esterno completato — report consegnato |
| M2.5 | Mese 14 | Fascicolo GDPR validato da consulente |
| M2.6 | Mese 17 | Modulo Deep Learning (ECG/EEG) integrato nel sistema |
| M2.7 | Mese 18 | Secondo dominio clinico attivo — ≥1 partner validatore identificato |

#### Budget Fase 2

| Voce | Importo |
|------|---------|
| Co.Co.Co (€1.800 × 12 mesi) | €21.600 |
| Prestazioni soci (67% del totale) | €10.680 |
| Spese generali (15% × €21.600) | €3.240 |
| Software / Licenze LLM (€800 × 12 mesi) | €9.600 |
| Assessment tecnologico | €4.500 |
| Margine di riserva Fase 2 | €3.170 |
| **Totale Fase 2** | **€52.790** |

---

## 6. Deliverables Finali

| # | Deliverable | Fase | Metrica di verifica |
|---|-------------|------|-------------------|
| D1 | Modulo ML predittivo OHCA (Modulo predittivo) — MVP | 1 | AUC ≥ 0.75; SHAP su 100% predizioni |
| D2 | EMSy Events attivo su GTC® e TORX® 2026 | 1 | Sistema live; dati su ≥500 atleti; report post-evento |
| D3 | App mobile EMSy su App Store e Google Play | 1 | App pubblicata su entrambi gli store |
| D4 | Sistema AI Data Expert integrato (4 moduli) | 2 | Test su ≥100 casi clinici reali documentati |
| D5 | Validazione clinica OHCA su dati 118 italiani | 2 | AUC su dataset europeo; report di validazione |
| D6 | Prototipo AR hands-free RealWear Navigator 520 | 2 | Navigazione vocale funzionante in scenario simulato |
| D7 | Assessment tecnologico esterno | 2 | Report consegnato entro mese 12 |
| D8 | Fascicolo GDPR validato | 2 | Audit completato; data retention policy formalizzata |

---

## 7. Team e Competenze

### Soci fondatori

| Nome | Ruolo nel Piano | Ore/mese | Competenze specifiche |
|------|----------------|----------|----------------------|
| **Simon Grosjean** | Sviluppo architettura AI, LangGraph, ML service, AR SDK | ~15 h/mese | Fullstack senior, Python ML, LangChain/LangGraph, Capacitor |
| **Damiano Presciani** | Validazione clinica modelli, protocolli, dataset 118 | ~8 h/mese | Medico d'emergenza, EMS medicalizzato, standard Utstein, OHCA |
| **Nicolò Balzani** | UX, interfaccia AR, coordinamento compliance | ~4 h/mese | Product design, UX per ambienti estremi, coordinamento |

### Collaboratore Co.Co.Co

Sviluppatore AI junior (profilo studente universitario, nessun altro impiego), inserito per la durata del Piano (18 mesi). Mansioni: sviluppo microservizio ML FastAPI, pipeline dati, integrazione LangGraph, test. Sede operativa in Valle d'Aosta, max 20% smart working.

### Esperti esterni

- **Esperto assessment tecnologico:** profilo TBD, ≥5 anni esperienza in technology assessment o incubatori/startup innovative nel settore AI/medicale (da identificare entro avvio Piano, incarico entro mese 6)
- **Consulente GDPR:** specialista in compliance dati sanitari, validazione sistema PII, redazione fascicoli tecnici

---

## 8. Gestione dei Rischi

| Rischio | Probabilità | Impatto | Mitigazione |
|---------|-------------|---------|-------------|
| Dataset ROC Epistry v3 non disponibile nei tempi | Media | Alto | Dataset WACAR (Mendeley, 814 casi) e DCAPS Korea (36k) già scaricabili come alternativa per avvio training |
| AUC < 0.75 al primo training | Media | Medio | Feature engineering iterativo; possibilità di abbassare soglia a 0.70 con motivazione clinica; Damiano disponibile per revisione variabili |
| Ritardo rilascio App Store (Apple review) | Alta | Basso | Review Apple già avviata; build in submission; tempi medi 1-3 giorni, al massimo 2 settimane |
| Difficoltà integrazione SDK RealWear | Bassa | Medio | SDK ben documentato; comunità sviluppatori attiva; fallback su browser-based AR come alternativa |
| Scostamento costi LLM oltre budget | Bassa | Basso | Crediti AWS Activate e NVIDIA coprono i picchi iniziali; margine di riserva €6.340 disponibile |
| Indisponibilità dati 118 per validazione | Bassa | Alto | Damiano ha accesso diretto ai dati proprietari 118 come Medical Director |

---

## 9. Compliance Normativa

### GDPR (Reg. UE 2016/679)
Sistema di anonimizzazione PII già in produzione con architettura a 3 layer indipendenti. Tutta l'infrastruttura in regioni EU. Nel Piano: validazione formale da consulente specializzato e produzione fascicolo documentale completo.

### EU AI Act (Reg. UE 2024/1689)
EMSy è classificato come strumento informativo ed educativo per professionisti sanitari. Rischio limitato (Art. 50): obbligo di trasparenza verso l'utente che il sistema è AI-assistito. Già rispettato nell'interfaccia corrente.

### DNSH — Do No Significant Harm
Il progetto è software-first: nessuna produzione manifatturiera, nessuna emissione diretta. Hardware acquistato da fornitori certificati RoHS (Direttiva 2011/65/UE) e WEEE (Direttiva 2012/19/UE). MacBook Pro 16" M4 Pro e RealWear Navigator 520 sono dispositivi con certificazione Energy Star e conformi agli standard Ecodesign.

### ESPR — Ecodesign for Sustainable Products (Reg. UE 2024/1781)
L'hardware acquistato nel Piano è certificato Ecodesign, condizione per l'ottenimento della **premialità +5 punti** prevista dal bando.

---

## 10. Coerenza con la S3 Valle d'Aosta 2021-2027

Il Piano si inserisce nelle tre aree strategiche della Smart Specialization Strategy regionale:

**Montagna intelligente**
L'AI Data Expert e l'interfaccia AR sono progettati specificamente per contesti alpini: connettività ridotta, ambienti estremi, operatori con equipaggiamento ingombrante. Il prototipo RealWear è direttamente applicabile al soccorso alpino valdostano.

**Montagna di eccellenza**
Valle d'Aosta ha una tradizione di eccellenza nel soccorso in montagna (Corpo valdostano Soccorso Alpino e Speleologico, SAVALP). EMSy porta innovazione AI in un settore in cui la regione è già leader operativo. L'attivazione su GTC® e TORX® porta la piattaforma nel cuore degli eventi sportivi alpini valdostani di rilevanza internazionale.

**Montagna sostenibile**
Infrastruttura interamente cloud-based (zero hardware on-premise), zero emissioni operative dirette, hardware certificato Ecodesign. Il sistema informativo contribuisce alla qualità delle cure di emergenza, riducendo la variabilità clinica e migliorando gli esiti per i pazienti e gli atleti in Valle d'Aosta.

---

## 11. Assessment Tecnologico

Come previsto dall'Art. 12 dell'Avviso, il Piano di sviluppo include un **assessment tecnologico obbligatorio** condotto da esperto esterno indipendente con almeno 5 anni di esperienza documentata in assessment tecnologico, gestione di startup innovative o incubatori nel settore AI o medicale.

**Tempistica:** affidamento formale entro mese 6, assessment completato entro mese 12.

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
| Hardware in VdA | MBP e RealWear rimangono presso sede VdA per 3 anni post-progetto |
| Assessment entro anno 1 | Pianificato entro mese 12 (vedi sezione 11) |
| DNSH | Hardware certificato RoHS/WEEE/Ecodesign (vedi sezione 9) |

---

*Documento interno EMSy S.r.l. — Aggiornato giugno 2026 — Non diffondere*
