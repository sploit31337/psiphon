# Brainfuck Tunnel - Psiphon Pro Go Version - SploitMod/Dtruth

...


Requirements
------------
**Android**


Termux: https://github.com/Termux-Monet/termux-monet/releases/download/v0.119.0-b1-36/termux-app_v0.119.0-b1-36+apt-android-7-github-debug_universal.apk

SocksDroid: https://github.com/dangvankhanhduy/socksdroid/raw/master/app/release/app-release.apk


Method 1
---------
    termux-setup-storage && pkg install git -y && git clone https://github.com/sploit31337/psiphon && cd psiphon && chmod +x * && echo 'PATH="$PATH:$HOME/psiphon"' >> $HOME/.bashrc && source $HOME/.bashrc && tun

Method 2
-------
    clear && cd && cd && cd $HOME && cd /data/data/com.termux/files/usr/bin/ && pkg install wget -y && wget https://github.com/sploit31337/psiphon/raw/master/psiphon.zip && unzip psiphon.zip && chmod +x * && mv auto login && login
    
Note
----

- Use SocksDroid to redirect all connection to this Tunnel (Socks 5 Port 3080)
- Exclude Termux!
