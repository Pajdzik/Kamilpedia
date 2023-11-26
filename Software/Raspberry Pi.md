# Installation
1. Install Balena Etcher (used `brew`)
	- `brew install balenaetcher`
	- an alternative is to use [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
2.  Download [Raspberry Pi OS 32-bit image](https://www.raspberrypi.com/software/operating-systems/#raspberry-pi-os-32-bit)
	- The Pi3 series use 64-bit ARM cores with a 32-bit GPU. The recommended RPiOS is 32-bit with the option of using the 64-bit kernel (userland is still 32 bit). 
3. Setup Wi-Fi password
	1. `cd /Volumes/bootfs`
	2. `touch ssh`
	3. Copy the configuration from #wpa_supplicant
	4. `pbpaste > wpa_supplicant.conf`
4. `diskutil unmount /Volumes/bootfs/`
## wpa_supplicant.conf
```makefile
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
    ssid="YOUR_SSID"
    psk="YOUR_WIFI_PASSWORD"
    key_mgmt=WPA-PSK
}
```
# NAS
1. `sudo apt-get install nfs-common -y`
2. `sudo mkdir /mnt/media`
3. `sudo nvim /etc/fstab`
4. `sudo mount -t nfs 192.168.x.x:/home /mnt/synology`[5](https://kb.synology.com/en-ro/DSM/tutorial/How_to_access_files_on_Synology_NAS_within_the_local_network_NFS#x_anchor_id9)
# VPN
1. Install WireGuard – `sudo apt update && sudo apt install openresolv wireguard iptables`
2. Generate a configuration file – https://mullvad.net/en/account?platform=linux&next=%2Fen%2Faccount%2Fwireguard-config
3. scp source.conf pajdziu@192.168.X.X:/home/Y
4. 
   
## Links
- [WireGuard on Linux terminal (easy)](https://mullvad.net/en/help/easy-wireguard-mullvad-setup-linux/)