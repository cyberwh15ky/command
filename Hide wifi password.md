# list wifi
netsh wlan show networks

# add and delete wifi filter
netsh wlan add filter permission = allow ssid ="ssidname" networktype = infrastructure
netsh wlan delete filter permission = allow ssid ="ssidname" networktype = infrastructure
