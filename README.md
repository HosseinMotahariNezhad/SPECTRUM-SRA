# SPECTRUM SRA: Systematic Review Automation

[![Live App](https://img.shields.io/badge/🚀%20Launch-Live%20App-success)](https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRISMA 2020](https://img.shields.io/badge/PRISMA-2020-orange)](http://www.prisma-statement.org/)
[![Platform](https://img.shields.io/badge/Platform-Web-blue)](https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/)
[![Source](https://img.shields.io/badge/Source-Closed%20(available%20on%20request)-lightgrey)](#source-code-availability)

> **▶️ Try the live application:** [**https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/**](https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/)

---

## Abstract

**SPECTRUM SRA** is an interactive, browser-based web application designed to automate and streamline the workflow of **systematic reviews and meta-analyses**. It integrates eight core modules — **S**earch, **P**RISMA diagram, d**E**duplication, s**C**reening, da**T**a extraction, **R**eporting, q**U**ery, and su**M**marization — into a single, reproducible pipeline.

The application supports end-to-end evidence synthesis: from PICO-based inclusion/exclusion criteria and automated MeSH term retrieval, to query generation for **PubMed**, **Scopus**, and **Web of Science**, dual-reviewer screening with automatic **Cohen's Kappa** calculation, deduplication (DOI-based and fuzzy), generation of publication-ready **PRISMA 2020 flow diagrams**, and structured data extraction with optional LLM assistance.

SPECTRUM SRA is intended for systematic reviewers, evidence synthesis methodologists, information specialists, and academic researchers who require a transparent, citable, and reproducible tool that reduces manual workload without sacrificing methodological rigor.

---

## ⚠️ Source Code Availability

**This repository hosts documentation, citation, and release information only.**

The source code of SPECTRUM SRA is **not publicly distributed**. The full application is freely accessible as a hosted web service at:

> **https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/**

Academic and non-commercial access to the source code may be granted upon reasonable request to the authors (see *Contact* below). Requests should state the intended use (research, teaching, or collaboration).

---

## Key Features

| Module | Description |
|--------|-------------|
| **Inclusion & Exclusion Criteria** | Structured PICO input propagated across the entire workflow. |
| **MeSH Term Extraction** | Automated mapping of PICO elements to PubMed MeSH descriptors with n-gram phrase extraction and parallel fetching. |
| **Keyword Identification** | Upload PDFs to extract top uni-, bi-, and tri-grams using text-mining techniques. |
| **Multi-Group Query Builder** | Up to 5 Boolean groups (× 5 terms each), with date range, language, document type, sex, species, and age-group filters. |
| **Database Query Translation** | Generates equivalent, syntax-correct queries for PubMed, Scopus, and Web of Science. |
| **Automated Search Execution** | Direct API retrieval from PubMed and Scopus; one-click launch into Web of Science. |
| **Deduplication** | Exact DOI matching + fuzzy string matching for DOI-less records. |
| **Dual-Reviewer Screening** | 1 or 2 independent reviewers at title/abstract and full-text stages, with automatic disagreement detection and Cohen's Kappa. |
| **PRISMA 2020 Flow Diagram** | Auto-generated, editable, publication-quality diagram with high-resolution JPEG export. |
| **Search & Screening Reports** | Auto-generated textual summaries of yield, duplicates, screening outcomes, and Kappa. |
| **LLM-Assisted Data Extraction** | Structured ChatGPT/GPT-4 prompts covering 16 extraction fields. |

---



---

## How to Use

1. **Open the app:** [https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/](https://motaharinezhad.shinyapps.io/SPECTRUM_SRA/)
2. **Define criteria:** Enter PICO elements under *Inclusion & Exclusion Criteria*.
3. **Identify keywords (optional):** Upload PDFs to extract frequent terms, or fetch MeSH descriptors.
4. **Build the search:** Use *Search* to construct Boolean groups and apply filters.
5. **Generate queries:** Visit *Search Queries* to obtain PubMed / Scopus / WoS equivalents.
6. **Run searches:**
   - PubMed — no API key required.
   - Scopus — enter a free [Elsevier API key](https://dev.elsevier.com/).
   - Web of Science — click *Run in WoS* to launch.
   - Other databases — upload using the provided template.
7. **Merge and deduplicate** by DOI, then by fuzzy matching.
8. **Screen** with 1 or 2 reviewers via downloadable/uploadable `.xlsx` templates.
9. **Resolve disagreements** — the app computes Cohen's Kappa.
10. **Generate the PRISMA diagram** and export as JPEG.
11. **Extract data** with the built-in LLM prompt.

---

## Methodology

SPECTRUM SRA operationalizes **PRISMA 2020** and standard Cochrane / JBI workflows:

- **MeSH mapping** via NCBI E-utilities.
- **Query translation** from a canonical PubMed query to Scopus (`TITLE-ABS-KEY`, `PUBYEAR`, `DOCTYPE`, `LANGUAGE`) and Web of Science (`TS=`, `PY=`, `DT=`, `LA=`) syntax.
- **Two-stage deduplication:** exact DOI matching, then fuzzy matching on normalized title, first-author surname + initial, and abbreviated journal name.
- **Inter-rater reliability** via **Cohen's Kappa**:
  κ = (P₀ − Pₑ) / (1 − Pₑ)
- **PRISMA flow diagram** rendered with a fixed column layout matching the PRISMA 2020 template.

---

## Data Sources & APIs

| Source | Access | Notes |
|--------|--------|-------|
| PubMed | NCBI E-utilities | No key required |
| Scopus | Elsevier API | Free key from [dev.elsevier.com](https://dev.elsevier.com/) |
| Web of Science | Manual launch | Requires institutional subscription |
| Other databases | Excel/CSV template | User-supplied |

**Privacy notice:** All user data is processed in-session and is **not stored** on the server. Scopus API keys are used only for the duration of a request.

---

## Citation

If you use SPECTRUM SRA in your research, please cite:

> Motahari Nezhad, H., & Cheshmehsohrabi, M. (2025). *SPECTRUM SRA: An Interactive Web Application for Systematic Review Automation* [Computer software]. University of Isfahan. https://doi.org/10.5281/zenodo.XXXXXXX

A machine-readable `CITATION.cff` is included in this repository. GitHub will display a **"Cite this repository"** button in the sidebar.

---

## License

This project is distributed under the **MIT License** — see [`LICENSE`](LICENSE).

> Note: The license applies to the **documentation, screenshots, and metadata** in this repository. The application source code is separate and is **not** distributed under this license; see *Source Code Availability* above.

---

## Authors & Contact

| Role | Name | Affiliation |
|------|------|-------------|
| **Developer** | Hossein Motahari Nezhad | Department of Knowledge and Information Science, University of Isfahan, Iran |
| **Supervisor** | Dr. Mehrdad Cheshmehsohrabi | Professor, Department of Knowledge and Information Science, University of Isfahan, Iran |

**Email:** h.motahari.lib@gmail.com · h.motaharinezhad@edu.ui.ac.ir

For source-code access requests, please email with subject line: `SPECTRUM SRA — Source Code Request`.

---

## Acknowledgments

We thank the University of Isfahan for institutional support.

---

## Disclaimer

SPECTRUM SRA assists — but does not replace — human judgment in systematic reviews. LLM-generated summaries and suggested decisions must be verified by the reviewer.
