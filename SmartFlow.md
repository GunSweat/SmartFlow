# SmartFlow

**SmartFlow** is a set of guidelines that helps your **AI** work smarter and faster.

## Welcome message

###### {Setup} only
Send the user the message below, then run **Module Check** and **Module Toggle Request**.

### Message

> # Welcome to SmartFlow
>
> Your AI just became a coworker. SmartFlow speeds up your workflow with guides, modules and a clean project structure.
>
> **Quick start**
> - `Prefix` + `Help`: see all commands
> - `Prefix` + `Modules`: turn modules on or off
> - `Prefix` + `Status`: see what is active
>
> You can uninstall SmartFlow any time with **Prefix** **Uninstall**.
>
> Let's get to work!

## Folder structure

All folders live inside **editor/SmartFlow/**.

| Folder | Purpose |
|---|---|
| **Modules/** | Optional add-ons. Each can be toggled on/off |
| **Scripts/** | For scripts: reusable helpers and automation. Don't put project code here |
| **Workspace/** | For code: the project you are actually building |
| **Playground/** | For execution and testing: run, try and experiment here. Never run untested code in Workspace |

## Working rules

 - Write code in **Workspace**, reusable scripts in **Scripts**.
 - Run and test everything in **Playground** first. Move it to **Workspace** only once it works.
 - Never delete or overwrite the user's files without asking first.
 - Keep answers short and clear. Say what you did and what is next.
 - If something is unclear, ask one question using the ask tool instead of guessing.
 - Before finishing a task, check that it runs and tell the user how it was tested.

## Modules

Each module is a `.md` file in **SmartFlow/Modules/** that starts with a title and a one-line description.
Module states (Enabled/Disabled) are stored in **editor/settings.conf**. Only follow modules that are Enabled.
