# Satisfactory Framework for Life and Business

*Captured: 2026-01-20*

## The Core Insight

In Satisfactory, when you build something, it exists permanently. You solve a problem once—figure out how to produce 500 iron ingots per minute—and that production is stable forever. It becomes a foundation you can build on, an abstraction you can depend on.

Jason wants to apply this to life and business. Wrap the chaos of real life in abstractions that feel like a video game. Wake up every day and "play the game" instead of being overwhelmed by the firehose of decisions and information.

## The Satisfactory Metaphor

**Resources:** time, money, energy, connections, AI compute, knowledge

**Production Facilities:** agents, workflows, systems you've built, relationships

**Throughput:** leads per week, revenue per month, agent tasks completed, problems solved

**Tiers:** levels of autonomy and reliability
- Tier 0: Holding the button (manual, fragile)
- Tier 1: Machines running, you're placing them (reliable, you're still in the loop)
- Tier 2: Blueprints, stamping down whole factories (scalable, human on the loop)
- Tier 3: Self-expanding, you're just steering (autonomous)

---

## Silos and Their Tiers

### 1. Income

- **Tier 0:** Zero income, no clients
- **Tier 1:** First client closed, work delivered, payment received. Proof the loop works.
- **Tier 2:** Repeatable. Multiple clients, predictable revenue.
- **Tier 3:** Scaled. Revenue exceeds needs, can invest in growth.

### 2. Memory (Aria System)

- **Tier 0:** Functional but unreliable. Amnesia issues. Key things get forgotten.
- **Tier 1:** Scalable and reliable. Remembers what needs to be remembered. The three-tier architecture (key moments, rolling summaries, full history) is implemented and working.
- **Tier 2:** Anticipatory. Surfaces things before asked. Recognizes patterns. Says "this keeps coming up, should we make it a rule?"

### 3. Agent Autonomy - Knowledge Work

- **Tier 0:** Can spin up an agent for a task, it generally completes but may need intervention.
- **Tier 1:** Reliable one-shot completion. Give task, get result.
- **Tier 2:** Proactive. Agent identifies related tasks and does them without being asked.

### 4. Agent Autonomy - Coding

- **Tier 0:** Can do coding tasks but often need to finish the last 10%.
- **Tier 1:** Autonomous PRs that generally work first try. Proper testing, verification.
- **Tier 2:** Architectural decisions. Agent can refactor, improve, not just implement.

### 5. Agent Orchestration (Main Aria)

- **Tier 0:** Basic orchestration. Gates Linear for agents. Coordinates but doesn't verify.
- **Tier 1:** Strategic. Verifies agent work. Pushes back when quality is low.
- **Tier 2:** Proactively strategic. Notices patterns across tasks. Spawns agents based on what she sees coming.

### 6. Ralph / Long-Horizon Agents

- **Tier 0:** Not yet using Ralph. Aware of the concept.
- **Tier 1:** Effective Ralph agents with human on the loop. Minimal intervention. Ralph completes multi-step tasks with periodic guidance.
- **Tier 2:** Oracle supervising Ralphs. Human only intervenes on true exceptions.
- **Tier 3:** Ralphs spawning sub-Ralphs. Self-organizing swarm completing objectives.

### 7. Oracle Integration

- **Tier 0:** Oracle exists, can be consulted manually.
- **Tier 1:** Routine part of the system. Consulted regularly for strategy and course correction.
- **Tier 2:** Oracle as supervisor layer for autonomous agents. Writes corrective prompts for Ralphs.

### 8. Voice Aria

- **Tier 0:** Functional voice assistant. Conversations work but blocking operations, manual delegation.
- **Tier 1:**
  - Main Aria used seamlessly as a tool, not spoken of as separate entity
  - Non-blocking async operations, conversations flow naturally
  - Thought loop fires at least once daily (ambient awareness)
  - Android app, can talk without screen on
  - Main Aria pulls context from conversation history automatically
- **Tier 2:**
  - Ambient, always on regardless of device or screen state
  - Context flows seamlessly between devices
  - Chooses right modality (voice vs artifacts) without being told
  - Thought loop hourly with actual agency, makes decisions autonomously
  - Proactively notices and handles things

### 9. Development Workflow

- **Tier 0:** Can't even see Main Aria logs updating in real time. Afraid to modify her. Feature freeze.
- **Tier 1:** Safe effective dev workflow. Worktrees with parallel development. Separate test/dev instance. Can iterate without fear of breaking production.
- **Tier 2:** Automated testing. CI/CD. Changes deploy with confidence.

### 10. Dashboard / Visibility

- **Tier 0:** No visibility. Flying blind.
- **Tier 1:** Metrics you can see. Current state of each silo. What tier you're at.
- **Tier 2:** Shows bottlenecks. Suggests what to work on next. "Your throughput is limited by X, here's how to unlock it."

---

## The Business Model (Ralph Vision)

Two Ralph loops:
1. **Lead Gen Ralph:** Generates warm leads, schedules meetings
2. **Implementation Ralph:** Builds the deliverables after contracts close

Jason's role: Interface layer. Takes meetings, builds trust, closes deals, supervises Ralphs. The human parts.

This is Tier 2/3 of the business. Tier 1 is doing it all manually first to understand what you're automating.

---

## Immediate Tier 1 Unlocks

Small changes with outsized impact:

1. **LiveKit agent naming** - Thread 504 found the answer. Enables dev instances and multi-user.
2. **Thought loop bug fix** - One daily thought loop gives ambient awareness.
3. **Main Aria reads conversation history** - Seamless context transfer, Voice Aria can delegate with minimal overhead.
4. **Main Aria log streaming fix** - Can actually see what's happening.

---

## The Dashboard Vision

Wake up every day and see:
- Current tier for each silo
- Throughput metrics (leads, revenue, tasks completed)
- Bottlenecks (what's limiting you)
- Suggested next action (what would unlock the most)
- Progress toward next tier

It's not a to-do list. It's a factory view of your life.
