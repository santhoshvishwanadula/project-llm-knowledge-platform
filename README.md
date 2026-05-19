# 🧠 LLM-Powered Enterprise Knowledge Platform

> **Azure OpenAI + LangChain + RAG for intelligent enterprise document search — NTT DATA**

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat-square&logo=python)](https://python.org)
[![Azure OpenAI](https://img.shields.io/badge/Azure_OpenAI-GPT--4-0078D4?style=flat-square&logo=microsoft-azure)](https://azure.microsoft.com)
[![LangChain](https://img.shields.io/badge/LangChain-0.1-1C3C3C?style=flat-square)](https://langchain.com)
[![Azure Databricks](https://img.shields.io/badge/Azure_Databricks-FF3621?style=flat-square&logo=databricks)](https://databricks.com)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)

---

## 📌 Overview

An **enterprise knowledge assistant** built on the Azure ecosystem, enabling employees to search, query, and extract insights from thousands of internal documents using natural language. Built at NTT DATA to replace manual document search with an intelligent LLM-powered system backed by semantic embeddings and RAG.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│              Enterprise Data Sources             │
│   ADLS Gen2 · Azure Blob · SharePoint Docs      │
└──────────────────┬──────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────┐
│           Azure Data Factory Pipeline            │
│        (Ingestion · Preprocessing · ETL)         │
└──────────────────┬──────────────────────────────┘
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
┌───────────────┐   ┌─────────────────────────┐
│  Azure        │   │  Sentence Transformers   │
│  Databricks   │   │  (Embedding Generation)  │
│  (PySpark)    │   └────────────┬────────────┘
└───────────────┘                │
                                 ▼
                    ┌─────────────────────────┐
                    │   Azure Cognitive Search │
                    │   + FAISS Vector Store  │
                    └────────────┬────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │   LangChain RAG Chain   │
                    │   + Azure OpenAI GPT-4  │
                    └────────────┬────────────┘
                                 │
                    ┌────────────┴────────────┐
                    ▼                         ▼
          ┌──────────────┐         ┌───────────────────┐
          │  Chat API    │         │  Power BI Reports │
          │  (FastAPI)   │         │  (Synapse backed) │
          └──────────────┘         └───────────────────┘
```

---

## ✨ Key Features

- **Azure-native RAG** — Built entirely on Azure OpenAI, Cognitive Search, and Azure Databricks
- **Semantic Embeddings** — Sentence Transformers + Hugging Face for document embedding
- **Dual Index Strategy** — Azure Cognitive Search (managed) + FAISS (high-speed local retrieval)
- **Prompt Engineering** — Custom prompt templates fine-tuned for enterprise document Q&A
- **Power BI Integration** — AI-driven analytics surfaced through executive dashboards
- **CI/CD Pipeline** — Automated deployment via Azure DevOps
- **Containerized** — Docker-based workloads with automated rollout

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| LLM | Azure OpenAI (GPT-4) |
| Orchestration | LangChain |
| Embeddings | Sentence Transformers, Hugging Face |
| Vector Search | Azure Cognitive Search, FAISS |
| Data Processing | Azure Databricks, PySpark |
| Storage | ADLS Gen2, Azure Blob Storage |
| Reporting | Power BI, Azure Synapse Analytics |
| CI/CD | Azure DevOps |
| Containerization | Docker |
| Languages | Python, PySpark, SQL |

---

## 📁 Project Structure

```
project-llm-knowledge-platform/
│
├── src/
│   ├── ingestion/
│   │   ├── adf_connector.py         # Azure Data Factory integration
│   │   ├── blob_loader.py           # Azure Blob Storage document loader
│   │   └── preprocessing.py         # Text cleaning & normalization
│   │
│   ├── embeddings/
│   │   ├── sentence_transformer.py  # HuggingFace embedding pipeline
│   │   └── batch_embedder.py        # Large-scale batch embedding
│   │
│   ├── indexing/
│   │   ├── cognitive_search.py      # Azure Cognitive Search indexer
│   │   └── faiss_local.py           # Local FAISS index management
│   │
│   ├── rag/
│   │   ├── prompt_templates.py      # Enterprise Q&A prompt templates
│   │   ├── langchain_chain.py       # LangChain RAG pipeline
│   │   └── azure_openai.py          # Azure OpenAI client wrapper
│   │
│   ├── analytics/
│   │   ├── synapse_connector.py     # Azure Synapse integration
│   │   └── powerbi_export.py        # Power BI data push
│   │
│   └── api/
│       └── main.py                  # FastAPI application
│
├── databricks/
│   └── pyspark_etl.py               # Distributed ETL on Databricks
│
├── devops/
│   ├── azure-pipelines.yml          # CI/CD pipeline
│   └── Dockerfile
│
├── requirements.txt
└── README.md
```

---

## 📊 Results & Impact

- ✅ Enterprise-wide document search reduced from hours of manual search to seconds
- ✅ Intelligent Q&A over thousands of internal documents with source citations
- ✅ Power BI dashboards delivered AI-driven insights to executive stakeholders
- ✅ Prompt engineering improved response relevance and factual accuracy
- ✅ Fully automated CI/CD deployment pipeline via Azure DevOps

---

## 👤 Author

**Santhosh Vishwanadula** — Senior AI/ML Engineer

- 🌐 [Portfolio](https://santhoshvishwanadula7-lgtm.github.io)
- 💼 [LinkedIn](https://www.linkedin.com/in/santhoshvishwanadula)
- 📧 santhoshvishwanadula7@gmail.com

> *Note: This repository documents the architecture and approach. Source code is proprietary to NTT DATA.*
