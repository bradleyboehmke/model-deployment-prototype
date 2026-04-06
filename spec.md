# Model Deployment & Prototyping Workshop Spec

## Overview
Create a Quarto RevealJS presentation titled:
**From Model to Usable System: Prototyping Deployment & Monitoring**

This is a 90-minute applied lecture combining:
- conceptual framing of deployment & monitoring
- practical prototyping approach
- Rossmann project demo using FastAPI, Streamlit (and optionally Evidently)

---

## Resources

- Presentation to use as a template:
  ~/Desktop/UC/Applied Workshops/model-experimentation

- Model Deployment chapter:
  ~/Desktop/UC/uc-bana-7075/book/08-modelops-deployment.qmd

- Model Monitoring chapter:
  ~/Desktop/UC/uc-bana-7075/book/09-modelops-monitoring.qmd 

- Rossmann Forecasting Project:
  ~/Desktop/Projects/rossmann-forecasting

Focus on:
- FastAPI app (model serving via MLflow)
- Streamlit UI (user interaction)
- (Optional) Evidently monitoring setup

---

## Design Principles

### Slide Philosophy
- Minimal text
- Concept → application → demo flow
- Emphasize usability over infrastructure

### Speaker Notes
- Medium-light detail
- Focus on framing and interpretation
- Avoid deep technical walkthroughs

### Visuals
- Mermaid diagrams for architecture
- Image placeholders:
  - [IMAGE: model stuck in notebook]
  - [IMAGE: stakeholder confused]
  - [IMAGE: simple app UI]

---

## Core Learning Goals

Students should:
- Understand deployment in practice
- Understand monitoring importance
- Recognize gap between modeling and production
- Learn to build a usable ML prototype
- See FastAPI + Streamlit as a system

---

## Slide Structure

---

## Section 1 — Framing

### Opening Hook
Slide: “When does a model actually create value?”
Notes:
- Models don’t create value alone
- Value comes from use

---

### The Problem
Slide: “Most models never get used”
Notes:
- Stuck in notebooks
- No stakeholder interaction

---

### Key Idea
Slide: “Our goal is not to deploy models — it’s to make them usable”
Notes:
- Anchor message

---

## Section 2 — Deployment Concepts

### What is Deployment?
Slide: “Deployment = making models accessible”
Notes:
- Input → prediction → output

---

### Production View
Slide: “What production involves”
- APIs
- Infrastructure
- Monitoring

---

### Reality Check
Slide: “This is hard”
- Engineering support
- Time
- Uncertainty

---

## Section 3 — Prototyping

### The Shift
Slide: “Before production → prototype”

---

### Prototype Definition
Slide: “A usable ML prototype includes:”
- user input
- model prediction
- interaction

---

### Prototype Stack
Slide: “Minimal ML System”
- FastAPI
- Streamlit
- (Optional) Monitoring

---

## Section 4 — Monitoring

### Why Monitoring Matters
Slide: “Models degrade over time”

---

### What We Monitor
Slide:
- data drift
- prediction drift

---

## Section 5 — Architecture

### System Flow
Slide: “Prototype Architecture”
Mermaid:
User → Streamlit → FastAPI → MLflow → Model → Prediction → UI

---

## Section 6 — Rossmann Demo

### Demo Framing
Slide: “What to watch for”
- predictions
- interaction
- system flow

---

### FastAPI
Slide: “Serving the model”

---

### Streamlit
Slide: “Making it usable”

---

### (Optional) Monitoring
Slide: “Observing behavior”

---

## Section 7 — Reflection

Slide: “Your Project”
- Inputs?
- User controls?
- Outputs?

---

## Section 8 — Final Project MVP

### Mapping
Slide: “Your MVP System”
- API → Model interface
- UI → Interaction
- Monitoring → Optional

---

### MVP Definition
Slide: “MVP ≠ Production”
NOT:
- perfect
- scalable

IS:
- usable
- interactive
- demo-able

---

### Assignment Placeholder
Slide: “Final Project MVP”
[TO BE FILLED]

---

## Claude Code Instructions

- Keep slides minimal
- Use notes for explanation
- Use Mermaid diagrams
- Use placeholders for visuals
- Emphasize usability over complexity

---

## Success Criteria

Students:
- understand deployment concepts
- understand monitoring importance
- can define a usable ML system
- can connect to real implementation
- feel confident building MVP
