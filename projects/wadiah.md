# Wadiah — Smart Lost & Found System for Al-Masjid Al-Haram

## Overview

Wadiah is a bilingual AI-assisted lost-and-found system designed for the operational environment of **Al-Masjid Al-Haram**.

The system supports the full workflow from lost-item reporting and found-item registration to AI-assisted candidate matching, staff verification, ownership evidence review, notification, and secure PIN-based handover.

AI is used as a decision-support tool rather than an autonomous ownership decision-maker.

## My Contribution

I led development across most of the end-to-end system, including:

- Flutter/Firebase application development
- Visitor and staff workflows
- FastAPI backend integration
- AI-assisted multimodal retrieval
- Dynamic indexing and rematching
- Firebase data and image integration
- Ownership verification workflow
- PIN-based handover
- Testing, debugging, and system refinement

SMS integration was handled by a teammate.

## System Architecture

The system combines:

- **Flutter** for the Arabic/English mobile application
- **Firebase Authentication** for user authentication
- **Cloud Firestore** for reports, status information, and match metadata
- **Firebase Storage** for item images
- **FastAPI** for AI-assisted search and indexing
- Visual and textual embedding pipelines for candidate retrieval

## AI Matching Pipeline

### Visual Matching

Item images are processed using **MobileNetV3Small through TensorFlow Lite** to generate visual embeddings.

Candidate items are compared using **cosine similarity**, and the system returns the **Top-5 most similar items** for staff review.

### Multilingual Text Matching

When a lost-item report does not contain an image, structured fields such as item type, color, brand, location, and description are combined into a textual representation.

The system uses **paraphrase-multilingual-MiniLM-L12-v2** through SentenceTransformers to generate multilingual embeddings for Arabic and English descriptions.

Cosine similarity is then used to rank candidate items.

### Dynamic Indexing

Newly registered items can be indexed individually instead of rebuilding the entire embedding collection.

The system also supports staff-initiated rematching when updated candidate results are needed.

## Human-in-the-Loop Verification

AI-generated matches are treated as suggestions.

Staff remain responsible for:

- Reviewing candidate matches
- Comparing item details
- Requesting additional ownership evidence
- Accepting or rejecting matches
- Confirming the final item handover

## Evaluation

The system was tested through functional testing and User Acceptance Testing.

The UAT included **five participants**.

- **100% strongly agreed** that the interface was clear and easy to use.
- **100% strongly agreed** that the overall system was useful and easy to use.
- No negative responses were recorded across the evaluated usability metrics.

The evaluation was intentionally limited in scope: the participant sample was small, no official Lost & Found staff participated, and testing did not reproduce real peak-season conditions inside Al-Masjid Al-Haram.

## Tech Stack

Flutter · Dart · Firebase · FastAPI · Python · TensorFlow Lite · MobileNetV3Small · SentenceTransformers · Cosine Similarity

## Project Evidence

![Selected Wadiah interfaces](../assets/wadiah-ui-showcase.png)

## Repository

[View repository →](https://github.com/Rawan806/2025_GP_18)
