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

#Open Issue 4
ASCS00 and ERS00 EFS filesystem creation

#Known 1
The Instance type is selected to non-nitro then the disk is created as nvme format.

#Knwon 2
Password has to be 10+ digit.
Product ID,
NW_ABAP_ASCS:S4HANA2021.CORE.HDB.ABAPHA
NW_ERS:S4HANA2021.CORE.HDB.ABAPHA

Known 3
Modificiation of the description for the version has to be carried out in the code.

Known 4
/usr/sap/SD1/SYS/exe/uc/linuxx86_64/sapcpe: /lib64/libstdc++.so.6: version `GLIBCXX_3.4.26' not found (required by /usr/sap/SD1/SYS/exe/uc/linuxx86_64/sapcpe)
3119751 - Linux Requirements for SAP Kernel 754 and for SAP Kernel 788 and higher
mkdir /usr/sap/lib
ln -s /opt/rh/SAP/lib64/compat-sap-c++-10.so /usr/sap/lib/libstdc++.so.6
chown -R sd1adm:sapsys /usr/sap/lib

Known 5
/usr/sap/trans
/ASCS
/ERS

Known 6
Prepare ERS files has been deleted from the ERS installation prepare_ers_files.yml
---

# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: MIT-0

- name: Copy AD0 exe binaries from sapmnt to ERS folder
  copy: 
    src: "{{ ascs_source_sapcontrol_binaries }}"
    dest: "{{ ers_dest_sapcontrol_binaries }}"
    remote_src: yes

- name: Fix permissions on folder
  file:
    path: "/usr/sap/{{ GLOBAL_ASCS_SID }}"
    state: directory
    mode: 0777
    recurse: yes
  when: GLOBAL_PRODUCT_TO_INSTALL == "ERS"

Known 7
Global overlay IP variable




