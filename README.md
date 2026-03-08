# AI-Care Medical Platform

A comprehensive healthcare platform with dual portals for doctors and patients, featuring AI-powered medical document extraction and analysis.

## 📁 Project Structure

```
AI-care medical platform/
├── docker-compose.yml          # Root orchestration
├── doctor/                     # Doctor Portal
│   ├── backend/               # Node.js API server
│   │   ├── extraction-service/ # Python AI extraction service
│   │   └── src/               # Controllers, routes, models
│   └── frontend/              # React + Vite application
└── medical/                   # Patient Portal
    ├── backend/               # Node.js API server
    │   └── extraction-service/ # Python extraction service
    └── frontend/              # React + Vite application
```

## 🚀 Features

### Doctor Portal
- **Patient Management** - View, search, and manage patient records
- **Electronic Health Records (EHR)** - Access complete patient medical history
- **AI-Powered Summaries** - Automatically generate patient health summaries
- **Document Upload & Analysis** - Upload medical documents and extract key information
- **Lab Report Interpretation** - Instant analysis of laboratory results with risk indicators
- **Dashboard Analytics** - Visual overview of patient statistics and alerts

### Patient Portal
- **Personal Health Records** - Access your complete medical history anytime
- **Document Upload** - Securely upload prescriptions, lab reports, and medical documents
- **Health Insights** - AI-generated explanations of your medical reports
- **Multi-language Support** - Available in English and Tamil
- **Appointment History** - Track past and upcoming medical appointments

### AI-Powered Analysis
- **Smart Document Extraction** - Automatically extract data from scanned documents and images
- **Risk Assessment** - Identify potential health risks from lab values
- **Structured Data Conversion** - Convert unstructured medical documents into organized records

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Frontend | React, Vite, Tailwind CSS |
| Backend | Node.js, Express |
| AI/ML | Python, Gemini API |
| Database | MongoDB (configured via database.js) |
| Containerization | Docker, Docker Compose |

## 📋 Prerequisites

- Docker & Docker Compose
- Node.js 18+ (for local development)
- Python 3.9+ (for extraction service)

## 🏃 Quick Start

### Using Docker (Recommended)

```bash
# Start all services
docker-compose up -d

# Or start individual portals
cd doctor && docker-compose up -d
cd medical && docker-compose up -d
```

### Local Development

#### Doctor Portal

```bash
# Backend
cd doctor/backend
npm install
npm run dev

# Frontend
cd doctor/frontend
npm install
npm run dev
```

#### Medical Portal

```bash
# Backend
cd medical/backend
npm install
npm run dev

# Frontend
cd medical/frontend
npm install
npm run dev
```

#### Extraction Service

```bash
cd doctor/backend/extraction-service
pip install -r requirements.txt
python main.py
```

## 🔧 Configuration

### Environment Variables

Create `.env` files in each backend directory:

```env
# Database
MONGODB_URI=mongodb://localhost:27017/aicare

# JWT
JWT_SECRET=your-secret-key

# AI Services
GEMINI_API_KEY=your-gemini-api-key
```

## 📡 API Endpoints

### Doctor Portal (`/api`)
- `POST /auth/login` - Doctor authentication
- `GET /patients` - List patients
- `GET /ehr/:id` - Get patient EHR
- `POST /extraction` - Extract medical document data
- `GET /summary/:id` - Get AI-generated summary

### Medical Portal (`/api`)
- `POST /auth/login` - Patient authentication
- `GET /records` - Patient health records
- `POST /upload` - Upload medical documents

## 🤖 Extraction Service

The AI extraction service processes medical documents using:

- **OCR Extractor** - Image-based document text extraction
- **Table Extractor** - Structured data from tables
- **Lab Parser** - Laboratory result interpretation
- **Risk Analyzer** - Health risk assessment
- **Gemini Structurer** - LLM-powered data structuring

## 🐳 Docker Services

| Service | Port | Description |
|---------|------|-------------|
| doctor-frontend | 3000 | Doctor portal UI |
| doctor-backend | 5000 | Doctor API server |
| medical-frontend | 3001 | Patient portal UI |
| medical-backend | 5001 | Patient API server |
| extraction-service | 8000 | AI extraction API |

## 📝 License

This project is proprietary software.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Open a pull request
