
# CentOS 7 reinstall script & kickstart for Dedibox dedicated servers

CAUTION: backup your data before doing anything.

THIS SCRIPT WILL REINSTALL YOUR SERVER AND DESTROY ALL ITS DATA.


### Prerequisites

A webserver (temporary web hosting will do) to host the kickstart and pubkeys file.

A dedicated server ripe for reinstall.


### HowTo

First step: install CentOS on your Dedibox using the console

Edit the kickstart:
* replace YOUR_GATEWAY YOUR_IP by your dedibox' gateway and IP addresses
* replace YOUR_HOSTNAME_FQDN by your dedibox' hostname
* replace YOUR_PASSWORD_STRING_IN_SHA512 by an encrypted password string 
* replace INSTALL_SRV_FQDN by the FQDN of your installation server (can be temporary web hosting)
* host the kickstart and a "pubkeys" file (containing your ssh public key(s)) in the INSTALL_SRV_FQDN

Prepare and install the dedibox:
* Upload install-dedibox.sh to /root/ in your temporary CentOS installation
* Edit install-dedibox.sh and replace KICKSTART_SRV_FQDN by the FQDN of your install server.
* Launch "/bin/bash /root/install-dedibox.sh" as root.
* Reboot your server ("reboot").
* Installation takes about 15-20 mins on a Dedibox with SSD.
* Once ssh is up, login using your SSH key and change the root password.


### Notes

This script:
* uses Google's DNS servers.
* uses the IRCAM's public mirror which may not be the closest to your location.
* installs CentOS 7.2.1511 which may not be the latest version.
* enables the EPEL and remi-safe repositories.

Please adapt to your needs.


### Wishlist

* network: use dhcp to boot, generate a kickstart snippet in %pre to switch to static during install
* rootpw: add generator example

