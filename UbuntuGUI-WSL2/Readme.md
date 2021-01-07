https://dev.to/darksmile92/linux-on-windows-wsl-with-desktop-environment-via-rdp-522g


> sudo apt update && sudo apt -y upgrade
> sudo apt install xrdp
> sudo apt install -y xfce4 # Light weight GUI
              0r
> sudo apt install -y xfce # gdm3/lightdm
> sudo apt install -y xfce4-goodies

> sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak #backup of xrdp file
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini #diffrent port number
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini # increase resolution
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
> echo xfce4-session > ~/.xsession
> sudo nano /etc/xrdp/startwm.sh
> Comment out last two lines and add 
#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
#exec /bin/sh /etc/X11/Xsession
# xfce
startxfce4
> sudo /etc/init.d/xrdp start


