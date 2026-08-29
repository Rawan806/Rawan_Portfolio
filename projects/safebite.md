# SafeBite — AI-Assisted Food Safety System

## Overview

SafeBite is a bilingual AI-assisted food-label screening system designed to help children with celiac disease and their parents make safer decisions when checking packaged food products.

Users can scan a product barcode or upload an image of the package. The system analyzes available product and ingredient information and classifies the result as:

- **Safe**
- **Unsafe**
- **Needs Verification**

If a product is classified as unsafe, the system can also suggest safer alternatives from the same product category.

SafeBite is designed as a decision-support system rather than a medical or regulatory certification tool.

## My Contribution

I own the end-to-end development of SafeBite, covering the mobile application, backend services, product data pipeline, OCR workflow, rule-based ingredient screening, AI fallback logic, evaluation, and system integration.

My work includes:

- Flutter mobile development and Firebase integration
- FastAPI backend development
- Barcode lookup and product-data processing
- OCR-based ingredient extraction
- Deterministic gluten-related ingredient screening
- Gemini-based reasoning for unresolved cases
- Evaluation of multilingual ingredient classification approaches
- Product alternative recommendation logic

## Technical Approach

SafeBite follows a conservative, rule-first pipeline.

1. The user scans a barcode using ML Kit.
2. The system attempts to retrieve structured product information.
3. If product data is unavailable, package images can be processed using OCR.
4. Google Cloud Vision extracts readable ingredient text.
5. An OCR quality gate checks whether the extracted evidence is usable.
6. Deterministic ingredient rules are applied before any LLM reasoning.
7. Gemini 2.5 Flash is used only when readable evidence remains ambiguous.
8. The system returns Safe, Unsafe, or Needs Verification.

Unreadable or insufficient evidence is not guessed; it is explicitly classified as **Needs Verification**.

## Data & Evaluation

- Collected and processed **22K+ SFDA barcode records** for product lookup and enrichment workflows.
- Prepared a manually labeled benchmark of **80 ingredient cases** across the three decision classes.
- Evaluated multilingual classification approaches and compared baseline models with LLM-assisted fallback reasoning.

## Tech Stack

**Mobile:** Flutter · Firebase · ML Kit  
**Backend:** FastAPI · Python  
**AI / OCR:** Google Cloud Vision · Gemini 2.5 Flash  
**Data:** SFDA product records · Open Food Facts

## Repository

[View repository →](https://github.com/Rawan806/safebite)
