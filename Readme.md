# TinyFuzz: Directed Greybox Fuzzing based on AFLGo

# Getting Started
Let's get started with building TinyFuzz (on Ubuntu 20.04 LTS) and fuzz the target `libxml2`:

```bash
# For new computer
sudo apt install -y git python3-pip tmux openssh-server curl texinfo bison flex libbz2-dev gcc-multilib g++-multilib libc6-dev-i386
sudo pip3 uninstall pydot networkx -y
pip3 install networkx==2.5 pydot==1.4.2

# SSH 
sudo systemctl enable --now ssh
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up

# Start 
git clone https://github.com/ducdatdau/MOD-AFLGO.git
cd MOD-AFLGO
export AFLGO=$PWD

chmod 777 -R *

# Build
sudo ./build.sh

# When you fuzz for the very first time...
sudo sh -c 'echo core > /proc/sys/kernel/core_pattern'

# Fuzzing libxml2
cd examples
./libxml2-ef709ce2.sh
```