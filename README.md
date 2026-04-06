# From Model to Usable System: Prototyping Deployment

A practical introduction to model deployment and prototyping for analytics and data science students.

## Purpose

This workshop teaches students how to transform trained models from experimental notebooks into usable, interactive systems. By introducing practical deployment patterns with FastAPI and Streamlit, students learn to build **accessible, interactive, and demonstrable** ML prototypes that showcase their technical capabilities — a critical skill when presenting ML projects to stakeholders and potential employers.

The workshop bridges the gap between model training (covered in the MLflow experimentation workshop) and creating systems that non-technical stakeholders can actually use.

## Workshop Goals

By the end of this workshop, students will:

- Understand deployment as making models accessible and usable, not just production infrastructure
- Learn the difference between production deployment and prototyping
- Understand REST APIs and their role in model serving
- See how FastAPI, Streamlit, and MLflow work together to create an ML system
- Explore a real-world example using the Rossmann forecasting project
- Know how to apply these concepts to build their own ML system prototypes
- Understand the MVP expectations for their final project

## Philosophy

The workshop emphasizes **usability over infrastructure** — moving from models trapped in MLflow registries to systems that stakeholders can actually interact with. We acknowledge that full production deployment requires significant engineering support, while encouraging students to build functional prototypes that demonstrate their models in action and create real value.

The key message: **A prototype doesn't need to be production-ready. It needs to show progress, be demo-able, and have a clear vision for completion.**

## Workshop Content

The 90-minute workshop covers:

1. **The Problem**: Understanding the usability gap between trained models and stakeholder interaction
2. **Deployment Concepts**: What deployment actually means in practice
3. **REST APIs**: The industry standard for model serving
4. **Prototyping Approach**: Building usable systems without production infrastructure
5. **System Architecture**: How FastAPI + Streamlit + MLflow work together
6. **Live Demo**: Walkthrough of the Rossmann forecasting project
7. **Final Project MVP**: Requirements, expectations, and getting started

## Workshop Slides

View the presentation slides: [deployment-prototyping.html](https://bradleyboehmke.github.io/model-deployment-prototype/workshop/slides/deployment-prototyping.html)

## Example Project

The workshop uses the [Rossmann Store Sales forecasting project](https://github.com/bradleyboehmke/rossmann-forecasting) as a real-world case study, demonstrating:

1. **Model Registry** — MLflow tracking and versioning of ensemble models
2. **REST API** — FastAPI endpoint serving predictions with auto-generated documentation
3. **User Interface** — Streamlit dashboard for stakeholder interaction
4. **Feature Engineering** — Abstracting technical complexity from end users (7 inputs → 46 features)
5. **System Integration** — How components connect to create a complete, usable system

Students see how these components work together to make a model accessible and useful, transforming a trained model into an interactive system.

## Target Audience

Analytics and data science students who want to move beyond training models in isolation and build interactive ML systems that stakeholders can use, test, and provide feedback on.

---

**Note:** This is part of the Applied Workshops Series, which bridges the gap between classroom learning and industry best practices.
