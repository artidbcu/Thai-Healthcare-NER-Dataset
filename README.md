# The Annotation of Thai Healthcare Terminology with SNOMED CT

**Authors:** Artid Boonrerng, Nouh Sabri Elmitwally, Edlira Vakaj, and Shadi Basurra  
**Affiliation:** Birmingham City University  
**Corresponding Author:** [artid.boonrerng@mail.bcu.ac.uk](mailto:artid.boonrerng@mail.bcu.ac.uk)  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0) 

---

## 🧠 Overview

This repository contains the datasets, annotation scripts, and documentation.

The dataset provides the **first comprehensive Thai healthcare corpus** annotated with **SNOMED CT** concept types.  
It was developed using a **rule-based word reconstruction algorithm** combined with **Typhoon 2.0**, a state-of-the-art Thai large language model (LLM), to enhance segmentation and ontology alignment in Thai medical text.

---

## 📦 Repository Contents

| File | Format | Description |
|------|---------|-------------|
| `thai_healthcare_bio.json` | JSON | BIO-tagged token-level dataset for NER models. |
| `thai_healthcare_instruction.json` | JSON | Instruction-format dataset for instruction-tuned LLMs. |
| `original_articles_metadata.csv` | CSV | Metadata of 500 Thai healthcare journal articles (title, abstract, keywords, journal, year, URI). |
| `snomed_mapping_guidelines.pdf` | PDF | Annotation and SNOMED CT mapping guidelines, including prompt templates for Typhoon 2.0. |
| `src/` | Folder | Python scripts for preprocessing, POS tagging, compound word reconstruction, SNOMED CT annotation, and BIO conversion. |

---

## 🧩 Dataset Description

The dataset contains:
- **166,849 Thai tokens**
- **9,022 annotated entity spans**
- **18 SNOMED CT top-level categories**

Each token is tagged using the standard **BIO (Begin–Inside–Outside)** scheme and aligned with **SNOMED CT** ontology types such as:

- *Body structure*
- *Clinical finding*
- *Environments and geographical locations*
- *Event*
- *Observable entity*
- *Organism*
- *Pharmaceutical/biologic product*
- *Physical force*
- *Physical object*
- *Procedure*
- *Qualifier value*
- *Record artifact*
- *Situation with explicit context*
- *Social context*
- *Special concept*
- *Specimen*
- *Staging and scales*
- *Substance*

All annotations were partially validated by **healthcare specialists** to ensure **semantic accuracy** and **clinical relevance**.

---

## 🧪 Methodology Summary

1. **Data Collection:**  
   500 Thai healthcare articles were retrieved from [Thai Journals Online (ThaiJO)](https://www.tci-thaijo.org/) between 2021–2024 (Tier 1 journals under TCI).

2. **Rule-Based Word Reconstruction:**  
   POS-tag sequences were analysed to reconstruct compound nouns (e.g., `NCMN + NPRP + VACT`).  
   Algorithm achieved **F1 = 0.61** at threshold 0.4.

3. **Annotation with SNOMED CT:**  
   The **Typhoon 2.0** model was prompted with structured JSON templates to map terms to SNOMED CT categories.

4. **BIO and Instruction Dataset Creation:**  
   Annotations were converted to BIO format for token-level NER and instruction–response format for LLM fine-tuning.

5. **Manual Validation:**  
   Review by three medical domain experts achieved **accuracy = 68.81%**, confirming semantic correctness and practical reliability.

---

## 📊 Technical Validation

| Metric | Score |
|---------|-------|
| Precision | 0.89 |
| Recall | 0.69 |
| F1 Score | 0.75 |
| Manual validation accuracy | 68.81% |
| Compound noun reconstruction F1 | 0.61 |

Validation confirms the dataset’s quality and suitability for both **sequence labelling** and **instruction-tuned learning** tasks in Thai healthcare NLP.

---

## 💡 Use Cases

- Thai medical **Named Entity Recognition (NER)**  
- **Ontology-aware** NLP systems aligned with SNOMED CT  
- **Fine-tuning** of Thai instruction-following LLMs (e.g., Typhoon 2.0, Mistral-7B-Instruct)  
- **Knowledge Graph** construction and clinical term normalization  
- **Cross-lingual** research for low-resource healthcare NLP  

---

## Acknowledgements

We gratefully acknowledge:
- **Dr. Sopida Wongwas**, Life Sciences (University of Warwick)
- **Dr. Pollasak Worakrai**, M.D. (Khon Kaen University)
- **Dr. Thapanee Thumachart**, D.D.S. (Prince of Songkla University)

for their expert validation of SNOMED CT mappings and entity accuracy.

---

⚖️ License

This dataset and code are released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** and **MIT License** respectively.
You are free to use, modify, and share the materials with proper attribution.

---

🔗 Related Resources

- [Thai Journals Online (ThaiJO)](https://www.tci-thaijo.org/)
- [SNOMED CT Concept Model](https://www.snomed.org/)
- [Typhoon 2.0 Model](https://huggingface.co/scb10x)
- [PyThaiNLP Library](https://github.com/PyThaiNLP/pythainlp)

---

🧭 Contact

**Artid Boonrerng**
PhD Student, School of Computing and Digital Technology, Birmingham City University

📧 artid.boonrerng@mail.bcu.ac.uk
