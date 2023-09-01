## Python environment error

If you are unable to set python environment in vscodium on windows using powershell as your default terminal of choice, then you need to follow the tutorial below.  


### Tutorial

If you want to set the execution policy to “Unrestricted”, you can do so by following these steps:

1. Open PowerShell with administrative privileges and “Run as administrator”.
2. Run the command `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` in PowerShell.
3. Type Y and press Enter to confirm the change.
4. This will change the execution policy to “Unrestricted”, which allows all scripts to run, regardless of their origin or whether they have been signed. 


### Caveat 
However, please note that this setting is not recommended as it can expose your system to potential security risks. It is important to only run scripts from trusted sources and to be cautious when downloading scripts from the internet.
