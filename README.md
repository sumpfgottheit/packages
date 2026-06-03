# RPM und APT Repo for @sumpfgottheit

## Debian / Ubuntu

```bash
curl -fsSL https://sumpfgottheit.github.io/packages/gpg.key \
  | sudo gpg --dearmor -o /etc/apt/keyrings/sumpfgottheit.gpg

echo "deb [signed-by=/etc/apt/keyrings/sumpfgottheit.gpg] \
  https://sumpfgottheit.github.io/packages/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/chooz.list

sudo apt update && sudo apt install chooz
```

## Fedora / RHEL / CentOS

```bash
sudo rpm --import https://sumpfgottheit.github.io/packages/gpg.key

sudo tee /etc/yum.repos.d/chooz.repo <<'EOF'
[chooz]
name=chooz packages
baseurl=https://sumpfgottheit.github.io/packages/rpm/$basearch/
enabled=1
gpgcheck=1
gpgkey=https://sumpfgottheit.github.io/packages/gpg.key
EOF

sudo dnf install chooz
```
