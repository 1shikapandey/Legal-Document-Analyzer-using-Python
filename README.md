# Legal-Document-Analyzer-using-Python
Legal Document Analyzer – AI-Powered Clause Detection, Risk Assessment, and Summarization in Python
<br>
<br>
<br>


The **Legal Document Analyzer** is a Python-based application designed to **automate the review and risk assessment** of legal documents such as **contracts, agreements, and memoranda**. It leverages **Natural Language Processing (NLP)**, **pattern matching**, and **text summarization** techniques to:

* Extract **key clauses, entities, and legal concepts**
* Summarize lengthy documents into concise overviews
* Provide **objective signing recommendations** based on identified risks and favorable terms

It supports multiple document formats including **PDF, DOCX, and TXT**, making it versatile for various legal and compliance workflows.

---

## Key Features

* **Clause Identification** – Detects the presence and location of critical clauses such as confidentiality, indemnification, and governing law.
* **Entity Extraction** – Recognizes parties, organizations, monetary amounts, dates, and jurisdictions using both standard NLP and custom patterns.
* **Risk & Favorable Pattern Detection** – Highlights risky terms (e.g., *unlimited liability*) and favorable terms (e.g., *mutual termination*) with adjustable weights.
* **Summarization** – Generates concise summaries of long legal documents for quick understanding.
* **Scoring & Recommendations** – Produces a percentage-based favorability score along with actionable signing recommendations.
* **Customizable Rules** – Clause patterns, entity definitions, and scoring weights can be tailored for specific domains or risk tolerances.

---

## 📂 Use Cases

* **Contract Review** – Quickly highlight critical clauses, missing terms, and potential risks in business contracts.
* **Due Diligence** – Review large volumes of agreements for compliance and risk during mergers, acquisitions, or audits.
* **Negotiation Support** – Identify clauses that require renegotiation (e.g., one-sided terms, high-risk liability).
* **Legal Research** – Extract and summarize legal concepts for further analysis.
* **Document Summarization** – Provide clear, non-technical summaries for clients or executives.

---

## Technical Overview

### Libraries & Their Purpose

| Library            | Purpose                                                  |
| ------------------ | -------------------------------------------------------- |
| `re`               | Regular expressions for text and pattern matching        |
| `unicodedata`      | Unicode normalization for text cleaning                  |
| `PyPDF2`           | Reading and extracting text from PDF files               |
| `python-docx`      | Reading and extracting text from DOCX (Word) files       |
| `dataclasses`      | Structured data containers (`@dataclass`, `field`)       |
| `typing`           | Type hinting for function signatures and data structures |
| `spacy`            | NLP pipeline for entity recognition and tokenization     |
| `spacy.matcher`    | Custom pattern matching for legal entities and concepts  |
| `sumy.parsers`     | Parsing plain text for summarization                     |
| `sumy.nlp`         | Tokenization for summarization                           |
| `sumy.summarizers` | LSA-based text summarization                             |

---

## 🧩 Core Components

### **Class:** `LegalDocumentAnalyzer`

### **Data Class:** `AnalysisResult`

#### Main Methods:

* `__init__` – Initializes NLP models, clause/risk/favorable patterns
* `print_debug` – Debug messages for verbose mode
* `_add_custom_matcher_patterns` – Adds legal-specific entity patterns
* `clean_text` – Cleans and normalizes document text
* `load_document` – Loads documents by extension (PDF, DOCX, TXT)
* `_load_pdf` / `_load_docx` / `_load_text` – File-type specific text extraction
* `identify_clauses` – Finds key legal clauses via regex
* `extract_entities` – Extracts entities using spaCy NER + custom matchers
* `summarize_text` – Summarizes content using LSA summarization
* `calculate_signing_recommendation` – Scores favorability and identifies missing clauses
* `analyze` – Full analysis pipeline returning a structured result

---

## Example Workflow

1. **Input** – Upload a contract (`PDF`, `DOCX`, or `TXT`).
2. **Processing** – The analyzer:

   * Cleans text
   * Extracts clauses and entities
   * Summarizes content
   * Evaluates risk/favorable patterns
3. **Output** – Receive a structured report with:

   * Key clauses & locations
   * Parties, dates, monetary terms, jurisdictions
   * Document summary
   * Risk & favorable findings
   * Missing clauses
   * Signing recommendation with percentage score

---

## Benefits

* Speeds up document review
* Improves consistency in legal analysis
* Reduces manual effort for lawyers, compliance teams, and business professionals
* Customizable to match different industries and jurisdictions


