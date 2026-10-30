---
title: Digital Twins in healthcare a comprehensive review and future directions
date: 2026-10-05
tags:
  - "#digitalTwin"
  - "#review"
---

> [!info] Follow-up reading
> Task status is maintained in [[Reading Backlog]]. The original selection comments and links below are retained as references to that backlog.

## Brief Overview
An overview about digital twins in healthcare. Defines various types of DT4H implementations like physics-based modeling approaches, statistical learning algorithms, neural network-based control systems and emerging AI techniques. DT4H enables **patient-specific modeling**. Mostly source of existed approaches and definition of current research gaps. 

## Source paper

![[fdgth-07-1633539.pdf]]

## Key takeoffs
- Have a lot of specific cancer applications. Omitted for now due the lack of cancer case project
- Highly cited paper across this review: https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2024.1336050/full
- Contains also DT methodology chapter which structures as follows:
	- Data collection and integration, from sensor-based monitoring to EHR, but they didn't mentioned omics (real-time streaming employs cloud based analytics using frameworks as Kafka Apache and Message Queuing Telemetry Transport, allows efficiently handle high velocity data)
	- A chapter about perturbation cell datasets and prediction approaches. Not needed now, but maybe in future
	- and on perturbation it ends, kinda confusing chapter title, because they discussed only initial data (without omics) in general and later focused on cell perturbation only 
- DT limitations:
	- data quality and availability - need longitudinal datasets with multiple physiological parameters. If they exist, often it discriminate rare diseases or population
	- Computational constraints - this problem is mostly for physics-based models. I think that model retraining in stream learning on cloud is not quite a problem.
	- Implementation complexity - one of the biggest challenges in this domain is to integrate with current, legacy healthcare systems
	- Validation challanges, and they directly pointed that such standardized validations don't exist 
	- Privacy and security sratatata
	- Digital equity - overrepresentation of specific populations, digital skills gap etc. 
	- regulations
- Future opportunities:
	- Enhancing personalization - mostly by diverse data modalities integration from omics to social determinants of health, transformed into holistic patient representations
	- Improve prediction accuracy - "The integration of sophisticated ML architectures with mechanistic models promises to combine the pattern recognition strengths of AI with the biological plausibility of physics-based approaches" (need to check how to estabilish physic-based representation based on eg. omics and EHR)
	- Expanded application areas- Cardiovascular, neurological and oncological applications currently dominates DT landscape. They've pointed promising areas as autoimmune disordes, psychiatric conditions, pediatric development and geriatric syndromes and population based DT. Also simulations for gene therapies utilizing CRISPR

## Follow-up papers
#### Patient-specific modeling:
- https://link.springer.com/article/10.1186/s13073-019-0701-3 #reading — [[Reading Backlog#^read-f029|F029 · backlog]]
- https://onlinelibrary.wiley.com/doi/10.1002/9781394287420.ch5 #reading  — [[Reading Backlog#^read-f030|F030 · backlog]]
- https://www.mdpi.com/2076-3417/13/13/7940 #reading  — [[Reading Backlog#^read-f031|F031 · backlog]]
- https://www.sciencedirect.com/science/article/pii/S1471490623000480?via%3Dihub #reading  — [[Reading Backlog#^read-f032|F032 · backlog]]
- https://www.mdpi.com/2075-4426/12/5/742 #reading  — [[Reading Backlog#^read-f033|F033 · backlog]]

#### Real-time monitoring: 
- https://www.semanticscholar.org/paper/Towards-continuous-monitoring-in-personalized-twins-Rivera-Jim%C3%A9nez/b10c13e2d67cc74914ea38f29067a6e0ce0a5a34 — [[Reading Backlog#^read-f034|F034 · backlog]]
- https://www.researchgate.net/publication/340466788_Digital_Twins_for_Precision_Healthcare — [[Reading Backlog#^read-f035|F035 · backlog]]
- https://www.nature.com/articles/s41598-024-62567-1 — [[Reading Backlog#^read-f036|F036 · backlog]]

