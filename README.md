# **Automatic Setup**

Linux:
1. Download the ".sh" file in the releases and edit the paramter where it says path="yourpath"
2. Enjoy!

Windows
1. Download the ".bat" file in the releases and edit the paramter where it says path="yourpath"
2. Enjoy!

# **Manual Setup**

Connect to the internet to be able to SSH automatically without fiddling with an hdmi cable

1. Flash the ARMBIAN OS to your desired sd card
2. Once done, go to the path of your sd card, in this case "armbi_root/etc/netplan/"
3. Edit 10-dhcp-all-interfaces.yaml, input the following and edit put your WIFI info inside

```
# Added by Armbian
#
# Reference: https://netplan.readthedocs.io/en/stable/netplan-yaml/
#
# Let systemd-networkd manage all Ethernet devices on this system, but be configured by Netplan.

network:
  version: 2
  renderer: networkd
  wifis:
    wlan0:
      dhcp4: true
      dhcp6: true
      access-points:
        "WiFiName":
          password: "WifiPassword"
```

4. Save and put it into your pi, connect to the IP by looking for the devices in your router's admin panel
5. Enjoy!
