# How-to-install-OpenClaw-with-Wsl-on-Windows-11

First Open PowerShell as Administrator and run: 
```wsl --install```

Then on PowerShell as Administrator and run:
```wsl --install -d Ubuntu```   ( then restart )

After restart, Ubuntu will open and ask you to:
Create a username
Create a password 
after all complete the installation 

open the Ubuntu terminaland enter:
```sudo tee /etc/wsl.conf >/dev/null <<'EOF'
[boot]
systemd=true
EOF
```

Then back in PowerShell:
```wsl --shutdown```

Re-open the Ubuntu terminal and verify that systemd is enabled:
```systemctl --user status```

# Install Prerequisites: Node.js
Inside Ubuntu (WSL)

Update packages:
```sudo apt update && sudo apt upgrade -y```

Install Node.js 22+:
```curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
```

Check versions:
```node --version
npm --version   (OpenClaw requires Node.js 22 or higher)
```

# Install OpenClaw
inside WSL Ubuntu

Enter and run this code
```sudo npm install -g openclaw@latest```

```curl -fsSL https://openclaw.ai/install.sh | bash```


# Run Onboarding & Install Gateway

Inside the Ubuntu terminal, start OpenClaw’s setup wizard:
```openclaw onboard --install-daemon```





