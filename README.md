# prek-starter-hooks

A starter pre-commit hooks configuration for new projects.

## What's included

The `.pre-commit-config.yaml` includes these hooks:

- **trailing-whitespace** - Removes trailing whitespace from files
- **end-of-file-fixer** - Ensures files end with a newline
- **check-yaml** - Validates YAML syntax
- **check-added-large-files** - Prevents giant files from being committed

## Setup

### 1. Install prek

```bash
# macOS
brew install prek
```

### 2. Copy the config to your project

Copy `.pre-commit-config.yaml` to the root of your git repository.

### 3. Install the hooks

```bash
cd your-project
prek install
```

Now the hooks will run automatically on every `git commit`.

## Manual usage

```bash
# Run hooks on all files
prek run --all-files

# Run a specific hook
prek run trailing-whitespace --all-files
```

## Skipping hooks (when needed)

```bash
# Skip all hooks for one commit
git commit --no-verify -m "message"

# Skip specific hooks
SKIP=trailing-whitespace git commit -m "message"
```
