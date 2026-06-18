# 📦 ULB (usr/local/bin) Utility Pack

A collection of high-performance, professional Linux utilities designed for efficiency, reliability, and a zero-dependency footprint. These tools are engineered to act as native system commands, providing a seamless experience for system administrators and developers.

## 🛠️ Included Utilities

### 1. `2m4b` (Too Much for Backup)
A universal, multi-channel backup and distribution pipeline.
- **Local**: Dynamic compression with automated pruning (count/age).
- **Mirroring**: Direct copying to network/mounted paths.
- **Remote**: Secure offloading via FTP and SSH/SFTP.
- **Notification**: Real-time alerts via Webhooks and SMTP.
- **Lifecycle**: Pre- and post-backup shell command hooks.

### 2. `gitpush`
A streamlined wrapper for the Git commit-and-push workflow.
- **Fast-Track**: Adds all changes, commits with a custom or default message, and pushes to the remote repository in one command.

---

## 🚀 Deployment Guide

To use these utilities as native system commands from any directory, they must be deployed to `/usr/local/bin`.

### 1. Installation & Permissions
Copy the scripts to the local binary directory and grant them execution permissions:
```bash
# Copy files to local bin
sudo cp 2m4b /usr/local/bin/
sudo cp gitpush /usr/local/bin/

# Grant execution permissions
sudo chmod +x /usr/local/bin/2m4b
sudo chmod +x /usr/local/bin/gitpush
```

### 2. Verification
```bash
2m4b --help
gitpush
```

## 📖 Usage Examples

### `2m4b` (The Backup Powerhouse)

Standard Local Backup:

```bash
2m4b
```

Advanced Remote Pipeline:

```bash
2m4b -s /var/www/html -t /mnt/backups -c 10 \
     --ftp-host ftp.example.com --ftp-user admin --ftp-password secret \
     --webhook-url https://hooks.example.com/alert --webhook-post \
     --command-before "docker compose down" \
     --command-after "docker compose up -d"
```

### `gitpush` (The Efficiency Tool)

Push with default message ("Update"):

```bash
gitpush
```

Push with custom message:

```bash
gitpush "Fixed critical bug in API"
```