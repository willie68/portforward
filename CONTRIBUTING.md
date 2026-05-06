# Contributing

Thanks for helping improve this project. This document explains how to set up a development environment, what we expect in pull requests, and how reviews are routed.

## Prerequisites

- Windows 10 or 11 (primary target)
- Python 3.11 or newer
- `git` and `kubectl` on your `PATH`
- Access to a Kubernetes cluster for manual testing (optional but recommended)

## Local setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

Run the application:

```bash
python -m src.main
```

Or with a custom config:

```bash
python -m src.main path\to\config.yaml
```

## Before you open a pull request

1. **Smoke test** your change locally (start the app, exercise the affected feature).
2. **Compile check** (same as CI):

   ```bash
   python -m compileall src
   ```

3. **Do not commit** secrets, kubeconfigs, personal `config.yaml` contents, or large log files. Runtime logs under `logs/` are ignored by `.gitignore`; keep it that way.

4. **Keep changes focused** — one logical change per PR is easier to review.

## Code style

- Match existing patterns in the files you touch (imports, naming, structure).
- Prefer small, readable changes over large refactors unless discussed first.
- Avoid unrelated formatting or drive-by edits in files you are not changing for the task.

## Pull requests

- Use the PR template and fill in **Summary**, **Testing**, and **Checklist**.
- Link related issues when applicable (`Fixes #123`).
- If behavior changes (health checks, restart logic, config format), update `README.md` or `LOGGING.md` as needed.

## Issues

- Use the bug report or feature request templates when opening issues.
- Include steps to reproduce, expected vs actual behavior, and relevant log excerpts from `portforward.log` when reporting bugs.

## Questions

Open a discussion issue or comment on an existing one if you are unsure about direction before investing a lot of time in a large change.
