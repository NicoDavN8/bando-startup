# Budget Forecast Dettagliato — EMSy S.r.l.
**Bando FESR DGR 575/2025 — Sostegno alle startup innovative — Valle d'Aosta**
**Progetto:** Sistema AI multi-agente per il supporto informativo all'emergenza preospedaliera in ambiente montano
*Aggiornato: giugno 2026*

---

## 1. Riepilogo Generale

| | Fase 1 (mesi 1–6) | Fase 2 (mesi 7–18) | TOTALE |
|---|---|---|---|
| **Costo progetto** | €27.210 | €52.790 | **€80.000** |
| **Contributo FESR (70%)** | €19.047 | €36.953 | **€52.800** (arrotondato) |
| **Cofinanziamento EMSy (30%)** | €8.163 | €15.837 | **€27.200** |

---

## 2. Budget per Voce di Spesa

### Riepilogo per fase

| Voce | Fase 1 | Fase 2 | TOTALE |
|------|--------|--------|--------|
| Co.Co.Co sviluppatore AI | €10.800 | €21.600 | €32.400 |
| Prestazioni soci (UCS) | €5.320 | €10.680 | €16.000 |
| Spese generali (15%) | €1.620 | €3.240 | €4.860 |
| Hardware (quota ammortamento) | €2.040 | €0 | €2.040 |
| Software / Licenze LLM | €4.800 | €9.600 | €14.400 |
| Assessment tecnologico | €0 | €4.500 | €4.500 |
| Margine di riserva | €2.630 | €3.170 | €5.800 |
| **TOTALE** | **€27.210** | **€52.790** | **€80.000** |

---

## 3. Dettaglio Co.Co.Co Sviluppatore AI

| | Fase 1 (6 mesi) | Fase 2 (12 mesi) | Totale 18 mesi |
|---|---|---|---|
| Compenso lordo mensile | €1.800 | €1.800 | |
| Totale compensi lordi | €10.800 | €21.600 | **€32.400** |
| Ore rendicontabili/mese (€1.800 ÷ €33 UCS) | ~54,5 h | ~54,5 h | |
| Ore totali rendicontabili | ~327 h | ~654 h | **~981 h** |
| Valore UCS (981 ore × €33) | | | **€32.373** |
| Rimborso FESR 70% su valore UCS | | | **~€22.661** |

> ⚠️ Il rimborso FESR si calcola sul **valore UCS** (ore × €33), non sul costo reale aziendale. Il costo reale include anche i contributi INPS Gestione Separata a carico azienda (~€398/mese), per un totale reale di ~€2.198/mese.

---

## 4. Dettaglio Prestazioni Soci

**Tariffa UCS:** €33/ora (Art. 12, PD n.2417 del 07/05/2025) — fissa per tutte le categorie.
**Tetto massimo:** 20% del costo complessivo del progetto = €16.000 (rispettato).

### Distribuzione per socio

| Socio | % budget | Totale 18 mesi | Ore totali | Ore/mese | Ore/settimana |
|-------|----------|---------------|-----------|----------|---------------|
| Simon Grosjean | 55% | €8.800 | 267 ore | ~14,8 h | ~3,5 h |
| Damiano Presciani | 30% | €4.800 | 145 ore | ~8,1 h | ~2 h |
| Nicolò Balzani | 15% | €2.400 | 73 ore | ~4,1 h | ~1 h |
| **Totale** | **100%** | **€16.000** | **485 ore** | **~27 h** | |

### Distribuzione per fase

| Socio | Fase 1 (6 mesi, 33%) | Fase 2 (12 mesi, 67%) | Totale |
|-------|---------------------|----------------------|--------|
| Simon | €2.907 (88 ore) | €5.893 (179 ore) | €8.800 |
| Damiano | €1.587 (48 ore) | €3.213 (97 ore) | €4.800 |
| Nicolò | €793 (24 ore) | €1.607 (49 ore) | €2.400 |
| **Totale** | **€5.287** | **€10.713** | **€16.000** |

---

## 5. Dettaglio Spese Generali

Le spese generali sono calcolate come quota forfettaria del **15%** sui costi del personale in collaborazione (Co.Co.Co), ai sensi dell'Avviso. Nessuna fattura o documentazione richiesta.

| | Fase 1 | Fase 2 | Totale |
|---|---|---|---|
| Base di calcolo (Co.Co.Co) | €10.800 | €21.600 | €32.400 |
| Spese generali (15%) | **€1.620** | **€3.240** | **€4.860** |

Copertura forfettaria: commercialista, rendicontazione FESR, utenze, amministrazione.

---

## 6. Dettaglio Hardware

| Dispositivo | Prezzo acquisto | Mesi ammortamento progetto | Mesi vita utile | Quota ammessa (18/60) |
|-------------|----------------|--------------------------|-----------------|----------------------|
| Server GPU dedicato per LLM (inferenza on-premise h24) | €5.000 | 18 | 60 | **€1.500** |
| Display AR binoculare XREAL 1S (Micro-OLED, 1920×1200/occhio, 52° FoV — strumento di prototipazione UI/UX interfaccia clinica in AR) | €459 | 18 | 60 | **€138** |
| **Totale** | **€5.459** | | | **€1.638** |

