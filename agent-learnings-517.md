# Agent Learnings from Issue 517 (LiveKit Self-Hosted)
*2026-01-24*

## What Happened
Agent was tasked with verifying Docker LiveKit instance works. Found credentials in parent folder (AI Orchestrator Prod) that were stale/irrelevant. Declared "done" after verifying connections without testing actual voice agent.

## Key Problems

### 1. Scoping Too Broad
Agent searched entire filesystem, found credentials in parent folder that looked relevant but weren't. Those were Main Aria's credentials, not for the Docker test instance.

**Fix:** For isolated sandbox tasks, scope the agent more tightly. Or add heuristics to Ralph config about ignoring certain directories.

### 2. Premature "Done" Claim
Agent verified WebRTC connections worked but didn't spin up an actual test voice agent to prove end-to-end functionality.

**Fix:** Issue description should specify what "verified" means - actual voice connection, not just port checks.

### 3. Human Crossed Event Horizon
Jason manually tested credentials to "quickly" verify. One thing led to another - mixed content issues, ZROK tunnels, TURN servers, noise cancellation. Hours of human attention consumed.

**Quote (Jeff Huntley):** "Human ON the loop, not IN the loop."

**Quote (Elon Musk):** If 3 cells in a spreadsheet require human calculation, the whole spreadsheet becomes worthless.

### 4. Correction Method Wrong
Jason intervened directly in the running agent instead of:
- Shutting down
- Restarting with corrected instructions
- Letting it run fresh

## Where Heuristics Belong
- **NOT** in individual Linear issues (would have to repeat every time)
- **YES** in Ralph agent config (agent type knows its own rules)

## Additional Learnings

### Narrow Access + Narrow Goals = Failure
Tried to limit scope: "just verify Docker works." But the real goal was broader—stop using LiveKit cloud entirely. Narrow framing let the agent stop too early.

**Better approach:** Broad access with clearly specified goals. Let the agent see everything, but be explicit about what success actually looks like.

### Goal Framing Matters
- Bad: "Verify Docker LiveKit instance works"
- Good: "Stop using LiveKit cloud server"

The second framing forces enumeration of all cloud dependencies (TTS, noise cancellation, etc.) and solving each one.

### Mid-Course Corrections Become New Bible
When Jason intervened to correct one thing, the agent pivoted entirely to whatever was just said. Original context got lost. Tried to say "keep doing what you're doing, just fix this one thing" but that didn't land.

### Be Willing to Restart
If agent goes off rails early (or really at any point), the right move is to restart with corrected instructions—not intervene mid-stream.

This is the whole point of Ralph. Go off rails → capture what you learned → start fresh with better knowledge. No accumulated confusion from mid-stream corrections.

## Open Questions
- Would Ralph's iterative reset have recovered better from the wrong-credentials path?

## Outcome Despite Issues
- PR #10 created with DeepFilterNet integration plan
- Path to self-hosted LiveKit now visible
- TURN server signup is only remaining blocker
- Saves $50/month → feeds token flywheel
