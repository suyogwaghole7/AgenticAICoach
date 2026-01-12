AI Ethics & Responsible AI Coach

Agentic AI System for Ethical, Transparent & Compliant AI Development

Overview

AI Ethics & Responsible AI Coach is an agentic AI system designed to help AI builders, startups, and enterprises design ethical, compliant, and trustworthy AI systems.

The system acts as a virtual Responsible-AI consultant that:

Collects structured product information Identifies ethical, legal, and operational risks Generates compliance-ready risk registers Produces actionable mitigation plans Outputs governance templates for audits and reviews

It supports multiple domains including: HR & hiring systems Healthcare & hospital AI Fintech & credit scoring AI products using sensitive or regulated data The application is available in two modes: Chat-based UI (Streamlit) for human interaction Production-ready API (FastAPI) for system integration What makes this an Agentic AI

This system is built using CrewAI with multiple specialized agents: Agent Responsibility Intake Agent Asks structured questions about the AI product Risk Agent Identifies ethical, legal, and fairness risks Compliance Agent Maps issues to Responsible AI & regulatory concerns Action Agent Produces mitigation and governance steps Template Agent Generates ready-to-use policy and audit templates

Agents collaborate automatically to produce a complete Responsible-AI report from a single user description.

Architecture

User → Streamlit Chat UI Streamlit → FastAPI FastAPI → CrewAI Agents CrewAI → Local LLM (Ollama) CrewAI → Structured Ethics & Compliance Output

Tech Stack

CrewAI – agent orchestration Ollama – local LLM runtime FastAPI – production API Streamlit – conversational UI Render – deployment

Repository Structure ai-ethics-coach/ │ ├── api/ │ └── app.py # FastAPI application │ ├── src/ │ └── responsible_ai_coach/ │ ├── crew.py # CrewAI orchestration │ └── config/ │ ├── agents.yaml # Agent definitions │ └── tasks.yaml # Task definitions │ ├── ui/ │ └── streamlit_app.py # Chat UI │ ├── render.yaml # Render deployment config ├── requirements.txt ├── .env.example └── README.md

Live Production API

The API is deployed on Render:

https://ai-ethics-coach.onrender.com

Swagger UI:

https://ai-ethics-coach.onrender.com/docs

Health check:

https://ai-ethics-coach.onrender.com/healthz

How to Run Locally

Install prerequisites
Python 3.10+

Git

Ollama

Install Ollama from: https://ollama.com

Clone the repository git clone https://github.com/suyogwaghole7/ai-ethics-coach.git cd ai-ethics-coach

Create virtual environment

Windows:

python -m venv .venv ..venv\Scripts\Activate.ps1

Mac / Linux:

python3 -m venv .venv source .venv/bin/activate

Install dependencies pip install -r requirements.txt

Run Ollama

Check installed models: ollama list

If needed: ollama pull llama3.2:3b

Test: ollama run llama3.2:3b "Say READY"

Start FastAPI uvicorn api.app:app --reload --port 8000
Open Swagger:

http://127.0.0.1:8000/docs

Start Streamlit Chat UI
Open a new terminal: streamlit run ui/streamlit_app.py

Open:

http://localhost:8501

How to Use the Coach

Describe your AI system Example:

Domain (HR, hospital, etc)

Who uses it What decision it makes What data it use Human oversight The AI asks structured intake questions Answer them in numbered format

The system generates: Risk Register Action Plan Governance Templates

You can then ask for refinements: “Make it healthcare-specific”

“Add EU AI Act mapping”

“Refine bias mitigation”

To start a new product: Click Reset chat in Streamlit.

FastAPI Endpoints Endpoint Description POST /intake Generates intake questions POST /report Generates full ethics & compliance report GET /healthz Health check GET /docs Swagger UI Deployment (Render)

Build command: pip install -r requirements.txt

Start command: uvicorn api.app:app --host 0.0.0.0 --port 10000

Why this matters This project demonstrates:

Agentic AI design

Multi-agent orchestration Responsible AI governance Production-ready deployment Chat-based ethical decision support

It is suitable for:

AI startups Hospitals & HR teams Compliance officers Regulators & auditors

