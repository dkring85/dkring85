# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **GitHub special profile repository** (`dkring85/dkring85`). Its only tracked content is `README.md`, which GitHub renders on the owner's profile page (`https://github.com/dkring85`).

Key facts for future agents:

- There is **no application, service, package manager, build system, lint config, or test suite**. There are no dependencies to install and nothing to compile or start.
- The update/install script is intentionally a no-op. Do not add dependency installation or service startup steps.
- The only "product" is the Markdown that renders on the GitHub profile. Editing `README.md` is the primary development task.
- To preview how the profile will look, render `README.md` to HTML (e.g. GitHub renders standard Markdown; `<!--- ... --->` blocks are HTML comments and stay hidden). A quick local preview: `pip install markdown` then convert `README.md` to HTML and open it in a browser. Keep any preview scaffolding outside the repo (e.g. `/tmp`) so it is not committed.
