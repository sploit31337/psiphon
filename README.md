# Psiphon - Sploit/Dtruth - BF Tunnel Mod

Read Everything here man

Requirements
------------
**Android**


Termux (Mandatory): https://github.com/Termux-Monet/termux-monet/releases/download/v0.119.0-b1-36/termux-app_v0.119.0-b1-36+apt-android-7-github-debug_universal.apk

SocksDroid (Recommended) : https://github.com/dangvankhanhduy/socksdroid/raw/master/app/release/app-release.apk

OpenVPN for Android (Best): https://github.com/schwabe/ics-openvpn/releases/download/v0.7.61/ics-openvpn-0.7.61.apk

---------------------------------------------------------------------------

Install Method 1 - Not fully tested yet. Do not use
---------
    termux-setup-storage && pkg install git -y && git clone https://github.com/sploit31337/psiphon && cd psiphon && chmod +x * && echo 'PATH="$PATH:$HOME/psiphon"' >> $HOME/.bashrc && source $HOME/.bashrc && tun

---------------------------------------------------------------------------

Install Method 2 - This assumes you have a active Internet Connection. This is just a 1 liner command to install the Zip if you dont already have it
-------
    clear && cd && cd && cd $HOME && cd /data/data/com.termux/files/usr/bin/ && pkg install wget -y && wget https://github.com/sploit31337/psiphon/raw/master/psiphon.zip && unzip psiphon.zip && chmod +x *

---------------------------------------------------------------------------

Install Method 3 - Assumes you already have the Zip and are Manually Installing this - TESTED AND WORKING
-------
**# Drop the Zip in to the Below Folder**

        /data/data/com.termux/files/usr/bin/


**# Change directory to the bin folder**

    cd /data/data/com.termux/files/usr/bin/

**# unzip the shit yo**

    unzip -o psiphon.zip && chmod +x *

**## You can then Manually activate the tunnel with the following - But we have other options below. READ BELOW

    tun -c 4 -tw 6 -r us -l 4 -f "*" -w "*:*"

---------------------------------------------------------------------------
### Commands (In the /data/data/com.termux/files/usr/bin directory)

    p-menu.mybin
This is a general menu for manually starting the tunnel with a few options right now

    p-auto-tunvar.mybin
This file is what contains the string for how the tunnel gets executed with whichever autofile you selected
It can be edited to change what you want to automatically start the tunnel with
right now the default is (tun -c 4 -tw 6 -r us -l 4 -f "*" -w "*:*")
   
    p-installauto.mybin
(See Below)
   
**### Auto Start Option Information ###**
----
Termux will automatically look for a binary executable file called "login".
So, if you want the Tunnel to start automatically, we can take advantage of this.

# USAGE:
    p-installauto.mybin
This installs the Auto System for Whichever app you have installed and It Also has a remove option to remove the system
It will install one of the auto files by simply copying it to a new file called "login"

---------------------------------------------------------------------------
## Clean Up (Removal of this system)
    p-cleanup.mybin
This is for cleaning up the entire installation (Removing it)

---------------------------------------------------------------------------

Note 1 - ### Socks5 IP address and Port Information
----

- The Psiphon Tunnel will start on the IP address of 127.0.0.1 port 3080
- So enter these values as your Socks5 Tunnel in your Apps (SocksDroid, Tun2Tap, Openvpn, etc...)
- AND MAKE SURE and Exclude Termux in those apps!

Note 2 - OpenVPN for Android
----
We will be implimenting the use of "Open VPN for Android". Currently it has been tested and works
Download Here: https://github.com/schwabe/ics-openvpn/releases/download/v0.7.61/ics-openvpn-0.7.61.apk

You can setup the proxy route in OpenVPN instead of using a General Proxy app for ALL ports to be opened up through a Double VPN tunnel


Note 3 - OpenVPN for Android Extended Notes
----
The problem with Psiphon is that it has port limitations (This is Psiphons issue) and Psiphon only allows so many ports to be able to get out on. So by utilizing Proxifier, DroidProxy, SocksDroid, Socks2Tun, Etc... then the apps that you then Proxy through Psiphon are at the mercy of whatever Psiphon allows to be opened. For Standard Internet Browsing this isn't an issue, but for Voice Service apps that use UDP protocols or other ports outside of Psiphons allowed range, this is a major issue.

So What do we do?
So instead of using a Proxy App, we will use a REAL Vpn Tunnel such as OpenVPN. The Problem is OpenVPN Connect doesn't support Socks5. However, "OpenVPN For Android" a custom Android OpenVPN App does. We can then use this version of OpenVPN to tunnel Via Port 443 (One of Psiphons Allowed Ports) to a 443 Capable VPN service (Like NordVPN) we then are Double VPN'd, meaning that the "OpenVPN for Android" app initiates a connection through the Psiphon Proxy address at 127.0.0.1 on Port 3080, connects to NordVPN and then Every Single App is then Directly tunneled through NordVPN as if they are directly connected to a very secure internet connection, and no longer at the mercy of Psiphon


Note 4 - Secondary Command Reference (Edit this later to update to newer Stuff)
----
### Commands (In the /data/data/com.termux/files/usr/bin directory)

    p-menu.mybin
This is a general menu for manually starting the tunnel with a few options right now

    p-auto-tunvar.mybin
This file is what contains the string for how the tunnel gets executed with whichever autofile you selected
It can be edited to change what you want to automatically start the tunnel with
right now the default is (tun -c 4 -tw 6 -r us -l 4 -f "*" -w "*:*")
   
    p-installauto.mybin
This is for Installation of the Auto Login for Specific Apps


    p-cleanup.mybin
This is for cleaning up the entire installation (Removing it)

   
