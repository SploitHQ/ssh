# SSH – Secure Shell for Remote Access and Connectivity

**SSH** (Secure Shell) is the standard protocol for secure remote login and command execution over an encrypted connection. It’s widely used by system administrators, developers, and penetration testers to manage servers, tunnel traffic, transfer files, and maintain persistence.

🔗 [Explore SSH Use Cases on SploitHQ](https://sploithq.com/ssh)

---

## 🔍 What Can SSH Do?

- Remote shell access over encrypted channel
- Secure file transfer with `scp` or `sftp`
- Port forwarding and dynamic tunneling
- Key-based authentication
- Proxy access and pivoting for red teaming

---

## ⚙️ Basic Syntax

```bash
ssh [options] user@host
```

---

## 🧰 Common SSH Options

| Option                | Description                                           |
|------------------------|-------------------------------------------------------|
| `-p <port>`            | Specify a custom port                                |
| `-i <identity_file>`   | Use a specific private key for login                 |
| `-L <local>:<remote>`  | Local port forwarding (tunnel from your machine)     |
| `-R <remote>:<local>`  | Remote port forwarding (expose your local port)      |
| `-D <port>`            | Dynamic SOCKS proxy (acts like a VPN)               |
| `-N`                   | Don’t execute a remote command (for tunneling only) |
| `-T`                   | Disable pseudo-terminal allocation                   |
| `-f`                   | Run in background after authentication               |
| `-v`                   | Verbose output for debugging                         |

---

## 🧪 Examples

### Basic SSH login
```bash
ssh user@192.168.1.100
```

### Login on custom port
```bash
ssh -p 2222 user@target.com
```

### Use private key
```bash
ssh -i ~/.ssh/id_rsa user@target.com
```

### Forward local port 8080 to remote port 80
```bash
ssh -L 8080:localhost:80 user@target.com
```

### Expose local port 22 on remote server (reverse tunnel)
```bash
ssh -R 2022:localhost:22 user@vps.com
```

### Start SOCKS proxy (for proxychains or browser)
```bash
s
