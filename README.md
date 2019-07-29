
# Dynamic Horizon DNS with openvpn and dnsmasq

This is a script to create dynamic horizon DNS from openvpn connections using dnsmasq as the local resolver.

The script is modified from https://github.com/alfredopalhares/openvpn-update-resolv-conf , which is a similar script to update dns dynamically using the resolveconf program.

The script depends on having [Augeas](http://augeas.net/) installed to safely edit the dnsmasq configuration files.

Place the script in `/etc/openvpn/update-dnsmasq`.

Add these lines to your openvpn client configuration file.

```
script-security 2
up /etc/openvpn/update-dnsmasq
down /etc/openvpn/update-dnsmasq
```

