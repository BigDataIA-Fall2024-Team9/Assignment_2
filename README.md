# Scalable Automated Text Extraction & OpenAI-based Interactive Query System

An end-to-end platform for automating PDF text extraction from the GAIA dataset and enabling users to securely interact with extracted content through a FastAPI + Streamlit application - with JWT authentication and cloud deployment.

---

## Overview

Airflow pipelines automate the acquisition and processing of GAIA dataset PDFs using both open-source (PyMuPDF) and enterprise-grade (Google Document AI) extraction methods. Extracted text is stored in GCP for retrieval. A FastAPI backend with JWT authentication serves the data to a Streamlit frontend where users can register, log in, and query PDF content interactively.

---

## Architecture

![Architecture Diagram](https://github.com/user-attachments/assets/24c97ffd-f317-44a7-86f9-5198200f8807)

---

## Key Features

- **Automated PDF Ingestion** — Airflow pipelines handle data acquisition and text extraction at scale
- **Dual Extraction Methods** — PyMuPDF (open-source) and Google Document AI (enterprise) for flexible, accurate extraction
- **Secure Authentication** — JWT-based user registration and login with protected API endpoints
- **Interactive Q&A** — Users query specific PDF extracts through a clean Streamlit interface
- **Fully Containerized** — Docker Compose deployment on public cloud for scalable access

---

## Tech Stack

| Category | Tools |
|---|---|
| Cloud & Storage | Google Cloud Platform (GCP) |
| Orchestration | Apache Airflow |
| Backend | FastAPI, Python, JWT |
| Frontend | Streamlit, JavaScript |
| PDF Extraction | PyMuPDF, Google Document AI |
| DevOps | Docker, Docker Compose |
| Version Control | Git |

---

## Project Structure

```
├── backend/
│   ├── main.py              # FastAPI app — auth, endpoints, business logic
│   ├── auth.py              # JWT authentication
│   └── pdf_query.py         # PDF querying logic
├── frontend/
│   └── app.py               # Streamlit UI — register, login, query
├── airflow/
│   └── dags/                # Airflow DAGs for PDF ingestion and extraction
├── Dockerfile.fastapi
├── Dockerfile.streamlit
└── docker-compose.yml
```

---

## How It Works

### 1. Data Ingestion
- Airflow DAGs pull PDFs from the GAIA dataset
- Text is extracted using PyMuPDF or Google Document AI
- Extracted content is stored in GCP for retrieval

### 2. Authentication
- Users register and log in via FastAPI endpoints
- JWT tokens are issued on login
- All endpoints except registration and login are protected

### 3. Query Interface
- Authenticated users access the Streamlit frontend
- Users select between open-source or API-based PDF extracts
- Natural language queries return relevant answers from the extracted content

### 4. Deployment
- FastAPI and Streamlit containerized with Docker Compose
- Deployed on GCP with public access

---

## Getting Started

```bash
# Clone the repo
git clone https://github.com/Chinmay1220/Automated_Document_Processing_System.git
cd Automated_Document_Processing_System

# Set up environment variables
cp .env.example .env
# Add your GCP, Google Document AI, and JWT secret credentials

# Run with Docker Compose
docker-compose up --build
```

---

## Resources

- [Documentation](https://docs.google.com/document/d/1bWeRfD-PZkUzgzmZkl6oEnWgsRIx5cKflwPPp1grAXk/edit?tab=t.0#heading=h.gjdgxs)
- [Demo Video](https://drive.google.com/drive/folders/1u76RGgwkakKqHV_WSMLZuZ8VOHN1u0Xl?usp=drive_link)
