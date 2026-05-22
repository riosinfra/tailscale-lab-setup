08 — Troubleshooting Reference

A running log of issues encountered during this lab and how they were resolved.
Updated throughout the project.

##  Potential Connection issues

| Symptom | Diagnosis | Resolution |
|---------|-----------|------------|
| Device not appearing in tailnet | tailscaled not running | `sudo systemctl start tailscaled` |
| Can't reach peer by Tailscale IP | Peer offline or key expired | `tailscale status` — check peer state |
| Subnet route not working | IP forwarding disabled | `sysctl net.ipv4.ip_forward` should be 1 |

## Useful diagnostic commands
```bash
tailscale status              # show all peers and their state
tailscale ping 100.x.x.x     # test connectivity to a specific peer
tailscale netcheck            # check NAT type and relay latency
tailscale debug               # verbose diagnostic output
sudo journalctl -u tailscaled # service logs
```
