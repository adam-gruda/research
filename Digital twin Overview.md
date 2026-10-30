---
title: Digital Twin Overview
created: 2026-10-11
updated: 2026-10-12
tags:
  - digitalTwin
  - literature-synthesis
  - healthcare
---
# Digital Twin Overview

This note synthesizes the four DT4H review notes in `01_literature_review` and consolidates their follow-up readings and resources. **IBD and IQSEC2 are concurrent research directions with equal weight.** Relevance assessments below are research judgments, not findings demonstrated for those diseases unless explicitly stated.

> [!info] How to read this note
> **Review synthesis** comes from the existing notes and checked passages in their source PDFs. **Abstract summary** describes a follow-up publication at abstract level, without implying full-text appraisal. **Research value** is an inference about possible transfer to IBD or IQSEC2. **Provisional** means the abstract or resource documentation could not be verified. Original review summaries, selection comments, and source links are preserved. Reading and exploration task status is maintained in [[Reading Backlog]]; this overview uses ordinary bullets.

## Navigation

- [[Reading Backlog|Reading and exploration backlog]] — one task per item, with topic/source tags and no due dates.
- [[#Reviewed sources]]
- [[#Shared definition and minimum description]]
- [[#Agreement, disagreements, and boundaries]]
- [[#Architecture and application taxonomy]]
- [[#Research implications for IBD and IQSEC2]]
- [[#Glossary]]
- [[#Categorized follow-up publications]]
- [[#Projects, platforms, products, and consortia]]
- [[#Source corrections and claims to verify]]

## Reviewed sources

The letters below are source aliases used throughout the overview. Publication dates refer to the papers, not the dates of the review notes.

| Source | Existing note | Publication and contribution | Checked passages |
|---|---|---|---|
| A | [[Digital Twin for healthcare systems]] | Vallée (2023), mini-review. Patient care, prediction/prevention, operations, education; broad explanation of the DT system. [DOI](https://doi.org/10.3389/fdgth.2023.1253050). | [[fdgth-05-1253050.pdf#page=2\|PDF p. 2]]: definition, closed-loop updating, statistical/mechanistic approaches; pp. 3–5: applications and limitations. |
| B | [[Digital Twins in healthcare a comprehensive review and future directions]] | Khoshfekr Rudsari et al. (2025). Modeling across physiological levels; methods, implementations, limitations, opportunities. [DOI](https://doi.org/10.3389/fdgth.2025.1633539). | [[fdgth-07-1633539.pdf#page=2\|PDF p. 2]]: benefits/definition; pp. 17–20: methods and limitations; pp. 21–25: source identities. |
| C | [[Digital twins for health a scoping review]] | Katsoulakis et al. (2024). Explicit DT4H definition, three components, 5Is, application examples and consortium landscape. [DOI](https://doi.org/10.1038/s41746-024-01073-0). | [[s41746-024-01073-0 (1).pdf#page=2\|PDF p. 2]]: definition and taxonomy; pp. 6–8: personalization and challenges; pp. 9–11: references. |
| D | [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation]] | Giansanti and Cosenza (2026). Dynamic patient representation, six application dimensions, maturity, evidence consolidation, R1–R6 recommendations. [DOI](https://doi.org/10.3390/medsci14020330). | [[medsci-14-00330-v3.pdf#page=2\|PDF pp. 2–3]]: competing definitions; pp. 15–17: six dimensions; pp. 23–28: limitations and recommendations. |

These reviews overlap in primary sources and sometimes cite each other. Agreement among them is conceptual convergence; it is not four independent demonstrations of clinical effectiveness.

## Shared definition and minimum description

**Working synthesis:** a healthcare digital twin is an individualized computational representation of a real patient, biological subsystem, or healthcare process, coupled to observations of that counterpart and updated over time, with executable capabilities for monitoring, prediction, simulation, or decision support.

For a **patient DT system with clinical feedback**, model outputs inform a clinician/patient action and subsequent observations support checking and updating the representation. The feedback can involve human decisions; bidirectionality does not imply autonomous treatment. This formulation combines A–D, rather than reproducing a universally accepted definition. [[Digital Twin for healthcare systems|A]], [[Digital Twins in healthcare a comprehensive review and future directions|B]], [[Digital twins for health a scoping review|C]], [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]].

C's stricter formulation requires a physical entity, virtual representation, and connecting relationship, together with five qualities: individualized, interconnected, interactive, informative, and impactful. C discusses real-time bidirectional interaction. D also recognizes implementations with periodic updates, unidirectional flows, or incomplete clinical coupling. Report the actual properties of a proposed system instead of relying on its DT label. [[s41746-024-01073-0 (1).pdf#page=2|C, p. 2]]; [[medsci-14-00330-v3.pdf#page=2|D, pp. 2–3]].

A practical description for either disease should state: **what is twinned; the clinical question; available observations; update cadence; model outputs and uncertainty; whether outputs affect real care; and the stage of validation.** A broad “digital copy of a patient” description leaves these properties unresolved.

## Agreement, disagreements, and boundaries

| Issue | Shared position or common direction | Difference, tension, or correction | Consequence for this research |
|---|---|---|---|
| Representation versus a complete system | Patient-specific representation matters, but models, data, and connections operate together. | C explicitly rejects equating one ML algorithm with the whole DT. D emphasizes orchestration. A also describes closed-loop adaptation; its short replication definition alone understates this. | Distinguish a predictor, individualized model, and integrated DT system when describing the contribution. |
| Required coupling | Updating from real observations recurs across the reviews. | C's stated definition specifies bidirectional real-time impact. D's synthesis recognizes periodic updates and implementations with weaker or one-way coupling. This is a tension between strict criteria and broad survey coverage, not proof that D considers one-way coupling sufficient. | Specify update and feedback properties; avoid claiming a fully bidirectional system from retrospective forecasting alone. |
| Static and offline models | Simulation models contribute to the DT landscape. | C describes static, mirror/functional, shadow/self-adaptive, and intelligent twins, while its healthcare definition requires stronger coupling. D treats loosely coupled models as part of a heterogeneous maturity continuum. | Preserve the distinction between a taxonomy stage and the properties required by a strict definition. |
| “Digital shadow” terminology | Data acquisition and adaptation are important. | C uses “shadow twin” for a self-adaptive functional twin. This vocabulary should not be silently replaced with a universal one-way-data-flow definition from another taxonomy. | State the taxonomy source whenever using “shadow,” “mirror,” or “intelligent” twin. |
| Real time versus longitudinal time | The representation should evolve with the counterpart. | C emphasizes real-time links; D acknowledges continuous or periodic updating. Follow-up [[#^f068\|F068]] explicitly describes an offline twin. | Choose cadence according to the observed process and decisions. Updating after visits can be longitudinal without being continuous streaming. |
| Statistical versus mechanistic methods | A and B distinguish data-driven and mechanistic approaches; hybridization is a recurring opportunity. | None of these reviews establishes that every DT needs both, or that one approach always outperforms the other. C/D place more weight on the surrounding system. | Select models for the question and available data, then test the value of biological constraints and hybridization. |
| Multimodal versus more data | Heterogeneous observations may improve personalization. | D also cautions that aggregation alone does not create a twin and additional measurements can introduce noise. B's initial data-collection subsection is narrower than its broader discussion of omics. | Evaluate each modality's added value, temporal availability, and missingness; no requirement to collect everything. |
| Promise versus maturity | Monitoring, treatment exploration, prevention, and optimization are recurring proposed benefits. | A/B use strong transformation language; C/D emphasize early development, heterogeneous evidence, and incomplete validation. These are differences in emphasis, not necessarily contradictory effect estimates. | Keep computational performance, clinical usefulness, and prospectively demonstrated benefit separate. |
| Novelty versus evolution | DTs extend biomedical modeling toward evolving patient representations. | D presents continuity with older individualized modeling alongside a distinct paradigm of data–model integration. | State the concrete improvement over an existing model or workflow rather than claiming novelty from the DT name alone. |

Sources: [[Digital Twin for healthcare systems|A]], [[Digital Twins in healthcare a comprehensive review and future directions|B]], [[Digital twins for health a scoping review|C]], [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]], with the checked passages listed above. The clearest tensions concern **coupling requirements, update cadence, and maturity terminology**. D itself uses stronger continuous/bidirectional language in its operational definition (p. 3) and conceptual discussion (pp. 23–24), while acknowledging weaker implementations in its literature survey (p. 2). Survey inclusion should not be mistaken for endorsement of minimum criteria.

## Architecture and application taxonomy

### Components and responsibilities

A useful synthesis is a modular system: observations and data integration → individualized state/model representation → monitoring/prediction/simulation → interpretable outputs and decisions → subsequent observations and evaluation. Different models may serve different responsibilities; statistical learning and mechanistic modeling need not compete for a single role. [[Digital Twin for healthcare systems|A]], [[Digital Twins in healthcare a comprehensive review and future directions|B]], [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]].

**Updating a patient's state is different from retraining a model.** A system may assimilate a new observation or recalibrate patient parameters without changing population-model weights. Online learning is one possible implementation, not a defining requirement established by these reviews. This distinction is an implementation inference relevant to the stream-learning questions in your notes.

Classify a DT along independent axes rather than one combined label:

| Axis | Examples | Why it matters |
|---|---|---|
| Entity / hierarchical level | Cell, tissue, organ, patient, population, care process | A disease-process model may cover a small part of a person. |
| Function | Monitoring, prediction, simulation, optimization, education | Prediction of progression and simulation of treatment effects are different tasks. |
| Modeling approach | Statistical/ML, mechanistic, hybrid | Determines assumptions, data needs, interpretation, and computation. |
| Coupling | Static/offline, periodic, continuous; one-way or feedback | Makes the actual connection with observations and care explicit. |
| Evidence / maturity | Concept, prototype, retrospective evaluation, prospective evaluation, deployed system | Describes support for the intended use rather than model complexity alone. |

Sources: B and D; the hierarchical/application/maturity taxonomy is a follow-up in [[#^f079|F079]]. The coupling and evidence descriptions above are practical synthesis labels, not a new validated maturity scale.

### Six application dimensions from D

1. Continuous, multimodal, personalized patient representation.
2. Predictive modeling and simulation-based medicine, including in-silico trials.
3. Procedural, interventional, and imaging-guided support.
4. Integration into digital-health and AI ecosystems.
5. Implementation, scalability, regulatory alignment, and health-system integration.
6. **Domain diversification, human-centric design, and socio-technical transformation.** This sixth dimension was absent from the five-item list in the existing note and is restored here from the paper, pp. 15–17.

### Shared limitations and recommendations

- **Observations:** longitudinal data availability, measurement quality, missing data, biased inclusion, and temporal alignment across modalities. Sparse rare-disease cohorts make applicability especially uncertain. A–D.
- **Models:** complexity, computational burden, uncertain transfer across people or settings, and the limits of representing interacting biological processes. B–D.
- **Evaluation:** incomplete prospective and real-world validation, inconsistent reporting, and difficulty comparing systems with different intended uses. B/D.
- **Deployment:** integration with legacy systems, semantic interoperability, clinician/patient acceptance, workflow design, and infrastructure. A–D.
- **Governance:** privacy, security, consent, ownership, access, and equity. A–D. Legal/regulatory descriptions in these reviews are literature context, not an assessment of current obligations.

D's recommendations organize these into: **R1** broader disease/population coverage; **R2** standardization and reproducibility; **R3** integration of enabling technologies; **R4** ethical/governance frameworks; **R5** longitudinal, prospective, real-world evaluation; **R6** interoperability and scalability. [[medsci-14-00330-v3.pdf#page=27|D, pp. 27–28 recommendations]].

## Research implications for IBD and IQSEC2

These are proposed research questions, informed by the reviews and your notes. They are not clinical recommendations or demonstrated disease-specific results.

| Design question | IBD track | IQSEC2 track |
|---|---|---|
| What is the initial task? | Compare disease-state estimation, future activity forecasting, and time-to-flare prediction as distinct outcomes. | First establish an observable longitudinal phenotype and a feasible outcome; compare descriptive trajectories with predictive aims. |
| What individualizes the model? | Longitudinal clinical measurements, PROs, treatment history, and available molecular data; assess each modality. | Phenotypic and genetic information, developmental/time context, and other observations actually available in a relevant cohort. |
| What transfers from existing work? | Chronic inflammatory disease models, multiomic prediction, missing-modality methods, and causal frameworks are methodological leads. | Deep phenotyping, limited-data modeling, pediatric governance, and neurobiological integration are methodological leads. |
| What could justify a simulation claim? | Explicit intervention assumptions or a validated disease mechanism; observed treatment associations alone are insufficient. | A model whose represented mechanisms and outcomes can be connected to the condition; generic infant metabolism or dementia modeling alone does not establish this. |
| How should it be evaluated? | Patient-level and temporal evaluation, calibration, missingness/subgroup analysis, and comparison with practical baseline predictions. | Evaluation matched to cohort size and outcome reliability, explicit uncertainty, and cautious assessment of transfer from other populations. |
| What distinguishes the DT system? | How longitudinal observations update representation and whether predictions feed a measured decision loop. | How repeated observations refine representation and support a clearly bounded research or care decision. |

The [[PHD]] note provides the IBD prediction/interpretability direction. [[IBD Plexus]] and [[SFARI]] are existing dataset leads, not evidence that the required cohort or modalities are accessible. [[Arivale]] is relevant through [[#^f049|F049]]; that paper concerns **type 2 diabetes-related trajectories**, not type 1 diabetes.

### Questions retained from the review notes

- How can location/environment observations be measured at a useful resolution, with meaningful exposure definitions rather than location alone? C.
- How much history is needed, when can old observations be aggregated, and what information would aggregation discard? D.
- How should missing observations and changing measurement practices affect state estimation, prediction, and uncertainty? B/C; research synthesis.
- Can omics and EHR observations constrain a mechanistic representation, and does it improve performance or plausibility over statistical baselines? B.
- How does noisy incoming data affect a model? Stream learning is a candidate approach; it does not automatically solve signal/noise, drift, or measurement validity. D note; research hypothesis.
- Are cloud computation and retraining practically affordable for the intended scale and latency? The note's view that retraining may be manageable is a hypothesis to measure, not a conclusion of B.
- Could patient simulation support healthcare education? Retain as a parallel application interest, with [[#^f071|F071]]/[[#^f072|F072]]/[[#^f028|F028]]; it has different evaluation targets from disease forecasting.

## Glossary

Definitions are concise paraphrases. Where vocabulary differs, the source-specific meaning is retained. “Synthesis” identifies an operational distinction used in this overview.

| Term | Short definition | Source / boundary |
|---|---|---|
| Digital twin (DT) | An individualized computational representation coupled to an identified real counterpart and updated from its observations. | Working synthesis A–D; minimum criteria differ. |
| DT4H / health digital twin | A DT applied to a health-related biological entity, person, or healthcare process. | A–D; C's explicit healthcare definition centers a person. |
| Digital twin system (DTS) | The representation together with observation, updating, analytic, simulation, and decision-support components. | D, pp. 2–3, 24; an algorithm is one component. |
| Virtual human twin | A digital representation of health/disease across levels of biological organization. | D, p. 3; see VHT initiative [[#^f080\|F080]]. |
| Patient-specific model | A computational model individualized with patient characteristics or observations. | B/D; personalization alone does not establish ongoing coupling. |
| Virtual / in-silico patient | A computational subject used to simulate physiology, disease, or interventions. | B–D; may represent a hypothetical rather than a paired real patient. |
| Digital human / virtual replica | Broad representation labels whose level, purpose, and update properties need specification. | D note; not automatic synonyms for a complete DT system. |
| Physical counterpart | The identifiable real person, subsystem, device, or process represented. | A/C. |
| Bidirectional feedback | Observations update the representation; its outputs inform actions affecting the counterpart. | C/D; clinical decisions may remain human-mediated. |
| Digital thread | Traceable information connecting a counterpart's observations and evolution across time/lifecycle. | C, p. 2; [[#^f018\|F018]] provides an industrial implementation context. |
| Static twin | A representation with static properties. | C's taxonomy, p. 2. |
| Mirror / functional twin | A static representation extended with dynamic behavior capabilities. | C's taxonomy, p. 2. |
| Shadow / self-adaptive twin | A functional twin that acquires observations and updates its model. | C's taxonomy, p. 2; taxonomy-specific, not a universal flow-direction definition. |
| Intelligent / cognitive / extended twin | A self-adaptive twin with learning/reasoning/action capabilities and potential interaction with other twins. | C, p. 2; degrees of autonomy differ. |
| 5Is | Individualized, interconnected, interactive, informative, impactful. | C's stated DT criteria. |
| Data-driven model | A model learning statistical relationships from observations. | A/B. |
| Mechanistic model | A model expressing explicit domain relationships or processes to explain or simulate behavior. | A/B; includes physiological/biological models, not only mechanics. |
| Hybrid model | A combination of learned relationships and explicit mechanistic structure or constraints. | B; [[#^f021\|F021]]/[[#^f032\|F032]]/[[#^f044\|F044]] give examples or perspectives. |
| Multimodal data | Different forms of observation, such as clinical records, imaging, omics, and behavior. | B/C/D. |
| Multiscale modeling | Representation of processes across levels, such as molecular, cellular, organ, and patient. | B/C/D; different from merely combining data types. |
| Deep phenotyping | Detailed, precise characterization of an individual's phenotypic features. | C; [[#^f094\|F094]]'s definition is the follow-up source. |
| Digital phenotyping | Characterizing behavior or health from digitally captured observations. | C; [[#^f095\|F095]]/[[#^f096\|F096]] are follow-up leads. |
| Digitosome | The collection of digital data generated about/by an individual. | C; broad data concept, not an executable model. |
| Comprehensive genomic profiling (CGP) | Broad genomic characterization used to identify potentially relevant alterations and treatment targets. | C/[[#^f097\|F097]] oncology context; distinct from IQSEC2-specific genetic assessment. |
| Multiomics | Combining observations from several molecular layers, such as proteomics and metabolomics. | B; [[#^f049\|F049]]. |
| Knowledge graph | Entities and typed relationships organizing biomedical knowledge in a graph. | B/[[#^f049\|F049]]; a graph connection does not alone establish causality. |
| QSP | Quantitative systems pharmacology: mechanistic modeling connecting biological systems, drug action, and response. | B/[[#^f110\|F110]]. |
| Virtual population (VPOP) | A collection of simulated subjects representing relevant parameter variability. | B/[[#^f110\|F110]]; different from longitudinal twins of observed individuals. |
| In-silico trial | Computational evaluation of an intervention or product in simulated subjects/systems. | B/C; credibility and intended use require evaluation. |
| Counterfactual prediction | Estimating what would occur under an alternative intervention, with explicit causal assumptions. | Follow-ups [[#^f037\|F037]]/[[#^f038\|F038]]; prediction alone is insufficient. |
| Longitudinal updating | Incorporating observations over time to revise an individual's representation. | A–D; may be periodic. |
| State update versus model learning | Revising a patient's current state/parameters versus changing the learned model itself. | Research synthesis; distinguish when designing stream learning. |
| FHIR | Fast Healthcare Interoperability Resources: a standard for structuring and exchanging health information. | B/[[#^f074\|F074]]; technical exchange does not guarantee all semantic alignment. |
| PRO | Patient-reported outcome: an observation reported directly by the patient about their health or experience. | D note; used here as a proposed data source. |
| Model credibility | Evidence that a model is sufficiently trustworthy for its stated use. | Follow-up [[#^f078\|F078]]; separate from a single accuracy score. |

## Categorized follow-up publications

Each item appears once under its primary category. Stable IDs support linking within this long note and can remain when dedicated paper notes are added. Relevance is described independently for **IBD** and **IQSEC2**, with no disease-based priority ranking. An abstract-based assessment remains a screening result, not a full study-quality assessment.

**Provenance:** A/B/C/D link to the source notes above. Original heading/context is retained, especially where the retrieved publication differs from the reason it was saved. Alternate URLs are retained for merged records when they help recover the original reference. Website descriptions are assessed separately in the resource section. Abstracts were retrieved from publishers, author repositories, Europe PMC/Crossref metadata, or reconstructed from OpenAlex abstract indexes; the latter are labeled explicitly. These are summaries of the authors' text, not evaluations generated by those indexes.

Inventory: **95 publication entries** (including review C retained as an already-reviewed reference) and **12 resource entries**. All 113 original task lines are represented. Of the publication entries, **1 have provisional descriptions** because no usable abstract was obtained; [[#^f016|F016]]/[[#^f072|F072]] are summarized from primary article text and [[#^f096|F096]] from an indexed journal summary. Sources were checked on 10–11 October 2026.

| Publication category | Entries |
|---|---:|
| [[#Foundations and classification]] | 13 |
| [[#Longitudinal disease modeling and monitoring]] | 8 |
| [[#Multimodal data, omics, and phenotyping]] | 7 |
| [[#Mechanistic and hybrid modeling]] | 11 |
| [[#Treatment effects, causal inference, and perturbations]] | 8 |
| [[#Learning with limited data and synthetic cohorts]] | 5 |
| [[#Data acquisition and interoperability]] | 12 |
| [[#Validation and model credibility]] | 1 |
| [[#Health-system implementation and governance]] | 5 |
| [[#Patient-centered care and evidence]] | 12 |
| [[#Other applications: procedures, education, and rehabilitation]] | 5 |
| [[#Transferable methods from industry]] | 7 |
| [[#Already reviewed source retained from follow-ups]] | 1 |

### Foundations and classification

- **[Digital Twins in Healthcare: Is It the Beginning of a New Era of Evidence-Based Medicine? A Critical Review](https://doi.org/10.3390/jpm12081255)** · **[[#^f001|F001]]**

  **Abstract summary:** Reviews DT applications in precision medicine, trial design, and hospital operations, alongside technical, regulatory, and ethical barriers.

  **Research value (inference):** **IBD:** Framing disease-model ambitions and deployment barriers. **IQSEC2:** Framing rare-disease ambitions and constraints.

  **Boundary / reading question:** A critical review, rather than a wearable validation study.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Wearables:). **Basis:** abstract. ^f001

- **[Digital Twins: From Personalised Medicine to Precision Public Health](https://doi.org/10.3390/jpm11080745)** · **[[#^f006|F006]]**

  **Abstract summary:** Reviews dynamic bidirectional twins from individualized medicine to public health, with applications and ethical/technical challenges.

  **Research value (inference):** **IBD:** Connecting individual trajectories with population context. **IQSEC2:** Connecting individualized representation with population knowledge.

  **Boundary / reading question:** Preserves both multimodal and chronic-monitoring selection contexts.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Multimodal aspect:; cue: multimodal gives comprehensive view / 'Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2075-4426/11/8/745). ^f006

- **[Digital twin in healthcare: Recent updates and challenges](https://doi.org/10.1177/20552076221149651)** · **[[#^f007|F007]]**

  **Abstract summary:** Reviews medical DT examples, potential applications, and remaining challenges in personalized diagnosis and treatment.

  **Research value (inference):** **IBD:** A reference map for disease-specific implementations. **IQSEC2:** A reference map for neurological and personalized modeling.

  **Boundary / reading question:** Also saved as an initial-DT-idea source; consolidate those contexts.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Personalized treatments plans: / coordinated care:; cue: Initial DT idea). **Basis:** abstract. Saved link: [original 1](https://journals.sagepub.com/doi/10.1177/20552076221149651). ^f007

- **[The Digital Twin in Medicine: A Key to the Future of Healthcare?](https://doi.org/10.3389/fmed.2022.907066)** · **[[#^f008|F008]]**

  **Abstract summary:** Discusses medical DT potential and limitations around data acquisition, fusion, and simulation using AI and IoT.

  **Research value (inference):** **IBD:** Defining what a disease-management framework must actually implement. **IQSEC2:** Defining achievable scope with limited patient observations.

  **Boundary / reading question:** A perspective on future capability rather than proof of outcome improvement.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Personalized treatments plans: / coordinated care:; cue: simulation of disease progress). **Basis:** abstract. Saved link: [original 1](https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2022.907066/full). ^f008

- **[Exploring the revolution in healthcare systems through the applications of digital twin technology](https://doi.org/10.1016/j.bmt.2023.02.001)** · **[[#^f009|F009]]**

  **Abstract summary:** Reviews healthcare DT needs, enabling technologies, applications, and patient-centered services using IoT observations and AI models.

  **Research value (inference):** **IBD:** Background lead on applications and service design. **IQSEC2:** Background lead on applications and service design.

  **Boundary / reading question:** The abstract describes proposed capabilities; the saved readmission percentage is still unverified.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Personalized treatments plans: / 'Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'); [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Digital twin could reduce hospital readmission by up to 25% for certain chronic diseases). **Basis:** indexed abstract (OpenAlex). Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S2949723X23000065). ^f009

- **[Impactful Digital Twin in the Healthcare Revolution](https://doi.org/10.3390/bdcc6030083)** · **[[#^f017|F017]]**

  **Abstract summary:** Reviews healthcare DT concepts and life-stage functions and proposes digital twinning as a healthcare service.

  **Research value (inference):** **IBD:** Scoping representations and service architecture. **IQSEC2:** Scoping personalized representations across life stages.

  **Boundary / reading question:** Conceptual review; does not establish coordinated-care benefits by experiment.

  **Origin:** [[Digital Twin for healthcare systems|A]] ('Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'; cue: patient centered care / coordinated care:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2504-2289/6/3/83). ^f017

- **[Digital twins to personalize medicine](https://doi.org/10.1186/s13073-019-0701-3)** · **[[#^f029|F029]]**

  **Abstract summary:** Proposes high-resolution patient models that can be computationally exposed to candidate drugs to support personalization.

  **Research value (inference):** **IBD:** Conceptual foundation for individualized disease models. **IQSEC2:** Conceptual foundation for individualized rare-disease models.

  **Boundary / reading question:** A proposal, not evidence that thousands of therapies can already be safely personalized.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Patient-specific modeling: / Methods in building DT:; cue: Preventive aspect of DT4H). **Basis:** abstract. Saved link: [original 1](https://link.springer.com/article/10.1186/s13073-019-0701-3). ^f029

- **[Machine Learning–Enabled Digital Twins for Diagnostic and Therapeutic Purposes](https://doi.org/10.1002/9781394287420.ch5)** · **[[#^f030|F030]]**

  **Abstract summary:** Reviews how ML and diverse patient observations can augment digital representations for personalized diagnostics, risk assessment, and therapy decision support.

  **Research value (inference):** **IBD:** Method overview lead for patient-specific prediction. **IQSEC2:** Method overview lead for individualized prediction.

  **Boundary / reading question:** A chapter overview of proposed capabilities, not a new clinical-validation experiment.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Patient-specific modeling:). **Basis:** publisher abstract (chapter Summary). [Checked source](https://onlinelibrary.wiley.com/doi/10.1002/9781394287420.ch5). Saved link: [original 1](https://onlinelibrary.wiley.com/doi/10.1002/9781394287420.ch5). ^f030

- **[Digital Twins: The New Frontier for Personalized Medicine?](https://doi.org/10.3390/app13137940)** · **[[#^f031|F031]]**

  **Abstract summary:** Reviews patient and healthcare-institution twins, multiomics, procedural uses, and practical data-security/interoperability challenges.

  **Research value (inference):** **IBD:** Broad application and integration reference. **IQSEC2:** Broad personalized-modeling reference.

  **Boundary / reading question:** Potential capabilities are reviewed, not jointly demonstrated by one implementation.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Patient-specific modeling:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2076-3417/13/13/7940). ^f031

- **[Personal Digital Twin: A Close Look into the Present and a Step towards the Future of Personalised Healthcare Industry](https://doi.org/10.3390/s22155918)** · **[[#^f040|F040]]**

  **Abstract summary:** Reviews personal DTs and proposes a framework combining DT, AI, and blockchain, with nutrition and chronic-care use cases.

  **Research value (inference):** **IBD:** A personal longitudinal-care reference architecture. **IQSEC2:** A personal-care reference architecture and boundaries.

  **Boundary / reading question:** Conceptual framework; blockchain is one proposed technology, not an established requirement.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Longitudinal health management); [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: extended DT, a system, which communicate with each other and are self-learning / Key takeoffs; cue: Personal digital twin). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/1424-8220/22/15/5918). ^f040

- **[Digital twin in healthcare: Classification and typology of models based on hierarchy, application, and maturity](https://doi.org/10.1016/j.iot.2024.101379)** · **[[#^f079|F079]]**

  **Abstract summary:** Reviews healthcare DTs using hierarchical level, application purpose, and maturity/sophistication to compare models and guide development.

  **Research value (inference):** **IBD:** Classifying the proposed system's scope and maturity. **IQSEC2:** Classifying the proposed system's scope and maturity.

  **Boundary / reading question:** The title is “typology,” not topology; abstract checked at the publisher.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: Classification and topology od DT). **Basis:** publisher abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S2542660524003202). ^f079

- **[Digital Transformation Revolution with Digital Twin Technology](https://doi.org/10.1109/ISMSIT50672.2020.9254288)** · **[[#^f093|F093]]**

  **Abstract summary:** Discusses current applications and future opportunities for DTs across healthcare, industry, and smart-city management.

  **Research value (inference):** **IBD:** Cross-domain DT background and architecture lead. **IQSEC2:** Cross-domain DT background and architecture lead.

  **Boundary / reading question:** Saved for drug-manufacturing optimization; that specific effect is not established in the abstract.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT optimize drug manufatcturing process). **Basis:** author manuscript abstract. [Checked source](https://www.researchgate.net/publication/347041305_Digital_Transformation_Revolution_with_Digital_Twin_Technology). Saved link: [original 1](https://ieeexplore.ieee.org/document/9254288). ^f093

- **[Digital twins for well-being: an overview](https://doi.org/10.12688/digitaltwin.17475.2)** · **[[#^f109|F109]]**

  **Abstract summary:** Reviews well-being DT definitions, architectures, framework evolution, challenges, and design requirements.

  **Research value (inference):** **IBD:** An architecture/requirements checklist for longitudinal wellness context. **IQSEC2:** An architecture/requirements checklist for individualized support.

  **Boundary / reading question:** Version .2 abstract checked; general overview rather than disease-specific validation.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT for wellbeing reveiw). **Basis:** publisher abstract. Saved link: [original 1](https://www.tandfonline.com/doi/full/10.12688/digitaltwin.17475.2). ^f109

### Longitudinal disease modeling and monitoring

- **[Digital Twins for Multiple Sclerosis](https://doi.org/10.3389/fimmu.2021.669811)** · **[[#^f005|F005]]**

  **Abstract summary:** Proposes integrating clinical, molecular, patient, and life-context data into individualized DTs for multiple-sclerosis management and shared decisions.

  **Research value (inference):** **IBD:** An inflammatory chronic-disease framework to compare with IBD. **IQSEC2:** A neurological-care framework with possible multimodal design transfer.

  **Boundary / reading question:** A conceptual review; anticipated benefits are not a clinical effectiveness trial.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Multimodal aspect: / Advantege DT therapy over traditional:). **Basis:** abstract. Saved link: [original 1](https://www.frontiersin.org/journals/immunology/articles/10.3389/fimmu.2021.669811/full). ^f005

- **[A Digital Twins Machine Learning Model for Forecasting Disease Progression in Stroke Patients](https://doi.org/10.3390/app11125576)** · **[[#^f023|F023]]**

  **Abstract summary:** Uses a variational-autoencoder twin model to generate stroke-related clinical trajectories and compares simulated and held-out real data distributions.

  **Research value (inference):** **IBD:** Trajectory generation and distributional evaluation ideas. **IQSEC2:** Trajectory-generation methods worth testing under rare-disease data limits.

  **Boundary / reading question:** Distributional similarity does not establish valid intervention effects.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: disease forecast); [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2076-3417/11/12/5576). ^f023

- **[The health digital twin to tackle cardiovascular disease-a review of an emerging interdisciplinary field](https://doi.org/10.1038/s41746-022-00640-7)** · **[[#^f025|F025]]**

  **Abstract summary:** Maps cardiovascular DT literature, commercial activity, and patents; many applications remain numerical simulations with barriers to real-time deployment.

  **Research value (inference):** **IBD:** Comparing maturity and coupling in disease-specific twins. **IQSEC2:** Comparing maturity and coupling in neurological/rare-disease proposals.

  **Boundary / reading question:** Merged publisher and DOI links; saved for visual presentation and population triage, which are not the abstract's central claims.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: Population based triage (?) / coordinated care:; cue: visual aspect of DT4H). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41746-022-00640-7). ^f025

- **[Tracing and Forecasting Metabolic Indices of Cancer Patients Using Patient-Specific Deep Learning Models](https://doi.org/10.3390/jpm12050742)** · **[[#^f033|F033]]**

  **Abstract summary:** Builds LSTM-based patient models of metabolic-panel trajectories during cancer care and personalizes a master model through transfer learning.

  **Research value (inference):** **IBD:** Patient-specific trajectory prediction and calibration methods. **IQSEC2:** Transfer-learning design for small individual time series.

  **Boundary / reading question:** Small cancer examples require careful validation before disease transfer.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Patient-specific modeling:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2075-4426/12/5/742). ^f033

- **[Establishing the longitudinal hemodynamic mapping framework for wearable-driven coronary digital twins](https://doi.org/10.1038/s41746-024-01216-3)** · **[[#^f048|F048]]**

  **Abstract summary:** Develops a wearable-driven coronary hemodynamics framework using scalable simulation and clustering to reconstruct long-term maps.

  **Research value (inference):** **IBD:** Reducing redundant computation while retaining longitudinal patterns. **IQSEC2:** Ideas for efficient representation of repeated observations.

  **Boundary / reading question:** Saved under regression interpretability; it is primarily computational hemodynamic mapping.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Regression models fo interpretability in DT:). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41746-024-01216-3). ^f048

- **[Machine-Learning-Based Digital Twin System for Predicting the Progression of Prostate Cancer](https://doi.org/10.3390/app12168156)** · **[[#^f050|F050]]**

  **Abstract summary:** Uses clinical-data-warehouse information from prostate-cancer patients to predict pathology and biochemical recurrence in a DT/CDSS framework.

  **Research value (inference):** **IBD:** A comparator for progression-model design and reporting. **IQSEC2:** A comparator for patient-outcome-model design and reporting.

  **Boundary / reading question:** Accuracy alone does not establish calibration, utility, or feedback coupling.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Regression models fo interpretability in DT:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2076-3417/12/16/8156). ^f050

- **[Deep Learning-Empowered Clinical Big Data Analytics in Healthcare Digital Twins](https://doi.org/10.1109/tcbb.2023.3252668)** · **[[#^f052|F052]]**

  **Abstract summary:** Combines clinical data acquisition, IoT visualization, and improved random-forest classification in a healthcare DT platform with sepsis examples.

  **Research value (inference):** **IBD:** Feature-selection and clinical-data-platform methods. **IQSEC2:** Feature-selection and clinical-data-platform methods.

  **Boundary / reading question:** The title emphasizes deep learning, while the abstract also describes random forests; verify the actual implementation.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** abstract. Saved link: [original 1](https://dl.acm.org/doi/abs/10.1109/TCBB.2023.3252668). ^f052

- **[Digital twins to enable better precision and personalized dementia care](https://doi.org/10.1093/jamiaopen/ooac072)** · **[[#^f087|F087]]**

  **Abstract summary:** A perspective develops a healthcare decision-support twin concept for personalized dementia care.

  **Research value (inference):** **IBD:** Longitudinal personalized-care framework comparison. **IQSEC2:** A neurological longitudinal-care comparison.

  **Boundary / reading question:** A perspective extrapolated from manufacturing, not a validated IQSEC2 or dementia predictor.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT for dementia). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/35992534). ^f087

### Multimodal data, omics, and phenotyping

- **[A framework towards digital twins for type 2 diabetes](https://doi.org/10.3389/fdgth.2024.1336050)** · **[[#^f049|F049]]**

  **Abstract summary:** Presents a type-2-diabetes framework combining multiomic clinical prediction, knowledge graphs, and proposed mechanistic modeling.

  **Research value (inference):** **IBD:** A close methodological lead for interpretable clinical/molecular trajectory models. **IQSEC2:** A lead for integrating phenotypic/molecular knowledge under data constraints.

  **Boundary / reading question:** The saved paper focuses chiefly on ML and knowledge-graph components; a complete mechanistic feedback system is not demonstrated.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Regression models fo interpretability in DT: / Methods in building DT:; cue: For type 2 diabetes, comprehensive frameworks combining ML, multiomic data and knowledge graphs have enhanced predictive accuracy for disease trajectories and treatment responses: ⏫ performed on [[Arivale]] dataset and SPOKE knowledge graph). **Basis:** abstract and saved full text. Saved links: [original 1](https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2024.1336050/full), [original 2](https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2024.1336050/full). ^f049

- **[A novel computational framework for integrating multidimensional data to enhance accuracy in predicting the prognosis of colorectal cancer](https://doi.org/10.1002/mef2.27)** · **[[#^f075|F075]]**

  **Abstract summary:** Develops random non-negative matrix factorization to train on multidimensional colorectal-cancer data while allowing survival prediction from a single modality.

  **Research value (inference):** **IBD:** A useful lead on missing modalities and time-to-event prediction. **IQSEC2:** A useful lead on missing modalities under limited data.

  **Boundary / reading question:** Saved as general flare-hazard survival analysis; its actual contribution is a specific oncology integration framework.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Survival analysis, estimates hazard functions for time-to-event data while handling censored observations: (eg. flare hazard estimation in IBD)). **Basis:** abstract. Saved link: [original 1](https://onlinelibrary.wiley.com/doi/10.1002/mef2.27). ^f075

- **[A Systematic Review on Biomarker Identification for Cancer Diagnosis and Prognosis in Multi-omics: From Computational Needs to Machine Learning and Deep Learning](https://doi.org/10.1007/s11831-022-09821-9)** · **[[#^f076|F076]]**

  **Abstract summary:** Reviews ML/DL, feature selection, tools, and challenges for identifying cancer biomarkers from single- and multiomic data.

  **Research value (inference):** **IBD:** Feature-selection and biomarker-method evaluation. **IQSEC2:** Feature-selection and biomarker-method evaluation.

  **Boundary / reading question:** Cancer-focused review; disease-specific biomarker transfer is not established.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Review about biomarker identification using ML and DL). **Basis:** publisher abstract. Saved link: [original 1](https://link.springer.com/article/10.1007/s11831-022-09821-9). ^f076

- **[Scalable and accurate deep learning with electronic health records](https://doi.org/10.1038/s41746-018-0029-1)** · **[[#^f081|F081]]**

  **Abstract summary:** Represents sequential raw EHRs using FHIR and evaluates deep learning for several inpatient outcomes at two medical centers.

  **Research value (inference):** **IBD:** A reference for longitudinal EHR representation and temporal prediction. **IQSEC2:** A representation reference whose large-data assumptions may not transfer.

  **Boundary / reading question:** Prediction from EHRs is a component lead, not a complete DT by itself.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: Deep learning on EHR). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/31304302). ^f081

- **[Deep phenotyping for precision medicine](https://doi.org/10.1002/humu.22080)** · **[[#^f094|F094]]**

  **Abstract summary:** Defines precise, comprehensive phenotyping and reviews computational standards linking phenotype, genomic variation, and clinical information.

  **Research value (inference):** **IBD:** Improving outcome/phenotype definitions and data semantics. **IQSEC2:** A particularly relevant method lead for detailed rare-disease phenotypes.

  **Boundary / reading question:** Foundational precision-medicine paper; not a condition-specific DT implementation.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Deep phenotyping). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/22504886). ^f094

- **[Deep Digital Phenotyping and Digital Twins for Precision Health: Time to Dig Deeper](https://doi.org/10.2196/16770)** · **[[#^f095|F095]]**

  **Abstract summary:** A viewpoint argues for combining real-world digital observations with clinical and omics information for precision health.

  **Research value (inference):** **IBD:** Designing multimodal longitudinal observations. **IQSEC2:** Designing multimodal phenotype observations.

  **Boundary / reading question:** A viewpoint on data collection and personalization, not a clinical effectiveness study.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Deep phenotyping). **Basis:** abstract. Saved link: [original 1](https://www.jmir.org/2020/3/e16770). ^f095

- **[Digital Phenotyping: Technology for a New Science of Behavior](https://doi.org/10.1001/jama.2017.11295)** · **[[#^f096|F096]]**

  **Document summary:** A viewpoint discusses smartphone sensor, keyboard, voice, and speech observations as possible digital phenotypes for individualized behavioral care.

  **Research value (inference):** **IBD:** A behavioral-observation concept lead. **IQSEC2:** A behavioral/developmental observation concept lead.

  **Boundary / reading question:** Indexed journal summary rather than a methods/results abstract; phenotype validity requires further reading.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Deep phenotyping). **Basis:** indexed summary (OpenAlex). Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/28973224). ^f096

### Mechanistic and hybrid modeling

- **[The 'Digital Twin' to enable the vision of precision cardiology](https://doi.org/10.1093/eurheartj/ehaa159)** · **[[#^f021|F021]]**

  **Abstract summary:** A position paper argues for synergy between mechanistic and statistical patient models to enable precision cardiology.

  **Research value (inference):** **IBD:** A concrete conceptual guide for combining predictive and biological models. **IQSEC2:** A guide to choosing complementary models for individualized representation.

  **Boundary / reading question:** Cardiac evidence and assumptions need separate justification for either disease.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: That idea about categorization of DT technologies); [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: digital twin for precision cardiac case example). **Basis:** abstract. Saved link: [original 1](https://academic.oup.com/eurheartj/article/41/48/4556/5775673). ^f021

- **[Precision medicine in human heart modeling : Perspectives, challenges, and opportunities](https://doi.org/10.1007/s10237-021-01421-z)** · **[[#^f022|F022]]**

  **Abstract summary:** Reviews individualized heart modeling and argues for creating personalized models from population libraries instead of necessarily simulating an entire high-resolution heart.

  **Research value (inference):** **IBD:** Useful precedent for bounded models tailored to a clinical question. **IQSEC2:** Useful precedent for selecting feasible scope under limited information.

  **Boundary / reading question:** Mechanistic cardiac applications, not a universal whole-body requirement.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: That idea about categorization of DT technologies). **Basis:** abstract. Saved link: [original 1](https://link.springer.com/article/10.1007/s10237-021-01421-z). ^f022

- **[Towards systems immunology of critical illness at scale: from single cell 'omics to digital twins](https://doi.org/10.1016/j.it.2023.03.004)** · **[[#^f032|F032]]**

  **Abstract summary:** Discusses integrating single-cell omics with parsimonious mathematical models of inflammation and immunity toward multiorgan twins.

  **Research value (inference):** **IBD:** A strong methodological lead for inflammatory disease modeling. **IQSEC2:** A possible approach to biological representation if relevant mechanisms/data exist.

  **Boundary / reading question:** Critical-illness perspective; not direct evidence for IBD or IQSEC2.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Patient-specific modeling:). **Basis:** abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S1471490623000480). ^f032

- **[CellBox: Interpretable Machine Learning for Perturbation Biology with Application to the Design of Cancer Combination Therapy](https://doi.org/10.1016/j.cels.2020.11.013)** · **[[#^f044|F044]]**

  **Abstract summary:** Combines explicit cellular dynamics with ML to fit drug-perturbation responses and obtain interpretable network models in a melanoma cell line.

  **Research value (inference):** **IBD:** Hybrid modeling of inflammatory cellular responses, as a transfer hypothesis. **IQSEC2:** Hybrid modeling of biological responses, as a transfer hypothesis.

  **Boundary / reading question:** Cell-line response evidence; clinical/patient-level transfer remains untested here.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S2405471220304646). ^f044

- **[Human <i>In Silico</i> Drug Trials Demonstrate Higher Accuracy than Animal Models in Predicting Clinical Pro-Arrhythmic Cardiotoxicity](https://doi.org/10.3389/fphys.2017.00668)** · **[[#^f045|F045]]**

  **Abstract summary:** Evaluates human cardiac action-potential model populations for pro-arrhythmic drug risk against experimental/reference evidence.

  **Research value (inference):** **IBD:** A precedent for virtual-population validation. **IQSEC2:** A precedent for mechanistic safety-model validation.

  **Boundary / reading question:** Comparison with animal models is specific to cardiac safety, not all DT applications.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** abstract. Saved link: [original 1](https://www.frontiersin.org/journals/physiology/articles/10.3389/fphys.2017.00668/full). ^f045

- **[HPC Framework for Performing in Silico Trials Using a 3D Virtual Human Cardiac Population as Means to Assess Drug-Induced Arrhythmic Risk](https://doi.org/10.1007/978-1-0716-3449-3_14)** · **[[#^f047|F047]]**

  **Abstract summary:** Describes high-performance 3D cardiac virtual-population simulations for drug-induced arrhythmic risk with sex-specific characteristics and experimental checks.

  **Research value (inference):** **IBD:** Virtual-population and model-credibility design. **IQSEC2:** Virtual-population and biological-variability design.

  **Boundary / reading question:** Saved under regression interpretability; the paper concerns cardiac simulation and in-silico trials.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Regression models fo interpretability in DT:). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/37702946). ^f047

- **[Control of medical digital twins with artificial neural networks](https://doi.org/10.1098/rsta.2024.0228)** · **[[#^f059|F059]]**

  **Abstract summary:** Tests dynamics-informed neural controllers for agent-based biomedical models and quantifies uncertainty in stochastic model/control parameters.

  **Research value (inference):** **IBD:** A lead on controlling simulated immune processes. **IQSEC2:** A lead on controlling stochastic biological models if disease mechanisms support it.

  **Boundary / reading question:** Simulation/control methods; no disease-specific clinical intervention is established.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Neural Networks for high dimensional healthcare data:). **Basis:** abstract. Saved link: [original 1](https://royalsocietypublishing.org/rsta/article/383/2292/20240228/108445/Control-of-medical-digital-twins-with-artificial). ^f059

- **[Digital twin predicting diet response before and after long-term fasting](https://doi.org/10.1371/journal.pcbi.1010469)** · **[[#^f068|F068]]**

  **Abstract summary:** Develops a mechanistic diet/fasting model integrating clinical studies and predicting independent data, with individual adaptation from historical metabolite observations.

  **Research value (inference):** **IBD:** A model-integration example for nutrition-related questions if justified. **IQSEC2:** A personalization example if relevant metabolic questions/data exist.

  **Boundary / reading question:** The abstract explicitly describes an offline twin; preserve this boundary case.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: DT checking before and after fasting metabolic responses). **Basis:** abstract. Saved link: [original 1](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1010469). ^f068

- **[Personalized metabolic whole-body models for newborns and infants predict growth and biomarkers of inherited metabolic diseases](https://doi.org/10.1016/j.cmet.2024.05.006)** · **[[#^f069|F069]]**

  **Abstract summary:** Develops sex-specific infant whole-body metabolic models, personalizes them with metabolome/weight observations, and predicts inherited metabolic-disease biomarkers and responses.

  **Research value (inference):** **IBD:** An age-dependent whole-body modeling example, if pediatric metabolism is relevant. **IQSEC2:** A pediatric personalization example to investigate for methodological transfer.

  **Boundary / reading question:** Inherited metabolic disease is not IQSEC2; no IQSEC2 applicability is demonstrated.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Sex specific, personalized metabolic whole-body models (WBMs) have been developed for newborns and infants (IQSEC2 application maybe)). **Basis:** abstract. Saved link: [original 1](https://linkinghub.elsevier.com/retrieve/pii/S1550413124001827). ^f069

- **[Impact of genetic dynamics and single-cell heterogeneity on development of nonstandard personalized medicine strategies for cancer](https://doi.org/10.1073/pnas.1203559109)** · **[[#^f070|F070]]**

  **Abstract summary:** Uses a mathematical cancer-therapy model with genetic evolution and single-cell heterogeneity to compare simulated treatment strategies.

  **Research value (inference):** **IBD:** An example of modeling changing heterogeneity and future states. **IQSEC2:** An example of explicit biological dynamics rather than static association.

  **Boundary / reading question:** Cancer evolution differs from germline rare-disease mechanisms; transfer needs justification.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: genetic dynamics). **Basis:** abstract. Saved link: [original 1](https://www.pnas.org/doi/full/10.1073/pnas.1203559109). ^f070

- **[Systems-based digital twins to help characterize clinical dose-response and propose predictive biomarkers in a Phase I study of bispecific antibody, mosunetuzumab, in NHL](https://doi.org/10.1111/cts.13501)** · **[[#^f110|F110]]**

  **Abstract summary:** Generates individual twins and a virtual population from a mosunetuzumab QSP model to analyze phase-I lymphoma dose-response and potential biomarkers.

  **Research value (inference):** **IBD:** A lead for mechanistic exposure/response modeling and patient heterogeneity. **IQSEC2:** A lead for individualized mechanistic inference if suitable mechanisms/data exist.

  **Boundary / reading question:** Recovered from B's reference 76, DOI 10.1111/cts.13501; no direct IBD/IQSEC2 evidence.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (; cue: systems-based DT approach for characterizing dose-response relationships in non-hodkin lymphoma, using quantitative systems pharmacology (QSP) to generate virtual patients). **Basis:** abstract. ^f110

### Treatment effects, causal inference, and perturbations

- **[Causal machine learning for healthcare and precision medicine](https://doi.org/10.1098/rsos.220638)** · **[[#^f037|F037]]**

  **Abstract summary:** Reviews causal ML for intervention effects and clinical decision support, including confounding, temporal relationships, and distribution shift.

  **Research value (inference):** **IBD:** Separating flare prediction from treatment-effect estimation. **IQSEC2:** Separating observed trajectories from hypothetical intervention effects.

  **Boundary / reading question:** Methodological lead; causal assumptions and data support remain necessary.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Enhanced Decision support). **Basis:** abstract. Saved link: [original 1](https://royalsocietypublishing.org/rsos/article/9/8/220638/96716/Causal-machine-learning-for-healthcare-and). ^f037

- **[Estimating categorical counterfactuals via deep twin networks](https://doi.org/10.1038/s42256-023-00611-x)** · **[[#^f038|F038]]**

  **Abstract summary:** Introduces counterfactual-ordering constraints and deep twin networks for categorical counterfactual inference, tested across several domains.

  **Research value (inference):** **IBD:** Counterfactual modeling of categorical outcomes under explicit assumptions. **IQSEC2:** Counterfactual modeling when outcomes are categorical and data support is adequate.

  **Boundary / reading question:** “Twin network” is a causal construction; it does not by itself constitute a healthcare DT system.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Enhanced Decision support). **Basis:** publisher abstract. Saved link: [original 1](https://www.nature.com/articles/s42256-023-00611-x). ^f038

- **[scPerturb: harmonized single-cell perturbation data](https://doi.org/10.1038/s41592-023-02144-y)** · **[[#^f041|F041]]**

  **Abstract summary:** Harmonizes 44 single-cell perturbation datasets and introduces methods for quantifying perturbation effects and comparing responses.

  **Research value (inference):** **IBD:** Resource for inflammatory-cell perturbation methods, subject to dataset suitability. **IQSEC2:** Resource for gene/cell perturbation methods, subject to relevant coverage.

  **Boundary / reading question:** Preserve as a paper with an associated data/software resource, not a clinical DT demonstration.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41592-023-02144-y). ^f041

- **[Causal Imputation via Synthetic Interventions](https://proceedings.mlr.press/v177/squires22b.html)** · **[[#^f042|F042]]**

  **Abstract summary:** Extends synthetic interventions to estimate unobserved action/context pairs under a latent-factor model and tests compound effects on gene expression.

  **Research value (inference):** **IBD:** Method lead for unmeasured perturbation responses. **IQSEC2:** Method lead for limited intervention/context coverage.

  **Boundary / reading question:** Causal imputation of interventions is different from ordinary EHR missing-value imputation.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** publisher abstract. ^f042

- **[Bicycle: Intervention-Based Causal Discovery with Cycles](https://proceedings.mlr.press/v236/rohbeck24a.html)** · **[[#^f043|F043]]**

  **Abstract summary:** Bicycle learns cyclic causal relationships from perturbation-aware data and tests generalization to unseen single-cell perturbations.

  **Research value (inference):** **IBD:** Feedback-aware gene/network modeling methods. **IQSEC2:** Feedback-aware gene/network modeling methods if relevant perturbation data exist.

  **Boundary / reading question:** Modeling causal cycles requires more than observational patient correlations.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** publisher abstract. ^f043

- **[A dynamic single cell-based framework for digital twins to prioritize disease genes and drug targets](https://doi.org/10.1186/s13073-022-01048-4)** · **[[#^f091|F091]]**

  **Abstract summary:** Builds time-dependent multicellular networks from single-cell observations to prioritize upstream regulators in allergy and other inflammatory diseases.

  **Research value (inference):** **IBD:** A strong methodological lead for dynamic inflammatory-network modeling. **IQSEC2:** A gene/network prioritization lead if relevant cells/data can be obtained.

  **Boundary / reading question:** Disease-associated gene prioritization is not proof of a patient's treatment response.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Single cell based framework for targeted drug therapy). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/35513850). ^f091

- **[Recent applications of deep learning and machine intelligence on in silico drug discovery: methods, tools and databases](https://doi.org/10.1093/bib/bby061)** · **[[#^f092|F092]]**

  **Abstract summary:** Reviews ML/DL virtual screening, compound/protein representations, tools, and datasets for drug-target interaction prediction.

  **Research value (inference):** **IBD:** Drug-target-method background for mechanistic hypotheses. **IQSEC2:** Drug-target-method background for mechanistic hypotheses.

  **Boundary / reading question:** Virtual screening supports discovery but does not establish individual therapy safety or efficacy.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Applications of DL and ML in drug discovery). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/30084866). ^f092

- **[A validated single-cell-based strategy to identify diagnostic and therapeutic targets in complex diseases](https://doi.org/10.1186/s13073-019-0657-3)** · **[[#^f103|F103]]**

  **Abstract summary:** Uses multicellular network models from single-cell data to prioritize diagnostic and therapeutic targets, with human/mouse arthritis and cross-disease validation.

  **Research value (inference):** **IBD:** A methodological inflammatory-disease lead for target prioritization. **IQSEC2:** A methodological gene/cell-network lead if a valid disease mapping exists.

  **Boundary / reading question:** Its tested target prioritization differs from simulating thousands of drugs in a patient twin.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT copies for testing thousands drugs on simulation and optimize doses). **Basis:** abstract. Saved link: [original 1](https://link.springer.com/article/10.1186/s13073-019-0657-3). ^f103

### Learning with limited data and synthetic cohorts

- **[ClinicalGAN: powering patient monitoring in clinical trials with patient digital twins](https://doi.org/10.1038/s41598-024-62567-1)** · **[[#^f036|F036]]**

  **Abstract summary:** Introduces ClinicalGAN for personalized multivariate clinical-trial journeys and termination prediction, evaluated in Alzheimer's trial datasets.

  **Research value (inference):** **IBD:** Synthetic trajectory and patient-retention modeling ideas. **IQSEC2:** Synthetic-data methods to scrutinize under small-cohort constraints.

  **Boundary / reading question:** Patient-level generation is not evidence of patient-specific causal simulation.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Real-time monitoring:). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41598-024-62567-1). ^f036

- **[Metaverse and Healthcare: Machine Learning-Enabled Digital Twins of Cancer](https://doi.org/10.3390/bioengineering10040455)** · **[[#^f051|F051]]**

  **Abstract summary:** Presents a cancer DT/metaverse framework with classical ML approaches and a breast-cancer case example.

  **Research value (inference):** **IBD:** A baseline-method and interface-design comparison. **IQSEC2:** A baseline-method and interface-design comparison.

  **Boundary / reading question:** Inspect what is actually twinned and validated before accepting the DT framing.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2306-5354/10/4/455). ^f051

- **[Artificial intelligence models in digital twins for health and well-being](https://doi.org/10.1016/B978-0-32-399163-6.00011-1)** · **[[#^f054|F054]]**

  **Abstract summary:** Reviews AI-based health/well-being twin models for early warnings, risk classification, and healthcare-management prediction, alongside technological gaps.

  **Research value (inference):** **IBD:** A method-map lead for selecting candidate models. **IQSEC2:** A method-map lead for selecting candidate models.

  **Boundary / reading question:** Saved under tree ensembles; inspect individual methods before treating it as specific evidence for ensemble superiority.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** publisher abstract. [Checked source](https://www.sciencedirect.com/science/chapter/edited-volume/abs/pii/B9780323991636000111). Saved link: [original 1](https://www.researchgate.net/publication/367504395_Artificial_intelligence_models_in_digital_twins_for_health_and_well-being). ^f054

- **[TWIN-GPT : Digital Twins for Clinical Trials via Large Language Model](https://doi.org/10.1145/3674838)** · **[[#^f073|F073]]**

  **Abstract summary:** TWIN-GPT uses LLMs to generate individualized clinical-trial twins and cross-dataset information for outcome prediction under limited data.

  **Research value (inference):** **IBD:** A synthetic-data/transfer method to compare with simpler forecasting baselines. **IQSEC2:** A synthetic-data/transfer method to investigate under limited cohort size.

  **Boundary / reading question:** Generation fidelity and privacy claims do not establish biological or causal fidelity.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: LLM in DT, TWIN-GPT: , as transfer learning approach, when we don't have enough data). **Basis:** abstract. Saved link: [original 1](https://dl.acm.org/doi/10.1145/3674838). ^f073

- **[Accurate predictions on small data with a tabular foundation model](https://doi.org/10.1038/s41586-024-08328-6)** · **[[#^f077|F077]]**

  **Abstract summary:** Introduces TabPFN, learned from synthetic tabular tasks, and reports strong classification/regression performance on small-to-medium datasets.

  **Research value (inference):** **IBD:** A candidate small-data comparator, including calibration/missingness evaluation. **IQSEC2:** A candidate comparator for limited-data prediction tasks.

  **Boundary / reading question:** Broad benchmarks do not establish superiority in IBD or IQSEC2; retain the original request to inspect medical examples.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Paper about TabPFN use on small medical dataset ⏫ (They said that it outperforms treebased models referencing original paper, where I didn't found any proves or examples)). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41586-024-08328-6). ^f077

### Data acquisition and interoperability

- **[Digital Twin for Intelligent Context-Aware IoT Healthcare Systems](https://doi.org/10.1109/JIOT.2021.3051158)** · **[[#^f019|F019]]**

  **Abstract summary:** Implements a context-aware IoT healthcare DT framework and evaluates ML classification of ECG heart rhythms as a monitoring example.

  **Research value (inference):** **IBD:** Candidate architecture for patient observations and context. **IQSEC2:** Candidate architecture for repeated physiological/behavioral observations.

  **Boundary / reading question:** Merged ResearchGate and IEEE links. ECG-classification evidence does not establish validated IBD/IQSEC2 trajectories.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:); [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Neural Networks for high dimensional healthcare data:). **Basis:** indexed abstract (OpenAlex). [Checked source](https://qspace.qu.edu.qa/handle/10576/35509). Saved links: [original 1](https://www.researchgate.net/publication/348475365_Digital_Twin_for_Intelligent_Context-Aware_IoT_Healthcare_Systems), [original 2](https://ieeexplore.ieee.org/document/9320532). ^f019

- **[A Novel Cloud-Based Framework for the Elderly Healthcare Services Using Digital Twin](https://doi.org/10.1109/ACCESS.2019.2909828)** · **[[#^f020|F020]]**

  **Abstract summary:** Proposes CloudDTH, an extensible cloud framework connecting physical/virtual health representations, and illustrates real-time supervision scenarios and a case study.

  **Research value (inference):** **IBD:** Longitudinal monitoring architecture and alert design. **IQSEC2:** Potential remote-observation architecture; population transfer is uncertain.

  **Boundary / reading question:** An elderly-care architecture/proof of concept; transfer to other cohorts and clinical outcomes requires evaluation.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:); [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: cloud based DTH for alarming in elderly). **Basis:** indexed abstract (OpenAlex). Saved link: [original 1](https://www.researchgate.net/publication/332586623_A_Novel_Cloud-Based_Framework_for_the_Elderly_Healthcare_Services_Using_Digital_Twin). ^f020

- **[Digital Twins for Healthcare 4.0—Recent Advances, Architecture, and Open Challenges](https://doi.org/10.1109/MCE.2022.3208986)** · **[[#^f028|F028]]**

  **Abstract summary:** Reviews healthcare DT architectures and use cases, emphasizing proactive analytics and networks with limited operator intervention.

  **Research value (inference):** **IBD:** Architecture ideas for long-running patient services. **IQSEC2:** Architecture ideas for remote and individualized observation.

  **Boundary / reading question:** Abstract checked in the University of Brighton record; education was the original selection cue.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: DT for training and simulation). **Basis:** repository abstract. [Checked source](https://research.brighton.ac.uk/en/publications/digital-twins-for-healthcare-40-recent-advances-architecture-and-/). Saved link: [original 1](https://research.brighton.ac.uk/en/publications/digital-twins-for-healthcare-40-recent-advances-architecture-and-). ^f028

- **[Towards continuous monitoring in personalized healthcare through digital twins](https://doi.org/10.5555/3370272.3370310)** · **[[#^f034|F034]]**

  **Provisional description:** Verified conference citation concerns continuous monitoring in personalized healthcare through DTs; abstract unavailable.

  **Research value (inference):** **IBD:** Lead on a continuous-observation architecture. **IQSEC2:** Lead on longitudinal individualized observation.

  **Boundary / reading question:** Also saved under RNN patient trajectories; a specific RNN implementation was not verified.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Real-time monitoring: / Neural Networks for high dimensional healthcare data:). **Basis:** provisional. Saved link: [original 1](https://www.semanticscholar.org/paper/Towards-continuous-monitoring-in-personalized-twins-Rivera-Jim%C3%A9nez/b10c13e2d67cc74914ea38f29067a6e0ce0a5a34). ^f034

- **[Digital Twins for Precision Healthcare](https://doi.org/10.1007/978-3-030-35746-7_8)** · **[[#^f035|F035]]**

  **Abstract summary:** Reviews DT design for precision healthcare at patient and system levels, including active participation, monitoring, cybersecurity, and ethics.

  **Research value (inference):** **IBD:** Integration and patient-participation design. **IQSEC2:** Individualized monitoring and security design.

  **Boundary / reading question:** Abstract checked in the authors' institutional publication record.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Real-time monitoring:). **Basis:** repository abstract. [Checked source](https://pure.kfupm.edu.sa/en/publications/digital-twins-for-precision-healthcare/). Saved link: [original 1](https://www.researchgate.net/publication/340466788_Digital_Twins_for_Precision_Healthcare). ^f035

- **[An ISO/IEEE 11073 Standardized Digital Twin Framework for Health and Well-Being in Smart Cities](https://doi.org/10.1109/ACCESS.2020.2999871)** · **[[#^f046|F046]]**

  **Abstract summary:** Implements a DT framework for collecting personal-health-device observations using ISO/IEEE 11073, including wrappers for noncompliant devices and user/caregiver feedback.

  **Research value (inference):** **IBD:** Device-data integration and interoperability lead. **IQSEC2:** Device-data integration and interoperability lead.

  **Boundary / reading question:** A proof-of-concept interoperability/monitoring framework; saved under drug development but not a drug-response model.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (DT for Drug development). **Basis:** indexed abstract (OpenAlex). Saved link: [original 1](https://ieeexplore.ieee.org/document/9108291). ^f046

- **[Survey on Sensors and Smart Devices for IoT Enabled Intelligent Healthcare System](https://doi.org/10.1007/s11277-023-10528-8)** · **[[#^f061|F061]]**

  **Abstract summary:** Surveys sensors and smart devices used in IoT healthcare monitoring, including edge computing and device merits/limitations.

  **Research value (inference):** **IBD:** Selecting feasible longitudinal observations and measurement devices. **IQSEC2:** Selecting feasible repeated observations and devices.

  **Boundary / reading question:** A sensor survey can suggest candidates; it does not automatically identify a clinical gold standard.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: IoT devices enables early detection of potential problems: (could contain info about wearable golden standard, beacuse it reviews many existed solutions)). **Basis:** abstract. Saved link: [original 1](https://link.springer.com/article/10.1007/s11277-023-10528-8). ^f061

- **[The Emergence of AI-Based Wearable Sensors for Digital Health Technology: A Review](https://doi.org/10.3390/s23239498)** · **[[#^f062|F062]]**

  **Abstract summary:** Reviews physical, chemical, and biosensors and the role of AI in wearable measurement, processing, and personalized monitoring.

  **Research value (inference):** **IBD:** Assessing measurement limitations before integrating wearable data. **IQSEC2:** Assessing measurement limitations before integrating wearable data.

  **Boundary / reading question:** Device and algorithm claims require verification in the intended population/use.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/1424-8220/23/23/9498). ^f062

- **[Digital twin: Data exploration, architecture, implementation and future](https://doi.org/10.1016/j.heliyon.2024.e26503)** · **[[#^f063|F063]]**

  **Abstract summary:** Reviews data across DT phases, including acquisition, storage, integration, and physical/virtual connections across application domains.

  **Research value (inference):** **IBD:** Data-pipeline architecture and history management. **IQSEC2:** Data-pipeline architecture and history management.

  **Boundary / reading question:** A cross-domain review, rather than a disease-specific wearable validation.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:). **Basis:** abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S2405844024025349). ^f063

- **[Fast Healthcare Interoperability Resources (FHIR) for Interoperability in Health Research: Systematic Review](https://doi.org/10.2196/35724)** · **[[#^f074|F074]]**

  **Abstract summary:** Reviews FHIR implementations in health research for capture, standardization, and data exchange.

  **Research value (inference):** **IBD:** Structuring clinical data integration. **IQSEC2:** Structuring clinical/genetic observation exchange where supported.

  **Boundary / reading question:** FHIR supports interoperability; the review does not guarantee semantic completeness for every modality.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: FHIR). **Basis:** abstract. Saved link: [original 1](https://medinform.jmir.org/2022/7/e35724). ^f074

- **[Wearable Technologies and AI at the Far Edge for Chronic Heart Failure Prevention and Management: A Systematic Review and Prospects](https://doi.org/10.3390/s23156896)** · **[[#^f086|F086]]**

  **Abstract summary:** Reviews wearables with edge AI for chronic-heart-failure prevention/management, emphasizing service needs, constraints, and open challenges.

  **Research value (inference):** **IBD:** Choosing edge versus cloud for chronic monitoring. **IQSEC2:** Choosing edge versus cloud for chronic monitoring.

  **Boundary / reading question:** Cardiac disease context; evaluate whether proposed measurements are meaningful in either track.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: DT in chronic heart diseases). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/37571678). ^f086

- **[DTCoach: Your Digital Twin Coach on the Edge During COVID-19 and Beyond](https://doi.org/10.1109/MIM.2021.9513635)** · **[[#^f089|F089]]**

  **Abstract summary:** Introduces DT health/well-being concepts in which observations and AI analysis provide feedback, motivating an edge-based coaching application.

  **Research value (inference):** **IBD:** Patient-facing monitoring/coaching architecture lead. **IQSEC2:** Patient/caregiver-facing coaching architecture lead.

  **Boundary / reading question:** The indexed abstract is largely introductory; coaching effectiveness and implementation detail need full-text reading.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs). **Basis:** indexed abstract (OpenAlex). Saved link: [original 1](https://ieeexplore.ieee.org/document/9513635). ^f089

### Validation and model credibility

- **[Credibility of In Silico Trial Technologies-A Theoretical Framing](https://doi.org/10.1109/JBHI.2019.2949888)** · **[[#^f078|F078]]**

  **Abstract summary:** Proposes a theoretical framework for evaluating credibility of predictive models used in in-silico trials across modeling approaches.

  **Research value (inference):** **IBD:** Designing evaluation tied to a stated clinical/modeling use. **IQSEC2:** Designing evaluation tied to limited evidence and a stated use.

  **Boundary / reading question:** A credibility framework, not an in-silico efficacy demonstration.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: In silico clinical trails). **Basis:** abstract. Saved link: [original 1](https://ieeexplore.ieee.org/document/8884189). ^f078

### Health-system implementation and governance

- **[Digital Twins for Managing Health Care Systems: Rapid Literature Review](https://doi.org/10.2196/37641)** · **[[#^f014|F014]]**

  **Abstract summary:** Reviews twins of healthcare products, processes, and systems for management and user experience, excluding organ-level precision-medicine applications.

  **Research value (inference):** **IBD:** Care-process and workflow integration around a patient model. **IQSEC2:** Care-process and coordination around individualized care.

  **Boundary / reading question:** Saved for chronic monitoring; this review's stated scope is healthcare management.

  **Origin:** [[Digital Twin for healthcare systems|A]] ('Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'). **Basis:** abstract. Saved link: [original 1](https://www.jmir.org/2022/8/e37641). ^f014

- **[The Promise of Digital Health: Then, Now, and the Future](https://doi.org/10.31478/202206e)** · **[[#^f016|F016]]**

  **Document summary:** Discusses digital health's development, learning systems, data exchange, equity, and barriers to realizing its promise.

  **Research value (inference):** **IBD:** Planning sustainable integration of clinical and patient-generated data. **IQSEC2:** Planning accessible integration and data governance.

  **Boundary / reading question:** Description based on the official discussion-paper text, not a retrieved abstract.

  **Origin:** [[Digital Twin for healthcare systems|A]] ('Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'; cue: patient adherence aspect). **Basis:** document. Saved link: [original 1](https://nam.edu/perspectives/the-promise-of-digital-health-then-now-and-the-future). ^f016

- **[Technical, Ethical, Legal, and Societal Challenges With Digital Twin Systems for the Management of Chronic Diseases in Children and Young People](https://doi.org/10.2196/39698)** · **[[#^f039|F039]]**

  **Abstract summary:** Reviews technical, ethical, legal, and societal challenges of sensor/software DT systems for children with chronic disease.

  **Research value (inference):** **IBD:** Pediatric chronic-care design if that cohort is studied. **IQSEC2:** Pediatric/caregiver participation, trust, and observation feasibility.

  **Boundary / reading question:** Direct pediatric chronic-care context, but not specific IQSEC2 evidence.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Longitudinal health management). **Basis:** abstract. Saved link: [original 1](https://www.jmir.org/2022/10/e39698). ^f039

- **[Spoofing detection system for e-health digital twin using EfficientNet Convolution Neural Network](https://doi.org/10.1007/s11042-021-11578-5)** · **[[#^f057|F057]]**

  **Abstract summary:** Proposes EfficientNet-based detection of genuine versus spoofed iris samples to secure access to an e-health DT cloud.

  **Research value (inference):** **IBD:** Security design around a patient-data service. **IQSEC2:** Security design around sensitive longitudinal/genetic information.

  **Boundary / reading question:** A biometric anti-spoofing study, not disease-state neural modeling.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Neural Networks for high dimensional healthcare data:). **Basis:** publisher abstract. Saved link: [original 1](https://link.springer.com/article/10.1007/s11042-021-11578-5). ^f057

- **[Digital Twins in Health Care: Ethical Implications of an Emerging Engineering Paradigm](https://doi.org/10.3389/fgene.2018.00031)** · **[[#^f108|F108]]**

  **Abstract summary:** Explores ethical consequences of detailed longitudinal personal twins, including changing notions of normality, inequality, discrimination, privacy, and governance.

  **Research value (inference):** **IBD:** Consent, individual baselines, and fairness in disease-state interpretation. **IQSEC2:** Consent, individual baselines, and fairness in genetic/phenotypic representation.

  **Boundary / reading question:** Conceptual ethics paper; its forecasts are not measured clinical effects.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: ethical implication in DT). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/29487613). ^f108

### Patient-centered care and evidence

- **[Balancing personalized medicine and personalized care](https://doi.org/10.1097/ACM.0b013e3182806345)** · **[[#^f002|F002]]**

  **Abstract summary:** Discusses the gap between technologically personalized medicine and holistic care, including psychological, religious, and ethical barriers to genetic information use.

  **Research value (inference):** **IBD:** Designing patient-facing explanations and shared decisions. **IQSEC2:** Considering individual and family expectations around genetic information.

  **Boundary / reading question:** Background perspective; does not demonstrate DT performance.

  **Origin:** [[Digital Twin for healthcare systems|A]] (DT4H improves healthcare system performance:). **Basis:** abstract. Saved link: [original 1](https://academic.oup.com/academicmedicine/article-abstract/88/3/309/8351491). ^f002

- **[A Concept Analysis of Holistic Care by Hybrid Model](https://doi.org/10.4103/0973-1075.197960)** · **[[#^f003|F003]]**

  **Abstract summary:** Defines holistic care through literature analysis and interviews with eight nurses using a hybrid concept-analysis method.

  **Research value (inference):** **IBD:** Choosing patient-centered outcomes beyond measured disease activity. **IQSEC2:** Broadening outcomes beyond molecular or diagnostic measurements.

  **Boundary / reading question:** “Hybrid model” means a concept-analysis method here, not hybrid ML/mechanistic modeling.

  **Origin:** [[Digital Twin for healthcare systems|A]] (DT4H improves healthcare system performance:). **Basis:** abstract. Saved link: [original 1](https://jpalliativecare.com/a-concept-analysis-of-holistic-care-by-hybrid-model). ^f003

- **[Precision Medicine, AI, and the Future of Personalized Health Care](https://doi.org/10.1111/cts.12884)** · **[[#^f010|F010]]**

  **Abstract summary:** Discusses the convergence of AI and precision medicine using genomic and nongenomic determinants, symptoms, clinical history, and lifestyle.

  **Research value (inference):** **IBD:** Motivating combined clinical and molecular representation. **IQSEC2:** Motivating phenotype/genotype integration.

  **Boundary / reading question:** Background precision-medicine discussion; not a DT clinical benefit study.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Proves, examples that indeed they boost quality:). **Basis:** abstract. Saved link: [original 1](https://ascpt.onlinelibrary.wiley.com/doi/10.1111/cts.12884). ^f010

- **[Personalized medicine: motivation, challenges, and progress](https://doi.org/10.1016/j.fertnstert.2018.05.006)** · **[[#^f011|F011]]**

  **Abstract summary:** Reviews personalized medicine's motivation, enabling technologies, successes, setbacks, and deployment limitations.

  **Research value (inference):** **IBD:** Evaluating personalization claims and practical baselines. **IQSEC2:** Evaluating the rationale and limitations of individualized models.

  **Boundary / reading question:** Saved as evidence of DT benefit, but its scope is personalized medicine generally.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Proves, examples that indeed they boost quality:). **Basis:** abstract. Saved link: [original 1](https://www.fertstert.org/article/S0015-0282(18)30407-2/fulltext). ^f011

- **[The next generation of evidence-based medicine](https://doi.org/10.1038/s41591-022-02160-z)** · **[[#^f012|F012]]**

  **Abstract summary:** A perspective on future clinical trials and evidence generation informed by wearables, data science, and patient-centered design.

  **Research value (inference):** **IBD:** Planning evaluation beyond retrospective model scores. **IQSEC2:** Considering evidence generation with constrained recruitment.

  **Boundary / reading question:** A future-oriented perspective, not an effect estimate for DTs.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Proves, examples that indeed they boost quality:). **Basis:** abstract. Saved link: [original 1](https://www.nature.com/articles/s41591-022-02160-z). ^f012

- **[Empowering Patients and Transforming Healthcare in the Post-COVID-19 Era: The Role of Digital and Wearable Technologies](https://doi.org/10.3390/jpm13050722)** · **[[#^f015|F015]]**

  **Abstract summary:** The short abstract introduces digital and wearable technologies as responses to healthcare gaps revealed by COVID-19.

  **Research value (inference):** **IBD:** Patient engagement and wearable-adoption background. **IQSEC2:** Engagement and feasibility background for families/caregivers.

  **Boundary / reading question:** Brief editorial-style abstract; specific adherence effects need further reading.

  **Origin:** [[Digital Twin for healthcare systems|A]] ('Real-time monitoring through DT is particularly beneficial for patients with chronic conditions'; cue: patient adherence aspect). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2075-4426/13/5/722). ^f015

- **[Breast cancer early detection: A phased approach to implementation](https://doi.org/10.1002/cncr.32887)** · **[[#^f024|F024]]**

  **Abstract summary:** Describes phased implementation of breast-cancer early detection, with access barriers, governance, and monitoring metrics.

  **Research value (inference):** **IBD:** Implementation and outcome-measurement lessons for early detection. **IQSEC2:** Access and program-design lessons for individualized care.

  **Boundary / reading question:** A cancer early-detection consensus article; not DT prevention evidence.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: prevention). **Basis:** abstract. Saved link: [original 1](https://acsjournals.onlinelibrary.wiley.com/doi/10.1002/cncr.32887). ^f024

- **[Enhancing psychosomatic health using artificial intelligence-based treatment protocol: A data science-driven approach](https://doi.org/10.1016/j.jjimei.2022.100124)** · **[[#^f026|F026]]**

  **Abstract summary:** Uses questionnaires and EEG/brain-computer observations in a quantitative psychosomatic-health study and proposes extension toward AI protocols and DTs.

  **Research value (inference):** **IBD:** Exploratory lead on behavioral context and intervention design. **IQSEC2:** Exploratory lead on patient experience and behavioral representation.

  **Boundary / reading question:** The study proposes possible DT incorporation; the healthcare-systems review incorrectly assigns it a cardiovascular-review DOI.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:; cue: curious title "Enhancing psychosomatic health using artificial intelligence-based treatment protocol: A data science-driven approach). **Basis:** publisher abstract. [Checked source](https://www.sciencedirect.com/science/article/pii/S2667096822000672). Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S2667096822000672). ^f026

- **[Digital twin technologies for supporting self-care in adults with diet-related chronic conditions: a systematic review](https://doi.org/10.1016/j.ijmedinf.2026.106404)** · **[[#^f082|F082]]**

  **Abstract summary:** Systematically reviews DT-supported self-care in diet-related chronic disease; all four included studies concern type 2 diabetes.

  **Research value (inference):** **IBD:** A clinical-evidence design lead for behavioral/longitudinal care. **IQSEC2:** A clinical-evidence design lead; pediatric/rare-disease transfer is uncertain.

  **Boundary / reading question:** No IBD evidence is established by this review; distinguish human coaching from DT-specific contributions.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: DT in chronic diseases related with diet). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/41880918). ^f082

- **[Artificial Intelligence-Driven Transformation of Pediatric Diabetes Care: A Systematic Review and Epistemic Meta-Analysis of Diagnostic, Therapeutic, and Self-Management Applications](https://doi.org/10.3390/ijms27020802)** · **[[#^f083|F083]]**

  **Abstract summary:** Reviews AI in pediatric diabetes, including monitoring, closed-loop systems, prediction, telemedicine, and self-management, with equity/validation limitations.

  **Research value (inference):** **IBD:** Pediatric chronic-care evidence and outcome selection. **IQSEC2:** Pediatric implementation and family-facing design leads.

  **Boundary / reading question:** The review covers AI broadly; self-learning/DT efficacy should be traced to individual studies.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: Self learning aspect of predictive DT using AI). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/41596449). ^f083

- **[Artificial intelligence in headache medicine: between automation and the doctor-patient relationship. A systematic review](https://doi.org/10.1186/s10194-025-02143-8)** · **[[#^f084|F084]]**

  **Abstract summary:** Reviews AI in headache care, including diagnosis, prediction, treatment response, patient trust, and limited generalizability evidence.

  **Research value (inference):** **IBD:** A framework for critical appraisal of patient-facing AI. **IQSEC2:** A neurological-care and clinician/patient-relationship comparison.

  **Boundary / reading question:** Broader AI review; not specific validation of a self-learning DT.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: Self learning aspect of predictive DT using AI). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/40898015). ^f084

- **[Molecular-Guided Off-Label Targeted Therapy in a Large-Scale Precision Oncology Program](https://doi.org/10.1200/po.22.00518)** · **[[#^f097|F097]]**

  **Abstract summary:** Studies real-world off-label molecular-guided cancer therapy after comprehensive genomic profiling, with response and evidence-level differences.

  **Research value (inference):** **IBD:** An example of evaluating molecular actionability and outcomes. **IQSEC2:** An example of evidence grading around genomic actionability.

  **Boundary / reading question:** Oncology study; it does not validate a DT or justify off-label therapy for IQSEC2.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/36787508). ^f097

### Other applications: procedures, education, and rehabilitation

- **[Twin-S: a digital twin for skull base surgery](https://doi.org/10.1007/s11548-023-02863-9)** · **[[#^f064|F064]]**

  **Abstract summary:** Introduces Twin-S for skull-base surgery using optical tracking, calibration, and real-time updates of tools, anatomy, and drilling.

  **Research value (inference):** **IBD:** A concrete example of observing and updating a bounded process. **IQSEC2:** A concrete example of bounded representation and updating.

  **Boundary / reading question:** Saved as therapy testing on a digital copy; the reported application is surgical tracking.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: testowanie terapii na cyfrowej kopii). **Basis:** abstract. Saved link: [original 1](https://link.springer.com/article/10.1007/s11548-023-02863-9). ^f064

- **[Development and usability testing of a patient digital twin for critical care education: a mixed methods study](https://doi.org/10.3389/fmed.2023.1336897)** · **[[#^f071|F071]]**

  **Abstract summary:** Evaluates an EHR-based critical-care patient simulator with residents using usability, workload, and qualitative feedback.

  **Research value (inference):** **IBD:** A parallel education application and evaluation framework. **IQSEC2:** A parallel education application and evaluation framework.

  **Boundary / reading question:** Usability/acceptance evidence is not proof of disease-model clinical effectiveness.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: patient digital twin for healthcare education). **Basis:** abstract. ^f071

- **[Highly Accurate, Patient-Specific, 3-Dimensional Mixed-Reality Model Creation for Surgical Training and Decision-making](https://doi.org/10.1001/jamasurg.2019.2546)** · **[[#^f072|F072]]**

  **Document summary:** Describes CT-based patient-specific 3D mixed-reality models, anatomical segmentation, and visualization for surgical training and intraoperative planning.

  **Research value (inference):** **IBD:** Procedural/education representation ideas. **IQSEC2:** Procedural/education representation ideas.

  **Boundary / reading question:** Primary surgical-innovation text checked; no conventional abstract. Personalized 3D anatomy does not alone establish a continuously updated twin.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: ,- simalar, but for surgicals case). **Basis:** document. [Checked source](https://discovery.ucl.ac.uk/id/eprint/10083676/). Saved link: [original 1](https://jamanetwork.com/journals/jamasurgery/article-abstract/2748068). ^f072

- **[Using 3D and 4D digital human modeling in extended reality-based rehabilitation: a systematic review](https://doi.org/10.3389/fbioe.2025.1496168)** · **[[#^f085|F085]]**

  **Abstract summary:** Reviews 3D/4D digital-human modeling in XR rehabilitation, finding limited heterogeneous evidence and a need for stronger studies.

  **Research value (inference):** **IBD:** Rehabilitation/user-interface methods if function is an outcome. **IQSEC2:** Potential rehabilitation/functional-outcome methods, subject to cohort relevance.

  **Boundary / reading question:** Digital human models and XR are not automatically coupled patient DTs.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: XR in rehabilitation using digital human modeling). **Basis:** abstract. Saved link: [original 1](https://pubmed.ncbi.nlm.nih.gov/40144388). ^f085

- **[A Dual Doctor-Patient Twin Paradigm for Transparent Remote Examination, Diagnosis, and Rehabilitation](https://doi.org/10.1109/iros51168.2021.9636626)** · **[[#^f088|F088]]**

  **Abstract summary:** Presents two robotic systems representing doctor and patient, with bidirectional haptic telepresence, visual analysis, and a patient DT for remote assessment and rehabilitation.

  **Research value (inference):** **IBD:** Remote examination and interface-design lead. **IQSEC2:** Remote examination and rehabilitation interface lead.

  **Boundary / reading question:** A robotics/telemedicine framework; clinical outcome and disease-specific modeling validity require separate checking.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: tele-coach telemedicine DT). **Basis:** repository abstract. [Checked source](https://portal.fis.tum.de/en/publications/a-dual-doctor-patient-twin-paradigm-for-transparent-remote-examin/). Saved link: [original 1](https://dl.acm.org/doi/abs/10.1109/IROS51168.2021.9636626). ^f088

### Transferable methods from industry

- **[Predictive maintenance using digital twins: A systematic literature review](https://doi.org/10.1016/j.infsof.2022.107008)** · **[[#^f004|F004]]**

  **Abstract summary:** Synthesizes 42 studies of industrial predictive maintenance, including DT architectures, communication, representations, and design challenges.

  **Research value (inference):** **IBD:** Potential architecture and sparse-event design analogies. **IQSEC2:** Potential architecture lessons where outcomes are rarely observed.

  **Boundary / reading question:** Saved as healthcare-system-performance evidence; its domain is industrial maintenance.

  **Origin:** [[Digital Twin for healthcare systems|A]] (DT4H improves healthcare system performance:). **Basis:** publisher abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S0950584922001331). ^f004

- **[Overview of predictive maintenance based on digital twin technology](https://doi.org/10.1016/j.heliyon.2023.e14534)** · **[[#^f013|F013]]**

  **Abstract summary:** Reviews DT-based predictive maintenance across manufacturing, power, construction, aerospace, and shipbuilding, with a reference framework.

  **Research value (inference):** **IBD:** Possible monitoring and degradation-model analogies. **IQSEC2:** Possible adaptation and sparse-observation analogies.

  **Boundary / reading question:** Saved under DT therapy advantage; it provides industrial rather than therapeutic evidence.

  **Origin:** [[Digital Twin for healthcare systems|A]] (Advantege DT therapy over traditional:). **Basis:** abstract. Saved link: [original 1](https://www.cell.com/heliyon/fulltext/S2405-8440(23)01741-3). ^f013

- **[Developing a Digital Twin and Digital Thread Framework for an ‘Industry 4.0’ Shipyard](https://doi.org/10.3390/app11031097)** · **[[#^f018|F018]]**

  **Abstract summary:** Proposes a digital twin/thread framework for shipyard operations, emphasizing information continuity, traceability, and data management.

  **Research value (inference):** **IBD:** Traceability and history-management design analogies. **IQSEC2:** Traceability of evolving patient representations.

  **Boundary / reading question:** Saved under coordinated care; the application is an industrial shipyard.

  **Origin:** [[Digital Twin for healthcare systems|A]] (coordinated care:). **Basis:** abstract. Saved link: [original 1](https://www.mdpi.com/2076-3417/11/3/1097). ^f018

- **[Deep digital twins for detection, diagnostics and prognostics](https://doi.org/10.1016/j.ymssp.2019.106612)** · **[[#^f053|F053]]**

  **Abstract summary:** Trains deep generative twins on healthy industrial-asset observations to detect emerging faults, track degradation, and distinguish failure modes under changing operating conditions.

  **Research value (inference):** **IBD:** Possible analogies for individual baselines and anomaly scores. **IQSEC2:** Possible analogies for individual baselines when abnormal-state data are sparse.

  **Boundary / reading question:** Abstract checked in the author manuscript. Industrial anomaly-detection evidence; transfer to patient observations requires testing.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** author manuscript abstract. [Checked source](https://repository.up.ac.za/bitstreams/50b5c2ab-8451-4db8-b80c-2924a7747d09/download). Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S0888327019308337). ^f053

- **[Cloud-Based Digital Twinning for Structural Health Monitoring Using Deep Learning](https://doi.org/10.1109/TII.2021.3115119)** · **[[#^f055|F055]]**

  **Abstract summary:** Proposes cloud-connected structural monitoring that combines mathematical, finite-element, and ML models, tested for bridge damage detection.

  **Research value (inference):** **IBD:** Cloud architecture and model-updating analogy. **IQSEC2:** Cloud architecture and model-updating analogy.

  **Boundary / reading question:** An engineering structural-health study; transferable cloud/model-orchestration lessons, not patient-health evidence.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Tree-based ensemble methods applications:). **Basis:** repository abstract. [Checked source](https://repository.mdx.ac.uk/item/897y1). Saved link: [original 1](https://ieeexplore.ieee.org/document/9547763). ^f055

- **[A neural network based digital twin model for the structural health monitoring of reinforced concrete bridges](https://doi.org/10.1016/j.istruc.2023.105248)** · **[[#^f056|F056]]**

  **Abstract summary:** Develops a fiber-optic bridge-monitoring prototype whose neural network converts strain observations into an interactive DT representation, checked with finite-element analysis.

  **Research value (inference):** **IBD:** Potential monitoring architecture analogy. **IQSEC2:** Potential monitoring architecture analogy.

  **Boundary / reading question:** Saved as a healthcare neural-network example; the tested system is a reinforced-concrete bridge.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Neural Networks for high dimensional healthcare data:). **Basis:** publisher abstract. Saved link: [original 1](https://www.sciencedirect.com/science/article/pii/S235201242301336X). ^f056

- **[Recurrent Neural Networks for real-time distributed collaborative prognostics](https://www.repository.cam.ac.uk/items/331396a5-f4c4-46c7-8d6c-4dc876cab24b)** · **[[#^f060|F060]]**

  **Abstract summary:** Implements Weibull time-to-event RNNs for distributed prediction of industrial asset time-to-failure using collaboration across assets.

  **Research value (inference):** **IBD:** A time-to-event modeling analogy for possible flare-hazard research. **IQSEC2:** A time-to-event modeling analogy if a suitable outcome exists.

  **Boundary / reading question:** Original cue suggested patient trajectories; evaluated subjects are industrial assets.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Neural Networks for high dimensional healthcare data:). **Basis:** repository abstract. [Checked source](https://www.repository.cam.ac.uk/items/331396a5-f4c4-46c7-8d6c-4dc876cab24b). ^f060

### Already reviewed source retained from follow-ups

- **[Digital twins for health: a scoping review](https://doi.org/10.1038/s41746-024-01073-0)** · **[[#^f065|F065]]**

  **Abstract summary:** Surveys healthcare DT applications, research centers, limitations, and opportunities.

  **Research value (inference):** **IBD:** Already-analyzed foundation for the IBD track. **IQSEC2:** Already-analyzed foundation for the IQSEC2 track.

  **Boundary / reading question:** This is review C. Retained once because B's follow-up task cites it alongside the readmission claim.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: Digital twin could reduce hospital readmission by up to 25% for certain chronic diseases). **Basis:** abstract and saved full text. Saved link: [original 1](https://www.nature.com/articles/s41746-024-01073-0). ^f065

## Projects, platforms, products, and consortia

All website/resource leads are retained. Their descriptions concern documented functions or stated project aims. Availability of a website does not imply open research data, clinical effectiveness, or that the product satisfies a strict DT definition. A project and a paper about it remain separate kinds of source.

### Knowledge and research infrastructure

- **[SPOKE — Scalable Precision Medicine Open Knowledge Engine](https://spoke.ucsf.edu/home)** · **[[#^f067|F067]]**

  **Resource description:** SPOKE integrates biomedical entities and relationships into a knowledge graph with exploration tools and linked publications.

  **Research value (inference):** **IBD:** Connecting clinical/omic predictors to disease knowledge. **IQSEC2:** Exploring gene/phenotype/pathway relations; verify IQSEC2 coverage.

  **Boundary / reading question:** Official documentation checked. A knowledge graph is infrastructure, not a patient DT.

  **Origin:** [[Digital Twins in healthcare a comprehensive review and future directions|B]] (Methods in building DT:; cue: For type 2 diabetes, comprehensive frameworks combining ML, multiomic data and knowledge graphs have enhanced predictive accuracy for disease trajectories and treatment responses: ⏫ performed on [[Arivale]] dataset and SPOKE knowledge graph). **Basis:** official documentation. ^f067

- **[European Virtual Human Twins initiative](https://www.virtualhumantwins.eu)** · **[[#^f080|F080]]**

  **Resource description:** The European Virtual Human Twins initiative connects research and infrastructure efforts around multiscale virtual representations.

  **Research value (inference):** **IBD:** Models, interoperability initiatives, and potential collaborations. **IQSEC2:** Models, interoperability initiatives, and potential collaborations.

  **Boundary / reading question:** Project/network information; specific datasets, access, and deliverables require project-level checking.

  **Origin:** [[Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation|D]] (Follow-up papers; cue: European Virtual Human Twins). **Basis:** official documentation. ^f080

- **[Living Brain Project — Mount Sinai](https://icahn.mssm.edu/research/friedman/living-brain)** · **[[#^f090|F090]]**

  **Resource description:** Mount Sinai's Living Brain Project combines living brain tissue, molecular data, neurophysiology, imaging, and clinical observations in a neuroscience study.

  **Research value (inference):** **IBD:** Multimodal data-integration design inspiration. **IQSEC2:** A neurobiological multimodal research lead; cohort/data relevance must be checked.

  **Boundary / reading question:** This link is not the Dassault Living Brain project cited in C. It does not establish EEG-based brain-twin reconstruction.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Living brain project (maybe can be used with brain map from eeg?)). **Basis:** official documentation. ^f090

### Products and platforms

- **[MindBank AI](https://www.mindbank.ai)** · **[[#^f098|F098]]**

  **Resource description:** MindBank AI markets personal AI twins for expertise sharing and personal content.

  **Research value (inference):** **IBD:** Patient-facing representation/interface inspiration only. **IQSEC2:** Personal representation/interface inspiration only.

  **Boundary / reading question:** Current official page is a commercial service description; clinical DT validation is unverified.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Personal DT for wellness examples). **Basis:** official documentation. ^f098

- **[eMed UK](https://www.emed.com/uk)** · **[[#^f099|F099]]**

  **Resource description:** eMed UK's current page describes a managed/preemptive health service with clinical intake, screening, and data-informed care.

  **Research value (inference):** **IBD:** Service/workflow and engagement examples. **IQSEC2:** Service/workflow and engagement examples.

  **Boundary / reading question:** Saved as a wellness twin example; the current page does not establish a research-accessible patient DT.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Personal DT for wellness examples). **Basis:** official documentation. ^f099

- **[IBM Maximo — Asset Performance Management](https://www.ibm.com/products/maximo/asset-performance-management)** · **[[#^f100|F100]]**

  **Resource description:** IBM Maximo provides asset-performance management using operational data, AI, IoT, and automation.

  **Research value (inference):** **IBD:** Possible infrastructure/equipment-management analogy. **IQSEC2:** Possible infrastructure/equipment-management analogy.

  **Boundary / reading question:** Its “health” concerns assets, not a clinically validated personal wellness twin.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Personal DT for wellness examples). **Basis:** official documentation. ^f100

- **[MAI — BodyMap and AcuMap](https://www.mai.ai)** · **[[#^f101|F101]]**

  **Resource description:** MAI's current site presents BodyMap and AcuMap for immersive anatomy/acupuncture education.

  **Research value (inference):** **IBD:** An education/visualization resource. **IQSEC2:** An education/visualization resource.

  **Boundary / reading question:** Saved as a personal-wellness twin example; current product scope differs.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Personal DT for wellness examples). **Basis:** official documentation. ^f101

- **[mindLAMP](https://docs.lamp.digital)** · **[[#^f102|F102]]**

  **Resource description:** mindLAMP documents an open-source modular platform for mobile-health research, participant tools, and data analysis.

  **Research value (inference):** **IBD:** Potential collection of longitudinal patient-reported/behavioral observations. **IQSEC2:** Potential collection of repeated behavioral observations, subject to feasibility.

  **Boundary / reading question:** Check device support, study burden, licensing, and access before choosing it; a collection platform is one DT component.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: An open source platform for psychological and behavioral data collection). **Basis:** official documentation. ^f102

### Projects and consortia

- **[Empa — personalized drug-delivery digital twins](https://www.empa.ch/web/s604/eq71-digital-twin)** · **[[#^f104|F104]]**

  **Resource description:** Empa's official communications describe personalized simulations for drug delivery and transdermal pain therapy.

  **Research value (inference):** **IBD:** A mechanistic pharmacokinetic/patient-parameter modeling lead. **IQSEC2:** A mechanistic personalization lead if relevant physiological questions exist.

  **Boundary / reading question:** Original article link retained; official related page used because the saved URL was unavailable. Not proof of testing thousands of drugs.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT copies for testing thousands drugs on simulation and optimize doses). **Basis:** official related documentation. [Checked source](https://www.empa.ch/web/s604/personalized-medicine). ^f104

- **[OnePlanet — Human Digital Twin](https://www.oneplanetresearch.com/innovation/human-digital-twin)** · **[[#^f105|F105]]**

  **Resource description:** OnePlanet's Human Digital Twin program aims to integrate sensor/app health observations for individualized diet, lifestyle, and medication insights.

  **Research value (inference):** **IBD:** A gut-health/nutrition and longitudinal-platform research lead. **IQSEC2:** A personalized observation/platform research lead.

  **Boundary / reading question:** Official program aims, not demonstrated IBD/IQSEC2 effects or guaranteed data access.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT for diet optimization for individual). **Basis:** official documentation. [Checked source](https://www.oneplanetresearch.com/innovation/human-digital-twin/). ^f105

- **[DIGIPREDICT](https://www.digipredict.eu/outcomes)** · **[[#^f106|F106]]**

  **Resource description:** DIGIPREDICT describes edge-AI twins for infectious/cardiovascular disease progression and early intervention, with an outcomes page.

  **Research value (inference):** **IBD:** Project outputs and edge-monitoring design leads. **IQSEC2:** Project outputs and edge-monitoring design leads.

  **Boundary / reading question:** Inspect linked deliverables/publications individually; a consortium page is not an effectiveness trial.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: Prevention DT for cardiovascular and infections diseases). **Basis:** official documentation. ^f106

- **[Digital Twin Consortium — Healthcare & Life Sciences](https://www.digitaltwinconsortium.org/working-groups/healthcare)** · **[[#^f107|F107]]**

  **Resource description:** The Digital Twin Consortium healthcare/life-sciences working group addresses applicability, interoperability, and demonstration of DT value.

  **Research value (inference):** **IBD:** Terminology, architecture guidance, and community contacts. **IQSEC2:** Terminology, architecture guidance, and community contacts.

  **Boundary / reading question:** A professional working group, not a patient dataset or clinical validation study.

  **Origin:** [[Digital twins for health a scoping review|C]] (Key takeoffs; cue: DT4H consortium). **Basis:** official documentation. ^f107

## Source corrections and claims to verify

These corrections are recorded here; original review summaries and selection context are preserved. Follow-up checkboxes have been consolidated in [[Reading Backlog]], with references retained in the source notes.

| Original cue / claim | Finding from source checking | Treatment in this overview |
|---|---|---|
| A's short definition suggests a generic replica. | A, PDF p. 2, also describes real-time adaptation and closed-loop interaction. | Definition comparison incorporates the complete passage; A is not portrayed as rejecting dynamic coupling. |
| D note says six categories but lists five. | D, pp. 15–17, supplies a sixth dimension: domain diversification, human-centric design, and socio-technical transformation. | All six are included in the taxonomy. |
| B: “up to 25%” reduction in chronic-disease readmissions. | B, p. 2, cites references 19/20, which are a broad DT review ([[#^f009\|F009]]) and scoping review C ([[#^f065\|F065]]). No primary effect study was verified for this percentage. | Retain as an **unverified secondary claim**, not an established effect size for IBD/IQSEC2. |
| A: papers saved as DT quality/therapy benefits. | [[#^f010\|F010]]/[[#^f011\|F011]] concern precision medicine generally; [[#^f013\|F013]] concerns industrial maintenance. | Preserve them with their actual scope; do not present them as DT therapeutic-effect evidence. |
| A: coordinated-care example. | [[#^f018\|F018]] is a shipyard twin/thread framework. | Industrial methods section; possible traceability transfer only. |
| B: examples under tree ensembles / healthcare neural networks / patient RNN trajectories. | [[#^f053\|F053]]/[[#^f055\|F055]]/[[#^f056\|F056]]/[[#^f060\|F060]] concern engineering assets and structures; [[#^f057\|F057]] concerns iris anti-spoofing. | Reclassify by verified content; retain original selection context. |
| B: regression interpretability examples. | [[#^f047\|F047]] is cardiac HPC/in-silico trials; [[#^f048\|F048]] is longitudinal hemodynamic simulation. | Reclassify by verified abstracts. |
| B: general survival analysis for flare hazard. | [[#^f075\|F075]] is an RNMF-based colorectal-cancer prognosis framework trained with multidimensional data. | Retain as a potential modality-integration/time-to-event lead, without claiming an IBD survival-analysis result. |
| B: Arivale/type-2-diabetes framework. | [[#^f049\|F049]]'s saved full text uses the Arivale wellness cohort and concentrates on ML/knowledge-graph components; mechanistic integration is part of its proposed framework. | Correct the type-1-diabetes uncertainty in the dataset note's context here; avoid portraying a complete mechanistic DT as already implemented. |
| B: infant whole-body models might apply to IQSEC2. | [[#^f069\|F069]] models infant metabolism and inherited metabolic diseases. | Retain IQSEC2 relevance as exploratory methodological transfer. |
| D: chronic diet-related disease evidence. | [[#^f082\|F082]]'s four included studies all concern type 2 diabetes. | The review does not establish IBD effectiveness or generalization across diet-related diseases. |
| C: “Living brain” link, possibly EEG-based modeling. | [[#^f090\|F090]] is Mount Sinai's multimodal neuroscience study. C's bibliography names a Dassault Systèmes Living Brain project. | Retain the saved resource and distinguish the two identities; EEG-based twin reconstruction remains unverified. |
| C: personal wellness DT product examples. | Current [[#^f100\|F100]] is asset-management software; [[#^f101\|F101]] is anatomy/acupuncture education. [[#^f098\|F098]]/[[#^f099\|F099]] describe commercial personal-AI/health services. | Preserve current scope and original context; clinical-twin capabilities remain unverified. |
| B: unlinked lymphoma/QSP paper. | B reference 76 identifies Susilo et al., *Systems-based digital twins…mosunetuzumab…NHL*, DOI 10.1111/cts.13501. | Resolved and included as [[#^f110\|F110]]. |
| Bibliographic errors inside reviews. | A assigns [[#^f026\|F026]] a cardiovascular-review DOI. B reference 9 lists Vallée's title with the DOI of *Digital twins to personalize medicine*. | Use verified identities; do not propagate incorrect DOI pairings or merge different papers because a review reused a DOI. |

### Deduplication and completeness

- The original task inventory contains **113 task lines and 123 URL occurrences**, including task lines with multiple links and one task without a link. URLs were normalized while retaining meaningful query identifiers (e.g., the PLOS DOI).
- Repeated URLs were merged while retaining their origins and motivations. Publication identity additionally merged **F027 into [[#^f025|F025]]** (cardiovascular review), **F058 into [[#^f019|F019]]** (context-aware IoT paper), and **F066 into [[#^f049|F049]]** (type-2-diabetes framework with a trailing quote in the saved URL).
- The unlinked QSP task was identified as [[#^f110|F110]]. Every original linked item is represented by its retained entry or a documented merge. The website resources are included individually; none was discarded for being commercial, industrial, or outside either disease.
- Publications and resources can address several topics, but each appears once under a primary category. Original headings and comments retain secondary interests. [[#^f065|F065]] is already reviewed as C and is retained once in the follow-up inventory with that status.
- Descriptions marked **provisional** preserve identifiable leads whose abstracts could not be verified from primary sources. A provisional description should not be cited as a finding of the paper. Abstract screening is not full-text appraisal; commercial and project documentation provides claims/functions, not independent effectiveness evidence.
- Access/session query strings were removed from the Empa URL. The article identity and motivation are preserved without retaining an expiring access token.

### Next decisions when individual paper notes are created

Add links to the verified title/DOI, then appraise study design, population, observations, model assumptions, temporal/patient splitting, calibration, external evaluation, and demonstrated clinical coupling. For both IBD and IQSEC2, record separately what the paper demonstrates in its own domain and what remains a transfer hypothesis.
