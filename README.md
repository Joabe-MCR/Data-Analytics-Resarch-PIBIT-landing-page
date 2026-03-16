# Questionnaire Analysis System – Research Project

This repository contains a complete data collection and analysis flow built for an academic research project, but structured so it can be reused in other contexts and evaluated by international clients.

The system has two main parts:

1. **Python analysis backend** (folder `Sistema_Analise/`)
2. **Static web front‑end** (folder `Site/`)

---

## Features

### Python analysis backend (Sistema_Analise)
- Automatic processing of questionnaire data exported from Google Forms (Excel/CSV)
- Calculation of stress / psychometric scores using configurable rules
- Generation of personalized diagnostic reports (JSON, Excel, Markdown)
- Simple configuration through JSON files
- REST API built with Flask for integration with the web front‑end

### Web front‑end (Site)
- Responsive landing page for participants
- TCLE / consent flow before answering questionnaires
- Sequential questionnaires with unique anonymous IDs
- Results page that consumes the Python API to show personalized feedback
- Admin/test pages for validating the full flow locally

---

## Project structure

```text
.
├── Sistema_Analise/          # Python backend (Flask API + data processing)
│   ├── dados_entrada/        # Raw Google Forms exports (Excel/CSV)
│   ├── diagnosticos/         # Generated diagnostic reports
│   ├── resultados/           # Processed datasets (JSON/Excel)
│   ├── api_web.py            # Main API server
│   ├── main.py               # Batch processing entry point
│   ├── processador_questionarios.py
│   ├── gerador_diagnosticos.py
│   └── requirements.txt      # Python dependencies
└── Site/                     # Static front‑end
    ├── index.html            # Landing page + consent
    ├── questionarios.html    # Questionnaire hub
    ├── diagnostico.html      # Result page
    ├── questionarios.js      # Questionnaire orchestration logic
    ├── diagnostico.js        # Result rendering logic
    └── assets/               # Images and other static assets
```

---

## Running locally

### 1. Backend (Python)

Requirements: Python 3.8+ and `pip`.

```bash
cd Sistema_Analise
pip install -r requirements.txt
python api_web.py
```

By default the API runs on `http://localhost:5000`.

### 2. Front‑end (static site)

Any static HTTP server works (VS Code Live Server, `python -m http.server`, etc.).

```bash
cd Site
python -m http.server 8000
```

Then open `http://localhost:8000/index.html` in your browser.

---

## What this project showcases (for clients)

- **Backend engineering (Python/Flask):** REST API design, routing, JSON I/O, simple security practices.
- **Data processing:** Use of `pandas` and related libraries to clean, transform and aggregate questionnaire data.
- **Front‑end integration:** JavaScript code that coordinates multiple pages, localStorage state and API calls.
- **System design & documentation:** End‑to‑end flow from consent → questionnaires → analysis → personalized report.

For a more detailed (Portuguese) description of the original academic project, see the file `README-ptbr.md` and the additional documentation under `Sistema_Analise/`.
