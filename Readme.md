# AFLGo: Directed Greybox Fuzzing

# Getting Started
Let's get started with building MOD-AFLGo (on Ubuntu 20.04) and fuzz the target libxml2:

```bash
git clone https://github.com/ducdatdau/MOD-AFLGO.git
cd MOD-AFLGO
export AFLGO=$PWD

chmod 777 *

# Build AFLGo
sudo ./build.sh

sudo pip3 uninstall pydot networkx -y
pip3 install networkx==2.5 pydot==1.4.2

# When you fuzz for the very first time...
sudo sh -c 'echo core > /proc/sys/kernel/core_pattern'

# Fuzz the target libxml2
cd examples
./libxml2-ef709ce2.sh
```