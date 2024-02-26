# Tailscale
This readme should help you with tailscale client setup. The packages is based on the work of [janknieling](https://github.com/janknieling) for tailscale original packages.

## Install
There are two binaries related to tailscale. Tailscaled (daemon which has to run every time you want to be connected to VPN) and tailscale (package with a utility which is necessary for registering device). Tailscale has the option to combine both binaries into one file. This packages does combine-compile Tailscale for smaller routers.

To install it run
```
opkg install tailscale-min
```
> [!NOTE]
> By default this package will use nftables. If you wish to use iptables, the config file `/etc/config/tailscale` can be modfied, changing the line `fw_mode 'nftables'` to `fw_mode 'iptables'`. You can then run `/etc/init.d/tailscale restart` to restart tailscale using your chosen method

## First setup

First, enable and run daemon

```
/etc/init.d/tailscale enable
/etc/init.d/tailscale start
```

Then you should use tailscale utility to get a login link for your device.

Run command and finish device registration with the given URL.
```
tailscale up
```

See the [OpenWrt wiki](https://openwrt.org/docs/guide-user/services/vpn/tailscale/start) for more detailed setup instructions
