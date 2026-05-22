07 — Tailscale SSH
 
## Outcome
You can SSH into the droplet over the tailnet without port 22 open to
the public internet. The droplet's public IP is no longer needed for access.
 
## Why this matters
This is a zero-trust access pattern — the droplet is completely dark
to the public internet. Access is controlled entirely by tailnet identity.
Common in enterprise Tailscale deployments.
 
## Steps
 
### 1. Enable Tailscale SSH on the droplet
```bash
sudo tailscale up \
  --advertise-routes=10.YOUR.VPC.0/20 \
  --advertise-exit-node \
  --ssh
```
> When ever new flags are added using `tailscale up` all previous used tags must be included as well to maintain current state
 
### 2. Test SSH over the tailnet
```bash
# From your Mac — use MagicDNS hostname, not the public IP
ssh root@host.FQDN
```
 
### 3. (Optional) Remove public SSH access
In DigitalOcean Networking → Firewalls, remove the rule allowing port 22
from 0.0.0.0/0. The droplet is now only accessible via Tailscale.
 
## Troubleshooting
- **Connection refused:** confirm --ssh flag was passed in tailscale up
- **Permission denied:** check Tailscale ACL — SSH access may be restricted by policy

