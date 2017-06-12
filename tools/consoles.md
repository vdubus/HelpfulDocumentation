# Consoles

## [PowerShell](https://github.com/PowerShell/PowerShell)

The most powerfull windows shell available.

## [CygWin](https://www.cygwin.com/)

Bring the linux console inside Windows!

## [ConsoleZ](https://github.com/cbucher/console)

A tool to manage consoles in tabs on windows.  
This is an upgrade of [Console 2](https://sourceforge.net/projects/console).

### PowerShell integration

Go to `Edit > Parameters > Tabs`, then add a new tab and:

-   edit the title to `PowerShell`
-   edit the icon to `${PowerShell_Base_Folder}\${PowerShell_Version}\assets\Powershell_256.ico`
-   edit the Shell path to `${PowerShell_Base_Folder}\${PowerShell_Version}\powershell.exe`

With for example:

-   `${PowerShell_Base_Folder}` = `C:\DEV\Applications\PowerShell`
-   `${PowerShell_Version}` = `6.0.0.17`

### CygWin integration

Go to `Edit > Parameters > Tabs`, then add a new tab and:

-   edit the title to `CygWin`
-   edit the icon to `${CygWin_Base_Folder}\Cygwin-Terminal.ico`
-   edit the Shell path to `${CygWin_Base_Folder}\Cygwin.bat`

With for example:

-   `${CygWin_Base_Folder}` = `C:\DEV\Applications\cygwin64`

## [ConEmu](https://conemu.github.io/)

Another tool allowing us to manage consoles in tabs.
