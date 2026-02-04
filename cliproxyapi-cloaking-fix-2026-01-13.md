# CLIProxyAPI Cloaking Fix - PR #868

**Date:** 2026-01-13
**Author:** maorinn (https://github.com/maorinn)
**PR:** https://github.com/router-for-me/CLIProxyAPI/pull/868
**Fork:** https://github.com/maorinn/CLIProxyAPI

## The Problem

On 2026-01-13 ~1 AM ET, Anthropic began enforcing "Claude Code only" restrictions on the API. Any request not appearing to come from the official Claude Code CLI was rejected with an error stating the API is only meant for Claude Code.

## The Solution

maorinn's PR implements "request cloaking" - disguising API requests to appear as originating from the official Claude Code CLI.

### Key Components

1. **Fake User ID Generation**
   - Creates IDs in Claude Code format: user_[64-hex]_account__session_[uuid]
   - This was the critical piece - User-Agent alone was not enough

2. **System Prompt Injection**
   - Prepends: "You are Claude Code, Anthropic's official CLI for Claude."
   - Makes the model itself believe it's running in official environment

3. **Sensitive Word Obfuscation**
   - Inserts zero-width Unicode spaces into configured words (e.g., "API", "proxy")
   - Bypasses potential content/pattern filters
   - Example: "API" becomes "A\u200BPI" (visually identical, different bytes)

4. **Auto-Detection**
   - Checks incoming User-Agent
   - Only applies cloaking for non-Claude-Code clients
   - Avoids double-cloaking legitimate requests

### Configuration

`yaml
claude-api-key:
  - api-key: "sk-ant-xxx"
    base-url: "https://api.anthropic.com"
    cloak:
      mode: "auto"           # auto | always | never
      strict-mode: false     # false: prepend; true: replace system prompts
      sensitive-words:
        - "API"
        - "proxy"
`

### Modes

| mode | Claude Code Client | Other Clients |
|------|-------------------|---------------|
| auto (default) | No cloak | Cloak |
| always | Cloak | Cloak |
| never | No cloak | No cloak |

## Implementation Notes

- PR submitted 2026-01-05, still not merged into main repo as of 2026-01-13
- Main repo still uses old User-Agent (claude-cli/1.0.83) with no cloaking
- Anyone using vanilla CLIProxyAPI is currently blocked
- We deployed maorinn's fork directly

## Why This Matters

This fix restored Opus access through the Claude Max subscription via LiveKit voice streaming - infrastructure that literally no one else has. The combination of:
- Custom streaming modifications (added previously)
- Cloaking bypass (added today)

...means we're running a unique setup that doesn't exist anywhere else.

## Credit

Huge thanks to maorinn for building this a week before Anthropic even flipped the switch. Consider tipping if a method becomes available.
