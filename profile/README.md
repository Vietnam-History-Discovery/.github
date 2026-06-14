# Vietnam History Discovery

> An AI-powered platform for exploring Vietnamese history through GraphRAG (Graph Retrieval-Augmented Generation) technology.

## About

Vietnam History Discovery is a research-based learning project that applies modern AI techniques to the study of Vietnamese history. The system uses the **Đại Việt Sử Ký Toàn Thư (DVSKTT)** — the most comprehensive Vietnamese historical chronicle — as its primary knowledge source.

## How It Works

```
User Question
     ↓
Vector Search (sentence-transformers)
     ↓
Knowledge Graph Expansion (Neo4j)
     ↓
LLM Generation (Gemini)
     ↓
Accurate Historical Answer
```

## Knowledge Base

| | |
|---|---|
| **Source** | Đại Việt Sử Ký Toàn Thư (Complete Annals of Đại Việt) |
| **Coverage** | 2879 TCN → 1788 SCN (Hồng Bàng → Hậu Lê dynasty) |
| **Size** | 1,504 pages · 3,442 chunks · 527,000+ words |
| **Graph** | 3,600+ nodes · 2,500+ relationships |

## Architecture

```
┌─────────────────────────────────┐
│     Frontend (React + Vite)     │
└────────────────┬────────────────┘
                 │
┌────────────────▼────────────────┐
│   API Gateway (Spring Boot)     │
│   JWT Authentication + Routing  │
└────────┬───────────────┬────────┘
         │               │
┌────────▼──────┐ ┌──────▼──────────────┐
│ User Service  │ │    Chat Service      │
│ (Spring Boot) │ │    (Spring Boot)     │
│ Auth + JWT    │ │ History + Sessions   │
└───────────────┘ └──────┬──────────────┘
                          │
              ┌───────────▼───────────┐
              │      AI Service       │
              │      (FastAPI)        │
              │   GraphRAG Pipeline   │
              │   Vector Search       │
              │   Graph Expansion     │
              │   LLM Generation      │
              └───────────┬───────────┘
                          │
              ┌───────────▼───────────┐
              │     Neo4j AuraDB      │
              │    Knowledge Graph    │
              └───────────────────────┘
```

## Repositories

| Repository | Description | Tech |
|---|---|---|
| [vietnam_hitory_discovery_BE](https://github.com/Vietnam-History-Discovery/vietnam_hitory_discovery_BE) | Backend services + AI pipeline | Python · Java · Spring Boot · FastAPI |
| [vietnam_hitory_discovery_FE](https://github.com/Vietnam-History-Discovery/vietnam_hitory_discovery_FE) | Frontend web application | React · Vite · TailwindCSS |

## Tech Stack

**Backend** — Java / Spring Boot 3 · Python / FastAPI · Neo4j AuraDB · PostgreSQL (Supabase) · Sentence Transformers · Google Gemini

**Frontend** — React 18 · Vite · TailwindCSS · React Query · React Router

## Team

Built as a Research-Based Learning (RBL) academic project at **FPT University Ho Chi Minh City**.

## License

MIT
