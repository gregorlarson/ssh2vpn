# ssh2vpn
Mesh VPN based on ssh TUN support

I created this because I was having issues with openvpn performance
due to the centralized nature of openvpn. Also, openvpn was not always
installed on every system I needed vpn access to.

This script depends on ssh client and relatively minor configuration changes to sshd:
- PermitTunnel yes

The ssh2vpn script allows you to create a simple VPN using the SSH TUN support. Configuration file is designed so that it can be identical on each host in the mesh.

It operates in a mesh, so it performs fairly well (well enough to run NFS with my AWS EC2 machine).

# ssh2vpn [status] [hostname|hostnum]
Without and command args, the status of connections will be displayed (for running or failed connections).

## Status TODO:
- Add an 'all' command which shows all possible connections and their state.
- Improve the output of status so it shows persistent connections which are awaiting re-connection.

# ssh2vpn start|persist [hostname|hostnum]
Using the ssh2vpn start or persist commands, you can run the tunnel without systemd or another service wrapper.
- the difference between start and persist, is that persist will continuously restart
  the tunnel if it fails, where as, start will run the tunnel only once.

## ssh2vpn stop [hostname|hostnum]
For locally managed (non systemd) connections, this stops the connection (kills the ssh tun session).
# ssh2vpn agent

# ssh2vpn mkcert

# ssh2vpn systemd wrapper
## systemd TODO:
Try an create a template wrapper that will work for multiple tunnels.

# TODO
- Documentation of config
- Certificate creation
- Documentation of agent use and authorized_keys.
