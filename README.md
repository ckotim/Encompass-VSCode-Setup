[//]: # (ctrl+shift+v to open this file with formatting in VSCode)

# ECP VSCode Configuration Instructions
## Prerequisites
- Install VS Build Tools
    1. Run the `vs_buildtools.exe` installer located in /.vscode/Setup/ directory. 
    2. Select __Web development build tools__ on the Workload tab.
    3. Select __.NET Framework 4.7.2 SDK__ and __.NET Framework 4.7.2 Targeting Pack__ on the Individual Components tab.
    4. Install selected components.
- Install TortoiseSVN command line tools via [their installer](https://tortoisesvn.net/downloads.html)
    1. Download and Follow Installer
    2. Make sure __command line client tools__ are selected to install
    3. Finish installation

## Setup

1. Run VSCode as an Administrator.
2. _File_ > _Open Workspace..._ > Select `ECP.code-workspace`
3. Install recomended extensions via popup or extensions menu

# Development Basics
## Compilation & Tasks
 
 |Task                      |Description                                    |
 |---                       |---                                            |
 |`ECP: Build`              |Builds ECP.dll & .ASPX Pages                   |
 |`ECP: Build-IgnoreASPX`   |Builds ECP.dll Only                            |
 |`ECP: Clean`              |Cleans Build Directory                         |
 |`ECP: Start-Memcache`     |Calls `run.bat` in `Tools/Memcache/` directory |

 - These can be invoked via pressing `ctrl + p` and typing `task` with a leading space.
 - You can map tasks to keybinds (this cannot be set on a project level).
 - To view or modify any of these confiugred tasks go to `/.vscode/tasks.json` 
    
## Debugging & Launch Configurations

|Lauch Config               |Description                                        |
|---                        |---                                                |
|`ECP: Debug`               |Attaches to `w3wp.exe` Process                     |
|`ECP: Debug-Build`         |Runs `ECP: Build` Task Then Attaches to `w3wp.exe` |
|`ECP: Debug-SelectProcess` |Attach To a Specified Process                      |

 - These can be invoked via pressing `ctrl + p` and typing `debug` with a leading space.
 - You can map tasks to keybinds (this cannot be set on a project level).
 - To view or modify any of these launch configurations go to `/.vscode/launch.json` 

# Notes
## Source Control
 - SVN Extension lets you pull, diff, and commit changes inside of VSCode. 
 - `ctrl+shift+g` opens the source control menu. 

## Keyboard Shortcuts
 - Shortcuts are user specific, the configuration file lives in AppData.
 - Example of binding `ECP: Build` task to `ctrl+shift+b`
 ```
    {
        "key": "ctrl+shift+b",
        "command": "workbench.action.tasks.runTask",
        "args": "ECP: Build"
    }
```

## Code Formatting
- `shift+alt+f` is the default formatting keybind.
- Formatting rules are determined by `omnisharp.json`.


