# Agentic Skills Collection

Reusable skills for Claude Code agents that teach AI how to complete domain-specific tasks.

## Skills Included

- **docx** — Word document creation and editing
- **pptx** — Presentation building
- **xlsx** — Excel spreadsheets and data analysis
- **pdf** — PDF extraction and manipulation
- **browsing-with-playwright** — Web automation
- **fetch-library-docs** — Library documentation access
- **doc-coauthoring** — Documentation workflows
- **lesson-summarizer** — Educational content summarization
- **internal-comms** — Company communication templates
- **interview** — Discovery conversations
- **skill-creator** — Create new skills
- **skill-creator-pro** — Production-grade skill development
- **skill-validator** — Quality validation
- **theme-factory** — Design theming toolkit

## Installation

```bash
git clone https://github.com/ali-rashid550/Agentic-skills.git
cp -r .claude/skills ~/.claude/skills
```

## Usage

Use skills in Claude Code with `/skill-name`:

```
/docx          # Documents
/pptx          # Presentations
/xlsx          # Spreadsheets
/pdf           # PDFs
/browsing-with-playwright  # Web automation
```

## What Are Skills?

- Markdown procedures that guide AI agents
- Encode organizational expertise and best practices
- Provide step-by-step guidance for consistent outputs
- Work alongside CLAUDE.md and MCP servers

## Key Benefits

- **Reusable** — Version in Git, share across teams
- **Scalable** — Support hundreds of skills efficiently
- **Non-Technical** — Domain experts can write skills
- **Integrated** — Works with MCP servers
- **Validated** — Built-in quality assurance

## Documentation

- Concept Overview: `summary/concept-behind-skills.md`
- MCP Integration: `summary/mcp-integration.md`
- Skill Creation: `skill-creator/SKILL.md`
- Quality Standards: `skill-validator/`

## Security

- Use verified MCP servers only
- Store tokens in system keychain
- Never embed secrets in commands

## Contributing

1. Create skill with `skill-creator`
2. Follow standard structure
3. Validate with `skill-validator`
4. Submit pull request

---

GitHub: [https://github.com/ali-rashid550/Agentic-skills](https://github.com/ali-rashid550/Agentic-skills)
