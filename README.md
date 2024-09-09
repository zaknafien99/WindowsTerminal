# Windows Terminal
I have been using windows terminal from it's earliest days from it's first public Beta to now. It has become a very powerful tool for system management and software development.

Obtainable from the Microsoft Store in windows 10 and 11 it has become my go to for PowerShell and software development. You can do some really cool things with it like make the prompt look awesome:
![image](https://github.com/user-attachments/assets/43c2a7e9-599a-46cb-8668-8f68b060a636)

You can get intellisense style command completion:
![image](https://github.com/user-attachments/assets/823fcc42-9667-43fd-9743-9cfda1aa1a89)

It just makes the experience better that using the standard command prompt or even powershell. But how do you set up this new hotness?

You will need to install a few powershell modules:
1. posh-git
2. Terminal-Icons
3. Powerline

I recommend using Visual Studio Code to edit the Microsoft.PowerShell_profile.ps1 file and enter these commands:

Add-WindowsPSModulePath

Import-Module -name posh-git

import-module -name Terminal-Icons

import-module -Name powerline

oh-my-posh init pwsh | Invoke-Expression

if ($host.Name -eq 'ConsoleHost')

{

    Import-Module PSReadLine    
}


Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward

Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward

Set-PSReadLineKeyHandler -Key Tab -Function Complete

Set-PSReadLineOption -PredictionSource History

Set-PSReadLineOption -PredictionViewStyle ListView

Set-PSReadLineOption -HistoryNoDuplicates

Set-PSReadLineOption -HistorySaveStyle SaveIncrementally

Set-PSReadLineOption -ShowToolTips

Set-PSReadLineOption -HistorySearchCursorMovesToEnd

Set-PSReadLineOption -EditMode Emacs

These commands enable Intellisense style autocompletion.

You also need to set a PowerLine font.
![image](https://github.com/user-attachments/assets/e123ec35-2bb4-4eb7-8012-778b8e75daa3)

You can also set this in the JSON and in the early days this was the only way to do it, but you have more control through the GUI and it won't break the terminal if you miss a comma. YOu can get some really cool fonts from NerdFonts. For more information read the great Scott Hansleman's blog: https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal

There's lots of great information out there, how have you set up your terminal?
