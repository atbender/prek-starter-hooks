# prek-starter-hooks

A starter pre-commit hooks configuration for new projects.

## What's included

The `.pre-commit-config.yaml` includes these hooks:

- **trailing-whitespace** - Removes trailing whitespace from files
- **end-of-file-fixer** - Ensures files end with a newline
- **check-yaml** - Validates YAML syntax
- **check-added-large-files** - Prevents giant files from being committed

## Setup

### 1. Install pre-commit

```bash
# macOS
brew install pre-commit

# or with pip
pip install pre-commit
```

### 2. Copy the config to your project

Copy `.pre-commit-config.yaml` to the root of your git repository.

### 3. Install the hooks

```bash
cd your-project
pre-commit install
```

Now the hooks will run automatically on every `git commit`.

## Manual usage

```bash
# Run hooks on all files
pre-commit run --all-files

# Run a specific hook
pre-commit run trailing-whitespace --all-files

# Update hooks to latest versions
pre-commit autoupdate
```

## Skipping hooks (when needed)

```bash
# Skip all hooks for one commit
git commit --no-verify -m "message"

# Skip specific hooks
SKIP=trailing-whitespace git commit -m "message"
```

## Adding more hooks

Browse available hooks at https://pre-commit.com/hooks.html

Common additions:

```yaml
# Python formatting
- repo: https://github.com/psf/black
  rev: 24.4.2
  hooks:
    - id: black

# JavaScript/TypeScript
- repo: https://github.com/pre-commit/mirrors-prettier
  rev: v4.0.0-alpha.8
  hooks:
    - id: prettier
```
