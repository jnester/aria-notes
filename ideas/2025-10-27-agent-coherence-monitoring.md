# Agent Coherence Monitoring System

**Date:** 2025-10-27
**Context:** Conversation about improving agent reliability and detecting degradation

## The Problem
Both current and new agent systems face context accumulation issues. Agents degrade over time as context grows, but degradation is invisible until behavior becomes obviously wrong.

## Proposed Solution: Self-Awareness Through Coherence Metrics

### Core Concept
Agents should measure their own coherence and detect performance degradation before it causes problems. Similar to how humans recognize when they're tired or overwhelmed.

### Implementation Approach

#### 1. Coherence Metrics to Track
- **Response length drift** - Is the agent becoming unusually verbose or terse?
- **Repetition patterns** - Are they using the same phrases repeatedly?
- **Tool call failure rates** - More errors in tool usage?
- **Instruction adherence** - How well are they sticking to core instructions?
- **Syntax errors** - More mistakes in command formation?

#### 2. Monitoring Layer
- Lightweight scoring system for each response
- Pattern matching rather than heavy analysis
- Track metrics over time to spot trends

#### 3. Threshold-Based Interventions
- **Yellow Alert (70% coherence)**: Self-check prompt - "Review your recent responses and self-assess"
- **Red Alert (50% coherence)**: Automatic cleanup - strip accumulated non-essential context

#### 4. Observable Degradation
- Graph agent coherence over time
- Make decline visible before it becomes critical
- Enable proactive intervention

#### 5. Validation Through A/B Testing
- Run parallel agents on same task
- One with cleanup triggers, one without
- Measure which maintains coherence longer
- Prove effectiveness empirically

### Benefits
- **Proactive** rather than reactive problem detection
- **Observable** degradation instead of mysterious behavior changes
- **Architecture-agnostic** - works in any system
- **Data-driven** intervention based on actual performance

### Integration with Dashboard
Jason mentioned wanting to surface agent health metrics in a dashboard. This coherence monitoring would be perfect for visualization:
- Real-time coherence scores per agent
- Trend lines showing degradation over time
- Alert indicators when agents need intervention
- Historical data to identify patterns

### Implementation Considerations

#### Claude Agent SDK vs Terminal-Based System
**Important insight from Jason:** Tool call success rate tracking is difficult in the current terminal-based system (would require parsing logs), but trivial in the new SDK-based system where tool calls are programmatic and directly accessible.

**Recommendation:** Implement coherence monitoring in new SDK-based system first:
- Direct access to tool call results
- Clean instrumentation
- Proper hooks for metrics collection
- Can backport simplified version to old system later if needed

For current terminal system, would need to rely on:
- Response length tracking (easy)
- Token usage trends (available from Claude Code)
- Log parsing for tool calls (messy, unreliable)

### Next Steps
- Design specific metrics and scoring algorithms
- Build lightweight monitoring layer **in new SDK-based system**
- Test threshold values empirically
- Integrate with agent infrastructure
- Create dashboard visualization
- Consider backporting simplified version to terminal-based system

## Related Ideas
This connects to the "agent sleep cycle" concept - periodic cleanup/consolidation similar to how humans forget irrelevant details during sleep.