#### Enhanced Decision support
- https://royalsocietypublishing.org/rsos/article/9/8/220638/96716/Causal-machine-learning-for-healthcare-and — [[Reading Backlog#^read-f037|F037 · backlog]]
- https://www.nature.com/articles/s42256-023-00611-x — [[Reading Backlog#^read-f038|F038 · backlog]]

#### Longitudinal health management
- https://www.jmir.org/2022/10/e39698 — [[Reading Backlog#^read-f039|F039 · backlog]]
- https://www.mdpi.com/1424-8220/22/15/5918 — [[Reading Backlog#^read-f040|F040 · backlog]]

#### DT for Drug development 
- https://www.nature.com/articles/s41592-023-02144-y — [[Reading Backlog#^read-f041|F041 · backlog]]
- https://proceedings.mlr.press/v177/squires22b.html — [[Reading Backlog#^read-f042|F042 · backlog]]
- https://proceedings.mlr.press/v236/rohbeck24a.html — [[Reading Backlog#^read-f043|F043 · backlog]]
- https://www.sciencedirect.com/science/article/pii/S2405471220304646?via%3Dihub — [[Reading Backlog#^read-f044|F044 · backlog]]
- https://www.frontiersin.org/journals/physiology/articles/10.3389/fphys.2017.00668/full — [[Reading Backlog#^read-f045|F045 · backlog]]
- https://ieeexplore.ieee.org/document/9108291 — [[Reading Backlog#^read-f046|F046 · backlog]]

