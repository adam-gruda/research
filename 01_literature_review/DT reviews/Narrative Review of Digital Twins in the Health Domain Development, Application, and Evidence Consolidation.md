---
title: Narrative Review of Digital Twins in the Health Domain Development, Application, and Evidence Consolidation
date: 2026-10-05
tags:
  - "#digitalTwin"
  - "#review"
---

> [!info] Follow-up reading
> Task status is maintained in [[Reading Backlog]]. The original selection comments and links below are retained as references to that backlog.

## Brief Overview
They defined DT4H as a dynamic, adaptive system, which evolves alongside with the patient (or other entitiy). Presenting three sections as a review results: emerging themes, maturity across applications and key limitations and conceptual issues. Very clearly organize reviewed articles in table and categorize them. 

## Source paper

![[medsci-14-00330-v3.pdf]]
## Key takeoffs
- Current DT splits into to approaches: 
	- simulation-oriented models - primarly used for scenario testing and predictive analysis
	- monitoring-oriented systems - that continuously ingest patient data, up to more exploratory constructs that remain loosely coupled with individual patients and are mainly used for research purposes
- We can characterize DT in levels:
	- hierarchical - cellular, organ, patient, population
	- functional purpose - simulation, monitoring, prediction, optimization
	- maturity stage - conceptual prototypes, partially validated clinical tools
- digital twin/ virtual patient/ in silico paitent/ patient specific model/ digital human/ virtual replica
- A first dominant theme is the shift toward continuous, data-driven patient representation, where DTS act as dynamic entities updated through real-time or near real-time data streams
- Defined six categories to which DT4H contributes: 
	- **Continuous & Personalized Patient Representation:** Models individual health longitudinally via physiological, behavioral, and wearable data to enable adaptive self-care and early complication detection.
	- **Predictive & Simulation-Based Healthcare:** Leverages AI and mechanistic models to forecast disease progression, predict therapy responses, and run _in-silico_ clinical trials.
	- **Procedural & Interventional Support:** Enhances surgical planning, intraoperative navigation, and rehabilitation through XR, 3D/4D modeling, and advanced imaging.
	- **Integration within Digital Health Ecosystems:** Connects DTs with broader AI, IoT, and blockchain infrastructures to ensure secure data governance, interoperability, and cross-system workflows.
	- **Implementation, Scalability & System-Level Impact:** Identifies systemic adoption barriers—from regulatory and infrastructure readiness to digital divide challenges—requiring coordinated healthcare governance. Use Human-centric design
