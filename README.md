tailscale-lab-setup

A documented Tailscale mesh network built on a DigitalOcean droplet,
connecting a cloud Linux node, Chromebook, iOS device, and Unraid server
into a single private tailnet.

## What problem this solves
Traditional VPNs require firewall rules, open ports, and centralized
infrastructure. This lab demonstrates how Tailscale creates encrypted
peer-to-peer connections across completely different networks with zero
firewall changes. 

## Architecture


## Tailnet nodes
| Device         | OS           | Role                        | Tailscale IP |
|----------------|--------------|-----------------------------|--------------|
| do-droplet     | Ubuntu 24.04 | Subnet router · Exit node   | 100.x.x.x    |
| Chromebook     | ChromeOS     | Client                      | 100.x.x.x    |
| iphone         | iOS          | Client                      | 100.x.x.x    |
| unraid-server  | Unraid/Linux | NAS · existing node         | 100.x.x.x    |

## Labs to be covered
- [01 — Provision DigitalOcean droplet](docs/01-provision-droplet.md)
- [02 — Install Tailscale on Linux](docs/02-install-tailscale-linux.md)
- [03 — Install Tailscale on ChromeOS](docs/03-install-ChromeOS.md)
- [04 — Install Tailscale on iOS](docs/04-install-ios.md)
- [05 — Subnet routing (VPC)](docs/05-subnet-routing.md)
- [06 — Exit node](docs/06-exit-node.md)
- [07 — MagicDNS](docs/07-magicdns.md)
- [08 — Tailscale SSH](docs/08-tailscale-ssh.md)
- [09 — Troubleshooting](docs/09-troubleshooting.md)

## What I learned


## Next steps
- Add a second subnet router for redundancy
- Explore Tailscale ACL posture checking
- Integrate with an identity provider