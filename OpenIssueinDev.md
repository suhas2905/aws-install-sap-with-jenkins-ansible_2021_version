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
