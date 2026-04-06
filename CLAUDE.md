# Model Deployment & Prototyping Workshop

## Project Overview

This repository contains materials for a 90-minute applied workshop titled **"From Model to Usable System: Prototyping Deployment"**. The workshop combines conceptual framing, practical prototyping approaches, and a live demo using FastAPI, Streamlit, and MLflow with the Rossmann forecasting project.

## Purpose

A Quarto RevealJS presentation that teaches students:
- Model deployment fundamentals and practical approaches
- The gap between MLflow-registered models and usable systems
- REST APIs and their role in model serving
- Prototyping patterns for ML systems (FastAPI + Streamlit + MLflow)
- Practical application through real-world examples
- Final project MVP expectations and requirements

## Technology Stack

- **Presentation Format**: Quarto RevealJS
- **Diagrams**: Mermaid
- **Demo Stack**: FastAPI, Streamlit, MLflow
- **Example Project**: Rossmann forecasting

## Key External Dependencies

This project references several external resources on the local machine:

1. **Template Structure**: `~/Desktop/UC/Applied Workshops/model-experimentation`
   - Reference presentation for structural guidance and Quarto setup

2. **Conceptual Content**:
   - `~/Desktop/UC/uc-bana-7075/book/08-modelops-deployment.qmd` - Model deployment concepts
   - `~/Desktop/UC/uc-bana-7075/book/09-modelops-monitoring.qmd` - Model monitoring concepts

3. **Demo Project**: `~/Desktop/Projects/rossmann-forecasting`
   - Real-world example for deployment demonstration
   - Focus on:
     - MLflow model registry (tracking and versioning)
     - FastAPI app (REST API for model serving)
     - Streamlit UI (user-friendly dashboard)
     - System integration (how components connect)

## Design Principles

### Slide Philosophy
- **Minimal text**: Slides should be visual and concise
- **Key takeaway focused**: Each slide has one clear message
- **Concept → Application → Demo flow**: Build from theory to practice
- **Usability over infrastructure**: Emphasize making models accessible, not production complexity

### Speaker Notes
- Medium-light detail
- Talking points, not full scripts
- Focus on framing and interpretation
- Avoid deep technical walkthroughs

### Visuals
- Use Mermaid diagrams for architecture and system flow
- Image placeholders for concepts:
  - `[IMAGE: model stuck in notebook]`
  - `[IMAGE: stakeholder confused by code]`
  - `[IMAGE: simple app UI]`
  - `[IMAGE: FastAPI docs]`
  - `[IMAGE: Streamlit dashboard]`
  - etc.

## Content Structure

The workshop follows this progression:

1. **The Problem** - Opening hook about model value and usability gap between MLflow experiments and stakeholder interaction
2. **Deployment Concepts** - What deployment means in practice
3. **Prototyping** - Shift from production thinking to usable prototypes
   - Includes architecture slides showing how components connect
   - Includes Rossmann demo slides integrated within prototyping section
4. **Getting Started** - Practical steps for students to apply concepts
5. **Final Project MVP** - Requirements, expectations, grading criteria, and deliverables

## Core Learning Goals

Students should be able to:
- Understand deployment as making models accessible and usable, not just production infrastructure
- Recognize the gap between MLflow-registered models and stakeholder interaction
- Understand the difference between production deployment and prototyping
- Understand REST APIs and why they're the industry standard for model serving
- Understand how FastAPI, Streamlit, and MLflow work together to create an ML system
- Apply these concepts to build their own ML system prototypes
- Understand MVP expectations: show progress, demo components, have a clear vision

## File Organization

```
.
├── _quarto.yml                        # Quarto configuration
├── README.md                          # Project overview and workshop description
├── CLAUDE.md                          # This file - detailed context for Claude
├── spec.md                            # Detailed workshop specification
├── .gitignore                         # Git ignore rules
├── docs/                              # Rendered Quarto output
└── workshop/
    └── slides/
        ├── assets/
        │   └── images/                # Images and media for slides
        └── deployment-prototyping.qmd  # Main presentation file
```

## Slide Formatting Reference

The presentation follows the conventions established in the model-experimentation template:

