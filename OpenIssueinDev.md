#Open Issue 1
echo "tsc" > /sys/devices/system/clocksource/*/current_clocksource
cp /etc/default/grub /etc/default/grub.backup
sed -i '/GRUB_CMDLINE_LINUX/ s|"| clocksource=tsc"|2' /etc/default/grub
grub2-mkconfig -o /boot/grub2/grub.cfg

HANA config_clocksoource is commented at the moment.

#Open Issue 2
The inbound CIDR for customer has all inbound access.

#Open Issue 3
The creations of all the instances are in Public IP.

#Known 1
The Instance type is selected to non-nitro then the disk is created as nvme format.

#Knwon 2
Password has to be 10+ digit.
Product ID,
NW_ABAP_ASCS:S4HANA2021.CORE.HDB.ABAPHA
NW_ERS:S4HANA2021.CORE.HDB.ABAPHA

Known 3
Modificiation of the description for the version has to be carried out in the code.