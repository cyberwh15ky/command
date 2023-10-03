Powershell History
Tool: cmd ( admin )
> %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

![image](https://github.com/cyberwh15ky/command/assets/142871997/1f4ccdad-a35f-4327-bd05-5a2fa3b66ba5)

Saved Windows Credentials
Tool: cmd ( admin )
> cmdkey /list

![image](https://github.com/cyberwh15ky/command/assets/142871997/f1fa1fff-530b-4b6c-8b30-6b3db45faeb5)

Try the user login
Tool: cmd ( admin )
> runas /savecred /user:admin cmd.exe

![image](https://github.com/cyberwh15ky/command/assets/142871997/ae29ae45-a559-4b11-a6d0-3884840a2952)

![image](https://github.com/cyberwh15ky/command/assets/142871997/26305a77-91b3-4550-8d86-d783c0afa33b)


Retrieve Credentials from Software: PuTTY
Tool: cmd ( admin )
> reg query HKEY_CURRENT_USER\Software\SimonTatham\PuTTY\Sessions\ /f "Proxy" /s

![image](https://github.com/cyberwh15ky/command/assets/142871997/fd76849c-6eaa-4f9d-81a9-4c447154b311)

![image](https://github.com/cyberwh15ky/command/assets/142871997/d2c68171-98c8-4b9b-bcc6-423b6458b993)




Scheduled Tasks
Tool: cmd ( admin )
> schtasks
