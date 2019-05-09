# tcpdump
To debug the packet flows.

Command | Desc
--|--
tcpdump host \<IP\> | Traffic that's going from and to the \<IP\>
tcpdump src \<IP\> | Only traffics from the IP
tcpdump dst \<IP\> | Only traffics to the IP
tcpdump net \<IP\>/CIDR | Traffic going to or coming from a subnet or network
tcpdump port \<PORT_NO\> | Packets flowing from and to via PORT_NO
tcpdump -nnvvS src \<IP\> and dst port \<PORT_NO\> | Finds all traffic from \<IP\> going to any host on port \<PORT_NO\>
tcpdump -n -vvv -i any port 53 | Any traffic that's going to DNS Server
tcpdump -nnSX port 443 | Picks all the traffic on port 443
tcpdump -i eth0 | Everything on the eth0 interface



# time
To debug the response time.
Create a txt file as following and save it as `time.txt`
```
    time_namelookup:  %{time_namelookup}\n
       time_connect:  %{time_connect}\n
    time_appconnect:  %{time_appconnect}\n
   time_pretransfer:  %{time_pretransfer}\n
      time_redirect:  %{time_redirect}\n
 time_starttransfer:  %{time_starttransfer}\n
                    ----------\n
         time_total:  %{time_total}\n
```

Now add the following in the normal `curl` like below.
```
curl -w "@time.txt" -o /dev/null -s "https://google.com"
```

The above command should give the time splits as follows.
```
    time_namelookup:  0.012 
       time_connect:  0.014
    time_appconnect:  0.727
   time_pretransfer:  0.727
      time_redirect:  0.000
 time_starttransfer:  0.785
                    ----------
         time_total:  0.785
```


# nslookup
nslookup is used to resolve the IP address to a FQDN (Fully Qualified Domain Name).

`nslookup <IP>`