- Acquisto previsto: **Fase 1** (mese 1), intero importo ammesso imputato a Fase 1
- Certificazioni: Energy Star + ESPR Ecodesign → **+5 punti premialità**
- Obbligo: i dispositivi rimangono presso la sede operativa VdA per 3 anni post-progetto
- Il server GPU riduce la dipendenza da API cloud esterne per l'inferenza LLM, abbassando i costi operativi a lungo termine

> **⚠️ NOTA INTERNA:** Modello esatto del dispositivo AR da confermare con Simon prima della presentazione.

---

## 7. Dettaglio Software / Licenze LLM

| Servizio | Tipologia | €/mese | Fase 1 (6m) | Fase 2 (12m) | Totale 18m |
|---------|-----------|--------|-------------|--------------|------------|
| Neon (database PostgreSQL hosted) | Infrastruttura cloud | €100 | €600 | €1.200 | €1.800 |
| Vercel (hosting + edge) | Infrastruttura cloud | €40 | €240 | €480 | €720 |
| OpenRouter (API LLM multi-modello) | Licenza LLM | €30 | €180 | €360 | €540 |
| AWS Bedrock (LLM compute) | Licenza LLM | €450 | €2.700 | €5.400 | €8.100 |
| Anthropic Claude Max (piano aziendale) | Licenza LLM | €100 | €600 | €1.200 | €1.800 |
| Google & servizi minori | Vari SaaS | €5 | €30 | €60 | €90 |
| Margine crescita (+10%) | Buffer | €75 | €450 | €900 | €1.350 |
| **Totale mensile stimato** | | **€800** | **€4.800** | **€9.600** | **€14.400** |

> Nota: i crediti AWS Activate e NVIDIA già ricevuti coprono parte dei costi nella fase iniziale, riducendo l'esborso effettivo nei primi mesi. Il budget è calcolato in scenario conservativo (crediti esauriti).

> Neon e Vercel sono al 100% imputabili al progetto: EMSy è un'azienda mono-prodotto e tali servizi supportano esclusivamente la piattaforma oggetto del Piano di sviluppo.

---

## 8. Dettaglio Assessment Tecnologico

| | |
|---|---|
| Fase | Fase 2 (mese 8–12) |
| Importo | €4.500 |
| Profilo esperto | Indipendente, ≥5 anni esperienza in technology assessment o gestione startup AI/medicale |
| Scostamento massimo senza autorizzazione | ±20% = ±€900 (range €3.600–€5.400) |
| Obbligo bando | Art. 12 Avviso — penalità -10% se ritardo, -25% se non eseguito |

---

## 9. Margine di Riserva

| | Fase 1 | Fase 2 | Totale |
|---|---|---|---|
| Margine di riserva | €2.630 | €3.170 | **€5.800** |

Il margine copre variazioni di costo entro il **20% per voce per fase** senza necessità di autorizzazione preventiva (Art. 10, comma 7 dell'Avviso). Da formalizzare con il commercialista per l'allocazione nella categoria ammessa del formulario SISPREG2014.

### Destinazione prevista del margine di riserva

| Voce | Fase | Importo stimato |
|------|------|----------------|
| Buffer per variazioni costi hardware/software Fase 1 | Fase 1 | €2.630 |
| Spese legali per certificazioni europee applicabili | Fase 2 | ~€1.000 |
| Consulenza Dott. Luca Carenzo (validazione clinica indipendente) | Fase 2 | ~€1.500 |
| Spese di ricerca medica — test prodotto con operatori durante eventi | Fase 2 | ~€670 |
| **Totale** | | **€5.800** |

---

## 10. Flusso di Cassa Stimato

| Mese | Entrate (FESR anticipi/SAL) | Uscite stimate | Saldo progressivo EMSy |
|------|----------------------------|----------------|----------------------|
| 1–3 | — | ~€4.500/mese | -€13.500 |
| 4–6 | **SAL Fase 1 ~€19.047** | ~€4.500/mese | +€1.047 |
| 7–12 | — | ~€4.800/mese | -€27.753 |
| 13–18 | **SAL Fase 2 ~€36.953** | ~€4.800/mese | +€9.200 |

> ⚠️ Il FESR rimborsa a rendicontazione (SAL). Nei mesi 1-3 e 7-12 EMSy sostiene le spese in anticipo. Il **finanziamento ponte Banca Sella/Alpifidi (€24.000)** copre il fabbisogno di liquidità nei periodi di attesa del rimborso.

---

## 11. Quadro Economico Finale

| | Importo |
|---|---|
| **Costo totale progetto** | €80.000 |
| **Contributo FESR (base 60%)** | €48.000 |
| **Bonus startup registry L.R. 14/2011 (+10%)** | €4.800 |
| **Contributo FESR totale (70%)** | **€52.800** |
| **Cofinanziamento EMSy (30%)** | **€27.200** |
| di cui coperto da finanziamento ponte | €24.000 |
| di cui da risorse proprie | €3.200 |

---

*Documento interno EMSy S.r.l. — Da condividere con il commercialista — Aggiornato giugno 2026*
