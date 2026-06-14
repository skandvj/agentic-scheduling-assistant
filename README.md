# Agentic Scheduling Assistant

A sophisticated, scalable conversational Agentic AI chatbot for automating receptionist work, built with LangGraph, LangChain, and modern web technologies. This solution provides natural, human-like interactions for patient management, appointment scheduling, and practice inquiries.

## 🏗️ Architecture

This project follows **Clean Architecture** and **SOLID principles** for maximum scalability and maintainability:

```
├── domain/           # Core business logic and entities
├── application/      # Use cases and orchestration
├── infrastructure/   # External integrations (LLM, database)
└── presentation/     # API and frontend
```
![Architecture](data/Architecture.png)


### Key Technologies

- **LangGraph**: State machine for conversation workflows
- **LangChain**: LLM integration and tool calling
- **FastAPI**: High-performance async backend
- **React/Next.js**: Premium frontend UI
- **Pydantic**: Type-safe data validation

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- Node.js 18+ (for frontend)
- Free-tier API key from one of:
  - [DeepSeek](https://api-docs.deepseek.com/)
  - [Google Gemini](https://ai.google.dev/gemini-api/docs)
  - [OpenAI](https://platform.openai.com/docs/api-reference/introduction)

### Setup

1. **Clone and navigate to the project:**
```bash
cd "Dentist Coversational AI"
```

2. **Create virtual environment:**
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies:**
```bash
pip install -r requirements.txt
```

4. **Configure environment:**
```bash
cp .env.template .env
# Edit .env and add your API key
```

5. **Initialize database:**
```bash
mkdir -p data
python scripts/init_database.py
```

6. **Start backend:**
```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

7. **Start frontend (in another terminal):**
```bash
cd frontend
npm install
npm run dev
```

8. **Access the application:**
- Frontend: http://localhost:3000
- API Docs: http://localhost:8000/docs

## 📋 Features

### Core Capabilities

1. **New Patient Registration**
   - Collects: Full name, phone, date of birth, insurance
   - Guides through first appointment booking

2. **Existing Patient Management**
   - Identity verification
   - Appointment rescheduling
   - Appointment cancellation

3. **Intelligent Appointment Scheduling**
   - Handles subjective dates ("later next week", "early next month")
   - Suggests alternatives when times don't work
   - Supports multiple appointment types:
     - Cleaning
     - General checkup
     - Emergency (with staff notification)

4. **Family Scheduling**
   - Book multiple appointments for family members
   - Coordinate back-to-back appointments
   - Manage family member relationships

5. **General Inquiries**
   - Insurance and payment options
   - Self-pay and membership plans
   - Location and hours information

6. **Emergency Handling**
   - Captures emergency details
   - Notifies staff immediately
   - Provides appropriate guidance

## 🎨 Design Philosophy

- **Premium UI**: Clean, Apple-inspired design with minimal clutter
- **Natural Conversations**: Human-like, context-aware responses
- **Scalable Architecture**: SOLID principles, dependency injection, clean separation
- **Error Resilience**: Comprehensive fallback mechanisms

## 📁 Project Structure

```
.
├── domain/              # Domain models and business logic
│   ├── entities/        # Core entities (Patient, Appointment, etc.)
│   └── value_objects/   # Value objects
├── application/         # Application layer
│   ├── use_cases/       # Business use cases
│   └── services/       # Application services
├── infrastructure/      # Infrastructure layer
│   ├── llm/            # LLM integrations
│   ├── database/       # Database implementations
│   └── tools/          # LangChain tools
├── presentation/        # Presentation layer
│   ├── api/            # FastAPI routes
│   └── frontend/       # React frontend
├── data/               # Database files
├── scripts/            # Utility scripts
└── main.py            # Application entry point
```

## 🔧 Configuration

All configuration is managed through environment variables (see `.env.template`). Key settings:

- **LLM Provider**: Choose DeepSeek, Gemini, or OpenAI
- **Database**: Local JSON (default) or Supabase
- **Practice Info**: Customize practice name, hours, contact

## 🧪 Testing Scenarios

The chatbot handles these key scenarios:

1. New patient booking a cleaning appointment
2. Existing patient rescheduling due to conflict
3. Family booking (parent + 2 kids, back-to-back)
4. Emergency appointment with details
5. Insurance inquiry for non-insured patient
6. Subjective date parsing ("next Tuesday afternoon")

## 📝 API Documentation

Interactive API documentation available at `/docs` when the server is running.

## 🎥 Demo Video

[Link to demo video will be added]

## 🤝 Contributing

This is an assessment project demonstrating:
- Rapid development capabilities
- Clean architecture principles
- Production-ready code quality
- Comprehensive error handling
- User experience excellence

## 📄 License

Assessment Project - Internal Use

