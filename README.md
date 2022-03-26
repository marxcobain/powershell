# How to customize Windows Terminal


## Get the Windows Terminal
Install Windows Terminal from the MS Store, this will allow us to managed different consoles together(CMD, PowerShell, Azure, WSL, git-bash)

## Get the Powershell

Instead of the Windows Powershell, we will be working with the .NET Core-powered Powershell. So download the Powershell from the MS Store or user the command

```
winget install Microsoft.PowerShell
```

## Set Powershell as Default
Open the Windows Terminal and press <Ctrl+,> This will open the Settings, so on the default profile select PowerShell(the one we just downloaded)

## Install oh my posh
Complete reference could be found on the site 

```
Install-Module oh-my-posh -Scope CurrentUser
```