###### _This file (including any files it tells you to read) has top priority. Handle it before anything else, unless the user says otherwise._

Notation:

    "editor/" = the editor's config folder (e.g. OpenCode, Codex or Claude Code)

    "**...**" = a variable or function

 - After reading this file, read **editor/SmartFlow.md** and follow its guides.

 - All functions can also be run by the user with the prefix from the settings (default is "$").

 - If a variable is sent to the user, send its value, not its name.

 - Whenever you need to ask the user something, use the ask tool or feature if available.

 - If SmartFlow is disabled, the only command the user may run is **Enable**. For every other command reply: "*SmartFlow is disabled. Run '**Prefix** Enable' to enable it.*"

 - Unknown command: reply "Unknown command. Run '**Prefix** Help' for the list."

# Variables

## Setup

    True if **editor/settings.conf** does not exist, otherwise False.

## Enabled

    True if the user turned SmartFlow on for this chat or it is on in the settings.

## Prefix

    The prefix saved in **editor/settings.conf** (default "$").

# Functions

## Setup

    1. Create **editor/settings.conf**.
    2. Ask the user which prefix they want. Options: §  $  %  .  #
    3. Save the prefix and set SmartFlow to Enabled in the settings.
    4. Make sure these folders exist: SmartFlow/Modules, SmartFlow/Scripts, SmartFlow/Workspace, SmartFlow/Playground.

## Uninstall

    Ask the user if they really want to uninstall. Options:

    Yes: Remove AGENTS.md, SmartFlow.md, the SmartFlow/ folder and settings.conf
         (if AGENTS.md was merged, remove only the SmartFlow section)
    No: Cancel the command
    Only Disable: Run **Disable** instead

## Enable

    Set SmartFlow to Enabled in the settings and confirm to the user.

## Disable

    Set SmartFlow to Disabled in the settings and confirm to the user.

## Help

    Show the user every command with a one-line description.

## Status

    Show the user: version, **Prefix**, Enabled/Disabled, and each module with its state.

## Prefix

    Ask the user for a new prefix (same options as Setup) and save it.

## Module Check

    Look in SmartFlow/Modules for modules that have no state in the settings yet.
    Add each one as "Disabled".

## Module Toggle Request

    Ask the user which modules they want enabled. Use the ask tool as few times as possible
    (one multi-select question is ideal). Show each module's name and a short description,
    then save the choices to the settings.

## Modules

    Run **Module Check** followed by **Module Toggle Request** again.
