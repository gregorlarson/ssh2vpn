# ssh2vpn
Mesh VPN based on ssh TUN support

I created this because I was having issues with openvpn performance
due to the centralized nature of openvpn. Also, openvpn was not always
installed on every system I needed vpn access to.

This script depends on ssh client and relatively minor configuration changes to sshd:
- PermitTunnel yes

The ssh2vpn script allows you to create a simple VPN using the SSH TUN support. Configuration file is designed so that it can be identical on each host in the mesh.

It operates in a mesh, so it performs fairly well (well enough to run NFS with my AWS EC2 machine).

## TODO
- Documentation of config
- Certificate creation
- Documentation of agent use and authorized_keys.