- **Section dividers**: `# Section Name {background="#43464B"}` (H1 with dark background)
- **Content slides**: `## Slide Title` (H2)
- **Speaker notes**: `::: {.notes}` ... `:::`
- **Callout boxes**: `.callout-note` (definitions), `.callout-tip` (goals/advice), `.callout-warning` (reality checks), `.callout-important` (key concepts)
- **Incremental reveals**: `::: {.incremental}` ... `:::`
- **Two-column layouts**: `::: {.columns}` with nested `::: {.column width="50%"}`
- **Mermaid diagrams**: ` ```{mermaid} ` with `%%| fig-width:` for sizing; HTML tags (`<b>`, `<br/>`) work inside node labels
- **Image placeholders**: `[IMAGE: description]` marks where real images should be added
- **Images**: Referenced as `assets/images/filename.png` (relative to the .qmd file)
- **RevealJS config**: `theme: simple`, `transition: fade`, `slide-number: true`, `mermaid: theme: neutral`

## Development Guidelines

### When Editing Slides

1. **Keep slides minimal** - Let the instructor fill in details
2. **Use speaker notes** - Provide talking points for each slide
3. **Insert Mermaid diagrams** - For architecture and system flows
4. **Use image placeholders** - Mark where visuals should go with `[IMAGE: description]`
5. **Align with Rossmann repo** - Ensure demo instructions match actual project
6. **Render to verify** - Run `quarto render workshop/slides/deployment-prototyping.qmd` to check for errors

### Content Alignment

- Ensure technical accuracy with referenced materials (BANA 7075 chapters)
- Match terminology from the course materials
- Verify deployment workflow matches Rossmann project implementation
- Emphasize usability and interaction over production complexity

## Success Criteria

The workshop is successful when students:
- Understand deployment as making models accessible and interactive (not just production infrastructure)
- Recognize the gap between MLflow experiments/registries and stakeholder usability
- Understand REST APIs as the industry standard for model serving
- Recognize the value of building usable prototypes over waiting for production infrastructure
- Understand how FastAPI + Streamlit + MLflow create an integrated ML system
- Can apply these concepts to build their own project MVPs
- Understand MVP expectations: demonstrate progress, not perfection

## Working with This Repository

### When Adding Content

1. Reference the specification file for detailed requirements
2. Check external resources for technical accuracy
3. Maintain the minimal slide / detailed notes pattern
4. Test that Mermaid diagrams render correctly
5. Verify demo steps match the actual Rossmann project

### When Updating

1. Keep the specification file synchronized with actual content
2. Update this file if project structure changes
3. Document any new external dependencies

## Rossmann Project Details

The demo references the Rossmann forecasting project. Key technical details for accuracy:

- **Model**: Weighted ensemble — XGBoost (60%), LightGBM (30%), CatBoost (10%)
- **User inputs**: 7 fields — Store, DayOfWeek, Date, Open, Promo, StateHoliday, SchoolHoliday
- **Engineered features**: 46 total (calendar, lag, rolling stats, store metadata) — all automated in the API
- **FastAPI endpoints**: `GET /health`, `GET /model/info`, `POST /model/load`, `POST /predict`
- **Streamlit pages**: Home (system status), Predictions (single + batch tabs)
- **Model registry**: MLflow with Production/Staging/Archived stages; model name `rossmann-ensemble`
- **Key design pattern**: User provides simple inputs; API handles all feature engineering behind the scenes
- **Launch scripts**: `scripts/start_mlflow.sh`, `scripts/launch_api.sh`, `scripts/launch_dashboard.sh`

**Note**: The Rossmann project includes monitoring capabilities (prediction logging and drift detection with Evidently AI), but these are NOT covered in this workshop. The focus is on building the core ML system prototype.

## Actual Workshop Sections

The final presentation includes these major sections:

1. **Introduction** (slides 1-51)
   - Title and framing
   - Workshop agenda and goals
   - The Problem section: model value, usability gap, stakeholder needs

2. **Deployment Concepts** (slides 52-198)
   - What is deployment
   - Production vs. prototyping
   - The need for usable systems

3. **Prototyping** (slides 199-942)
   - You don't need production infrastructure
   - Common prototype stack (Streamlit, FastAPI, MLflow)
   - System architecture and separation of concerns
   - Rossmann project overview
   - Demo slides (FastAPI, Streamlit dashboard, system status)
   - Getting started guide for students

4. **Final Project MVP** (slides 943-1237)
   - What is an MVP
   - MVP expectations: progress over perfection
   - Requirements (clear vision, working components, demo, plan)
   - Deliverable: recorded presentation
   - Grading rubric (detailed 4/2/0 point breakdowns)
   - Peer review requirement
   - Submission guidelines

5. **Closing** (slides 1238-end)
   - Key takeaways (6 main points)
   - Resources (FastAPI, Streamlit, MLflow, Rossmann project)

## Final Project MVP Details

A significant portion of the workshop covers the Final Project MVP requirements:

**Key Message**: LOW expectations — progress over perfection

**MVP Requirements**:
1. **Clear vision**: System diagram showing full architecture (even if not built)
2. **Working components**: Data pipeline + ML model development in progress
3. **Demo**: Show what's working, even if not fully integrated
4. **Plan**: Explain challenges and next steps

**Deliverable**: 5-10 minute recorded group presentation covering problem, system diagram, demo, and next steps

**Grading** (20 points total + extra credit):
- Clarity of Problem & Purpose (4 pts): 4/2/0 point rubric
- Clarity of System Diagram (4 pts): 4/2/0 point rubric
- Data Pipeline Implementation (4 pts): 4/2/0 point rubric
- ML Model Development (4 pts): 4/2/0 point rubric
- Presentation Quality (4 pts): 4/2/0 point rubric
- System Integration (Extra Credit): +2/+1/0 points

**Peer Review**: Students must review 2 other presentations with 100+ words of feedback (10% engagement penalty if not completed)

**Philosophy**: Acceptable to have data pipeline working + model training working but NO UI yet. Components don't need to be fully integrated. The goal is showing progress and having a clear vision for completion.

## Notes for Claude Code

- This is an educational/workshop content repository
- Focus on clarity and pedagogical effectiveness
- Slides should support teaching, not replace it
- Always verify technical content against source materials (see Key External Dependencies)
- Mermaid diagrams should be simple and clear
- Emphasize the practical "how to make this usable" over theoretical deployment concepts
- Connect concepts back to student final projects and portfolio building
- When editing slides, preserve the minimal text / rich notes pattern
- Render after changes to catch Mermaid or formatting errors
- The workshop emphasizes **progress over perfection** for the MVP — this is a core message throughout
