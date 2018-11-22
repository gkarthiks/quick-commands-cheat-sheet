Command | Description
--------|------------
`netstat -vanp tcp \| grep <port_number> ` | To get the process and its details using the specified port number
`sudo lsof -i tcp:<port_number>` | To get the process and its details using the specified port number on `El Capitan`
`sudo mdutil -E /` | Re-indexing for Spotlight
`mdfind -name <application name>` | To get all the places where the application is referenced
`sudo osascript -e 'set volume input volume <integer volume level>'` | To change the volume of the system
