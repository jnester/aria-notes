# Master Project & Task List

?? **[Edit this file](F:\repos\aria-notes\master-tasks.md)**

Last updated: 2025-12-12

---

## Personal / Time-Sensitive

- [ ] **Monday**: Call Anthem - ask what happens if Medicaid denies or doesn't respond before open enrollment ends. Does the application stay open or do you lose coverage?

---

## Active Projects

### Voice Agent System
**Status**: In Progress  
**Current Focus**: Extended thinking integration, TTS stability, visual communication  
**Next Actions**:
- [ ] Timeboxed Orpheus TTS on VLLM (30-60 min) - perfect voice, local privacy
- [ ] Implement visual communication pipeline (image input/output via LiveKit + Imagen)
- [ ] Background agent architecture for async work delegation
- [ ] Complete LiveKit Vue client with working voice connection

### Dynamic UI System
**Status**: Working  
**Current Focus**: Artifact system, iframe prototypes integration  
**Next Actions**:
- [ ] Build executive dashboard artifact
- [ ] Implement code review & approval workflow
- [ ] Create system monitoring dashboard

### AI Orchestrator
**Status**: Stable  
**Current Focus**: Background agent coordination  
**Next Actions**:
- [ ] Document agent communication patterns
- [ ] Improve task completion verification

---

## Completed Recently
**Nov 22-23:**
- [x] Fixed rolling summaries with Gemini agent (using Antigravity IDE)
- [x] Enabled extended thinking (2048 token budget) with tool use support
- [x] Switched to Inworld TTS for stability
- [x] Created progress notes system

**Nov 20:**
- [x] Created prototypes system for safe experimentation
- [x] Built IframeArtifact component for embedding prototypes
- [x] Fixed Dynamic UI emoji rendering issues
- [x] Established master task list system

---

## Backlog
- [ ] System monitoring dashboard
- [ ] Decision matrix tool
- [ ] Architecture diagram viewer
- [ ] Establish comprehensive organization system (task lists, notes, documentation structure with clear rules and ownership)
- [ ] Debug original Orpheus TTS issues (repeated audio, word cutoffs) - if VLLM attempt fails

---

*This file is the single source of truth for Jason's projects and tasks.*  
*Main Aria is responsible for keeping it updated.*  
*All agents can read; updates should be coordinated through Main Aria.*




### Biometrics Integration (Xiaomi Smart Band 10)
**Status**: Planned  
**Next Actions**:
- [ ] Set up data pipeline (Band -> Gadget Bridge -> Custom Endpoint -> Aria)
- [ ] Implement ambient context sensing in agent.py
- [ ] Create visual dashboard for heart rate/HRV metrics
