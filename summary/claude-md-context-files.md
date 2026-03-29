# Claude.md Context Files - Lesson Summary

## 📚 Beginner-Friendly Summary

**CLAUDE.md** is like a sticky note for your AI assistant. It's a simple markdown file that you place in your project folder, and Claude Code automatically reads it every time you start a new session.

**Why does it matter?** Think of it like an instruction manual for your project. Without it, you'd have to explain the same things to Claude over and over again—your tech stack, folder structure, coding style, etc. CLAUDE.md solves this problem by storing all that information in one place so Claude knows the context immediately.

**How does it work?** Claude Code uses your file system as "external memory." Since AI models don't remember past conversations, CLAUDE.md bridges the gap by providing instant context at the start of each session. It's like giving Claude a cheat sheet about your project before you even say hello.

**What goes in CLAUDE.md?** A well-organized CLAUDE.md file contains six key sections:
1. **Project Overview** — What your project does and why it exists
2. **Technology Stack** — Languages, frameworks, and libraries you use
3. **Directory Structure** — How your files and folders are organized
4. **Coding Conventions** — Your style preferences and naming patterns
5. **Key Commands** — How to run, test, and build your project
6. **Important Notes** — Special tips and things that might trip you up

**How to create it?** You can either use the `/init` command to auto-generate it from your code, or ask Claude directly to create one by analyzing your project.

**Pro tip:** Use **AGENTS.md** as a universal alternative that works with any AI coding agent, while keeping CLAUDE.md for Claude-specific features. Both files together give you maximum flexibility.

---

## 🎯 Exam-Ready Key Points

1. **Definition of CLAUDE.md** — A markdown file in your project root that Claude Code automatically loads at the start of each session to provide persistent context

2. **Core problem it solves** — Eliminates context friction by preventing developers from repeatedly explaining tech stack, directory structure, and conventions

3. **Why auto-loading is needed** — Claude Code is stateless; LLMs have no memory between requests, so CLAUDE.md treats the file system as external memory

4. **Six standard sections** — Project Overview, Technology Stack, Directory Structure, Coding Conventions, Key Commands, and Important Notes

5. **Creation methods** — Can use `/init` command for auto-generation or ask Claude to create it through conversation

6. **AGENTS.md alternative** — Industry-standard universal format that works with any AI agent; recommended to use both AGENTS.md and CLAUDE.md together

7. **Key benefit** — Provides immediate project context without manual setup or repetitive explanations in each session

---

## 📖 Source
- **Course**: General Agents Foundations
- **Lesson**: Claude.md Context Files
- **URL**: https://agentfactory.panaversity.org/docs/General-Agents-Foundations/general-agents/claude-md-context-files
- **Date Summarized**: 2026-03-27
