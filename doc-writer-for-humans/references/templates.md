# Document Templates Reference

Detailed templates for each documentation type. Load when generating specific document types.

## README Template

```markdown
# Project Name

One-line description of what this does.

## Why

What problem does this solve? Why would someone use this?

## Quickstart

```bash
# Install
pip install project-name

# Run
python -m project_name --help
```

## Usage

### Basic Example

```python
from project_name import Thing

thing = Thing()
result = thing.do_something("input")
print(result)  # Expected: "output"
```

### Common Operations

| Operation | Code | Result |
|-----------|------|--------|
| Create | `Thing()` | New instance |
| Process | `thing.process(x)` | Processed x |

## Configuration

| Option | Default | Description |
|--------|---------|-------------|
| `timeout` | 30 | Seconds before timeout |
| `retries` | 3 | Number of retry attempts |

## Troubleshooting

### Error: ConnectionRefused

**Cause**: Server not running.
**Fix**: Start server with `./start.sh`

## API Reference

See [API Documentation](docs/api.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT - see [LICENSE](LICENSE).
```

## Tutorial Template

```markdown
# Tutorial: [Learning Goal]

Learn to [specific skill] by building [concrete outcome].

**Time**: ~X minutes
**Prerequisites**: [Link to prerequisites]
**What you'll build**: [Screenshot or description]

## Overview

By the end of this tutorial, you will:
1. [Skill 1]
2. [Skill 2]
3. [Skill 3]

## Step 1: [Action]

[Brief context - one sentence max]

```bash
command here
```

You should see:
```
expected output
```

✓ Checkpoint: [What should be true now]

## Step 2: [Action]

...

## Step N: [Final action]

...

## What You Learned

- [Skill 1]: [One-sentence summary]
- [Skill 2]: [One-sentence summary]

## Next Steps

- [Tutorial 2: Advanced topic](tutorial-2.md)
- [How-to: Common task](howto-task.md)
- [Reference: Full API](api.md)
```

## How-To Template

```markdown
# How to [Specific Task]

[One sentence: When you need to do this]

## Prerequisites

- [Requirement 1]
- [Requirement 2]

## Steps

### 1. [First action]

```bash
command
```

### 2. [Second action]

```bash
command
```

### 3. Verify

```bash
verification command
```

Expected:
```
success output
```

## Common Variations

### Variation A: [When this applies]

[Modified steps]

### Variation B: [When this applies]

[Modified steps]

## Troubleshooting

### Issue: [Symptom]

**Cause**: [Why]
**Fix**: [How]

## Related

- [How to related task](related.md)
- [Reference for this feature](reference.md)
```

## API Reference Template

```markdown
# API Reference

## Module: `module_name`

### `function_name(arg1, arg2, *, kwarg=default)`

[One-line description]

**Parameters**:
- `arg1` (type): Description
- `arg2` (type): Description
- `kwarg` (type, optional): Description. Default: `default`

**Returns**: 
- `type`: Description

**Raises**:
- `ErrorType`: When condition

**Example**:
```python
result = function_name("input", 42)
# Returns: expected_value
```

**Notes**:
- Important caveat 1
- Important caveat 2

---

### `ClassName`

[One-line description]

**Constructor**: `ClassName(arg1, *, kwarg=default)`

**Attributes**:
- `attr` (type): Description

**Methods**:

#### `.method(arg)`

[Description]

**Example**:
```python
obj = ClassName("x")
obj.method("y")  # Returns: "xy"
```
```

## Explanation Template

```markdown
# Understanding [Concept]

## What It Is

[One paragraph: Define the concept simply]

## Why It Matters

[One paragraph: What problem does this solve?]

## How It Works

[Explain the mechanism. Use diagrams if helpful.]

```
┌──────────┐    request    ┌──────────┐
│  Client  │ ────────────> │  Server  │
└──────────┘ <──────────── └──────────┘
               response
```

## Mental Model

Think of [concept] like [familiar analogy].

[Extend the analogy to cover key behaviors]

## Key Points

1. [Point 1]
2. [Point 2]
3. [Point 3]

## Common Misconceptions

**Misconception**: [What people wrongly believe]
**Reality**: [The truth]

## When to Use

Use [concept] when:
- [Situation 1]
- [Situation 2]

Avoid when:
- [Situation where it's wrong]

## Further Reading

- [Related concept](concept-2.md)
- [Practical application](howto.md)
```

## Changelog Template

```markdown
# Changelog

All notable changes to this project.

Format based on [Keep a Changelog](https://keepachangelog.com/).

## [Unreleased]

### Added
- Feature description

### Changed
- Change description

### Fixed
- Bug fix description

## [1.0.0] - YYYY-MM-DD

### Added
- Initial release
- Feature A
- Feature B

### Known Issues
- Issue description
```

## Navigation Patterns

### Breadcrumb

```markdown
[Home](../index.md) > [Tutorials](index.md) > Basics
```

### Prerequisites Block

```markdown
> **Prerequisites**
> - Completed [Quickstart](../quickstart.md)
> - Familiarity with [Concept X](../explanation/concept-x.md)
```

### Next Steps Block

```markdown
---

## Next Steps

- **Continue learning**: [Next tutorial](02-intermediate.md)
- **Try it yourself**: [Exercise](exercises/01.md)
- **Go deeper**: [Explanation](../explanation/topic.md)
```

### Landing Page Pattern

```markdown
# Documentation

## Getting Started

New here? Start with the [Quickstart](quickstart.md).

## Learning Paths

| Goal | Path |
|------|------|
| Use the API | Quickstart → How-to guides |
| Understand internals | Explanations → Architecture |
| Contribute | Setup → Contributing guide |

## By Type

- **[Tutorials](tutorials/)**: Step-by-step learning
- **[How-to Guides](how-to/)**: Solve specific problems
- **[Explanations](explanation/)**: Understand concepts
- **[Reference](reference/)**: Technical details
```
