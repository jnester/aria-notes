# Thread State Notes - Context Window Management

*Captured: December 16, 2025*

## The Problem
Agents hit context window limits and compact/restart, losing active work state.

## Jason's Technique (15 years as developer)
Before leaving work, write a quick note capturing the *active thread* - not a full summary. Use shorthand that triggers memory recall. Next day, read the note, context floods back, pick up right where you left off within 5 minutes.

## Application for Agents
Before compaction, write a "thread state note":
- Active task
- Current hypothesis/approach  
- Next step
- Key context that would be lost

Load this into fresh context as starting point. Pick up the thread instead of starting from zero.

## Key Insight
Don't summarize everything. Capture the *pointer* to the active work. Targeted, surgical, thread-focused.

## Applies To
- Main Aria
- Thread agents
- Any agent with hard context cutoffs

(Voice Aria uses sliding window with rolling summaries - different approach)