- Pointed a problem, that more data may introduce more noise rather than a signal, but it's should be documented in Stream Learning concepts how to address this problems
- goal of DT4H is not to be better than data analysis or state classification based on traditional methods, but to create a bidirectional dynamic system, which automatically updates while new data comes
- > [!PDF|important] [[medsci-14-00330-v3.pdf#page=24&selection=28,0,29,47&color=important|their value emerges from the orchestration of heterogeneous technologies rather than from any single data source or algorithmic component]]
> their value emerges from the orchestration of heterogeneous technologies rather than from any single data source or algorithmic component

> [!PDF|important] [[medsci-14-00330-v3.pdf#page=24&selection=50,71,57,85&color=important|digital twins are not reducible to large-scale data aggregation systems, but instead represent evolving cyber-physical and computational representations of patients and healthcare processes. While challenges remain regarding validation, standardization, and clinical translation, the convergence of evidence across multiple domains supports the interpretation of DTS as a distinct paradigm of data–model integration, in which the primary innovation lies in transforming heterogeneous data into executable, continuously updated simulation systems capable of informing both individual care and population-level healthcare strategies.]]
> digital twins are not reducible to large-scale data aggregation systems, but instead represent evolving cyber-physical and computational representations of patients and healthcare processes. While challenges remain regarding validation, standardization, and clinical translation, the convergence of evidence across multiple domains supports the interpretation of DTS as a distinct paradigm of data–model integration, in which the primary innovation lies in transforming heterogeneous data into executable, continuously updated simulation systems capable of informing both individual care and population-level healthcare strategies.

> ([[medsci-14-00330-v3.pdf#page=26&selection=55,0,63,49&color=yellow|From a historical perspective, several secondary studies highlight that the conceptual foundations of digital twinning in medicine are not recent. Early forms of patientspecific anatomical and physiological modeling, including 3D vascular reconstructions and simulation-based phantoms, already demonstrated the feasibility of individualized digital representations for clinical planning and procedural simulation [49]. This evidence supports the interpretation of DTS as an evolutionary extension of biomedical modeling rather than an abrupt technological discontinuity]])
> From a historical perspective, several secondary studies highlight that the conceptual foundations of digital twinning in medicine are not recent. Early forms of patientspecific anatomical and physiological modeling, including 3D vascular reconstructions and simulation-based phantoms, already demonstrated the feasibility of individualized digital representations for clinical planning and procedural simulation [49]. This evidence supports the interpretation of DTS as an evolutionary extension of biomedical modeling rather than an abrupt technological discontinuity

- Functioning DT in healthcare system is problematic, because we can literally store infinity amount of wearable, PRO dynamic data. Here goes a question, how much old data we need in model and at which point we can aggregate it and in which form?

Recommendations for DT4H studies:
- **R1. Broader disease coverage and population diversity:** Expand digital twin applications beyond currently dominant domains such as diabetes, cardiology, and neuro-oncology toward multimorbidity, reproductive health, radiology ecosystems, and population-level healthcare systems.
    
- **R2. Standardization and reproducibility:** Develop internationally agreed frameworks for model development, reporting, validation, and open science practices, including code and dataset sharing to improve reproducibility and comparability.
    
- **R3. Integration of emerging technologies:** Strengthen convergence between artificial intelligence, wearable systems, omics technologies, edge computing, and immersive environments to support real-time and adaptive digital twin ecosystems.
    
- **R4. Ethical and governance frameworks:** Establish robust, scalable, and regulationaligned frameworks for data ownership, privacy, consent, security, and responsible data monetization in DT-based healthcare systems.
    
- **R5. Longitudinal and real-world validation:** Prioritize prospective, multi-center, and real-world clinical studies that move beyond simulation-based evidence toward outcome-driven evaluation of effectiveness and safety.
    
- **R6. Interoperability and scalability:** Address structural barriers related to crossplatform integration, semantic interoperability, and scalable deployment across heterogeneous healthcare infrastructures

## Follow-up papers
- Classification and topology od DT: https://www.sciencedirect.com/science/article/pii/S2542660524003202?via%3Dihub — [[Reading Backlog#^read-f079|F079 · backlog]]
- European Virtual Human Twins: https://www.virtualhumantwins.eu/ — [[Reading Backlog#^read-f080|F080 · backlog]]
- Deep learning on EHR: https://pubmed.ncbi.nlm.nih.gov/31304302/ — [[Reading Backlog#^read-f081|F081 · backlog]]
- DT in chronic diseases related with diet: https://pubmed.ncbi.nlm.nih.gov/41880918/ — [[Reading Backlog#^read-f082|F082 · backlog]]
- Self learning aspect of predictive DT using AI: https://pubmed.ncbi.nlm.nih.gov/41596449/, https://pubmed.ncbi.nlm.nih.gov/40898015/ — [[Reading Backlog#^read-f083|F083 · backlog]] · [[Reading Backlog#^read-f084|F084 · backlog]]
- XR in rehabilitation using digital human modeling: https://pubmed.ncbi.nlm.nih.gov/40144388/ — [[Reading Backlog#^read-f085|F085 · backlog]]
- DT in chronic heart diseases: https://pubmed.ncbi.nlm.nih.gov/37571678/ — [[Reading Backlog#^read-f086|F086 · backlog]]