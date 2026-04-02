# NeuroLex

## What This Is

An AI-powered language acquisition system that lives inside Obsidian. Forked from Claudian, stripped of generic features, and rebuilt as a dedicated language tutor with 10 specialized AI modules, spaced repetition, grammar prerequisite tracking, avoidance detection, and adaptive session orchestration. Each module has a single responsibility, behavioral rules, and a defined interface.

## Core Value

Learners acquire German systematically through an architecturally opinionated system that separates correction from instruction from planning from diagnosis — with every note, vocabulary list, and session recap owned as readable Obsidian notes.

## Current State

| Attribute | Value |
|-----------|-------|
| Type | Application |
| Version | 0.0.0 |
| Status | Initializing |
| Last Updated | 2026-04-02 |

**Repository:** git@github.com:bbehravan/NeuroLex.git

## Requirements

### Core Features

- 10 specialized AI modules (Übungsmeister, Sprechtrainer, Schreibtrainer, Wortmeister, Grammatiktrainer, Korrektor, Kurator, Diagnostiker, Architekt, Mentor)
- Spaced repetition system (SRS) with interval scheduling and semantic grouping
- Grammar prerequisite graph with strict zone enforcement (A → B → C)
- Avoidance detection system (usage ratio tracking, forced production tasks)
- Adaptive session orchestration (60-min sessions: Warm-up → Core → Application → Cool-down)
- Lernauftrag protocol (real-life language goals with deadline-driven plan adjustment)
- Three-tier data: MongoDB engine, Voyage embeddings, Obsidian learner notes
- Mentor Dashboard sidebar view (grammar progress, SRS health, avoidance alerts)

### Validated (Shipped)
None yet.

### Active (In Progress)
None yet.

### Planned (Next)
- Phase 0: Fork & Rebrand — clean NeuroLex shell running in Obsidian
- Phase 1: Intelligence Layer — MongoDB, Voyage, Diagnostiker, Architekt, Mentor, Dashboard
- Phase 2: Core Modules — Korrektor, Grammatiktrainer, Wortmeister, Übungsmeister
- Phase 3: Production Modules — Sprechtrainer, Schreibtrainer, Kurator, Lernauftrag
- Phase 4: Eval & Polish — eval framework, calibration flow, grammar notes
- Phase 5: Voice & Views (v1.1) — TTS, voice loop, Session View, Grammar Graph View

### Out of Scope

- Offline capability — deferred to future phase
- Multi-language support — v1.0 is German only
- Claudian upstream sync — fork diverges freely
- Obsidian mobile support — desktop only for v1.0
- Cost/token management — inference runs through CLI under user's subscription

## Target Users

**Primary:** Solo language learner (German, B1→B2)
- Intermediate German — knows basics, needs structured progression
- Uses Obsidian as personal knowledge base
- Wants to own their learning data as searchable, annotatable notes
- Has real-life language goals (emails, interviews, contracts)

## Context

**Business Context:**
Personal project — built for one learner first, architected to serve many. No commercial requirements for v1.0.

**Technical Context:**
Fork of Claudian (Obsidian plugin with Claude Agent SDK integration). Claudian provides chat UI, streaming, MCP infrastructure, tool rendering. NeuroLex adds module agents, custom views, MongoDB connector, and language-learning-specific settings.

## Constraints

### Technical Constraints

- Must run as Obsidian desktop plugin (Plugin API constraints)
- AI inference via Claude Code CLI or Codex CLI only (no direct API calls)
- MongoDB required for engine data (7 collections)
- Voyage AI MCP server required for embeddings
- Each module agent defined as `.md` file with system prompt + tool restrictions
- Claudian fork — must preserve core infrastructure (Agent SDK, streaming, MCP, chat UI)

### Business Constraints

- Solo developer — phased delivery essential
- No budget for hosted services — local MongoDB, CLI-based inference
- German B1→B2 scope only for v1.0

## Key Decisions

| Decision | Rationale | Date | Status |
|----------|-----------|------|--------|
| Fork Claudian rather than build from scratch | 70% of infrastructure already exists (Agent SDK, streaming, MCP, chat UI) | 2026-04-02 | Active |
| 10 separate agents, not monolithic prompt | Single responsibility per module, per-module model selection, isolated testing | 2026-04-02 | Active |
| Three-tier data (MongoDB + Voyage + Obsidian notes) | Engine queries, semantic intelligence, learner ownership — each tier serves a different need | 2026-04-02 | Active |
| MCP servers for external services | Plugin stays lightweight, services swappable | 2026-04-02 | Active |
| Grammar prerequisite graph with strict enforcement | Pedagogical backbone — never teach B4 before B1 | 2026-04-02 | Active |
| Per-module model overrides | Opus for nuance (Korrektor, Sprechtrainer, Mentor), Sonnet for simpler tasks | 2026-04-02 | Active |
| One-Correction Rule as universal policy | Overcorrection shuts learners down — one error per turn, prioritized by tier | 2026-04-02 | Active |
| German-only for v1.0 | Build deeply for one language rather than shallowly for many | 2026-04-02 | Active |
| CLI-based inference (no API billing) | Runs under user's existing subscription | 2026-04-02 | Active |

## Success Metrics

| Metric | Target | Current | Status |
|--------|--------|---------|--------|
| Full session completes without errors | 100% | - | Not started |
| Korrektor eval pass rate | ≥85% | - | Not started |
| Architekt prerequisite graph enforcement | 100% | - | Not started |
| SRS scheduling accuracy | 100% | - | Not started |
| Avoidance detection precision | ≥80% | - | Not started |
| Session recap generated after every session | 100% | - | Not started |
| CLI toggle works (Claude Code ↔ Codex) | 100% | - | Not started |

## Tech Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| Plugin runtime | Obsidian Plugin API + TypeScript | Target platform |
| AI backend | Claude Code CLI / Codex CLI | Configurable, no API billing |
| Agent framework | Claude Agent SDK | Each module is a custom agent |
| Build | esbuild | Inherited from Claudian |
| Data store | MongoDB (via MCP server) | 7 collections for engine data |
| Embeddings | Voyage AI (via MCP server) | Error clustering, coverage, similarity |
| STT | OpenAI Whisper / gpt-4o-transcribe | Inherited from Claudian |
| TTS | OpenAI TTS / ElevenLabs (v1.1) | Voice conversation loop |
| Testing | Jest + eval framework | Unit tests + GPT-4o judge evals |

## Links

| Resource | URL |
|----------|-----|
| Repository | git@github.com:bbehravan/NeuroLex.git |
| Vision Document | /home/bahman/Obsidian/B_AI/02_projects/neurolex/_vision/vision.md |
| Claudian Source | github.com/YishenTu/claudian |

---
*PROJECT.md — Updated when requirements or context change*
*Last updated: 2026-04-02*
