# 📦 **ULB** (`/usr/local/bin`) utility

A collection of high-performance, professional Linux utilities designed for efficiency, reliability, and a zero-dependency footprint. These tools are engineered to act as native system commands, providing a seamless experience for system administrators and developers.

## 🚀 Installation

Run the following command as `root` user;

```bash
cd /tmp && \
	git clone -q https://github.com/SKJoy/ULB.git && \
	rm -f ULB/README.md && \
	chmod 755 ULB/* && \
	mv -f ULB/* /usr/local/bin/ && \
	rm -rf ULB
```

### What does it do?
- Use a temporary path: `cd /tmp`
- Clone repository: `git clone -q https://github.com/SKJoy/ULB.git`
- Remove README.md file: `rm -f ULB/README.md`
- Set executable for all users: `chmod 755 ULB/*`
- Move to Linux binary folder: `mv -f ULB/* /usr/local/bin/`
- Delete the temporary folder: `rm -rf ULB`

### Verification command
- `2m4b -h`
- `gitpush`

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
	--command-before "docker compose down;#" \
	--command-after "docker compose up -d;#"
```

Note;
- **Backup file path** and **source path** are automatically *appended* to the `--command-before` & `--command-after` commands
- Use `;#` at the end of `--command-before` & `--command-after` commands to suppress trailing arguments

### `gitpush` (The Efficiency Tool)

Push with default message ("Update"):

```bash
gitpush
```

Push with custom message:

```bash
gitpush "Fixed critical bug in API"
```