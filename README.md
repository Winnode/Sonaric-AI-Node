# sonaric-install

## Windows

1. (optional but required for GPU support) Requires supported Nvidia GPU. Install the latest Nvidia driver from [here](https://www.nvidia.com/Download/index.aspx).
2. Install WSL2 from [Microsoft Store](https://aka.ms/wslstorepage).
3. Download and run `windows-install-sonaric.bat` script.

## MacOS

Paste that in a macOS Terminal.

```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Winnode/Sonaric-AI-Node/main/linux-install-sonaric.sh)"
```

## Linux

Execute the following command in a terminal.
Currently supported distributions are:
* Ubuntu 22.04+
* Debian 12+
* CentOS 8+
* Rocky Linux 8+

## Update 

```
sudo apt update && sudo apt upgrade
sudo apt upgrade sonaric
```

```
wget https://raw.githubusercontent.com/Winnode/Sonaric-AI-Node/main/linux-install-sonaric.sh chmod +x linux-install-sonaric.sh && ./linux-install-sonaric.sh

```

```
ssh -L 127.0.0.1:44003:127.0.0.1:44003 -L 127.0.0.1:44004:127.0.0.1:44004 -L 127.0.0.1:44005:127.0.0.1:44005 -L 127.0.0.1:44006:127.0.0.1:44006 root@<ip_vps>
```

## chage YourNode
```
sonaric identity-export -o YourNode.identity
sonaric identity-import -i YourNode.identity
systemctl status sonaricd
sonaric node-rename Winnode
```
Input Your Pass VPS

## save YourNode Identity

```
cat  YourNode.identity
```

## Check Succes Install

```
sonaric node-info
```
(save)

Alternatively, you can download and unpack the binaries, that requires prerequisites:

* Podman >=3.4.0 https://podman.io/docs/installation
* Wireguard https://www.wireguard.com/install/

```
curl -skSL --retry 3 https://storage.googleapis.com/sonaric-releases/stable/linux/sonaric-amd64-latest.tar.gz | tar -xz -C /usr/local/bin
```

With manual install you will need to start the sonaric service manually:

```
sudo /usr/local/bin/sonaricd
```
