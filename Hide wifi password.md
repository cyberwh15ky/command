# Basic Command
### Remove File
> del "filelocation\filename"

# WIFI
### WIFI: list wifi
> netsh wlan show networks

### WIFI: add and delete wifi filter
> netsh wlan add filter permission = allow ssid ="ssidname" networktype = infrastructure
> netsh wlan delete filter permission = allow ssid ="ssidname" networktype = infrastructure

### WIFI: list wifi profile
> netsh wlan show profile

### WIFI: get endpoint wifi profile
> netsh wlan export profile folder=C:\ key=clear

# Test domain state
## Test the domain port
> Test-NetConnection -Computername <domain> -Port 44
