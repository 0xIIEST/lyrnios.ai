<h1 align="center">lyrnios.ai - AI-Powered Educational Assistant</h1>

<div align="center">
  <p>An intelligent educational assistant that generates personalized learning content with interactive visualizations, code examples, and comprehensive study materials.</p>
  <p><strong><a href="#-features">Features</a> • <a href="#-quick-start">Installation</a> • <a href="#-usage">Usage</a> • <a href="#️-architecture">Architecture</a> • <a href="#-contributing">Contributing</a></strong></p>
</div>

---

## 📚 Features

### Core Capabilities
- **Intelligent Content Generation:** Uses Google’s Gemini AI to create structured, detailed educational content.
- **Multi-Modal Learning:** Combines text, diagrams, graphs, and code examples.
- **Interactive Visualizations:** Renders dynamic Mermaid diagrams and mathematical equations.
- **Progressive Content Reveal:** Smooth section-by-section presentation.
- **Text-to-Speech Integration:** Built-in narration using Puter.js.
- **Personalized Study Plans:** Custom learning roadmaps.

### Technical Features
- **Dual API Modes:**
  - `demo` – Preloaded examples for testing.
  - `generate` – Live AI content generation.
- **Responsive Design:** GitHub-inspired UI with glassmorphism.
- **Real-time Chat Interface:** Conversational learning experience.
- **Session Management:** UUID-based tracking.
- **Syntax Highlighting:** Multi-language code display.
- **LaTeX Rendering:** Math support via KaTeX.

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Node.js 16+
- Google Gemini API Key

### Installation

**Clone the repository**
```bash
git clone https://github.com/0xIIEST/lyrnios.ai.git
cd lyrnios.ai
```

**Backend Setup**
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Add API keys to .env
```

**Frontend Setup**
```bash
cd frontend
npm install
npm run dev
```

**Environment Example**
```json
API_KEYS="your_gemini_api_key_1,your_gemini_api_key_2"
```

**Run the Application**
```bash
# Terminal 1
cd backend
make dev  # or uvicorn app:app --reload --port 8000

# Terminal 2
cd frontend
make dev  # or npm run dev
```
Visit **http://localhost:3000**

---

## 🎯 Usage

### Basic Flow
1. Enter a topic or question in the input bar.  
2. Press **Enter** or click **Send**.  
3. Watch content reveal progressively.

### Sections
- **Foundations** – Core prerequisites  
- **Core Concepts** – Detailed explanations  
- **Formulas** – Mathematical equations  
- **Key Concepts** – Summaries  
- **Practice Problems** – Exercises  
- **Study Plan** – Structured roadmap  
- **Diagrams** – Visuals  
- **Code Examples** – Practical snippets  

### Interactions
- 🔊 Click speaker icon for narration  
- Zoom/pan diagrams  
- Explore **Further Questions**

---

## 🧩 API Endpoints

**Generate Content**
```bash
POST http://127.0.0.1:8000/generate
Content-Type: application/json
{
  "prompt": "Teach me about linear regression"
}
```

**Demo Content**
```bash
POST http://127.0.0.1:8000/demo
Content-Type: application/json
{
  "prompt": "write"
}
```

---

## 🏗️ Architecture

### Overview
```
┌─────────────────┐         ┌─────────────────┐
│ React Frontend  │ ◄─────► │ FastAPI Backend │
│ (Port 3000)     │         │ (Port 8000)     │
└─────────────────┘         └────────┬────────┘
                                     │
                            ┌────────▼────────┐
                            │ Google Gemini   │
                            │     API         │
                            └─────────────────┘
```

### Stack
#### Frontend
React, React Router, Tailwind, Mermaid, KaTeX, Axios, Framer Motion, React Markdown, Puter.js

#### Backend
FastAPI, Uvicorn, Google Gemini API, Pydantic, Python-dotenv

### Structure
```
lyrnios-ai/
├── backend/
│   ├── ai.py
│   ├── app.py
│   ├── demos/
│   ├── requirements.txt
│   └── Makefile
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   └── Makefile
└── README.md
```

---

## 🔧 Configuration

### Backend
**API Key Rotation**
```bash
API_KEYS=key1,key2,key3
```

**Model Parameters**
```python
model = "gemini-2.5-flash"
temperature = 0.3
max_output_tokens = 8192
```

### Frontend
**API Mode**
```javascript
const [apiEndpoint, setApiEndpoint] = useState('generate');
```

**Styling**
Edit `frontend/src/colors.css` to adjust theme.

---

## 📊 API Response Format

```json
{
  "foundations": "Core concepts and prerequisites...",
  "concepts": "Detailed explanations...",
  "formulas": "Mathematical representations...",
  "keyconcepts": "Essential takeaways...",
  "problems": "Practice exercises...",
  "study_plan": "Structured learning path...",
  "further_questions": ["Question 1", "Question 2"],
  "mermaid_diagram": "graph TD\nA-->B",
  "graph": { "description": "Graph", "image": "data:image/png;base64,..." },
  "code": "```python\nprint('Hello')\n```"
}
```

---

## 🚨 Error Handling

- Invalid diagrams replaced with placeholders  
- Automatic key rotation on API failure  
- JSON repair for malformed responses  
- Validation for diagrams, code blocks, and base64 data

---

## 🤝 Contributing

1. Fork the repo  
2. Create a branch: `git checkout -b feature/new-feature`  
3. Commit: `git commit -m "Add new feature"`  
4. Push: `git push origin feature/new-feature`  
5. Submit a PR

### Guidelines
- Follow code style  
- Document complex logic  
- Ensure responsiveness  
- Test across browsers

---

## 📝 License
Licensed under **GNU GPL v3**.  
Free to use, modify, and distribute with attribution.  
See [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgments
- Google Gemini AI  
- Mermaid  
- KaTeX  
- Puter.js  
- React Community

---

## 🗺️ Roadmap
- [ ] User authentication  
- [ ] Save/resume sessions  
- [ ] PDF export  
- [ ] Mobile app  
- [ ] Video generation (important)
<br/>

<div align="center">
<img src="https://img.shields.io/badge/license-GPL--3.0-blue.svg"/>
<img src="https://img.shields.io/badge/python-3.8+-blue.svg"/>
<img src="https://img.shields.io/badge/react-18.2+-blue.svg"/>
<img src="https://img.shields.io/badge/fastapi-0.120+-green.svg"/>
</div>

<br/>

<div align="center">
  <strong>Made with ❤️ by the 0xIIEST team</strong><br/>
</div>

<br/>
