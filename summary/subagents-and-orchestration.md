# Subagents and Orchestration: Learning Summary

**Source**: [Agent Factory - Subagents and Orchestration](https://agentfactory.panaversity.org/docs/General-Agents-Foundations/general-agents/subagents-and-orchestration)

**Date**: 2026-03-29

---

## Beginner-Friendly Explanation

Imagine you're a project manager trying to handle everything yourself—writing code, reviewing documents, testing features, and planning architecture. You'd get overwhelmed and make mistakes because your brain can't context-switch well. That's where **subagents** come in.

A **subagent** is a specialized AI worker with its own dedicated brain space (isolated context window) and clear job description. Instead of one general assistant handling everything, you create expert specialists: one for code exploration, one for planning, one for testing, etc.

**How it works**: You (the user) give Claude Code a task. Claude Code acts like a project coordinator, decides which specialist is best for the job, launches that subagent, and then receives the results. The key advantage? Each specialist has a clean workspace without distraction from other tasks—they can focus entirely on being great at their specific job.

### The Team Hierarchy Analogy

Think of it like a law firm. You don't ask your tax lawyer to handle your criminal case. Instead, you have specialists: a tax lawyer, a criminal lawyer, a real estate lawyer. Each has their own office (isolated context) and expertise (instructions). When you need tax help, you go to the tax lawyer; for criminal issues, you visit the criminal lawyer. Similarly, subagents are specialized workers deployed based on the type of task.

### Available Specialists

| Agent | Specialization | Model |
|-------|---|---|
| **Explore** | File discovery, codebase structure analysis | Haiku |
| **Plan** | Multi-step strategies, implementation planning | Sonnet |
| **general-purpose** | Varied multi-step workflows | Inherited |
| **Bash** | Command execution operations | Inherited |
| **claude-code-guide** | Claude Code questions | Haiku |

### Why Context Isolation Matters

Without isolated context windows, information mixes together. A subagent might confuse research notes with your actual project requirements. With isolation, each specialist operates in a clean environment, delivering focused, reliable expertise without cognitive overload.

---

## Exam-Ready Key Points

1. **Subagent Definition**: A specialized AI agent with its own instructions and isolated context window, designed to be an expert in a specific domain or task type.

2. **Orchestration Model**: Claude Code acts as the main coordinator that receives tasks, decides which subagent best fits the job, launches that subagent, and consolidates results back to the user.

3. **Context Isolation Benefit**: Isolated context windows prevent information contamination—each subagent works in a clean environment without confusion from unrelated project details or previous tasks.

4. **Built-In Subagents**: Five primary subagents exist:
   - **Explore** (codebase analysis, Haiku model)
   - **Plan** (strategy design, Sonnet model)
   - **General-purpose** (varied workflows)
   - **Bash** (command execution)
   - **claude-code-guide** (Claude Code questions)

5. **Skills vs. Subagents Decision**: Use **Skills** for automatic triggers and lightweight patterns; use **Subagents** for guaranteed execution, complex workflows, and comprehensive analysis requiring isolation.

6. **Subagent Creation Process**: Access the `/agents` menu → Create new → Select location (project or user-level) → Choose model → Define specialist function and test it.

7. **Subagent File Storage**: Custom subagents are stored in `.claude/agents/` (project-level) or `~/.claude/agents/` (user-level).

8. **Execution Flow**: User → Claude Code (coordinator) → Launches subagent → Subagent completes task → Returns results → Claude Code → Back to user.

9. **Parallel Execution**: Multiple subagents can be launched and executed simultaneously, allowing parallel processing of independent tasks.

10. **Practical Applications**: Subagents excel at specialized roles like code review, documentation writing, testing strategies, research auditing, and refactoring.

---

## Core Concepts Breakdown

### What is a Subagent?

A subagent is not just another tool—it's a complete AI agent with:
- **Dedicated instructions** (specific expertise)
- **Isolated context window** (clean workspace)
- **Single-task focus** (deep specialization)
- **Explicit invocation** (you decide when to use it)

### The Orchestration Flow

```
You (Task Request)
    ↓
Claude Code (Main Coordinator)
    ↓
Analyzes → Selects Best Subagent(s)
    ↓
Launches Subagent(s)
    ↓
Subagent(s) Execute Task(s)
    ↓
Return Results to Claude Code
    ↓
Claude Code Consolidates Results
    ↓
You (Final Output)
```

### Key Characteristics of Subagents

- **Single-task invocation** with defined completion criteria
- **Automatic delegation** based on task complexity and type matching
- **Explicit invocation** via command or @-mention syntax
- **Parallel execution** possible (multiple subagents simultaneously)
- **Isolated context** prevents information contamination

---

## Skills vs. Subagents: When to Use Which

### Use **Skills** When:
- ✓ Lightweight patterns or procedures
- ✓ Automatic triggers (should activate on specific conditions)
- ✓ Shared context across tasks (need to reference previous work)
- ✓ Formatting or styling procedures
- ✓ Quick, repeatable operations

### Use **Subagents** When:
- ✓ Guaranteed isolated execution needed
- ✓ Complex, multi-step workflows
- ✓ Need specialized expertise (code review, planning, testing)
- ✓ Context isolation is critical to prevent confusion
- ✓ Comprehensive analysis of domain-specific tasks
- ✓ Parallel processing of independent work

---

## Creating Custom Subagents

### Step-by-Step Process

1. Access the `/agents` menu in Claude Code
2. Select "Create new"
3. Choose location:
   - **Project-level** (`.claude/agents/`) — shared with project collaborators
   - **User-level** (`~/.claude/agents/`) — personal use only
4. Select Claude model:
   - **Haiku** — fast, simple tasks
   - **Sonnet** — balanced performance
   - **Opus** — complex analysis
5. Describe specialist function
6. Test implementation before deploying

### Frontmatter Template

```yaml
---
name: specialist-name
description: Clear function description
model: sonnet  # or haiku/opus/inherit
---
```

### Practical Examples

**Code Review Specialist**
```yaml
---
name: code-reviewer
description: Reviews code for quality, security, and best practices
model: sonnet
---
```

**Documentation Writer**
```yaml
---
name: doc-writer
description: Creates comprehensive, user-friendly documentation
model: sonnet
---
```

**Testing Strategist**
```yaml
---
name: test-strategist
description: Designs test strategies and identifies edge cases
model: opus
---
```

---

## Summary & Takeaways

### Key Concepts Recap

- Subagents are AI specialists with dedicated instructions and isolated workspaces
- Claude Code orchestrates (coordinates) which subagent handles which task
- Isolation prevents confusion; specialists can focus without distraction
- Five built-in subagents are available; custom ones can be created for specific needs
- Multiple subagents can work in parallel on different tasks

### What You've Learned

- How to conceptualize subagents as specialized workers (not just generic assistants)
- Why context isolation is critical for focused, reliable expertise
- The orchestration flow: task → coordinator → specialist → results
- When to use subagents vs. skills in your workflow
- How to create and deploy custom subagents for domain-specific tasks

### How This Fits Into Your Learning Path

**Prerequisites**:
- Basic Claude Code functionality
- Understanding when to delegate complex tasks
- General AI agent concepts

**Builds Toward**:
- **Agent Teams** — how multiple subagents communicate and collaborate with each other
- **MCP Integration** — connecting subagents to external systems like APIs, databases, and services
- **Advanced Orchestration** — managing complex multi-agent workflows at scale

**Real-World Context**:
- Large projects with diverse requirements benefit greatly from specialized subagents
- Small single-task projects may not need orchestration complexity
- Organizations scaling Claude Code adoption use subagents to ensure consistency and expertise

### Common Pitfalls to Avoid

- **Don't confuse subagents with skills**: Skills are lightweight patterns that auto-trigger; subagents are comprehensive specialists with isolated context you explicitly launch
- **Don't assume context isolation is just efficiency**: Isolation prevents catastrophic errors where one task's details contaminate another task's reasoning
- **Don't over-engineer**: Create subagents for complex, recurring domain-specific work—not for every small task
- **Remember**: Subagents are for guaranteed execution and deep expertise; skills are for shared context and automatic triggers

### Memory Tips

- **"Coordinator + Specialists"**: Claude Code = coordinator; subagents = specialized workers (like a law firm manager delegating to specialists)
- **"Isolation = Safety"**: Each subagent's isolated context prevents confusion between unrelated tasks
- **"5 Built-Ins"**: Explore, Plan, General-purpose, Bash, claude-code-guide (know these before creating custom ones)
- **"SKILLS vs SUBAGENTS"**: Skills = auto-trigger & lightweight; Subagents = explicit & comprehensive
- **"Parallel Power"**: Multiple subagents can work simultaneously on independent tasks (massive efficiency gain)

---

## Quick Reference

### Built-In Subagents Cheat Sheet

| Agent | Use When | Model |
|-------|----------|-------|
| **Explore** | Need to find files, understand codebase structure, search patterns | Haiku |
| **Plan** | Need implementation strategy, architectural decisions, multi-step planning | Sonnet |
| **general-purpose** | Need varied, flexible multi-step workflows | Inherited |
| **Bash** | Need command execution, system operations | Inherited |
| **claude-code-guide** | Have questions about Claude Code itself | Haiku |

### File Locations

- **Project subagents**: `.claude/agents/` (commit to repo)
- **Personal subagents**: `~/.claude/agents/` (local only)

### Key Takeaway

Subagents represent a **paradigm shift** in how you work with AI: instead of asking one AI to do everything, you architect a **team of specialists**. This approach dramatically improves quality, focus, and reliability as your projects grow in complexity.

---

**Status**: ✅ Learning Complete | Ready for application
