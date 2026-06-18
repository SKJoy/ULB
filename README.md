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

## 🚀 Installation
- Create a temporary local folder: `mkdir /ulb; cd /ulb`
- Clone repository: `git clone https://github.com/SKJoy/ULB.git`
- Set executable for all users: `chmod +x *; chmod 0755 *`
- Move to Linux binary folder: `mv -f * /usr/local/bin`
- You may delete the `/ulb` folder now

### Verification
- `24mb -h`
- `gitpush`

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