#### Regression models fo interpretability in DT:
- https://pubmed.ncbi.nlm.nih.gov/37702946/ — [[Reading Backlog#^read-f047|F047 · backlog]]
- https://www.nature.com/articles/s41746-024-01216-3 — [[Reading Backlog#^read-f048|F048 · backlog]]
- https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2024.1336050/full — [[Reading Backlog#^read-f049|F049 · backlog]]
- https://www.mdpi.com/2076-3417/12/16/8156 — [[Reading Backlog#^read-f050|F050 · backlog]]

#### Tree-based ensemble methods applications:
- https://www.mdpi.com/2076-3417/11/12/5576 — [[Reading Backlog#^read-f023|F023 · backlog]]
- https://www.mdpi.com/2306-5354/10/4/455 — [[Reading Backlog#^read-f051|F051 · backlog]]
- https://dl.acm.org/doi/abs/10.1109/TCBB.2023.3252668 — [[Reading Backlog#^read-f052|F052 · backlog]]
- https://www.sciencedirect.com/science/article/pii/S0888327019308337?via%3Dihub — [[Reading Backlog#^read-f053|F053 · backlog]]
- https://www.researchgate.net/publication/367504395_Artificial_intelligence_models_in_digital_twins_for_health_and_well-being — [[Reading Backlog#^read-f054|F054 · backlog]]
- https://ieeexplore.ieee.org/document/9547763 — [[Reading Backlog#^read-f055|F055 · backlog]]

#### Neural Networks for high dimensional healthcare data:
- https://www.sciencedirect.com/science/article/pii/S235201242301336X — [[Reading Backlog#^read-f056|F056 · backlog]]
- https://link.springer.com/article/10.1007/s11042-021-11578-5 — [[Reading Backlog#^read-f057|F057 · backlog]]
- https://ieeexplore.ieee.org/document/9320532 — [[Reading Backlog#^read-f019|F019 · backlog]]
- https://royalsocietypublishing.org/rsta/article/383/2292/20240228/108445/Control-of-medical-digital-twins-with-artificial — [[Reading Backlog#^read-f059|F059 · backlog]]
RNN in time-series problems such as patient trajectories:
- https://www.repository.cam.ac.uk/items/331396a5-f4c4-46c7-8d6c-4dc876cab24b — [[Reading Backlog#^read-f060|F060 · backlog]]
- https://www.semanticscholar.org/paper/Towards-continuous-monitoring-in-personalized-twins-Rivera-Jim%C3%A9nez/b10c13e2d67cc74914ea38f29067a6e0ce0a5a34 — [[Reading Backlog#^read-f034|F034 · backlog]]
#### Methods in building DT:
Data collection and integration:
- IoT devices enables early detection of potential problems: https://link.springer.com/article/10.1007/s11277-023-10528-8 (could contain info about wearable golden standard, beacuse it reviews many existed solutions) — [[Reading Backlog#^read-f061|F061 · backlog]]
- https://www.mdpi.com/1424-8220/23/23/9498 — [[Reading Backlog#^read-f062|F062 · backlog]]
- https://www.sciencedirect.com/science/article/pii/S2405844024025349?via%3Dihub — [[Reading Backlog#^read-f063|F063 · backlog]]


- digital twin for precision cardiac case example https://academic.oup.com/eurheartj/article/41/48/4556/5775673 — [[Reading Backlog#^read-f021|F021 · backlog]]
- Preventive aspect of DT4H https://link.springer.com/article/10.1186/s13073-019-0701-3 — [[Reading Backlog#^read-f029|F029 · backlog]]
- testowanie terapii na cyfrowej kopii: https://link.springer.com/article/10.1007/s11548-023-02863-9 — [[Reading Backlog#^read-f064|F064 · backlog]]
- Digital twin could reduce hospital readmission by up to 25% for certain chronic diseases: https://www.sciencedirect.com/science/article/pii/S2949723X23000065?via%3Dihub https://www.nature.com/articles/s41746-024-01073-0 — [[Reading Backlog#^read-f009|F009 · backlog]] · [[Reading Backlog#^read-f065|F065 · backlog]]
- 'For type 2 diabetes, comprehensive frameworks combining ML, multiomic data and knowledge graphs have enhanced predictive accuracy for disease trajectories and treatment responses: ⏫ https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2024.1336050/full' performed on [[Arivale]] dataset and SPOKE knowledge graph: https://spoke.ucsf.edu/home — [[Reading Backlog#^read-f049|F049 · backlog]] · [[Reading Backlog#^read-f067|F067 · backlog]]
- DT checking before and after fasting metabolic responses: https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1010469 — [[Reading Backlog#^read-f068|F068 · backlog]]
- "Sex specific, personalized metabolic whole-body models (WBMs) have been developed for newborns and infants (IQSEC2 application maybe)": linkinghub.elsevier.com/retrieve/pii/S1550413124001827  — [[Reading Backlog#^read-f069|F069 · backlog]]
- systems-based DT approach for characterizing dose-response relationships in non-hodkin lymphoma, using quantitative systems pharmacology (QSP) to generate virtual patients — [[Reading Backlog#^read-f110|F110 · backlog]]
- genetic dynamics: https://www.pnas.org/doi/full/10.1073/pnas.1203559109 — [[Reading Backlog#^read-f070|F070 · backlog]]
- patient digital twin for healthcare education: doi.org/10.3389/fmed.2023.1336897 — [[Reading Backlog#^read-f071|F071 · backlog]]
- -,- simalar, but for surgicals case: https://jamanetwork.com/journals/jamasurgery/article-abstract/2748068 — [[Reading Backlog#^read-f072|F072 · backlog]]
- LLM in DT, TWIN-GPT: https://dl.acm.org/doi/10.1145/3674838 , as transfer learning approach, when we don't have enough data — [[Reading Backlog#^read-f073|F073 · backlog]]
- FHIR: https://medinform.jmir.org/2022/7/e35724  — [[Reading Backlog#^read-f074|F074 · backlog]]
- Survival analysis, estimates hazard functions for time-to-event data while handling censored observations: https://onlinelibrary.wiley.com/doi/10.1002/mef2.27 (eg. flare hazard estimation in IBD) — [[Reading Backlog#^read-f075|F075 · backlog]]
- Review about biomarker identification using ML and DL: https://link.springer.com/article/10.1007/s11831-022-09821-9 — [[Reading Backlog#^read-f076|F076 · backlog]]
- Paper about TabPFN use on small medical dataset ⏫ https://www.nature.com/articles/s41586-024-08328-6 (They said that it outperforms treebased models referencing original paper, where I didn't found any proves or examples) — [[Reading Backlog#^read-f077|F077 · backlog]]
- In silico clinical trails: https://ieeexplore.ieee.org/document/8884189 — [[Reading Backlog#^read-f078|F078 · backlog]]
