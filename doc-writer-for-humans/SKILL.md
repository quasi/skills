---
name: doc-writer-for-humans
description: Generate human-oriented technical documentation optimized for comprehension, usability, and trust. Use when creating READMEs, quickstarts, tutorials, how-to guides, API docs, explanations, or any documentation intended for human readers. Triggers on requests like "write documentation", "create a README", "document this API", "write a tutorial", "explain how to use this". Produces teaching artifacts that prioritize progressive understanding and low cognitive load.
---

# Doc Writer for Humans

Generate documentation optimized for human comprehension. Documentation is a teaching artifact, not a specification.

## Core Principle

Humans read sequentially, forget context, and interpret emotionally. Optimize for:
- Clarity over completeness
- Progressive understanding
- Correct mental models
- Early success (quick wins)
- Low cognitive load

## Bundled Resources

Load these references as needed:

| Resource | When to Load |
|----------|--------------|
| `references/templates.md` | When generating READMEs, tutorials, how-to guides, API references, or explanations. Contains ready-to-use templates for each document type. |

**Template lookup**: Search `references/templates.md` for `## [Type] Template` (e.g., `## README Template`, `## Tutorial Template`).

## Mandatory: Audience Identification

Before generating documentation, identify:

1. **Reader role**: User, developer, operator, decision-maker
2. **Prior knowledge**: Beginner, intermediate, expert
3. **Primary task**: What does the reader want to accomplish?

If unclear, ask for clarification. Never assume.

## Document Type Selection

Select ONE type per document. Mixed intent confuses readers.

| Type | Intent | Structure |
|------|--------|-----------|
| Quickstart | First success in <5 min | Prerequisites → Install → Run → Verify |
| Tutorial | Teach by guided practice | Context → Steps → Checkpoints → Recap |
| How-to | Solve specific problem | Problem → Prerequisites → Solution → Verification |
| Explanation | Build conceptual understanding | What → Why → How it works → Mental model |
| Reference | Facts for lookup | Alphabetical/categorical, consistent format |

## Universal Structure Pattern

Every document follows this progression:

```
1. What this is (one sentence)
2. Why it exists / what problem it solves
3. Minimal working example (immediate value)
4. Common usage patterns
5. Edge cases and caveats
6. Where to go next (navigation)
```

Lead with value. Theory comes after the reader succeeds.

## Navigation Architecture

For documentation sets (multiple documents), establish clear navigation:

```
docs/
├── index.md          # Entry point with map
├── quickstart.md     # First success
├── tutorials/        # Learning paths
│   ├── 01-basics.md
│   └── 02-advanced.md
├── how-to/           # Task-oriented
├── explanation/      # Conceptual
└── reference/        # Lookup
```

Every document must include:
- **Header breadcrumb**: Where am I?
- **Prerequisites link**: What do I need first?
- **Next steps**: Where do I go after?

## Quickstart Rules

Goal: First visible success in minimal time.

1. Assume minimal knowledge
2. Skip theory entirely
3. Every step must be copy-pasteable
4. Show expected output after each command
5. End with "It works!" moment

```markdown
## Quickstart

### Prerequisites
- Python 3.8+
- pip

### Install
```bash
pip install mylib
```

### Run
```python
from mylib import greet
print(greet("World"))
```

Expected output:
```
Hello, World!
```

You now have mylib working. See [Tutorial](tutorial.md) to learn more.
```

Failure to produce visible success is unacceptable.

## Example Design

Examples must be:
- **Minimal**: Smallest code that demonstrates the concept
- **Complete**: Runs as written, no hidden setup
- **Realistic**: Solves plausible problems, not `foo/bar`
- **Correct**: Tested, actually works

Annotate with WHY, not WHAT:

```python
# Cache results to avoid repeated API calls (expensive)
@cache
def fetch_user(user_id):
    return api.get(f"/users/{user_id}")
```

Bad annotation: `# Decorator for caching`

## Step-by-Step Instructions

- Each step produces verifiable state
- One action per step
- Show expected result after each step

Bad:
> Configure and deploy the system

Good:
> 1. Open `config.yaml`
> 2. Set `port: 8080`
> 3. Save the file
> 4. Run `./deploy.sh`
> 5. Verify: `curl localhost:8080/health` returns `{"status": "ok"}`

## Code Snippets

- Must compile/run as written
- State context: filename, location, prerequisites
- Keep short (prefer multiple small snippets over one large block)
- Label pseudo-code explicitly

```python
# File: src/auth.py
# After: pip install pyjwt

import jwt

def verify_token(token: str, secret: str) -> dict:
    """Decode and verify JWT token."""
    return jwt.decode(token, secret, algorithms=["HS256"])
```

## Tone and Language

- **Calm, respectful, encouraging** (never patronizing)
- **Short sentences, active voice**
- **No jargon** unless defined
- **No absolutes** unless true
- **No shame** for reader mistakes

Write for someone tired, busy, and intelligent.

## Error Handling Section

For every documented operation:

1. List likely mistakes
2. Describe symptoms (what user sees)
3. Explain what error means (not just how to silence it)
4. Provide clear fix

```markdown
### Troubleshooting

**Error**: `ConnectionRefused: localhost:5432`

**Cause**: PostgreSQL is not running.

**Fix**:
```bash
# macOS
brew services start postgresql

# Linux
sudo systemctl start postgresql
```
```

## Progressive Disclosure

Start simple. Hide complexity until needed.

- Lead with the 80% use case
- Put edge cases in expandable sections or separate pages
- Link to deeper material, don't dump everything upfront

```markdown
## Basic Usage

```python
result = mylib.process(data)
```

For custom configuration, see [Advanced Options](advanced.md).
```

## Anti-Patterns to Avoid

- Walls of text without headings
- Theory before practice
- Unexplained acronyms
- Incomplete or untested examples
- "Obvious" steps skipped
- Missing navigation/next steps
- Mixing document types (tutorial + reference in one)
- Assuming reader remembers earlier content

## Validation Checklist

Before emitting documentation:

```
[ ] Target audience identified
[ ] Document type is clear (single type)
[ ] Leads with working example
[ ] All code snippets are tested
[ ] Jargon defined or avoided
[ ] Navigation present (breadcrumb, prerequisites, next steps)
[ ] Error scenarios documented
[ ] Progressive disclosure applied
```

## Integration with Other Skills

When documenting code generated by other skills:

- `cl-library-designer` output: Generate user guide matching the spec
- `elisp-writer` output: Generate README with installation and usage
- Code files: Generate API reference from docstrings

## Output Format

Produce `.md` files unless otherwise specified. For complex documentation sets, create multiple files with clear navigation structure.

When finished, summarize:
1. What documents were created
2. Entry point for readers
3. Any sections that need user input (e.g., specific examples)
