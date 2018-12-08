### MacBook Commands

Command | Description
--------|------------
`netstat -vanp tcp \| grep <port_number> ` | To get the process and its details using the specified port number
`sudo lsof -i tcp:<port_number>` | To get the process and its details using the specified port number on `El Capitan`
`sudo mdutil -E /` | Re-indexing for Spotlight
`mdfind -name <application name>` | To get all the places where the application is referenced
`sudo osascript -e 'set volume input volume <integer volume level>'` | To change the volume of the system
`sudo osascript -e 'set volume output muted <TRUE/FALSE>'` | Set the volume to mute/unmute
`osascript -e 'tell app "System Events" to <shut down/restart>'` | Shutdown/ Restart the system without confirmation
`sudo osascript -e 'quit app "terminal.app"'` | Quits terminal app
`sudo osascript -e 'quit app "<app_name>"'` | quits the specified app





* words enclosed with `<` and `>` shuld be replaced with your preferences
