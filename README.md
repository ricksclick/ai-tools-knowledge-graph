# AI Tools Knowledge Graph

> A comprehensive, structured knowledge graph of **AI tools, methodologies, and architectural patterns** for the Claude Code ecosystem and agentic AI development.

[![Knowledge Graph](https://img.shields.io/badge/Knowledge%20Graph-AI%20Tools-blue?style=for-the-badge)](INDEX.md)
[![Tools](https://img.shields.io/badge/Tools-19-brightgreen?style=for-the-badge)](data/knowledge-graph.json)
[![Relationships](https://img.shields.io/badge/Relationships-45+-orange?style=for-the-badge)](data/knowledge-graph.json)
[![Updated](https://img.shields.io/badge/Updated-2025--01--18-brightgreen?style=for-the-badge)]()

## Quick Start

**For AI Agents:**  
➦ Start with [**INDEX.md**](INDEX.md) for rapid tool discovery  
➦ See [**MAINTENANCE.md**](MAINTENANCE.md) for update procedures  
➦ Reference [**data/knowledge-graph.json**](data/knowledge-graph.json) for complete relationships

**For Developers:**  
➦ Browse tools by category below  
➦ Explore the interactive visualization  
➦ Check individual tool documentation

---

## Overview

This repository contains a **curated knowledge graph** of:

- **19 AI Tools** - Development environments, orchestration frameworks, debugging tools
- **8 Methodologies** - Patterns, best practices, and architectural approaches  
- **45+ Relationships** - How tools work together, when to use them, and what they enable

**Focus:** Tools, techniques, and patterns for Claude Code and agentic AI development  
**Source:** Direct tool repositories, official documentation, and architectural analysis

---

## Core Tools (Quick Reference)

### 🔨 Essential (Tier: Core)

| Tool | Purpose | Learn More |
|------|---------|------------|
| **Claude Code** | IDE for agentic coding with plan mode & multi-agent support | [INDEX.md](INDEX.md#claude-code) |
| **Ruflo** | CLI workflow orchestration framework | [INDEX.md](INDEX.md#ruflo-claude-flow) |
| **GSD** | Multi-agent orchestration & task decomposition | [INDEX.md](INDEX.md#gsd-get-shit-done) |
| **Claude Subagents** | Architectural pattern for agent delegation | [INDEX.md](INDEX.md) |
| **Plan Mode** | Essential Claude Code execution pattern | [INDEX.md](INDEX.md) |

### 🚀 Advanced (Tier: Advanced)

| Tool | Purpose |
|------|----------|
| GSD Build | Build automation within GSD ecosystem |
| VoltAgent | Multi-agent framework extending Claude Code |
| Awesome Claude Toolkit | MCP integrations & extensions |
| Everything Claude Code | 10+ repositories of advanced patterns |

### 🪩 Specialized (Tier: Intermediate)

| Tool | Purpose |
|------|----------|
| Talc AI | Debugging & error analysis for Claude Code |
| Paperclip | Alternative workflow architecture to Ruflo |
| Claude Code Templates | Pre-built project templates |
| Claude Loom Templates | Prompt templates & patterns |

---

## Core Methodologies

### Execution Patterns

1. **Plan Mode**
   - Essential Claude Code feature for task decomposition
   - Workflow: Analyze → Plan → Execute → Validate
   - **Best Practice:** Use for tasks with >3 steps

2. **Subagent Delegation**
   - Break complex tasks into specialized agents
   - Optimal count: 2-4 focused subagents per task
   - **Benefit:** Parallelization & error isolation

3. **Context Management**
   - Reserve 20% of context for execution
   - Techniques: Progressive disclosure, summarization, token budgeting
   - **Benefit:** Extended workflow capability

### Integration & Extension

4. **MCP Integration**
   - Extend Claude Code with external tools via Model Context Protocol
   - Common servers: Notion, GitHub, Slack, Web scraping
   - Configuration: `.claude/mcp.json` per project

5. **Hook Automation**
   - Scripts triggered on file edits, commits, deployments
   - Use cases: Auto-linting, test execution, documentation updates

### Development Practices

6. **Test-Driven Development**
   - RED-GREEN-REFACTOR cycle
   - Never write untested code
   - **Benefit:** Confidence through changes

---

## Tool Categories

### Claude Code Ecosystem
Tools directly extending or enhancing Claude Code IDE
- Claude Code, Everything Claude Code, Awesome Claude Code, Claude Code Ultimate Guide

### AI Agent Orchestration
Frameworks for managing multi-agent workflows
- GSD, VoltAgent

### Automation & Business
Workflow automation and business tool integration
- Ruflo, Paperclip, GSD Build, Hook Automation patterns

### LLM Debugging & Testing
Tools for testing and validating AI agent behavior
- Talc AI, Test-Driven Development methodology

### AI Frameworks & Patterns
Core architectural patterns and methodologies
- Plan Mode, Subagent Delegation, Context Management, MCP Integration

### Guides & Resources
Educational content and learning materials
- Claude Code Ultimate Guide, Learn Claude Code, Awesome Claude Skills

---

## Knowledge Graph Structure

### Data Format

**JSON** (`data/knowledge-graph.json`):
- `metadata`: Repository information & versioning
- `categories`: Tool classification (8 categories)
- `nodes`: 19 tools + 8 methodologies + 3 resources (30 total)
- `edges`: 45+ weighted relationship mappings

### Visualization

Mermaid diagrams rendered in `data/visualizations/` showing:
- Tool dependency relationships
- Integration patterns
- Methodology implementations

---

## Key Features

✅ **Tool-Focused**: Exclusively tools, methodologies, and patterns (no people/Instagram data)  
✅ **Structured Data**: JSON format with complete relationships and weights  
✅ **AI Agent Ready**: Designed for programmatic access and automated discovery  
✅ **Quick Reference**: INDEX.md for rapid lookups  
✅ **Maintenance Guide**: MAINTENANCE.md with procedures for AI agents  
✅ **Relationship Mapping**: Understand how tools work together  
✅ **Tiered Classification**: core → advanced → intermediate → reference  

---

## How to Use This Repository

### For AI Agents

1. Start with [INDEX.md](INDEX.md) for rapid tool discovery
2. Query [data/knowledge-graph.json](data/knowledge-graph.json) for complete relationships
3. Follow [MAINTENANCE.md](MAINTENANCE.md) to update the knowledge graph
4. Validate changes using JSON schema

### For Developers

1. Browse tools by category in the table above
2. Reference INDEX.md for quick answers
3. Read individual tool documentation (coming soon)
4. Study methodologies for best practices

### For Researchers

1. Analyze tool relationships in knowledge-graph.json
2. Study methodology implementations
3. Review tier classifications
4. Export for network analysis

---

## Repository Structure

```
ai-tools-knowledge-graph/
├── INDEX.md                    ✗ AI Agent Quick Reference
├── MAINTENANCE.md              ✗ Repository Maintenance Guide
├── README.md                  ✗ This file
├── data/
│   ├── knowledge-graph.json     ✗ Core data (JSON format)
│   └── visualizations/          ✗ Mermaid diagrams
├── docs/
│   ├── tools/                   ✗ Individual tool documentation
│   ├── methodologies/           ✗ Pattern & methodology guides
│   └── examples/                ✗ Usage examples
└── scripts/                    ✗ Maintenance automation scripts
```

---

## Statistics

| Metric | Count |
|--------|-------|
| **Tools** | 19 |
| **Methodologies** | 8 |
| **Categories** | 8 |
| **Relationships** | 45+ |
| **Last Updated** | 2025-01-18 |
| **Tier Levels** | 5 (core to reference) |

---

## Entity Relationships

### Most Connected Tools

1. **Claude Code** (10+ connections)
   - Core to: Ruflo, GSD, VoltAgent, Talc AI
   - Implements: Plan Mode, Subagent Delegation
   - Extended by: Everything Claude Code, Awesome Claude Code

2. **GSD** (8+ connections)
   - Orchestrates: Claude Code, multiple methodologies
   - Uses: Plan Mode, Subagent Delegation, MCP Integration
   - Integrates with: Ruflo, VoltAgent

3. **Plan Mode** (6+ connections)
   - Core feature of: Claude Code
   - Used by: GSD, Learn Claude Code
   - Enables: Subagent Delegation

---

## How This Was Created

This knowledge graph was compiled from:

1. **Direct Tool Analysis**
   - GitHub repositories and documentation
   - Official tool features and capabilities
   - Version information and maturity levels

2. **Architectural Analysis**
   - How tools integrate and complement each other
   - Pattern implementations
   - Ecosystem relationships

3. **Community Patterns**
   - Best practices from tool creators
   - Common usage patterns
   - Recommended configurations

**All data is tool and methodology-focused** with no personal information, Instagram accounts, or people references.

---

## Getting Started

### Quick Discovery
```markdown
# I need to orchestrate a complex workflow
→ Use: GSD + Plan Mode + Subagent Delegation

# I need to automate tasks
→ Use: Ruflo + Claude Code

# I need to debug agent behavior  
→ Use: Talc AI + TDD patterns

# I need external tool integration
→ Use: MCP Integration (Awesome Claude Toolkit)
```

### Learning Path

1. **Beginner**: Claude Code basics, simple scripts
2. **Intermediate**: Plan Mode, Context Management, Hooks
3. **Advanced**: Subagent Delegation, Orchestration
4. **Expert**: MCP Integration, Custom Frameworks

---

## Contributing

To maintain and update this knowledge graph:

1. Read [MAINTENANCE.md](MAINTENANCE.md) for procedures
2. Follow the data structure guidelines
3. Validate JSON before committing
4. Add relationships when discovering new connections
5. Update tool information quarterly

---

## License

This knowledge graph is maintained as a reference resource for the AI tools community.

---

## Related Resources

- [INDEX.md](INDEX.md) - Quick reference guide
- [MAINTENANCE.md](MAINTENANCE.md) - Repository maintenance procedures
- [data/knowledge-graph.json](data/knowledge-graph.json) - Complete dataset
- [Claude Code Official](https://github.com/anthropics/claude-code)

---

**Last Updated:** 2025-01-18  
**Focus:** AI Tools, Methodologies & Patterns (Tool-Only Knowledge Graph)  
**Maintained for:** AI Agents & Developers  

🚀 **Start exploring:** [INDEX.md](INDEX.md)
