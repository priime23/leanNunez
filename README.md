<h1 align="center">Hi, I'm Leandro Nuñez <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="35"></h1>

<p align="center">
  <b>Full Stack Developer</b> · Generative AI, RAG &amp; Agentic Systems
</p>

<p align="center">
  <a href="https://leannunez.github.io/myportfolio/"><img src="https://img.shields.io/badge/Portfolio-22d3ee?style=for-the-badge&logo=googlechrome&logoColor=black" alt="Portfolio"/></a>
  <a href="https://www.linkedin.com/in/lean-nunez/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:lean.p.dev@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
  <img src="https://img.shields.io/badge/Open%20to%20work-4ade80?style=for-the-badge&logoColor=black" alt="Open to work"/>
</p>

---

## About me

I build full stack web apps and put AI **inside** them — retrieval, function calling, agents. Not demos: auth, tests, CI/CD and real deploys included.

- 🎓 **Final-year** student of the [Tecnicatura Universitaria en Programación](https://cicloscortos.frt.utn.edu.ar/pregrado/t_u_programacion/) at [UTN — Facultad Regional Tucumán](https://www.utn.edu.ar/es/)
- 🤖 **IBM RAG and Agentic AI** Professional Certificate — 10 courses + capstone ([verify](https://coursera.org/verify/professional-cert/QWM3S2AR4S9Y))
- 🧠 Building agents that reason over tools with LangChain, LangGraph, CrewAI and MCP
- 🏅 Google Cloud Skill Badges — Gemini &amp; Vertex AI ([Credly](https://www.credly.com/users/lean-nunez/badges))
- 📍 San Miguel de Tucumán, Argentina — open to remote
- 💼 **Looking for my first role in IT.** I bring the work, not just the résumé.

<br>

## Featured projects

### 🔧 [Repuestero](https://repuestero.vercel.app/) — Multi-tenant, AI-native ERP

A rewrite of a real legacy ERP (Delphi/Paradox) for an auto-parts store — architecture with a scar behind it, not architecture for its own sake.

- **Tenant isolation via PostgreSQL Row-Level Security** — the `org_id` is resolved from the database, **not** the JWT, and the app connects on a `NOSUPERUSER` role with no `BYPASSRLS`. Proven with a dedicated cross-tenant isolation test
- **NL2SQL assistant orchestrated with LangGraph** (state machine with retries + Groq → OpenAI fallback) behind **5 layers of defense**: prompt-injection filter (keyword + semantic), SQL guard with sqlglot, read-only DB role and statement timeout — answers stream over SSE
- **Human-in-the-loop invoice ingestion**: a multimodal model reads a photo, the LLM *proposes* and a human *approves* — the model never writes to the DB; one invoice = one transaction, with a unique index on the image hash as a concurrency lock
- CI on GitHub Actions (9 pytest suites incl. RLS isolation + vitest) against a real Postgres/pgvector, with branch protection on `main`

`FastAPI` `SQLAlchemy 2.0` `PostgreSQL` `RLS` `pgvector` `LangGraph` `Groq/OpenAI` `sqlglot` `React 19` `Supabase`

<br>

### 🛒 [PremiumTech](https://ecommerce-tech-nu.vercel.app/) — Full stack e-commerce with an AI shopping assistant

A real store, not a tutorial clone. Feature-Sliced Design on the frontend, REST API on Express, and an assistant that can actually *do* things.

- **Hybrid semantic search** with pgvector + Cohere embeddings (1024-dim), blending full-text search and cosine similarity at `0.4 keyword + 0.6 semantic`
- **AI Shopping Assistant** with function calling (Groq `llama-3.3-70b`): 5 custom tools, SSE streaming, up to 8 reasoning rounds per query
- **Prompt injection guard** with a strike/ban system and rate limiting on every AI endpoint
- JWT auth with HttpOnly refresh tokens and `customer` / `admin` RBAC
- Vitest, React Testing Library and Supertest — integration tests run against a real PostgreSQL

`React 19` `TypeScript` `TanStack Router` `Zustand` `Node.js` `Express` `PostgreSQL` `Prisma` `pgvector` `Vitest`

<br>

### 💬 [Portfolio Chatbot](https://portfoliochatbot-sepia.vercel.app/) — RAG over my own CV

Ask it about me and it answers from retrieved context, not from vibes.

- Full **RAG pipeline** in FastAPI: markdown ingest → chunking → embeddings (Google `embedding-004`) → top-k retrieval in ChromaDB → generation with Gemini
- **Automatic fallback** Gemini → Groq on 429/quota errors, so it stays up under free-tier limits
- Backend containerized with Docker on Hugging Face Spaces; the ingest pipeline regenerates on every build

`Python` `FastAPI` `ChromaDB` `Gemini` `Groq` `Docker` `React` `Tailwind`

<br>

## Tech stack

**AI &amp; Agents**

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logoColor=white)
![CrewAI](https://img.shields.io/badge/CrewAI-FF5A50?style=for-the-badge&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-000000?style=for-the-badge&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=for-the-badge&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)

**Frontend**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white)

**Backend &amp; Databases**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![FastAPI](https://img.shields.io/badge/FastAPI-109989?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)

**Testing &amp; DevOps**

![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=for-the-badge&logo=vitest&logoColor=white)
![Testing Library](https://img.shields.io/badge/Testing_Library-E33332?style=for-the-badge&logo=testing-library&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

<br>

## Certifications

| Credential | Issuer | Year |
|---|---|---|
| [RAG and Agentic AI Professional Certificate](https://coursera.org/verify/professional-cert/QWM3S2AR4S9Y) — 10 courses + capstone | IBM | 2026 |
| [Prompt Design in Vertex AI](https://www.credly.com/users/lean-nunez/badges) | Google Cloud | 2025 |
| [Develop GenAI Apps with Gemini](https://www.credly.com/users/lean-nunez/badges) | Google Cloud | 2025 |

<br>

---

<p align="center">
  <i>Concepts before code. Foundations before frameworks.</i>
</p>
