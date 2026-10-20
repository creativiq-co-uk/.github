<h1 align="center">CreativIQ</h1>

<p align="center">
  <b>AI-powered creativity evaluation for film.</b><br>
  Turning a subjective human judgement into a transparent, repeatable score.
</p>

---

## 🎬 What it is

CreativIQ analyses a short film and scores its **creativity** — then explains *why*. It grades the film across visual, audio and narrative craft and maps the result to the four **Consensual Assessment Technique (CAT)** dimensions: **Originality, Elaboration, Fluency and Flexibility**.

> Built as an MSc Computer Science Individual Project — University of Leicester.

## 🧠 How it works

A **5-agent pipeline** (orchestrated with LangGraph) evaluates each film:

| Agent | What it does | Models |
|-------|--------------|--------|
| **Visual** | Composition, originality, scene diversity | GPT-4o Vision + CLIP |
| **Audio** | Dialogue & sound creativity | Whisper → GPT-4o |
| **Narrative** | Plot, character, theme | GPT-4o |
| **Scoring** | Fuses modalities → overall score → CAT dimensions | deterministic |
| **Report** | Written rationale + 5 improvement suggestions | GPT-4o |

`Overall score = 0.35 · Visual + 0.30 · Audio + 0.35 · Narrative`

## ✨ Features

- 🔐 Google OAuth2 / JWT authentication
- 💳 Transactional credit system (priced by video length)
- ⚡ Real-time, per-agent progress via WebSocket
- 📊 Interactive reports — CAT radar, rationale, transcript, keyframes
- 💬 Report-grounded chat assistant
- 🏆 Public leaderboard comparing AI scores against human ratings
- 🛠️ Admin dashboard

## 🏗️ Architecture

Three decoupled services, deployed on **Azure** with **CI/CD**:

- **Frontend** — Next.js 14 · React · Tailwind
- **Core API** — FastAPI (auth, credits, storage, queue producer)
- **AI Engine** — FastAPI worker running the LangGraph pipeline

**Infrastructure:** PostgreSQL · Redis (queue + pub/sub) · Azure Blob Storage · Azure Container Apps · GitHub Actions

## 🧰 Tech stack

`Python` · `FastAPI` · `LangGraph` · `Next.js` · `React` · `PostgreSQL` · `Redis` · `Azure` · `Docker` · `GPT-4o` · `CLIP` · `Whisper`

---

<p align="center"><i>Built by Kunal Borade · MSc Computer Science, University of Leicester · 2026</i></p>
