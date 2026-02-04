# Agent Delegation Learnings - 2026-01-15

## The SSH Task Case Study

Jason asked: "Find SSH instructions between laptop and server, verify they work."

What actually happened:
- Aria found docs but spoke code aloud (violation)
- Aria gave file path verbally instead of scratchpad (had to redirect twice)
- Aria tried SSH command and got stuck at password prompt (no timeout)
- Jason had to Ctrl+C the terminal manually
- Final output required multiple steering corrections

What an autonomous agent would have needed:
- Clear goal: "Find SSH docs, test connection, output to scratchpad"
- Search scope: ai-orchestrator-prod folder
- Permission to test (not just find)
- Guardrail: "Do not modify system configuration"
- Output location specified

## The Core Insight: Pre-Flight Interview Pattern

Before spawning an agent, gather just enough context to prevent failure modes—without requiring Jason to think through everything himself.

### Three Key Questions

1. **Scope** - Where should it look? What should it NOT touch?
2. **Verify** - Should it test what it finds, or just report?
3. **Output** - Skill file? Scratchpad? Just report back?

### The Tension

Too many questions = Jason is back to being fully involved
Too few questions = Agent goes off the rails

**Solution:** For NEW task types, ask questions. For KNOWN task types with existing skills, just execute.

## The Skill of Prompting

The skill is in how you specify:
- Not over-specify (you're doing the work yourself)
- Not under-specify (agent flails or causes damage)
- Stick to actual facts, objective, outcome
- Clear language: "Investigate and test only. Do not make system modifications."

### Example Good Prompt (SSH Task)

"I need to make sure SSH connection works between my server and laptop. This used to work in the past. I don't think it works now but I'm not sure.

We had instructions in one or more files. I think they're under the AI orchestrator prod folder.

Find the instructions and test them—first server to laptop, then if that works, laptop back to server.

Do not make system modifications or updates. This is investigate and test only."

## When Human Must Be Involved vs Autonomous

**Autonomous works when:**
- Goal is clear
- Scope is bounded
- Failure modes are known and handled
- Output location is specified
- Guardrails are explicit

**Human involvement needed when:**
- Discovery changes the goal
- Intuition required (e.g., "that file doesn't look right")
- Multiple valid paths require preference
- Risk of system damage without judgment

**Key realization:** Opus can usually self-heal on ambiguity. Sonnet gets confused by extra information.

## The Wizard UI Pattern

Instead of Jason crafting the perfect prompt upfront, Aria asks 2-3 targeted questions, then crafts the agent prompt WITH guardrails baked in.

Aria becomes the wizard UI—the interview that shapes the task before handoff.

This mirrors what Anthropic's Cowork app does: clarifying questions in cards before execution.

## Skills as Encoded Answers

Once a task type is understood, the answers get encoded into a skill file. Then Jason never gets asked again for that type.

Example: "SSH troubleshooting" skill would already know:
- Don't modify config
- Test both directions  
- Output to workspace
- Timeout after 30 seconds on prompts

## Meta-Learning

The process of doing this task manually with Aria, then reflecting on what happened, then extracting the pattern—this IS the training process. This is how skills get built.

Ralph formalizes this: every correction becomes a training signal.

---

*Captured from voice conversation 2026-01-15 morning*
