# Roadmap: NeuroLex

## Overview

NeuroLex progresses from a clean Claudian fork through intelligence infrastructure, core learning modules, production features, quality verification, and finally voice/visual enhancements — each phase independently testable and building on the last.

## Current Milestone

**v1.0 Initial Release** (v1.0.0)
Status: Not started
Phases: 0 of 6 complete

## Phases

| Phase | Name | Plans | Status | Completed |
|-------|------|-------|--------|-----------|
| 1 | Fork & Rebrand | TBD | Not started | - |
| 2 | Intelligence Layer | TBD | Not started | - |
| 3 | Core Modules | TBD | Not started | - |
| 4 | Production Modules | TBD | Not started | - |
| 5 | Eval & Polish | TBD | Not started | - |
| 6 | Voice & Views (v1.1) | TBD | Not started | - |

## Phase Details

### Phase 1: Fork & Rebrand

**Goal:** A clean NeuroLex shell that runs in Obsidian with no Claudian branding and CLI toggle working
**Depends on:** Nothing (first phase)
**Research:** Likely (need to evaluate Claudian codebase, identify removal candidates)
**Research topics:** Claudian latest stable tag, which features to strip, fork procedure

**Scope:**
- Fork Claudian repository
- Rebrand: plugin ID, name, logo (SVG lockup), CSS color variables
- Remove irrelevant Claudian features
- Add CLI selector setting (Claude Code / Codex)
- Verify clean build and install in Obsidian
- Set up CI and README

**Plans:**
- [ ] 01-01: Fork Claudian and rebrand all references
- [ ] 01-02: Strip irrelevant features, add CLI selector, verify build

### Phase 2: Intelligence Layer

**Goal:** The system brain is operational — it can assess a learner, plan sessions, and report progress
**Depends on:** Phase 1 (clean NeuroLex shell)
**Research:** Likely (MongoDB MCP server design, Voyage MCP server integration, agent patterns)
**Research topics:** MongoDB MCP server approach (build vs adapt existing), Voyage MCP server approach, agent .md file patterns in Claude Agent SDK

**Scope:**
- Deploy MongoDB MCP server (`neurolex-mongodb`)
- Deploy Voyage MCP server (`neurolex-voyage`)
- Implement Diagnostiker agent (learner profile, progress tracking, avoidance detection)
- Implement Architekt agent (session planning, prerequisite graph enforcement)
- Implement Mentor agent (session summaries, progress reports)
- Build Mentor Dashboard view (sidebar panel)

**Plans:**
- [ ] 02-01: MongoDB MCP server with core collections and tools
- [ ] 02-02: Voyage MCP server with embedding tools
- [ ] 02-03: Diagnostiker agent (profile, analytics, avoidance detection)
- [ ] 02-04: Architekt agent (session planning, prerequisite graph)
- [ ] 02-05: Mentor agent and Dashboard sidebar view

### Phase 3: Core Modules

**Goal:** End-to-end learning sessions work — full session flow from Warm-up through Cool-down
**Depends on:** Phase 2 (intelligence layer operational)
**Research:** Unlikely (building on established agent patterns from Phase 2)

**Scope:**
- Implement Korrektor agent (error correction with one-correction rule, tier prioritization)
- Implement Grammatiktrainer agent (prerequisite graph, processing instruction sequence)
- Implement Wortmeister agent (SRS scheduling, vocabulary notes generation)
- Implement Übungsmeister agent (session conductor, module routing, 60-min architecture)
- End-to-end test: full session flow

**Plans:**
- [ ] 03-01: Korrektor agent (error correction engine)
- [ ] 03-02: Grammatiktrainer agent (grammar practice with prerequisite enforcement)
- [ ] 03-03: Wortmeister agent (vocabulary SRS)
- [ ] 03-04: Übungsmeister agent (session conductor) and end-to-end test

### Phase 4: Production Modules

**Goal:** All 10 modules operational — full feature set for language learning
**Depends on:** Phase 3 (core session loop working)
**Research:** Unlikely (follows established patterns)

**Scope:**
- Implement Sprechtrainer agent (role plays, conversation practice, register awareness)
- Implement Schreibtrainer agent (writing tasks, note generation)
- Implement Kurator agent (text ingestion, passive tracking, vocabulary coverage)
- Implement Lernauftrag protocol (goal declaration → plan adjustment → execution → debrief)

**Plans:**
- [ ] 04-01: Sprechtrainer agent (speaking & conversation)
- [ ] 04-02: Schreibtrainer agent (writing practice)
- [ ] 04-03: Kurator agent (real-world text processor)
- [ ] 04-04: Lernauftrag protocol integration

### Phase 5: Eval & Polish

**Goal:** Quality-verified system with first-run calibration — ready for real use
**Depends on:** Phase 4 (all modules operational)
**Research:** Unlikely (eval patterns established from Lernkompass v1)

**Scope:**
- Port and build eval framework (Korrektor, Architekt, behavioral compliance)
- Learner calibration flow (first-run 20-minute diagnostic)
- Grammar note generation (all Zone A/B/C notes with wikilinks)
- Vocabulary note templates

**Plans:**
- [ ] 05-01: Eval framework (Korrektor accuracy, Architekt planning, behavioral compliance)
- [ ] 05-02: Learner calibration flow and grammar/vocabulary note generation

### Phase 6: Voice & Views (v1.1)

**Goal:** Voice-enabled tutoring and rich visual feedback
**Depends on:** Phase 5 (quality-verified system)
**Research:** Likely (TTS integration options, voice loop architecture)
**Research topics:** OpenAI TTS vs ElevenLabs, MCP server for TTS, Obsidian graph view extension API

**Scope:**
- TTS integration (OpenAI TTS or ElevenLabs via MCP server)
- Voice conversation loop in Sprechtrainer
- Session View (live session panel with timer and phase indicator)
- Grammar Graph View (visual prerequisite map with mastery colors)

**Plans:**
- [ ] 06-01: TTS MCP server and voice conversation loop
- [ ] 06-02: Session View and Grammar Graph View

---
*Roadmap created: 2026-04-02*
*Last updated: 2026-04-02*
