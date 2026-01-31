# ☕ COFFEE.CINEMA

**A Cinematic AI Studio for Screenwriters**

Transform your story ideas into professional film blueprints using AI-powered creative tools wrapped in an immersive, dark-mode cinematic interface.

---

## 🎬 What Makes This Different?

Unlike generic AI writing tools, **Coffee.Cinema** simulates a complete film production studio:

- **Role-Based AI Agents**: Separate engines for Story, Characters, Sound Design, Risk Analysis, and Director Styling
- **Immersive UI**: Glassmorphic design with particle systems, holographic effects, and cinematic transitions
- **Smart Fallback**: If the AI disconnects, context-aware mock generation keeps your workflow moving
- **Analysis Lab**: Built-in tools to critique pacing, dialogue authenticity, audience engagement, and market risk
- **Adaptation Engine**: One-click budget optimization and director style transformations

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- [Ollama](https://ollama.ai/) installed locally with `llama3:latest` model

### Installation

```bash
# Clone the repository
git clone https://github.com/Adarshyerram/coffee.cinema.git
cd coffee.cinema

# Create virtual environment
python -m venv .venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Mac/Linux

# Install dependencies
pip install -r requirements.txt

# Run the application
python run.py
```

Visit `http://localhost:5000` in your browser.

---

## 📁 Project Structure

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
│   ├── js/app.js              # Frontend logic and UI handlers
│   └── css/style.css          # Cinematic design system
├── templates/
│   ├── studio.html            # Main creative workspace
│   ├── dashboard.html         # Project vault
│   └── archives.html          # Saved screenplays
└── run.py                     # Application entry point
```

---

## 🎨 Features

### Master Control Panel
Three distinct creative phases:
1. **Creation**: Story blueprints, character profiles, sound design
2. **Analysis**: Health checks, audience simulation, pacing graphs
3. **Adaptation**: Budget optimization, director mode styling

### Analysis Lab
- **Story Risk Analyzer**: Market viability scoring
- **Audience Simulator**: Emotional engagement predictions
- **Pacing Analyzer**: Scene-by-scene intensity graphs
- **Dialogue Inspector**: Authenticity checks with improvement suggestions

### Fail-Safe Logic
Prevents accessing advanced features without a script foundation. Smart modals guide users through the correct workflow.

---

## 🛠️ Tech Stack

### Backend Framework
- **Flask** - Lightweight Python web framework
- **Flask-SQLAlchemy** - ORM for database operations
- **Flask-Login** - User session management
- **Flask-CORS** - Cross-origin resource sharing
- **Werkzeug** - Password hashing and security utilities

### Database
- **SQLite** - Embedded relational database
- Auto-initialized on first run at `instance/cinema.db`

### AI and LLM Integration
- **Ollama** - Local LLM runtime (required)
- **Llama 3** - Primary language model (`llama3:latest`)
- **Requests** - HTTP client for Ollama API communication
- **Smart Fallback Engine** - Context-aware mock generation when LLM unavailable

### Frontend Technologies
- **Vanilla JavaScript (ES6+)** - No frameworks, pure performance
- **TailwindCSS** - Utility-first CSS framework (CDN)
- **Custom CSS** - Glassmorphism, particle systems, holographic effects
- **Google Fonts** - Cinzel (serif), Inter (sans), Syncopate (tech)

### Export Capabilities
- **ReportLab** - PDF generation
- **python-docx** - DOCX file creation

### Development Tools
- **Python 3.8+** - Core runtime
- **Virtual Environment** - Dependency isolation
- **Git** - Version control

### Project Dependencies
```
flask
flask-cors
flask-sqlalchemy
flask-login
requests
python-docx
reportlab
```

### Architecture Pattern
- **MVC-inspired** - Routes, Services, Models separation
- **Service Layer** - Modular engines (Story, Analysis, Adaptation)
- **RESTful API** - JSON-based endpoints for frontend communication

---

## 🔧 Configuration

### Environment Variables (Optional)
Create a `.env` file for custom settings:

```env
FLASK_ENV=development
SECRET_KEY=your-secret-key-here
OLLAMA_URL=http://localhost:11434
```

### Database
SQLite database is auto-created at `instance/cinema.db` on first run.

---

## 📖 Usage Guide

1. **Login/Register**: Create an account on the landing page
2. **Dashboard**: View your project vault and director hall of fame
3. **Studio**: 
   - Click "Brew New Story" to generate a cinematic blueprint
   - Use Analysis tools to refine your script
   - Apply Director Mode or Budget Adaptation
4. **Archives**: Access saved screenplays and load them back into Studio

---

## 🎯 Roadmap

- [ ] Export to PDF/DOCX/Final Draft formats
- [ ] Collaborative editing (multi-user sessions)
- [ ] Voice-to-script dictation
- [ ] Integration with production management tools

---

## 🤝 Contributing

This is a personal project, but suggestions are welcome! Open an issue for bugs or feature requests.

---

## 📄 License

MIT License - feel free to use this for learning or personal projects.

---

## 🙏 Credits

**Developer**: Adarsh Yerram  
**AI Models**: Llama 3 (Meta AI)  
**Design Inspiration**: Film noir aesthetics, cyberpunk UI, professional screenwriting tools

---

**Built with ☕ and 🎬 by filmmakers, for filmmakers.**
