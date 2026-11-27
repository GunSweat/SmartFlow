# SmartFlow

**SmartFlow** is a set of guideline files for AI coding agents (OpenCode, Codex, Claude Code, …).
Drop it into a project and the agent gets a consistent workflow: a setup step, a small command
language, and swappable modules that change how it behaves.

> Status: early / work in progress. `Enhanced` is a stub, `Module Check` and
> `Module Toggle Request` are not implemented yet.

---

## How it works

The agent reads `AGENTS.md` from the project root. That file defines the SmartFlow **variables**
and **functions** and tells the agent to read the rest of the guidelines in `SmartFlow.md`.

```
SmartFlow/
├── AGENTS.md              # entry point – variables, functions, rules
├── SmartFlow.md           # guidelines: welcome message, modules, module handling
└── SmartFlow/
    └── scripts/
        ├── Enhanced.md    # "Enhanced" module (not implemented yet)
        └── Bypass.md      # "Bypass" persona module (experimental prompt override)
```

## Setup

`Setup` is `True` while `editor/settings.conf` does not exist. On the first run the agent asks for
a command prefix and writes it to `editor/settings.conf`, where `editor/` is the config folder of
whatever editor you use (for example `.opencode/`).

Available prefixes:

| Prefix | Example command |
| ------ | --------------- |
| `§`    | `§ Enable`      |
| `$`    | `$ Enable`      |
| `%`    | `% Enable`      |
| `.`    | `. Enable`      |
| `#`    | `# Enable`      |

The default prefix is `$`.

## Commands

Every command is prefixed with your configured prefix and can be typed by you or run by the agent.

| Command     | What it does                                                        |
| ----------- | ------------------------------------------------------------------- |
| `Enable`    | Turns SmartFlow on.                                                  |
| `Disable`   | Turns SmartFlow off. While disabled, only `Enable` is accepted.      |
| `Uninstall` | Asks for confirmation, then removes `AGENTS.md`, `SmartFlow.md` and the `SmartFlow/` folder. `Only Disable` just runs `Disable`. |

While SmartFlow is disabled, every other command answers with:

> *Smart Flow disabled run `<prefix> Enable` to enable it*

## Variables

| Variable    | Meaning                                                                 |
| ----------- | ----------------------------------------------------------------------- |
| `Setup`     | `True` if `editor/settings.conf` is missing, otherwise `False`.          |
| `Enhanced`  | `True` if enabled for the current chat or toggled on in the settings.    |
| `Prefix`    | The command prefix stored in `editor/settings.conf`.                    |

## Modules

Modules live in `SmartFlow/scripts/` and are toggled per chat or from the settings.

| Module     | File                       | State                              |
| ---------- | -------------------------- | ---------------------------------- |
| `Enhanced` | `SmartFlow/scripts/Enhanced.md` | Stub – answers "Enhanced Mode not implementet yet". |
| `Bypass`   | `SmartFlow/scripts/Bypass.md`   | Experimental. A long persona-override prompt that tells the assistant to adopt a fixed persona and drop its usual refusal behaviour. Expect it to conflict with your assistant's built-in safety policies, and read it before enabling it. |

`Module Check` (list available modules) and `Module Toggle Request` (enable/disable a module) are
planned but not implemented yet.

## Install into a project

```bash
git clone https://github.com/GunSweat/SmartFlow.git
```

Then copy `AGENTS.md`, `SmartFlow.md` and the `SmartFlow/` folder into the root of the project you
want SmartFlow in, and start your AI editor there. The agent runs `Setup` automatically on the first
start.

## Notes

- `AGENTS.md` has priority over the other guideline files.
- Commands are written with the configured prefix, never with a literal `$` unless that is your
  prefix.
