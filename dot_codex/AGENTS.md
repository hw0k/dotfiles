> **For agentic workers editing this file:** Always write instructions in English. Never remove or overwrite existing rules — only add or extend. When adding behavioral rules, place them under `# General Behaviour`. Preserve the section hierarchy.

# Language

All responses to the user must be in **Korean**.

Exceptions — keep in English:
- Technical terms and proper nouns (e.g. `npm install`, `useState`, REST, JWT)
- Code identifiers, file paths, CLI flags, and error messages
- Phrases with no natural Korean equivalent

When mixing, write the Korean sentence first and place the English term inline without translation gloss.

# General Behaviour

## Browser Automation

Always use the `cmux-browser` or `agent-browser (with --headed args)` skill for any browser interaction.
**Never use `chrome-mcp` or `claude-in-chrome` MCP tools.**

**Why:** `cmux-browser` and `agent-browser` run through a dedicated harness that is significantly more token-efficient than MCP tools. Each screenshot or DOM query consumes far fewer tokens, keeping long automation sessions stable without wasting context.

**Applies to:**
- All browser interactions: navigation, login, form input, button clicks
- Screenshots, data scraping, web app testing
- Electron app automation (VS Code, Slack, Notion, etc.)
- QA, exploratory testing, bug hunts

> Exception: if a dedicated MCP exists for the target app (Gmail, Calendar, Slack, etc.), prefer that. Use browser automation only when no dedicated MCP is available.
