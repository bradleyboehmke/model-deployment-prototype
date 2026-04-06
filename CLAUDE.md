# Model Deployment & Prototyping Workshop

## Project Overview

This repository contains materials for creating a 90-minute applied workshop titled **"From Model to Usable System: Prototyping Deployment & Monitoring"**. The workshop combines conceptual framing, practical prototyping approaches, and a live demo using FastAPI, Streamlit, and MLflow with the Rossmann forecasting project.

## Purpose

Create a Quarto RevealJS presentation that teaches students:
- Model deployment fundamentals and practical approaches
- The gap between notebook models and usable systems
- Prototyping patterns for ML systems (FastAPI + Streamlit)
- Basic monitoring concepts and drift detection
- Practical application through real-world examples

## Technology Stack

- **Presentation Format**: Quarto RevealJS
- **Diagrams**: Mermaid
- **Demo Stack**: FastAPI, Streamlit, MLflow, (optionally) Evidently
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
     - FastAPI app (model serving via MLflow)
     - Streamlit UI (user interaction)
     - (Optional) Evidently monitoring setup

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

1. **Framing** - Opening hook about model value and usability gap
2. **Deployment Concepts** - What deployment means in practice
3. **Prototyping** - Shift from production thinking to usable prototypes
4. **Monitoring** - Why and what to monitor
5. **Architecture** - System design with FastAPI + Streamlit
6. **Rossmann Demo** - Real-world workflow demonstration
7. **Reflection** - Applying concepts to student projects
8. **Final Project MVP** - Connecting to course final project

## Core Learning Goals

Students should be able to:
- Understand deployment as making models accessible and usable
- Recognize the gap between modeling and stakeholder interaction
- Understand the difference between production deployment and prototyping
- Build a functional ML prototype with FastAPI and Streamlit
- Understand basic monitoring concepts and drift detection

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
- Understand deployment as making models accessible (not just infrastructure)
- Recognize the value of building usable prototypes
- Can explain what monitoring captures and why it matters
- Understand how FastAPI + Streamlit create an ML system
- Can apply these concepts to build their own project MVPs

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
- **Streamlit pages**: Home (status), Predictions (single + batch tabs), Documentation, Monitoring
- **Model registry**: MLflow with Production/Staging/Archived stages; model name `rossmann-ensemble`
- **Prediction logging**: SQLite database at `data/monitoring/predictions.db`
- **Drift detection**: Evidently AI 0.7.20 comparing production features vs training reference data
- **Key design pattern**: User provides simple inputs; API handles all feature engineering behind the scenes

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
