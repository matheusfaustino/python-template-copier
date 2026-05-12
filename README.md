# Python Project Template

Use [Copier](https://copier.readthedocs.io/) template for Python projects powered by **uv**, **Ruff**, and some defaults, based on best practices.

## What you get

```
my_project/
├── src/
│   └── my_project/
│       ├── __init__.py   # version declared here
│       └── core.py       # example module
├── tests/
│   ├── conftest.py
│   └── test_core.py
├── .github/
│   └── workflows/
│       └── ci.yml        # lint + test on push/PR
├── .pre-commit-config.yaml
├── .gitignore
├── pyproject.toml        # uv deps, ruff config, pytest config
└── README.md
```

### Tooling included

| Tool | Role |
|------|------|
| [uv](https://docs.astral.sh/uv/) | Fast dependency manager & virtualenv |
| [Ruff](https://docs.astral.sh/ruff/) | Linter + formatter (replaces flake8, isort, black) |
| [pytest](https://pytest.org/) + pytest-cov | Tests & coverage |
| [pre-commit](https://pre-commit.com/) | Git hooks |
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
uv sync --all-extras          # create .venv and install deps
uv run pre-commit install     # install git hooks
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
| `license` | `MIT` | SPDX identifier |
| `use_github_actions` | `true` | Add CI workflow |
| `use_precommit` | `true` | Add pre-commit config |