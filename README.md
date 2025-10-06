# AI/ML Club - ORION: Not Just an Assistant, A Companion

**Academic Year:** 2025-2026 Fall Semester
**Project Duration:** September 2025 - Ongoing

## Project Description

Orion is a **privacy-first, user-owned, personality-driven AI companion** designed to be more than a tool — a presence that adapts to its user’s personality, mood, and lifestyle. Unlike generic cloud bots, Orion aims to offer explainability, personalization, and strict privacy guarantees while moving toward an offline-first endgame. Currently, it integrates **Fast Whisper STT**, **Coqui TTS**, and **Zephyr 7B Beta** as the local LLM, while Hybrid Mode combines the local edge device with a larger server-side model for enhanced reasoning power. The project will further fine-tune and train the local model to meet Orion’s long-term goals.

**Key Objectives:**

* Deliver a functional I/O loop: voice input (Fast Whisper) → reasoning (Zephyr 7B + server LLM) → voice output (Coqui).
* Build personality sliders, user profiles, and explainable system prompts for adaptable conversations.
* Develop a privacy-first memory subsystem with short-term, session, and long-term facts, plus semantic recall.
* Achieve strict privacy-first design: transparent logging, approval-based memory, and offline fallback.
* Prepare a scalable plugin/skills system and UI for usability and future extensibility.

## Lead Contact Information

