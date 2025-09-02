# Psiphon - Sploit/Dtruth - BF Tunnel Mod

Read Everything here man

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


Method 3 (Already have the Zip and you have root file browsing access)
-------
**# Drop the Zip in to the Below Folder**

        /data/data/com.termux/files/usr/bin/


**# Change directory to the bin folder**

    cd /data/data/com.termux/files/usr/bin/

**# unzip the shit yo**

    unzip -o psiphon.zip && chmod +x *

**## Manually activate the tunnel (You can create a script to do this, maybe we do it later)**

    tun -c 4 -tw 6 -r us -l 4 -f "*" -w "*:*"


**### SPECIFIC TO SOCKSDROID ###**
----
**# Move the auto script to a new name of login**

    mv auto login

**Optionally then type the below command to launch (This is specific to SocksDroid)**
----
    login 


Note 1 - ### SOCKSDROID
----

- Use SocksDroid to redirect all connection to this Tunnel (Socks 5 Port 3080)
- Exclude Termux!

Note 2 - OpenVPN for Android
----
We will be implimenting the use of "Open VPN for Android" instead
Download Here: https://github.com/schwabe/ics-openvpn/releases/download/v0.7.61/ics-openvpn-0.7.61.apk

You can setup the proxy route in OpenVPN instead of using proxifier for ALL ports to be opened up through a Double VPN tunnel

Note 3 - OpenVPN for Android
----
The problem with Psiphon is that it has port limitations (This is Psiphons issue) and Psiphon only allows so many ports to be able to get out on. So by utilizing Proxifier, DroidProxy, SocksDroid, Socks2Tun, Etc... then the apps that you then Proxy through Psiphon are at the mercy of whatever Psiphon allows to be opened. For Standard Internet Browsing this isn't an issue, but for Voice Service apps that use UDP protocols or other ports outside of Psiphons allowed range, this is a major issue.

So What do we do?
So instead of using a Proxy App, we will use a REAL Vpn Tunnel such as OpenVPN. The Problem is OpenVPN Connect doesn't support Socks5. However, "OpenVPN For Android" a custom Android OpenVPN App does. We can then use this version of OpenVPN to tunnel Via Port 443 (One of Psiphons Allowed Ports) to a 443 Capable VPN service (Like NordVPN) we then are Double VPN'd, meaning that the "OpenVPN for Android" app initiates a connection through the Psiphon Proxy address at 127.0.0.1 on Port 3080, connects to NordVPN and then Every Single App is then Directly tunneled through NordVPN as if they are directly connected to a very secure internet connection, and no longer at the mercy of Psiphon


Note 4 - Additional Commands
----
### Commands (In the /data/data/com.termux/files/usr/bin directory)

p-cleanup.mybin  ### This is for cleaning up the entire installation (Removing it)

p-menu.mybin	## This is a general menu for manually starting the tunnel with a few options right now

p-installauto.mybind   ## This installs the Auto System for Whichever app you have installed
			## It Also has a remove option to remove the system

p-auto-tunvar.mybin    ### This file is what contains the string for how the tunnel gets executed with whichever autofile you selected
			# It can be edited to change what you want to automatically start the tunnel with
			# right now the default is (tun -c 4 -tw 6 -r us -l 4 -f "*" -w "*:*")
			# This Applies to ALL tunnels you install as Auto, because those files SOURCE this file


