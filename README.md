# Python Project Template

Use [Copier](https://copier.readthedocs.io/) template for Python projects powered by **uv**, **Ruff**, and some defaults, based on best practices.

## What you get

```
my_project/
├── src/
│   └── my_project/
│       ├── __init__.py   # package docstring
│       ├── core.py       # example module
│       └── py.typed      # declares bundled type annotations
├── tests/
│   ├── conftest.py
│   └── test_core.py
├── .github/
│   └── workflows/
│       └── ci.yml        # lint + test on push/PR
├── .gitignore
├── AGENTS.md            # setup, checks, and coding conventions for agents
├── CONTRIBUTING.md      # contributor setup and development workflow
├── LICENSE              # MIT license
├── pyproject.toml        # version, dependencies, and tool configuration
└── README.md
```

### Tooling included

| Tool | Role |
|------|------|
| [uv](https://docs.astral.sh/uv/) | Fast dependency manager & virtualenv |
| [Ruff](https://docs.astral.sh/ruff/) | Linter + formatter (replaces flake8, isort, black) |
| [pytest](https://pytest.org/) + pytest-cov | Tests & coverage |
| [ty](https://docs.astral.sh/ty/) | Type checking |
| GitHub Actions | CI pipeline (lint → test) |

---

## Prerequisites

```bash
# Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh   # Linux / macOS
# or: brew install uv

# Install Copier
uv tool install copier
```

---

## Usage

### Generate a new project

```bash
copier copy path/to/this/template my-new-project
# or directly from GitHub:
# copier copy gh:YOUR_ORG/python-template my-new-project
```

Answer the prompts, then:

```bash
cd my-new-project
uv sync                      # create .venv and install runtime and dev dependencies
git init && git add -A && git commit -m "chore: initial commit from template"
```

### Update an existing project

If the template changes and you want to pull in the updates:

```bash
cd my-existing-project
copier update
```

Copier will apply a diff and let you resolve conflicts.

---

## Template options

| Question | Default | Description |
|----------|---------|-------------|
| `project_name` | – | Human-readable name |
| `project_slug` | auto | Python package name |
| `project_description` | – | One-liner |
| `author_name` | – | For pyproject.toml |
| `author_email` | – | For pyproject.toml |
| `python_version` | `3.12` | Minimum Python |
| `license` | `MIT` | MIT license for generated projects |

## License

This template and newly generated projects use the MIT license.
Generated projects use the supplied author name in their copyright notice.
| `use_github_actions` | `true` | Add CI workflow |
