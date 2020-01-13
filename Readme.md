# SharpAttack
***Executable of SharpAttack, THIS IS NOT MY TOOL! I have compiled it for use in the field***


SharpAttack is a console for certain things I use often during security assessments. It leverages .NET and the Windows API to perform its work. It contains commands for domain enumeration, code execution, and other fun things.

## Commands
```
=== SharpAttack Commands ===
Here are the commands available to you

Command                       Description
-------                       -----------
Help                          Displays Help
Exit                          Quits SharpAttack
DcomExec                      Executes a command against a remote machine through DCOM objects
DumpProcess                   Dumps the memory of a given process
FindLocalAdmin                Checks a list of computers to see if the current account has administrative
                              access to the endpoint
GetDomainComputer             Returns information about a domain computer.
GetDomainGroup                Returns information about a domain group.
GetDomainUser                 Returns information about a domain user.
GetLoggedOnUsers              Returns a list of users logged into a machine
GetSystem                     Attempts to impersonate NT AUTHORITY\SYSTEM
ImpersonateProcess            Impresonates the user that owns a given process
Kerberoast                    Returns a list of SPNs associated with user accounts
PowerShell                    Executes a PowerShell command without powershell.exe and attempts to evade
                              logging.
RevToSelf                     Reverts back to the original token for this process
WhoAmI                        Answers some really deep questions
WmiExec                       Executes a command against a remote machine over WMI
```
## Using SharpAttack
SharpAttack can be used as a standalone console or from the command line. To use SharpAttack from the command line, simply run `sharpattack.exe` followed by the command you'd like to run. For example:

```
.\SharpAttack.exe PowerShell Get-Date
```

If your parameter has spaces in it, wrap it in quotes (example: `SharpAttack.exe powershell "get-date; echo woot"`).

Some parameters accepts lists (mainly the ComputerName and IPAddress params). These should be entered as comma seperated values with no spacing (example: `-ComputerName target1,target2,target3`)

The `help` command lists what commands are available and what they do. You can also run `help <command>` to get help with a specific command and see its parameters.

Where possible, SharpAttack tries to use positional parameters (For example, `powershell get-date` works as well as `powershell -command get-date`). 

SharpAttack also works with Cobalt Strikes `execute-assembly`, just as it would on the command line. This does require that the SharpSploit library be trimmed down a bit, which I do by removing `Mimikatz.cs` from the SharpSploit project before compiling.

## Thanks
SharpAttack is built on top of [Cobbr's](https://twitter.com/cobbr_io) incredible [SharpSploit Project](https://github.com/cobbr/SharpSploit). SharpAttack is basically an easy way to interact with SharpSploit.


***Credit to JaredHaight: https://github.com/jaredhaight***
