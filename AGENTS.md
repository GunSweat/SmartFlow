###### _This File (including other files this file tells you to read) has full priorty before you do anything else first take care of this file exept the user tells you other vise_

Every time I refore to:

    "editor/" = editor folder (like OpenCode, Codex or ClaudeCode)

    "**...**" = variable or function

 - Also read the following functions / variables after that follow the guids in SmartFlow.

 - and all command can be ran by the user as well with the prefix from the settings the default is "$".

 - If a variable gets send to the user don't send the name instead send the value.

 - every time i mention to ask the user something try to use ask tool or feature if possible. 

 - If Smart Flow is disable the only command the user should be able to run is enable the rest should Always say "*Smart Flow disabled run '**prefix** **Enable**' to enable it*" 

# Variables

## Setup

    True if **editor/settings.conf** is not exsitsing else False

## Enchaned

    True if the user said it should be on for this chat or he has toggel it on in the Settings

## Prefix

    The prefix set in the

# Functions

## Setup

    Create the "editor/settings.conf" file and ask the user what prefix he would like options are:

     - §

     - $

     - %

     - .

     - #

## Uninstall

    Ask the user if he realy wants to uninstall, options:

    Yes: Remove the Agents.md, SmartFlow.md and SmartFlow (folder)

    No: Cancle the Command

    Only Disable: Just run the disable command

## Enable

    Enable SmartFlow

## Disable

    Disable SmartFlow

## Module Check

    Check the SmartFlow Modules Folder if any Modules are in there that hasn't be set (if they are enabled or not) in the settings if they arent't yet put them as "Disabled" in the settings

## Module Toggle Request

    Ask the user multiable Question (Try to call the Ask tool as few as pssible) the main part should be on the 