**Project Lead:** Gourav Mukherjee
📧 Email: [[gourav.mukherjee@sjsu.edu](mailto:gourav.mukherjee@sjsu.edu)]
💼 LinkedIn: [https://linkedin.com/in/gouravmukherjee](https://linkedin.com/in/gouravmukherjee)

**Faculty Advisor:** [Advisor Name]
📧 Email: [[advisor.email@sjsu.edu](mailto:advisor.email@sjsu.edu)]
🏢 Office: [Building Name, Room Number]

## Contributors

*For detailed member information including LinkedIn profiles and Discord handles, see [docs/members.csv](docs/members.csv)*

| Name                    | Role                     | Email                                                 | GitHub                               |
| ----------------------- | ------------------------ | ----------------------------------------------------- | ------------------------------------ |
| Gourav Mukherjee | Project Lead & Architect | [[gourav.mukherjee@sjsu.edu](mailto:gourav.mukherjee@sjsu.edu)]   | [@GouravMukherjee](https://github.com/GouravMukherjee) |
| [Member 2]              | AI/LLM Lead        | [[email@university.edu](mailto:email@university.edu)] | [@github](https://github.com/)       |
| [Member 3]              | Web/UI/UX Lead               | [[email@university.edu](mailto:email@university.edu)] | [@github](https://github.com/)       |
| [Member 4]              | Data & Memory Engineer       | [[email@university.edu](mailto:email@university.edu)] | [@github](https://github.com/)       |
| [Member 5]              | Device & Infra Engineer       | [[email@university.edu](mailto:email@university.edu)] | [@github](https://github.com/)       |
| [Member 6]              | Privacy/Security Engineer       | [[email@university.edu](mailto:email@university.edu)] | [@github](https://github.com/)       |

## Project Kanban Board

**🔗 Public Board:** [View our Kanban Board](https://github.com/aiml-club/orion/projects/1)

---

# 🌌 ORION — *Not just an assistant. A companion.*

> **Privacy-first, user-owned, personality-driven AI companion** that learns with you, adapts to you, and is controlled by you.

---

## ⚡ TL;DR

* **Mission:** Build a personal AI that feels human, is fully customizable (**personality sliders**), and respects your privacy by default.
* **Now:** Prototype using **Fast Whisper STT**, **Coqui TTS**, and **Zephyr 7B Beta** with hybrid edge+server integration.
* **Core Pillars:** User agency • Privacy & security • Explainable AI • Emotional intelligence • Digital well-being • Open ecosystem • Offline endgame.
* **Status:** ~50% complete — working loop with voice I/O, personality basics, and memory system; roadmap includes **VAD, prompt composer, semantic recall, PII redaction**.

---

## 🎯 Mission

**To create the most personal, adaptable, and human-like AI companion.** Not a generic chatbot, but a presence that understands you, grows with you, and evolves to align with your goals.

---

## 🌟 Orion Principles

1. **User Agency First** — User approves memory writes; visible logs for every outbound call.
2. **Privacy & Security by Design** — Local-first storage, encryption, and strict privacy modes.
3. **Explainability** — Compact summaries of why suggestions are made.
4. **Emotional Intelligence** — Adapts to tone, energy, and style.
5. **Digital Well-Being** — Focus modes, healthy nudges, do-not-disturb rules.
6. **Open & Modular** — Plugins and skills extendable by the community.
7. **Offline-First Endgame** — Cloud APIs are stepping stones; Orion targets full offline support.

---

## 🔒 Privacy & Security

**Modes:**

* **Strict Mode:** Local-only; no outbound calls; encrypted memory.
* **Hybrid Mode (default):** Combines Zephyr 7B (edge device) + larger server model, using Coqui and Fast Whisper. Logs every call; PII redaction before sending.
* **Cloud Mode:** Opt-in; full features, logs + export/delete supported.

**Data Flow Controls:**

* Memory writes are `always-ask`, `auto-approve`, or `never-store`.
* User commands: `show memory`, `forget`, `export`, `purge session`.
* Secure `.env` handling and encryption at rest.
* Transparent logs: API ledger tracks calls, tokens, purposes.

---

## 🧱 Architecture

**Layers & Components**

1. **Input:** Voice (Fast Whisper STT), Text (CLI/UI).
2. **Orchestrator:** Routes intent, applies policies + personality engine.
3. **Personality Engine:** Adjustable sliders and profiles.
4. **Memory Subsystem:** Short-term buffer, summaries, long-term facts, semantic recall.
5. **Skills Layer:** Weather, calendar, web search, system hooks.
6. **Output Layer:** Text + Coqui TTS with privacy-aware responses.
7. **Event Bus/Scheduler:** Cron-like routines and state handling.

**Flow:**

```
Mic/Text → Intent Router → Personality Engine → Local LLM (Zephyr 7B) + Server Model → Skills → Memory Approval → Output (Text/Coqui Voice) → Logs
```

---

## ✨ Features

* **Core Interaction:** Voice + text input/output, overrides, whisper/story modes.
* **Conversation & Personality:** Sliders (humor, sarcasm, creativity, etc.), presets (Study, Chill, Professional).
* **Memory & Learning:** Editable facts, semantic recall, session summaries, provenance tracking.
* **Knowledge & Tools:** Calendar, reminders, file Q&A, plugin system.
* **Reasoning & Creation:** Multi-turn planning, writing, coding help, translation, summarization.
* **Privacy:** Strict/hybrid/cloud modes; redaction + API ledger.
* **UI/UX:** Future dashboard with transcript, waveform, sliders, privacy toggles.
* **Automation:** Scheduler, reminders, morning briefings.
* **Accessibility:** Adjustable speaking rate, multilingual support, captions.
* **Reliability:** Retry policies, crash recovery, persistent sessions.

---

## 🧩 Personality Sliders

```jsonc
{
  "humor": 0.5,
  "honesty": 0.7,
  "formality": 0.5,
  "verbosity": 0.6,
  "sarcasm": 0.2,
  "creativity": 0.6,
  "initiative": 0.4
}
```

Profiles: **Study, Chill, Professional**.

---

## 🧠 Memory System

* **Scopes:** Short-term buffer, session summaries, long-term facts with provenance, vector store.
* **Approval Policies:** User-controlled storage (ask/auto/never).
* **Commands:** `show memory`, `forget`, `export`, `purge session`.

---

## 🧭 Explainability & Well-Being

* Why-explainers.
* Context previews.
* Focus mode.
* Healthy nudges.
* Do-not-disturb lists.

---

## 🧪 Acceptance Tests

* Voice ↔ Text toggle works.
* One-shot overrides trigger.
* Memory approvals prompt user.
* Strict mode blocks net calls gracefully.

---

## 📂 Repository Structure

> The repo root is the **project**. The inner `orion/` folder is the **Python package**. This clarifies imports and lets you run `python -m orion`.

```
ORION/                         # ← repository root
├── README.md                  # this document (AI/ML Club template + full details)
├── requirements.txt           # pinned deps for local/dev
├── .gitignore
├── .env                       # local config (never commit secrets)
├── .env.example               # template for contributors
├── LICENSE
├── docs/
│   ├── members.csv            # Team member details (LinkedIn, Discord)
│   ├── info.json              # Project metadata for club website automation
│   ├── thumbnail.webp         # Project thumbnail
│   └── pitch_slides.pdf       # Presentation deck
├── config/
│   ├── settings.yaml          # app defaults (modes, devices, paths)
│   └── personality.default.json
├── data/
│   ├── memory.json            # long‑term facts (JSON) — can migrate to SQLite
│   └── logs/
│       └── api_ledger.jsonl   # transparent API/LLM ledger
├── orion/                     # Python package (importable as `orion`)
│   ├── __init__.py
│   ├── __main__.py            # enables: python -m orion
│   └── app/
│       ├── cli.py             # CLI/voice loop entry
│       ├── orchestrator.py    # prompt composition + routing
│       ├── personality.py     # sliders, profiles, runtime adjustments
│       ├── router.py          # intent → skill/tool selection
│       ├── explain.py         # context preview + "why" summaries
│       ├── wellbeing.py       # focus mode, nudges, DND rules
│       ├── stt/
│       │   ├── __init__.py
│       │   ├── fast_whisper.py# Fast Whisper STT (local/hybrid)
│       │   └── vosk.py        # strict-mode fallback
│       ├── tts/
│       │   ├── __init__.py
│       │   └── coqui.py       # Coqui TTS adapter
│       ├── memory/
│       │   ├── __init__.py
│       │   ├── store.py       # CRUD for facts & session summaries
│       │   ├── vectors.py     # FAISS/Chroma embeddings (semantic recall)
│       │   └── policy.py      # approval policies (ask/auto/never)
│       ├── skills/
│       │   ├── __init__.py
│       │   ├── base.py        # skill interface
│       │   ├── weather.py
│       │   ├── calendar.py
│       │   └── websearch.py
│       └── utils/
│           ├── __init__.py
│           ├── vad.py         # WebRTC VAD
│           ├── redact.py      # PII masking before server calls
│           └── ledger.py      # logging helpers
├── server/
│   ├── __init__.py
│   ├── main.py                # runs larger server LLM (hybrid mode)
│   └── api_adapter.py         # edge (Zephyr 7B) ↔ server bridge
├── ui/
│   └── web/
│       ├── assets/
│       │   └── orion-logo.svg
│       └── index.html         # minimal dashboard stub
├── tests/
│   └── test_smoke.py
└── scripts/                   # optional helpers
    ├── dev_bootstrap.py
    ├── bench_stt.py
    └── bench_tts.py
```

### Current → Full‑Scale mapping (for this refactor)

* Root `orion.py` → **`orion/app/cli.py`** (entry loop)
* Root `orion_brain.py` → **`orion/app/orchestrator.py`** (prompt compose + routing)
* Root `memory.json` stays in **`data/memory.json`** (or migrate to SQLite later)
* `server/main.py` (keep) and move any root `api_adapter.py` to **`server/api_adapter.py`**
* Add **`orion/__main__.py`** so you can run `python -m orion`

---

## Quick Start Guide

**Prerequisites:** Python 3.11, Git. (Fast Whisper & Coqui TTS install with `requirements.txt`.)

1. **Clone & enter repo**

```bash
git clone https://github.com/aiml-club/orion.git
cd orion
```

2. **Create venv**

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

3. **Install deps**

```bash
pip install -r requirements.txt
```

4. **Run Orion (CLI)**

```bash
python -m orion
```

**Prerequisites:** Python 3.11, Git, Fast Whisper, Coqui TTS.

1. **Clone & Setup:**

```bash
git clone https://github.com/aiml-club/orion.git
cd orion
python -m venv venv
source venv/bin/activate   # or venv\\Scripts\\activate
pip install -r requirements.txt
```

2. **Run Orion:**

```bash
python -m orion.app.cli
```

---

## Technology Stack

* **Programming Language:** Python 3.11
* **ML/AI Libraries:** Fast Whisper, Coqui TTS, Zephyr 7B, Transformers, FAISS/Chroma
* **Development:** FastAPI, Uvicorn
* **Database:** SQLite (+SQLCipher planned)
* **Deployment:** Hybrid edge (local) + server
* **Version Control:** Git & GitHub

---

## 🗺️ Roadmap & Progress

| Phase              | Progress | Notes                            |
| ------------------ | :------: | -------------------------------- |
| 0 — Scaffold       |    50%   | Logging + config ✅               |
| 1 — Core Loop      |    75%   | STT/LLM/TTS ✅, VAD ❌             |
| 2 — Personality    |    25%   | Profiles ✅, sliders ❌            |
| 3 — Modes          |   100%   | Input/output overrides ✅         |
| 4 — Memory         |    66%   | Facts, summaries ✅, vectors ❌    |
| 5 — Explainability |    0%    | Not started                      |
| 6 — Skills         |   50%   | Weather, calendar ✅              |
| 7–10               |    0%    | UI, wake word, community pending |

**Overall Progress:** ~50%

---

## License

Licensed under the **MIT License**. All users own their Orion data fully.

---

## Acknowledgments

* AI/ML Club at SJSU for support.
* Open-source communities (Coqui, HuggingFace, Whisper).
* Broader vision of building **private, personal AI companions**.

---

**Last Updated:** September 25, 2025
**Next Review:** October 2025
