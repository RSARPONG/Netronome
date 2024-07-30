# Device Validation
# *********************************************
lspci -Dnnd 19ee:4000/6000


# Validating the Driver
# *********************************************
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade


# Confirm Upstreamed NFP Driver (upstreamed nfp module confirmation)
# *********************************************
modinfo nfp | head -3


# Confirm that the NFP Driver is Loaded
# *********************************************
sudo lsmod | grep nfp


# If not loaded go through this command:

modprobe nfp



# SmartNIC netdev interfaces (Optional - Naming consistency)
# *********************************************

sudo apt-get install agilio-naming-policy



# Validating the Firmware
# *********************************************
ls -ogR --time-style="+" /lib/firmware/netronome/


# Check kernel when the driver is loaded
sudo dmesg | grep -A 4 nfp.*firmware


# The loaded firmware for a particular <netdev> interface
ethtool -i <netdev/netdev port>


SFC-P4 : enp1s0np0
OVS: enp1s0np0


# Upgrading the firmware
# *********************************************

Download: agilio-bpf-firmware-2.0.6.124-1.deb

sudo dpkg -i agilio-bpf-firmware-2.0.6.124-1.deb

