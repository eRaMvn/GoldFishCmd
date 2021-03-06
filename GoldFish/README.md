# GoldFishCmd.py

Program created by eRaMvn. 

A simple program that generates commands and suggests interesting files for pentesters to avoid mistakes during an engagement

Please run
```
pip3 install -r requirements.txt
```

### Tools supported:

cafae | cewl | curl | dig | dirsearch | enum4linux | find | gobuster | grep | hydra | impacket |

merlin | mount | msfvenom | mssql | mysql | nc | nikto | nmap | others | patator |

plink | postgres | powershell | rdesktop | runas | shell | smbclient | smtp-user-enum | snmp | socat |

sqlmap | ssh | sshuttle | tar | tcpdump | unicorn | wfuzz | wpscan |

### Arguments

_positional arguments:_

   [source ip]    source ip address - usually attacker's ip address
   
   [target ip]    target's ip address

_optional arguments:_

  -h, --help      show this help message and exit

  -lp [port]      local port to listen to. Default port is 443

  -d [directory]  directory where files can be stored

  -c [tool_name]  quickly obtain the tool command without going through the program flow

  -v              show program's version number and exit
  
## Sample Output 1:

PS C:\Users\eRaMvn> & "C:/Users/eRaMvn/AppData/Local/Programs/Python/Python37-32/python.exe" "d:/GoldFish/GoldFishCmd.py" 10.11.12.11 10.11.12.23
```
You are currently in tool selection mode.

Please choose commmand to generate. Otherwise, type "list" to list tools supported, "change" to change ips and ports, "exit" to quit program.

Input: nmap

---nmap phase 1---
1. nmap -sSV -Pn -nvv -p- --reason -T4 -oN ~/Desktop/10.11.12.23_nmap_tcp_ports.txt 10.11.12.23
----------------------------------------------------------------------
---nmap phase 2---
2. nmap -sSV -sC -Pn -nvv -p[edit port] -A --version-intensity 9 -O --reason -T4 -oN ~/Desktop/10.11.12.23_nmap_detailed.txt 10.11.12.23
----------------------------------------------------------------------
---nmap phase 3---
3. nmap -A -O --script vuln -p[edit port] -oN ~/Desktop/10.11.12.23_nmap_vuln_scan.txt 10.11.12.23
----------------------------------------------------------------------
---nmap udp scan---
4. nmap -Pn -p- -sU --stats-every 3m --max-retries 2 -T4 -oN ~/Desktop/10.11.12.23_nmap_udp_ports.txt 10.11.12.23
----------------------------------------------------------------------
---nmap example script usage---
5. nmap -T4 -sV --script=firewalk.nse -oN ~/Desktop/10.11.12.23_nmap_firewalk.txt 10.11.12.23
----------------------------------------------------------------------

Please choose commmand number to copy to clipboard. Type "0" to return to tool selection

Input: 1

Command has been copied to your clipboard!

Please enter an integer from -1 to 5. 0 to return, -1 to list commands

Input: 0

-----------------------------

Taking you back to tool selection!

-----------------------------

You are currently in tool selection mode.

Please choose commmand to generate. Otherwise, type "list" to list tools supported, "change" to change ips and ports, "exit" to quit program.

Input: exit

Bye!
```
## Command in clipboard:
```
nmap -sSV -Pn -nvv -p- --reason -T4 -oN ~/Desktop/10.11.12.230_nmap_tcp_ports.txt 10.11.12.230
```

## Sample Output 2:
Generate the command without going through the program flow

PS C:\Users\eRaMvn> & "C:/Users/eRaMvn/AppData/Local/Programs/Python/Python37-32/python.exe" "d:/GoldFish/GoldFishCmd.py" 10.10.0.1 10.10.0.2 -c nmap
```
Please enter the port for nmap to scan. Leave blank to use default
Input: 
---nmap phase 1---
1. nmap -sSV -Pn -nvv -p- --reason -T4 -oN ~/Desktop/10.10.0.2_nmap_tcp_ports.txt 10.10.0.2
----------------------------------------------------------------------
---nmap phase 2---
2. nmap -sSV -sC -Pn -nvv -p[edit port] -A --version-intensity 9 -O --reason -T4 -oN ~/Desktop/10.10.0.2_nmap_detailed.txt 10.10.0.2
----------------------------------------------------------------------
---nmap phase 3---
3. nmap -A -O --script vuln -p[edit port] -oN ~/Desktop/10.10.0.2_nmap_vuln_scan.txt 10.10.0.2
----------------------------------------------------------------------
---nmap udp scan---
4. nmap -Pn -p- -nvvv -sU --stats-every 3m --max-retries 2 --min-rate 5000 -oN ~/Desktop/10.10.0.2_nmap_udp_ports.txt 10.10.0.2
----------------------------------------------------------------------
---nmap example script usage---
5. nmap -T4 -sV --script=firewalk.nse -oN ~/Desktop/10.10.0.2_nmap_firewalk.txt 10.10.0.2
----------------------------------------------------------------------
Please select commmand number to copy to clipboard. Type "e" to quit, "c" to clear screen.
Input: 1
It has been copied to your clipboard!
Please enter an integer from 0 to 5. 0 to exit, "l" to list options, "c" to clear screen.
Input: 0
----------------------------------------------------------------------
Program exits!
----------------------------------------------------------------------
```

## Command in clipboard:
```
nmap -sSV -Pn -nvv -p- --reason -T4 -oN ~/Desktop/10.10.0.2_nmap_tcp_ports.txt 10.10.0.2
```

-----------------------------------------------------------------------------------------------------------------------
# order.py

Program created by eRaMvn. 

This program creates a new folder with the name specified and copied all files that start with that name into that folder.

### Arguments

_positional arguments:_
  folder_name  specify the name of folder to create

_optional arguments:_
  -h, --help   show this help message and exit
  
## Sample Output:
```
python3 order.py 10.10.14.15
'10.10.14.15' directory already exists!
Do you want to remove that folder? (Y/N): Y
moved './10.10.14.15-abc - Copy (2).txt' to './10.10.14.15/./10.10.14.15-abc - Copy (2).txt'
moved './10.10.14.15-abc - Copy (3).txt' to './10.10.14.15/./10.10.14.15-abc - Copy (3).txt'
moved './10.10.14.15-abc - Copy (4).txt' to './10.10.14.15/./10.10.14.15-abc - Copy (4).txt'
moved './10.10.14.15-abc - Copy (5).txt' to './10.10.14.15/./10.10.14.15-abc - Copy (5).txt'
moved './10.10.14.15-abc - Copy.txt' to './10.10.14.15/./10.10.14.15-abc - Copy.txt'
moved './10.10.14.15-abc.txt' to './10.10.14.15/./10.10.14.15-abc.txt'

```
