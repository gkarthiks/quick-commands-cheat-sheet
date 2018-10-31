Command | Description
--------|------------
netstat -vanp tcp | grep <port_number> | To get the process and its details using the specified port number
sudo lsof -i tcp:<port_number> | To get the process and its details using the specified port number on `El Capitan`
