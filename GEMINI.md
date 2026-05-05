# Integrated Digital Educational Resource: Quadratic Function (§ 8)

This project is an Integrated Digital Educational Resource (ICOR) focused on § 8 "Quadratic function, its graph and properties" from the textbook "Mathematics. 7–9 grades" (Shkolnyi O. V., Nelin Ye. P., et al.). It is developed as part of Laboratory Work No. 2: "Development of educational materials in computer science using generative AI".

## 🚀 Project Overview

- **Topic:** Quadratic functions, graphs, and properties.
- **Goal:** Create a visually appealing, interactive, and functional educational website using Generative AI (Claude, Gemini, ChatGPT, etc.).
- **Target Audience:** 9th-grade students and mathematics teachers.
- **Hosting:** [GitHub Pages](https://ssemerikov.github.io/website_kf/)

## 📂 Project Structure

- `index.html`: The main entry point (currently a stub).
- `plan.md`: Comprehensive development plan including structure, simulator designs, and technical requirements.
- `Що зроблено.txt`: Progress log.
- `Додаткові матеріали/`: Source materials, textbook PDFs, and laboratory instructions.
  - `Як виконувати завдання.txt`: Detailed requirements and evaluation criteria for the project.

## 🛠️ Development Plan (Key Components)

1.  **Theory:** 5 interactive blocks covering definitions, parabola elements, properties, transformations, and fun facts.
2.  **Simulators (Trainees):**
    - **Constructor:** Interactive slider-based parabola builder.
    - **Detective:** Property analysis from graphs/formulas.
    - **Graphical Dictation:** Step-by-step construction training.
3.  **Assessment:** Tests and tasks categorized by difficulty (Levels 1-4).
4.  **Cabinets:** Personalized progress tracking for students and management tools for teachers.

## 💻 Tech Stack (Proposed)

- **Frontend:** Vanilla HTML/CSS/JS or React/Vue.
- **Math Visualization:** GeoGebra API or Desmos API.
- **Formulas:** KaTeX or MathJax.
- **Design:** Clean, modern, and accessible (min 16px font, high contrast).

## 📋 Development Conventions

- **Language:** Ukrainian (primary content).
- **Documentation:** Maintain `plan.md` as the source of truth for features and structure.
- **Workflow:** Use Generative AI for content creation (text, images, code) but verify all output for scientific accuracy.
- **Git:** Commit changes regularly; do not stage/commit unless requested.

## 🏃 Running and Testing

- **Local Development:** Since it's currently a static site, open `index.html` in any modern web browser.
- **TODO:** Set up a local development server (e.g., `npx serve`) if moving to a framework like React.
- **Deployment:** Automatic via GitHub Pages on push to the `main` branch.

## 📝 Current Tasks

- [ ] Transition from `index.html` stub to the main navigation structure.
- [ ] Implement the first theory block.
- [ ] Research GeoGebra/Desmos API integration for the "Constructor" simulator.
- [ ] Create the directory structure as specified in the "Technical Requirements" section of `Як виконувати завдання.txt`.
