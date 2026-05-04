# Repository Maintenance Guide for AI Agents

## Overview

This guide is designed for AI agents that need to maintain and update the AI Tools Knowledge Graph repository. It provides procedures for adding new tools, updating relationships, and keeping the knowledge graph current.

## Repository Structure

```
ai-tools-knowledge-graph/
├── INDEX.md                          # Quick reference (start here)
├── MAINTENANCE.md                    # This file
├── README.md                         # Full documentation
├── data/
│   ├── knowledge-graph.json         # Core data (JSON format)
│   └── visualizations/              # Mermaid diagrams
├── docs/
│   ├── tools/                       # Individual tool documentation
│   ├── methodologies/               # Pattern & methodology guides
│   └── examples/                    # Usage examples
└── scripts/                         # Automation scripts (optional)
```

## Data Structure: knowledge-graph.json

### Root Properties

```json
{
  "metadata": {...},          # Repository metadata
  "categories": [...],        # Tool classification buckets
  "nodes": [...],            # Tools, methodologies, resources
  "edges": [...]             # Relationships between nodes
}
```

### Node Structure

Each node must have:

```json
{
  "id": "unique_identifier",     # Format: type_name (e.g., tool_claude_code)
  "type": "tool|methodology|resource",
  "name": "Human-readable name",
  "category": "cat_id",
  "description": "What it is and does",
  "tier": "core|advanced|intermediate|beginner|reference"
}
```

Optional fields based on type:

- **Tools**: `url`, `capabilities`, `integration`, `version`
- **Methodologies**: `workflow`, `benefits`, `best_practice`
- **Resources**: `learning_path`, `content_type`, `coverage`

### Edge (Relationship) Structure

```json
{
  "source": "node_id_1",
  "target": "node_id_2",
  "relation": "extends|runs-on|implements|teaches|...",
  "weight": "critical|high|medium|low",
  "description": "Explanation of relationship"
}
```

## Maintenance Tasks

### Task 1: Adding a New Tool

**When**: A new AI tool is discovered that fits the ecosystem

**Steps**:

1. **Create the node entry** in `data/knowledge-graph.json` under `nodes` array:

```json
{
  "id": "tool_lowercase_name",
  "type": "tool",
  "name": "Display Name",
  "category": "cat_appropriate_category",
  "description": "2-3 sentence description of what it does",
  "url": "https://github.com/...",
  "capabilities": ["feature1", "feature2"],
  "tier": "core|advanced|intermediate",
  "best_practices": ["tip1", "tip2"]
}
```

2. **Add relationships** in `edges` array connecting to related tools/methodologies:

```json
{
  "source": "tool_new_tool",
  "target": "tool_claude_code",
  "relation": "extends|runs-on|alternative|...",
  "weight": "high",
  "description": "How it relates"
}
```

3. **Validate JSON** - Ensure no syntax errors: `python -m json.tool data/knowledge-graph.json > /dev/null`

4. **Commit with message**: `Add tool_name: Brief description`

### Task 2: Adding a New Methodology

**When**: A new pattern or technique is documented

**Steps**:

1. Create methodology node:

```json
{
  "id": "method_name",
  "type": "methodology",
  "name": "Pattern Name",
  "category": "cat_frameworks",
  "description": "How to apply this pattern",
  "workflow": "Step 1 → Step 2 → Step 3",
  "benefits": ["benefit1", "benefit2"],
  "best_practice": "Specific guidance",
  "tier": "core|advanced|intermediate"
}
```

2. Add edges showing which tools implement this methodology

### Task 3: Updating Tool Information

**When**: A tool's capabilities, URL, or status changes

**Steps**:

1. Find the tool's node by `id`
2. Update relevant fields (preserve `id`, `type`, `name`)
3. If significant changes, add entry to CHANGELOG section
4. Commit: `Update tool_name: What changed`

### Task 4: Refreshing Tool Status

**When**: Quarterly or when aware of major changes

**Steps**:

1. For each tool listed in INDEX.md critical section:
   - Verify repository still exists
   - Check for major updates/releases
   - Update `tier` if relevance changed
   - Update `version` if available

