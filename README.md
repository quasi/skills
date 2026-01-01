# Documentation Writer Skills

Two complementary Claude Code skills for generating documentation optimized for different audiences.

## The Core Distinction

| Aspect | doc-writer-for-humans | doc-writer-for-agents |
|--------|----------------------|----------------------|
| **Audience** | Engineers, operators, learners | LLMs, code assistants, static analyzers |
| **Goal** | Comprehension & usability | Deterministic parsing & reasoning |
| **Optimization** | Cognitive load ↓ | Token count ↓ |
| **Style** | Teaching artifact | API specification |
| **Structure** | Progressive disclosure | Grep-able sections |

## doc-writer-for-humans

Generates documentation that teaches. Optimized for readers who are tired, busy, and intelligent.

**Produces**: READMEs, quickstarts, tutorials, how-to guides, API docs, explanations

**Key principles**:
- Lead with working examples (quick wins)
- One document type per file (don't mix tutorial with reference)
- Progressive disclosure (simple first, complexity later)
- Navigation architecture (breadcrumbs, prerequisites, next steps)

**Document types**:
| Type | Intent | Time to Value |
|------|--------|---------------|
| Quickstart | First success | <5 minutes |
| Tutorial | Teach by doing | 15-30 minutes |
| How-to | Solve specific problem | <10 minutes |
| Explanation | Build mental models | Variable |
| Reference | Lookup facts | Instant |

**Structure**: `references/templates.md` contains ready-to-use templates for each document type.

## doc-writer-for-agents

Generates documentation that machines parse. Optimized for context windows and unambiguous interpretation.

**Produces**: SKILL.md files, CLAUDE.md project files, API specs for code assistants, rule catalogs

**Key principles**:
- Rules prevent bugs, patterns enable fluency (include both)
- RFC-style modal verbs (MUST/SHOULD/MAY)
- Dense notation over prose (DOT graphs, truth tables, BNF)
- Token efficiency (tables > paragraphs, examples > explanations)

**Required sections**:
```
1. Terminology (defined once, no synonyms)
2. Normative Rules (MUST/SHOULD/MAY with consequences)
3. Invariants (always true, mechanically checkable)
4. Exemplar Patterns (complete, idiomatic code examples)
5. Anti-Patterns (forbidden structures with symptoms)
6. Machine Checklist (binary verification gates)
```

**Critical addition**: Exemplar Patterns bridge rules to fluency. Without them, agents write code that's "mechanically correct but operationally awkward" — like having legal code without case law.

**Structure**: `references/patterns.md` contains CLAUDE.md templates, rule catalogs, transformation specs, and complete pattern examples.

## When to Use Which

```
User request
├─ "Write a README" ──────────────────→ doc-writer-for-humans
├─ "Document this for users" ─────────→ doc-writer-for-humans  
├─ "Create a tutorial" ───────────────→ doc-writer-for-humans
├─ "Write a SKILL.md" ────────────────→ doc-writer-for-agents
├─ "Document this for Claude Code" ───→ doc-writer-for-agents
├─ "Create a spec" ───────────────────→ doc-writer-for-agents

```

## Integration

Both skills integrate with other quasiLabs skills:

- **cl-library-designer**: Generate matching docs for library specs
- **elisp-writer**: Generate README and usage docs for Emacs packages

## Installation

Copy both directories to your Claude Code skills location:

```bash
cp -r doc-writer-for-humans /path/to/skills/
cp -r doc-writer-for-agents /path/to/skills/
```

## File Structure

```
doc-writer-for-humans/
├── SKILL.md              # Core guidance (7KB)
├── references/
│   └── templates.md      # Document templates (6KB)
└── LICENSE

doc-writer-for-agents/
├── SKILL.md              # Core specification (15KB)
├── references/
│   └── patterns.md       # Patterns & examples (27KB)
└── LICENSE
```

## License

MIT - See LICENSE in each skill directory.

Author: Abhijit Rao <quasi@quasilabs.in> with the help of Opus 4.5.
