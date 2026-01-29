# AI Asset Architecture (AAA) - Public Specifications

Welcome to the definitive source of truth for the **AI Asset Architecture (AAA)**. 
This repository contains the core specifications, governance policies, and architectural guidelines required for human-AI and AI-to-AI (A2A) collaboration.

## Purpose / Scope
Public specifications and governance references for AAA.

## Ownership / CODEOWNERS
Ownership is defined in CODEOWNERS at the repo root.

## Versioning / Release
Public specs are versioned through Git history and milestone releases.

## How to Consume / Use
Read the bootstrap documents and the registry index for the latest specifications.

## Contribution / Promotion Rules
Changes require governance review and alignment with the AAA playbook.

## 🤖 For AI Agents (A2A / MCP)
This documentation is optimized for AI consumption. If you are an AI Agent, please prioritize the following entry points:

- **Core Constitution**: [AI_CONSTITUTION.md](bootstrap/AI_CONSTITUTION.md) - Mandatory behavioral rules and milestone lifecycle.
- **Architecture Guide**: [WORKSPACE_ARCHITECTURE.md](bootstrap/WORKSPACE_ARCHITECTURE.md) - Multi-repo structure and governance inheritance.
- **Registry Index**: [index.json](index.json) - Capability discovery and asset catalog.

### Protocol Support
- **A2A (Markdown)**: All documents follow strict GFM headers for easy parsing.
- **MCP (Model Context Protocol)**: Use the `read_resource` tool on the above files for structural knowledge injection.

## 🏢 Overview
AAA creates a "Digital Rule of Law" where autonomous agents can operate within safe, auditable boundaries. We transform governance from a manual overhead into a machine-readable runtime.

### Key Principles
1. **Architecture-First**: Technical plan validation before any code change.
2. **Deterministic Governance**: Strict 3-Step Lifecycle (Init -> Asset Preservation -> Completion).
3. **Supreme Court**: Human-in-the-loop arbitration for edge cases.

---
*This repository is the public gateway. Private execution records and evidence are maintained in sovereign workspace repositories.*
