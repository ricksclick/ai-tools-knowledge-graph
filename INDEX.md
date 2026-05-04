# AI Tools Knowledge Graph - Quick Reference Index

## Purpose
This index provides AI agents and developers with a rapid lookup guide to tools, methodologies, and patterns in the Claude Code ecosystem.

## Core Tools (Tier: Critical)

### **Claude Code**
- **Type**: IDE/Development Environment
- **Category**: Claude Code Ecosystem
- **Documentation**: [Full Details](docs/tools/claude-code.md)
- **Key Features**: Plan mode, file operations, terminal access, multi-file editing
- **Best Practice**: Use plan mode for any task with >3 steps
- **Quick Start**: `claude --help`

### **Ruflo (Claude Flow)**
- **Type**: CLI Workflow Framework
- **Category**: Automation & Business
- **Documentation**: [Full Details](docs/tools/ruflo.md)
- **Integration**: Direct Claude Code integration
- **Best Use**: Building lightweight automation workflows
- **Quick Access**: GitHub: `ruvnet/ruflo`

### **GSD (Get Shit Done)**
- **Type**: Orchestration Framework
- **Category**: AI Agent Orchestration
- **Documentation**: [Full Details](docs/tools/gsd.md)
- **Core Patterns**: Plan mode, subagent delegation, task decomposition
- **Best Use**: Complex multi-step workflows at scale
- **Quick Access**: GitHub: `gsd`

---

## Core Methodologies

### 1. **Plan Mode**
   - Essential Claude Code feature
   - Workflow: Analyze → Plan → Execute → Validate
   - **When to use**: Tasks with >3 steps

### 2. **Subagent Delegation**
   - Break complex tasks into specialized agents
   - Optimal count: 2-4 subagents per task
   - **Benefit**: Parallelization & error isolation

### 3. **Context Management**
   - Reserve 20% of context for execution
   - Use rest for references
   - **Techniques**: Progressive disclosure, summarization, token budgeting

### 4. **MCP Integration**
   - Extend Claude Code with external tools
   - **Common servers**: Notion, GitHub, Slack, Web scraping
   - **Config**: `.claude/mcp.json` per project

---

## Tool Categories

| Category | Tools | Use Case |
|----------|-------|----------|
| **Orchestration** | GSD, VoltAgent | Multi-agent workflows |
| **Automation** | Ruflo, Paperclip, GSD Build | Workflow automation |
| **Debugging** | Talc AI, TDD patterns | Testing & validation |
| **Guides & Resources** | Everything Claude Code, Awesome Claude Code | Learning & reference |
| **Frameworks & Patterns** | Claude Subagents, MCP Integration | Architecture patterns |

---

## Quick Lookup by Problem

### "I need to orchestrate a complex workflow"
→ **Use**: GSD (Get Shit Done)

### "I need to automate a series of tasks"
→ **Use**: Ruflo + Claude Code

### "My agent needs external data/tools access"
→ **Use**: MCP Integration (Awesome Claude Toolkit)

### "I'm debugging Claude Code behavior"
→ **Use**: Talc AI + TDD patterns

### "I need to manage context efficiently"
→ **Study**: Claude Code Ultimate Guide + Context Management methodology

---

## Data Source

This knowledge graph was created from AI tools and resources discovered through:
- Direct tool documentation and repositories
- Community patterns and best practices
- Architectural analysis of Claude Code ecosystem

**Last Updated**: 2025-01-18
**Focus**: Tools, methodologies, and patterns only (no people/Instagram data)

---

## For AI Agents Using This Index

1. **Always check the JSON data source** (`data/knowledge-graph.json`) for complete relationship mappings
2. **Follow the weight and tier system**: "critical" → "high" → "medium"
3. **Reference individual tool documentation** in `/docs/tools/` for detailed implementation guides
4. **See MAINTENANCE.md** for repository update procedures

[← Back to README](README.md) | [Full Knowledge Graph](data/knowledge-graph.json)
