## OpenWRT build files for Raspberry Pi 0 Family
With this files the OpenWRT build will have:
- Luci web interface
- USB Gadget Ethernet assigned to lan by default
- `relayd` installed with luci proto.

> Defaults to `192.168.0.1` and Wifi is enabled by default with `openwrt` as SSID

After image burn, copy `cmdline.txt` and `config.txt` to the `/boot` partition, or add the following lines into those files:
```bash
# after "rootwait" in cmdline.txt
modules-load=dwc2,g_ether
# at the end in config.txt
dtoverlay=dwc2
```