# 🧠 PROJECT UNDERSTANDING: COFFEE.CINEMA

> "Not just a text generator, but a simulation of a creative studio."

This document explains the **Why, What, and How** of the project, focusing on the conceptual and architectural decisions that differentiate it from standard AI tools.

---

## 1. The Core Philosophy: "Digital Method Acting"

Most AI writing assistances behave like **Dictation Machines**—you speak, they type. They have one generic "AI" personality.

**Coffee.Cinema** is built on the theory of **Digital Method Acting**. We believe that to generate high-quality creative work, the AI must adopt the specific mental model of the professional role it is performing.

The system segments the Large Language Model (LLM) into distinct **Creative Agents**:

*   **The Screenwriter Agent**: Obsessed with structure, formatting (Sluglines), and narrative hooks.
*   **The Sound Engineer Agent**: Completely ignores the plot and focuses purely on auditory texture, Hz frequencies, and ambience.
*   **The Risk Analyst Agent**: A cold, calculating engine that looks for plot holes and market viability.
*   **The Director Agent**: Focuses on visual style, lighting, and camera movement (e.g., "The Nolan Look").

By forcing the AI to "stay in character," we achieve higher fidelity output than a generalist ChatGPT prompt.

---

## 2. Unconventional User Experience (Immersive UI)

We rejected the standard "SaaS Dashboard" aesthetic (white background, sidebar, blue buttons). Creative work requires a flow state.

*   **Dark Mode First**: To reduce eye strain during late-night writing sessions.
*   **Diegetic Interface**: The buttons and menus mimic film equipment (slates, monitors).
*   **Particle Systems**: The subtle background movement creates a sense of "living workspace" rather than a static web page.
*   **Master Control Panel**: A centralized hub that guides the user through the three stages of production: **Creation**, **Analysis**, and **Adaptation**.

---

## 3. Architecture Deep Dive

The application is built on a **Modular Service Architecture**. It is not a monolith; it is a collection of specialized engines.

### The Backend (Brain)
Located in `app/services/`:

1.  **`story_engine.py`**:
    *   Handles the creative writing.
    *   Understands "Genre" and "Tone".
    *   Generates 3 separate outputs: Logline, Characters, and Script.

2.  **`analysis_engine.py`**:
    *   **Post-Processing Logic**. It takes the generated script and runs it through heuristic algorithms.
    *   **Audience Simulator**: Uses sentiment analysis to predict where an audience might get bored (Drop-off points).
    *   **Pacing Analyzer**: Measures word count density per scene to create an "Intensity Graph".

3.  **`adaptation_engine.py`**:
    *   **Transformation Logic**. It takes existing text and rewrites it under constraints.
    *   **Budget Mode**: Rewrites scenes to remove expensive elements (e.g., "Explosion" -> "Loud noise").
    *   **Director Mode**: Rewrites scenes to apply specific stylistic adjectives.

4.  **`llm_client.py` (The Smart Gateway)**:
    *   Manages the connection to the local Ollama instance (Llama 3).
    *   **Key Feature: Smart Fallback**. If the local AI is offline or times out, this engine kicks in. It doesn't just error out. It inspects the user's prompt, extracts keywords (Names, Genre), and constructs a **architecturally valid** mock response. This ensures the UI never breaks during a demo.

### The Frontend (Lens)
Located in `static/js/app.js`:

*   **State Management**: The frontend maintains a `currentSessionData` object that holds the "Truth" of the current project.
*   **Fail-Safe Logic**: It prevents the user from trying to "Analyze" a script that doesn't exist yet, guiding them back to the "Creation" phase.

---

## 4. The User Workflow

1.  **Phase I: Creation**
    *   User enters a prompt.
    *   `StoryEngine` brews the raw material (Script, Characters, Sound).

2.  **Phase II: Analysis**
    *   User opens the **Analysis Lab**.
    *   `AnalysisEngine` critiques the work, providing objective data (Risk Score, Pacing Graph) on subjective art.

3.  **Phase III: Adaptation**
    *   User enters **Adaptation Studio**.
    *   `AdaptationEngine` transforms the script for specific needs (Lower Budget, Different Director Style).

4.  **Phase IV: Archival**
    *   Project is saved to the Vault (`dashboard.html`).
    *   Can be re-loaded into the Studio at any time for further refinement.

---

## 5. Technical Blueprint

### File Structure
```
Coffee-with-Cinema/
├── app/
│   ├── routes.py              # Flask API endpoints
│   ├── services/
│   │   ├── llm_client.py      # AI integration with smart fallback
│   │   ├── story_engine.py    # Narrative generation
│   │   ├── analysis_engine.py # Risk/Pacing/Dialogue analysis
│   │   └── adaptation_engine.py # Budget/Style transformations
│   └── models.py              # Database models
├── static/
│   ├── js/app.js              # Frontend logic (State & UI)
│   └── css/style.css          # Cinematic Design System
├── templates/
│   ├── studio.html            # Main Workspace (Master Control)
│   ├── dashboard.html         # Project Vault
│   └── archives.html          # Read-Only Archive
└── run.py                     # Entry Point
```

### Technology Stack
*   **Core**: Python 3.8+, Flask 2.3
*   **AI Runtime**: Ollama (Llama 3 Model)
*   **Database**: SQLite (SQLAlchemy ORM)
*   **Frontend**: Vanilla JS + TailwindCSS (No heavy frameworks)
*   **Security**: Werkzeug Hashing + Flask-Login

---

**Summary**: Coffee.Cinema is a tool that respects the complexity of filmmaking by treating each aspect of production—writing, sound, risk, direction—as a specialized discipline requiring a specialized AI agent.
