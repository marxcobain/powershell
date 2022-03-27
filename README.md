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
Complete reference could be found on the site [Oh My Posh](https://ohmyposh.dev/docs/windows)

From the Windows Terminal install the module
```
Install-Module oh-my-posh -Scope CurrentUser
```
THen update the module
```
Update-Module oh-my-posh
```

## Configure oh my posh

Edit the user profile file using the editor of your preference.
```
code $PROFILE
```
Then add the reference to the theme you wanted to use
```
oh-my-posh --init --shell pwsh --config $env:POSH_THEMES_PATH:/jandedobbeleer.omp.json | Invoke-Expression
```

## Adding Nerd Fonts
Some of the characters used will not be displayed correctly, so we must install additional fonts. 

* Download the desired font (I am using Caskaydia Cove Nerd Font)[Nerd Fonts](https://www.nerdfonts.com/font-downloads)
* Unzip the font
* On the control panel look for fonts 
* Copy the fonts to the fonts folder

On the Windows terminal open the settings (Ctrl+,) go to PowerShell profile(or Default profile), on Appearance tab go to Font face dropdown and select the new font (Caskaydia Cove Nerd Font) and Save 

## Add Icons to the directory listing

From the Terminal execute
```
Install-Module -Name Terminal-Icons -Repository PSGallery
```

Add the following lines to the $PROFILE file

```
Import-Module -Name Terminal-Icons
```

## Adding predictive IntelliSense

First install PSReadLine

```
Install-Module PSReadLine -AllowPrerelease -Force
```

Then add the reference to the $PROFILE file and add some configuration so it uses the history and the style view

```
Import-Module PSReadLine
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows
```