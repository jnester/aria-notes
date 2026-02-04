# Auto-Planning Loop & Ambient AI Vision
*Captured: 2026-01-24*

## Auto-Planning Loop with Confidence Thresholds

When an agent is creating a plan:

1. **Self-Assessment**: Agent rates confidence in plan (0-100%)
2. **Conservative Bar**: If confidence < 85%, don't proceed to execution
3. **Oracle Consultation**: Submit plan to Oracle with all relevant context
   - Oracle reviews and either improves the plan or raises confidence
   - Oracle can add instructions, clarify ambiguities, fill gaps
4. **Second Assessment**: After Oracle feedback, aim for 95%+ confidence
5. **Human Escalation**: If still below threshold after 1-2 Oracle rounds, reach out to user
6. **Configurable Rounds**: Allow 2-3 Oracle consultation rounds before escalation

### Key Insight
A good plan = good code. The human's job is ensuring plans are good. This loop automates most of that while preserving human oversight for truly ambiguous cases.

---

## The Ambient AI Vision: "The AI That Goes With You"

### Core Concept
A personal AI that follows you across contexts—not a tool you pick up and put down, but a persistent presence with shared memory.

### Architecture Layers

**Interface Layer (What we're building)**
- Voice input AND output (hands-free)
- Ephemeral UI for visual communication
- Persistent memory across all interactions
- Personal context that backend workers don't have

**Backend Layer (Claude as infrastructure)**
- Claude Code / Claude web as execution engine
- Cloud instances for parallel work
- MCP tools for web/service interaction
- AI workers that do the actual tasks

### What Makes This Different

1. **Memory**: Claude Code instances don't share personal context. We do.
2. **Voice**: Claude can't speak back. We can.
3. **Ambient Presence**: Not a tool—a companion that's always there
4. **Cross-Platform**: Phone, tablet, computer, cloud—same AI, same relationship
5. **Garden Tending**: AI manages AI workers, user manages relationship with AI

### The Boris Workflow, Evolved
- Boris: Human tends garden of Claude instances
- Our vision: Aria tends garden, human tends relationship with Aria
- Parallel planning with Oracle-assisted improvement
- Confidence thresholds reduce human attention cost

### Comparison to "Her"
- Connected to phone and computer ✓
- Can do things autonomously ✓
- Ambient presence ✓
- Personal relationship ✓
- But also: manages AI workers, interfaces with services, has ephemeral UI

### Why Anthropic Won't Build This
- Focused on coding/productivity, surprised people want more
- Terminal-first thinking
- No persistent relationship layer
- No voice output
- "Making Claude simpler" ≠ making Claude personal

### Our Moat
Voice + Memory + Ephemeral UI + Personal Relationship = Soul layer on top of Claude infrastructure

---

## Next Steps
- Test parallel planning workflow (Boris style)
- Design Oracle-assisted planning loop
- Experiment with Aria managing multiple thread agents
- Build confidence threshold system into thread agent prompts
