# 🏗️ TECHNICAL BLUEPRINT

**Project:** Coffee.Cinema  
**Version:** 2.0 (Studio Environment)

This document provides a detailed technical breakdown of the repository structure and the technology stack used. Use this as a reference when reviewing the code or managing the Git repository.

---

## 📁 Project File Structure

The repository is organized into a modular architecture:

```text
Coffee-with-Cinema/
├── .gitignore                 # Files excluded from Git (e.g., .venv, __pycache__)
├── README.md                  # Installation & Quick Start Guide
├── PROJECT_OVERVIEW.md        # Conceptual Philosophy ("Digital Method Acting")
├── requirements.txt           # Python Dependencies list
├── run.py                     # Main Entry Point (starts Flask server)
│
├── app/                       # Backend Logic (The Brain)
│   ├── __init__.py            # Flask App Factory
│   ├── routes.py              # API Endpoints (receives frontend requests)
│   ├── models.py              # Database Schema (Users, Projects)
│   └── services/              # specialized AI Engines
│       ├── llm_client.py      # Connects to Llama 3 (includes Smart Fallback)
│       ├── story_engine.py    # Generates creative content
│       ├── analysis_engine.py # Runs Risk/Pacing/Audience algorithms
│       └── adaptation_engine.py # Rewrites scripts (Budget/Director modes)
│
├── static/                    # Frontend Assets (The Lens)
│   ├── css/
│   │   └── style.css          # Custom Cinematic Styles (Glassmorphism)
│   ├── js/
│   │   └── app.js             # Main Application Logic (State Management)
│   └── images/                # Static assets (Logos, Icons)
│
├── templates/                 # HTML Views (The Stage)
│   ├── index.html             # Landing Page (Login/Register)
│   ├── dashboard.html         # User Dashboard (Archives Vault)
│   ├── studio.html            # Main Creative Workspace
│   └── author.html            # Profile/Settings Page
│
└── instance/                  # Local Data (Git Ignored usually, but created on run)
    └── cinema.db              # SQLite Database file
```

---

## 🛠️ Technology Stack

### 1. Backend (Server-Side)
*   **Language**: Python 3.8+
*   **Framework**: Flask 2.3 (Lightweight, extensible)
*   **Database**: SQLite (via Flask-SQLAlchemy ORM)
*   **Authentication**: Flask-Login (Session management)
*   **Security**: Werkzeug Security (Password hashing)

### 2. Frontend (Client-Side)
*   **Core**: Vanilla JavaScript (ES6+) - ensuring maximum performance without framework overhead.
*   **Styling**: TailwindCSS (Utility classes) + Custom CSS variables.
*   **Fonts**: Google Fonts (Cinzel, Inter, Syncopate).
*   **UI Paradigm**: "Diegetic UI" (Interface mimics real-world film equipment).

### 3. Artificial Intelligence
*   **Runtime**: Ollama (Running locally on port 11434).
*   **Model**: Meta Llama 3 (`llama3:latest`).
*   **Integration**: Custom `LLMClient` with timeout handling and "Smart Fallback" (heuristic mock generation).

### 4. Utilities & Libraries
*   **Requests**: For communicating with the Ollama API.
*   **ReportLab**: For exporting scripts to PDF.
*   **Python-Docx**: For exporting scripts to Word documents.

---

## 📦 Dependency Manifest

The following packages are required to run the application (found in `requirements.txt`):

| Package | Purpose |
| :--- | :--- |
| `flask` | The web server core. |
| `flask-cors` | Allows API calls from modern browsers. |
| `flask-sqlalchemy` | Manage the database. |
| `flask-login` | Handle user logins. |
| `requests` | Talk to the AI model. |
| `python-docx` | Create .docx files. |
| `reportlab` | Create .pdf files. |

---

## 🚀 Deployment / Git Push Checklist

When pushing this repository to GitHub, ensure:
1.  [x] `.gitignore` is present (prevents uploading heavy virtual env files).
2.  [x] `requirements.txt` is up to date.
3.  [x] No API keys are hardcoded (Environment variables used).
4.  [x] Database file (`instance/cinema.db`) is NOT pushed (it is auto-created).

This structure ensures a clean, professional, and reproducible codebase.
