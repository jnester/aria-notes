# Product Vision: Dashboard Agent / Main Orchestrator
*Captured: 2026-01-28*

---

## Core Insight: The Gap in Existing Systems

**ClaudBot limitation:** Can't interact with thread/sub-agents directly. With Jason's system, you CAN talk to thread agents directly, jump in to unblock them, spend 10% time to move them forward.

**Sub-agents become apps:** They build up context, become experts in their area, persist and can be returned to. Pool of specialized agents.

**Main orchestrator coordinates all:** Builds knowledge over time about which agent handles what role, routes requests intelligently.

---

## Product Vision: "ChatGPT but better"

### What's Missing from ChatGPT/Deep Research:
1. More tools than just deep research
2. Ability to launch MULTIPLE background agents
3. A **coordinator agent** to manage all long-running agents
4. Don't have to visit each one (but CAN if needed)
5. Voice/hands-free interaction with main orchestrator
6. Real-time collaboration on live artifacts
7. Built-in task management system

### The UX Vision:
- **Always talk to main agent only**
- Persistent task list panel (left side of screen in Jason's mind)
- Agent discerns: is this a project/goal or just a task?
- Tasks → spin up sub-agent, handle automatically
- Projects/goals → more intelligent breakdown

### Intelligence Layer:
- Help user PLAN what needs to be done
- Help user DISCOVER what they actually want
- Perfect recall of all past conversations

---

## What Jason Has Already Prototyped:
- ✅ Voice experience
- ✅ Long-running background agents (visitable, talkable)
- ✅ Task management system (Linear)
- ✅ Agents using Claude Tasks for work breakdown
- ⚠️ Sub-agent work not all logged/visible (maybe fine?)

---

## ClaudBot Memory Fix (Today):
- Memory had amnesia - captured coarse-grain facts only
- Missed: what was discussed, importance, synthesis
- **Fix:** Installed memory configuration skill from Claude Hub
- Configured: index actual session conversations
- Goal: All conversations indexed as part of agent memory going forward

---

## Open Questions:
- Does Claude Hub / ClaudBot UI have sub-agent visualizations? (Check before assuming gap)
- ClaudBot functionality is "buried" - unclear how to use advanced features

---

## Strategic Positioning:
This is the productized version of everything Jason has been building. The unique value is the orchestration layer that no one else has shipped yet—voice-first, agent-visible, task-integrated.

---

## Personal System Improvements (Immediate)

Now that the vision is clear, Jason can:
1. Customize his current system to close gaps
2. Build prototype sub-components (e.g., memory system that indexes all conversations)
3. Make it work for himself first before productizing

### Background Agent Capability Gap:
- Agents need to take work through to **actual completion**
- Currently agents spin up but don't always finish the job

### Ralph Integration:
- Every agent launch should essentially be a Ralph loop
- Deep research is good, but agents need MORE TOOLS
- Ralph = the loop that actually completes work
- Integrate Ralph into current system so agent creation spawns a real Ralph loop
- Then iterate on making those loops actually work

---

## Build Order:
1. Get personal system working end-to-end
2. Close gaps (memory, Ralph loops, agent completion)
3. Prototype dashboard UI
4. Then spec for productization

### Key Insight:
Once Ralph loops work reliably in the personal system, they become the **foundational units** of long-running agentic work for the final product. Prove it works for Jason first ? then it's the core primitive for the productized version.

---

## Architecture Wrestling (Stream of Consciousness)

### What Jason's System Has That ClaudBot Doesn't:
- Live dictation capture (like automatic meeting notes)
- Everything captured is actionable and gets broken down
- (But: not automatic enough, requires manual steps, memory imperfect)

### What ClaudBot Has That Jason's Doesn't:
- Self-improvement as first-class citizen
- Knows how to update + restart itself
- Only does config changes, not code changes = no syntax error risk
- Agent primitives are there, everything is configurable
- Thousands of config options (overwhelming but powerful)

### Key Insight: ClaudBot as Agent Primitive
- Think of ClaudBot as a discrete agent unit
- ALL agents could be ClaudBots: Voice Aria, Main Aria, thread agents
- Configure them, then spawn them
- Save/duplicate a working agent config
- New agents = copy of ClaudBot with skills, maybe lacking only memory
- Feed new agents with relevant memories at spawn time
- (Maybe sub-agents already work this way under the hood?)

### The Core Tension:
Option A: Build memory system for current Voice Aria (install library, point at files)
- Pro: Keep current system
- Con: Developing our own memory system

Option B: Hook LiveKit up to ClaudBot, run Voice Aria on ClaudBot infra
- Pro: Memory already working, skills already there, community updates
- Con: Migration effort, unknown unknowns

### The Question:
What's the path of least resistance to get:
1. Perfect conversation indexing
2. Background agents that complete work (Ralph loops)
3. Dashboard visibility
4. Voice-first interaction

Is it faster to add those to ClaudBot? Or add ClaudBot's strengths to the current system?
