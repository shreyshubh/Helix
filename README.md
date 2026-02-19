# 🧬 HELIX 
### Explainable AI-Powered Pharmacogenomic Risk Assessment Platform

---

## 📌 Overview

**HELIX** is a HealthTech decision-support system that analyzes a patient’s genetic variants to predict **drug-specific risks** using **pharmacogenomics**.

It addresses a critical challenge in modern medicine:

> *The same drug can be safe for one patient and harmful for another due to genetic differences.*

By combining **genetic data (VCF files)**, **rule-based pharmacogenomic logic**, and **AI-generated explanations**, PharmaGuard helps reduce adverse drug reactions and supports safer, personalized prescribing decisions.

⚠️ **Disclaimer:** PharmaGuard is a **clinical decision-support prototype**, not a diagnostic tool.

---

## 🚨 Problem Statement

Adverse Drug Reactions (ADRs) are a major global healthcare issue. Many ADRs occur because:

- Patients metabolize drugs differently
- Genetic variants affect drug activation, breakdown, and toxicity
- Raw genomic data is difficult for clinicians to interpret
- Prescriptions are often based on population averages

These reactions are often **preventable** with proper pharmacogenomic analysis.

**HELIX bridges this gap** by translating raw genetic data into **clear, explainable, and drug-specific risk insights**.

---

## 🧠 Scientific Background (Simplified)

- Genes act as instructions to produce enzymes
- Enzymes process drugs in the body
- Genetic variants can:
  - Reduce enzyme activity
  - Eliminate enzyme function
  - Increase enzyme activity
- This directly affects:
  - Drug safety
  - Drug effectiveness
  - Required dosage

PharmaGuard focuses on **six clinically critical pharmacogenomic genes**:

- CYP2D6  
- CYP2C19  
- CYP2C9  
- SLCO1B1  
- TPMT  
- DPYD  

These genes are well-known for influencing commonly prescribed medications.

---

## 🎯 Key Features

- Upload **VCF (Variant Call Format)** genetic files  
- Input one or multiple drug names  
- Identify pharmacogenomic variants  
- Classify drug risk:
  - Safe
  - Adjust Dosage
  - Toxic
  - Ineffective
  - Unknown  
- Calculate an **evidence-weighted confidence score**  
- Generate **AI-assisted biological explanations**  
- Suggest safer alternative drugs (when applicable)  
- Clean, minimal, clinician-friendly frontend  

---

## 🏗️ System Architecture

HELIX follows a **three-layer clinical decision-support architecture**:

Frontend (React + Vite)
↓
Backend API (Node.js + Express)
↓
Pharmacogenomic Logic Engine (Rules + AI)


### Layer Responsibilities

**Frontend**
- VCF file upload
- Drug input
- Risk visualization
- Confidence display
- Explainable results dashboard

**Backend (Node.js)**
- API gateway
- Input validation
- File handling
- Request orchestration
- Response formatting

**Pharmacogenomic Engine**
- Variant interpretation
- Gene–drug rule evaluation
- Risk classification
- Confidence scoring
- AI-based explanation generation

---

## 🔁 Data Flow

1. User uploads a VCF file and enters drug names  
2. Frontend sends data to backend API  
3. Backend parses and validates inputs  
4. Genetic variants are extracted  
5. Gene–drug rules are applied  
6. Risk and confidence are calculated  
7. AI generates a clear explanation  
8. Results are returned and visualized  

---

## 📥 Input Requirements

### 1️⃣ VCF File
- Format: **VCF v4.2**
- Maximum size: **5 MB**
- Required INFO tags:
  - `GENE`
  - `STAR`
  - `RS`

### 2️⃣ Drug Input
- Single or comma-separated drug names
- Supported drugs:
  - CODEINE
  - WARFARIN
  - CLOPIDOGREL
  - SIMVASTATIN
  - AZATHIOPRINE
  - FLUOROURACIL

---

## 📤 Output

For each drug, PharmaGuard provides:
- Risk classification
- Severity level
- Confidence score (0–1)
- Genetic variants involved
- Explainable biological reasoning
- Optional safer drug alternatives

All outputs follow a **strict JSON schema** for consistency and interoperability.

---

## 🧪 Example Use Case

- Patient uploads genetic test results (VCF)
- Clinician enters **CODEINE**
- System detects a CYP2D6 loss-of-function variant
- Codeine is flagged as **toxic**
- Explanation describes the biological mechanism
- Safer alternatives are suggested

---

## 🛠️ Tech Stack

### Frontend
- React
- Vite
- Tailwind CSS

### Backend
- Node.js
- Express.js

### Pharmacogenomic Engine
- Python
- FastAPI
- Rule-based logic
- LLM for explainable AI output

---

## 🚀 Local Setup

### Backend (Node.js)
```bash
cd backend
npm install
npm start
Backend (Python)
cd backend-python
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
Frontend
cd frontend
npm install
npm run dev
⚠️ Limitations
Limited to predefined genes and drugs

Rule-based pharmacogenomic knowledge

Prototype for research and decision support

Not a replacement for professional medical judgment

🔮 Future Scope
EHR system integration

Expanded gene and drug coverage

Batch patient analysis

Clinician audit logs

Regulatory-grade validation


📜 Disclaimer
HELIX is a research and clinical decision-support prototype.
It does not diagnose diseases or replace professional medical judgment.