2. Commit: `Refresh tool statuses - Q1 2025`

### Task 5: Adding Relationships

**When**: Discovering how tools work together

**Steps**:

1. Add edge to `edges` array:

```json
{
  "source": "source_tool_id",
  "target": "target_tool_id",
  "relation": "extends|orchestrates|debugs|teaches|implements|...",
  "weight": "critical|high|medium",
  "description": "Specific nature of relationship"
}
```

2. Valid relations:
   - `extends` - Tool adds features to another
   - `runs-on` - Tool builds on top of another
   - `orchestrates` - Tool manages execution of another
   - `implements` - Tool realizes a methodology
   - `debugs` - Tool helps troubleshoot another
   - `teaches` - Resource teaches about a tool
   - `documents` - Documentation for a tool
   - `alternative-architecture` - Alternative to another tool

### Task 6: Creating Tool Documentation Files

**When**: High-tier tools need detailed usage guides

**Steps**:

1. Create `docs/tools/{tool_name}.md`
2. Structure:

```markdown
# Tool Name

## Overview
- Quick description
- Primary use case

## Installation
```

## Features
- Feature 1
- Feature 2

## Relationships
- Works with: [Other tools]
- Used by: [What uses this]

## Examples
[Code examples]

## See Also
- [Related tool 1](../tools/tool1.md)
- [Related methodology](../methodologies/method.md)
```

3. Update INDEX.md `[Full Details]` links to point to new docs

## Validation Checklist

Before committing any changes:

- [ ] JSON is valid (use online validator or Python)
- [ ] All node IDs are unique and follow naming convention
- [ ] All relationships point to existing node IDs
- [ ] `tier` values are one of: core, advanced, intermediate, beginner, reference
- [ ] `weight` values are one of: critical, high, medium, low
- [ ] Descriptions are 2-3 sentences max (for nodes)
- [ ] No people names, Instagram handles, or account info in data
- [ ] No duplicate entries
- [ ] Commit message is clear and descriptive

## Common Errors & Fixes

| Error | Cause | Fix |
|-------|-------|-----|
| JSON parse error | Missing comma or bracket | Validate JSON format |
| Link to non-existent node | ID typo | Match exact node ID |
| Duplicate tool entry | Same tool added twice | Merge entries, pick one ID |
| Vague description | Insufficient detail | Expand to explain purpose |
| Missing relationships | Tool not connected | Add edges to related tools |

## Periodic Maintenance

### Monthly
- [ ] Check for new tool releases in Claude ecosystem
- [ ] Verify all GitHub links still work

### Quarterly  
- [ ] Full tool status refresh
- [ ] Remove deprecated tools (mark as deprecated first)
- [ ] Update tier classifications if relevance changed

### Annually
- [ ] Audit entire knowledge graph for accuracy
- [ ] Review methodology relevance
- [ ] Update README with latest statistics

## Tools & Scripts for Maintenance

### Validate JSON Syntax

```bash
# Using Python
python -m json.tool data/knowledge-graph.json > /dev/null

# Using jq (if installed)
jq . data/knowledge-graph.json > /dev/null
```

### Count Tools by Category

```bash
jq '.nodes | group_by(.category) | map({category: .[0].category, count: length})' data/knowledge-graph.json
```

### Find Tools Without URLs

```bash
jq '.nodes[] | select((.url == null) or (.url == "")) | .name' data/knowledge-graph.json
```

## Questions for AI Agents

When deciding what to update:

1. **Is this a tool or methodology?** Check if it fits one of these categories
2. **Is it about Claude Code ecosystem?** Should be related to agentic AI development
3. **Do I have evidence?** Can I link to official repos/docs?
4. **Will other tools reference this?** Should I add relationship edges?
5. **Is it established enough?** Is it used/documented in multiple places?

## Support & Questions

For issues with maintenance procedures:
1. Check this document first
2. Review existing similar entries in knowledge-graph.json
3. Validate your changes using JSON validator
4. Reference the edge types and weight system

---

**Last Updated**: 2025-01-18
**Version**: 1.0
**For**: AI Agents maintaining the knowledge graph
