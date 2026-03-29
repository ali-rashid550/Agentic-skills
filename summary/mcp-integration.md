# MCP Integration: Extending Claude Code with External Systems

**Source**: https://agentfactory.panaversity.org/docs/General-Agents-Foundations/general-agents/mcp-integration

---

## What This Lesson Is About

Model Context Protocol (MCP) is a technology that gives Claude Code access to information and tools outside your computer—like web browsers, documentation servers, and APIs. Think of it as adding extra "senses" to Claude so it can do real-world tasks.

**Why it matters**: Skills teach Claude *how* to work. MCP teaches Claude *where* to find information. Together with CLAUDE.md (project context), these three elements create a "Digital Full-Time Employee" that understands your goals, knows your workflow, and can safely access external systems.

---

## How MCP Works: The Simple Version

Imagine Claude Code as an assistant confined to your desk with only local files. MCP is like giving it:
- **Web browsing glasses** (Playwright MCP) to see websites
- **A library card** (Context7 MCP) to access documentation
- **Other specialized tools** for APIs, databases, or services

Each MCP server acts as a bridge between Claude and an external system, translating requests and bringing back results.

---

## Key Architectural Pillars

The "Digital FTE" framework consists of three pillars:

1. **CLAUDE.md** = Project understanding (your goals, conventions, context)
2. **Skills** = How Claude works (procedures, workflows, domain expertise)
3. **MCP** = Where Claude finds outside info (web, APIs, documentation, real-time data)

Together, these create an intelligent assistant that understands context, knows procedures, and can access external information safely.

---

## Two Essential MCPs for Beginners

### Playwright MCP (Web Browsing)
Enables Claude to navigate websites, fill forms, take screenshots, and extract data.

**Installation**:
```bash
claude mcp add playwright --transport stdio -- npx -y @playwright/mcp@latest
```

**Use cases**: Web scraping, form submission, UI testing, accessing real-time web content

### Context7 MCP (Documentation Access)
Lets Claude search and retrieve official library/framework documentation.

**Installation**:
```bash
claude mcp add context7 --transport stdio -- npx -y @upstash/context7-mcp
```

**Use cases**: Looking up API documentation, retrieving library references, accessing framework guides

---

## MCP Installation Syntax

The `--` separator is **critical**—it marks where Claude Code CLI flags end and the MCP server command begins.

**Format**:
```bash
claude mcp add <name> --transport stdio -- <server-command>
```

**Key points**:
- Everything before `--` is Claude Code configuration
- Everything after `--` is the MCP server command
- Missing the separator will cause installation to fail

---

## Performance Optimization: MCP Tool Search

Claude Code includes automatic **MCP Tool Search** (lazy-loading):
- Tool definitions are loaded only when needed
- Reduces context overhead by **~85%**
- Prevents Claude from consuming tokens on irrelevant tool definitions
- Can be configured manually via environment variables if needed

---

## Exam-Ready Key Points

1. **Model Context Protocol (MCP) Definition**: A system that extends Claude Code's capabilities to access external information sources and tools beyond local files. Skills teach *how* to do things; MCP teaches *where* to find information.

2. **Playwright MCP**: A web browsing MCP that enables Claude to navigate websites, fill forms, take screenshots, and extract data. Installed with: `claude mcp add playwright --transport stdio -- npx -y @playwright/mcp@latest`

3. **Context7 MCP**: A documentation access MCP that lets Claude search and retrieve official library/framework documentation. Installed with: `claude mcp add context7 --transport stdio -- npx -y @upstash/context7-mcp`

4. **MCP Installation Syntax**: The `--` separator is critical—it marks where Claude Code CLI flags end and the MCP server command begins. Format: `claude mcp add <name> --transport stdio -- <server-command>`

5. **MCP Tool Search (Optimization Feature)**: Lazy-loads tool definitions only when needed, reducing context overhead by ~85%. Prevents Claude from consuming tokens on irrelevant tool definitions.

6. **The Three-Pillar Framework**: CLAUDE.md (context) + Skills (procedures) + MCP (external access) = Digital FTE (Full-Time Employee) that understands goals, knows workflows, and safely accesses external systems.

7. **Appropriate MCP Use Cases**: Current/real-time information, web interaction, API integration, documentation lookup, live data fetching. Best for dynamic, frequently-changing information.

8. **MCP Security Best Practices**: Use verified/widely-adopted servers only, store tokens in system keychain (not plain text), never embed secrets in commands, avoid MCPs for sensitive/confidential data.

9. **MCP Anti-Patterns**: Don't use MCPs for private data, high-frequency polling, untrusted servers, or custom implementations without foundational knowledge.

10. **MCP vs. Skills**: Skills handle repeatable workflows and domain procedures; MCP handles external data fetching and system integration. Use together, not separately.

---

## Security Guidelines

MCP security involves:
- Using **verified, widely-adopted servers** only
- Storing tokens in **system keychain** (not plain text)
- **Never embedding secrets** in commands
- Avoiding MCPs for **sensitive/confidential data** access

Security is crucial because MCP grants Claude access to external systems. Always follow the principle of least privilege and verified sources.

---

## Summary & Takeaways

### Key Concepts Recap
- MCP extends Claude beyond local files to external systems
- Two primary MCPs: Playwright (web browsing) and Context7 (documentation)
- The `--` separator syntax is critical for proper installation
- Lazy-loading optimizations reduce context overhead significantly
- Security requires verified servers, keychain tokens, and no embedded secrets

### What You've Learned
- How to install and configure MCP servers in Claude Code
- When to use MCP (real-time data, web interaction, documentation lookup)
- The architectural role MCP plays alongside CLAUDE.md and Skills
- Security guidelines for safe external system integration
- Context efficiency through tool search and lazy-loading

### How This Fits In
- MCP is the third pillar of the "Digital FTE" framework (after CLAUDE.md and Skills)
- Enables Claude to fetch live documentation, browse the web, and integrate APIs
- Foundational for building intelligent, context-aware AI assistants
- Sets up prerequisites for advanced agent workflows and automation

### Common Pitfalls to Avoid
- **Don't forget the `--` separator** in MCP installation commands—it's easy to miss but essential
- **Don't embed API tokens or secrets** directly in commands; use system keychain instead
- **Don't use MCP for sensitive/private data**—it's designed for public, verified integrations
- **Don't confuse Skills and MCP**: Skills = procedural workflows; MCP = external data/system access
