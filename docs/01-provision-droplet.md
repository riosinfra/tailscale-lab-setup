# 01 — Provision a DigitalOcean Droplet

## Outcome
A running Ubuntu 24.04 droplet you can SSH into, ready for Tailscale installation.

## Prerequisites
- DigitalOcean account
- SSH key added to your account under Settings → Security Digital ocean documentation for SSH Keys.
(https://docs.digitalocean.com/products/droplets/how-to/add-ssh-keys/)

> All IPS shown here are for documentation purposes only. Droplets are destroyed at Lab conclusion

## Steps

### 1. Create the droplet
In the DigitalOcean console: Create → Droplets
- Image: Ubuntu 24.04 LTS
- Plan: Basic · $6/month (1 vCPU, 1GB RAM)
- Region: [choose closest to you or clients to reduce latency]
- Authentication: SSH Key

### 2. Connect via SSH
```bash
ssh root@YOUR_DROPLET_IP
```
**Example**

```bash
ssh root@146.190.138.48
```

### 3. Update the system
```bash
apt update && apt upgrade -y
```

## Verification
You should be at a root shell prompt on the droplet.

```bash
root@ubuntu:~#
```

## What broke

Nothing was broken but when I first copied the SSH key I had left out a few characters at the end. I had to update key in the Digital Ocean Console. 
