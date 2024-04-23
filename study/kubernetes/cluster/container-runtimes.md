# Container Runtimes

<figure><img src="https://images.unsplash.com/photo-1605745341112-85968b19335b?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxkb2NrZXJ8ZW58MHx8fHwxNzEzODgyNTk0fDA&#x26;ixlib=rb-4.0.3&#x26;q=85" alt=""><figcaption><p>Container</p></figcaption></figure>

## Forwarding IPv4 and letting iptables see bridged traffic Execute the below mentioned instructions:

```bash
cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf
overlay
br_netfilter
EOF

sudo modprobe overlay
sudo modprobe br_netfilter

# sysctl params required by setup, params persist across reboots
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-iptables  = 1
net.bridge.bridge-nf-call-ip6tables = 1
net.ipv4.ip_forward                 = 1
EOF

# Apply sysctl params without reboot
sudo sysctl --system
```

## Install Containerd

Run the following command to uninstall all conflicting packages.

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

Set up Docker's apt repository

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Install Containerd package

```bash
sudo apt-get install containerd.io
```

```
Customizing containerd
```

## Customizing containerd

Generate default configuration

```bash
sudo containerd config default | sudo tee /etc/containerd/config.toml
```

You need CRI support enabled to use containerd with Kubernetes. Make sure that cri is not included in the disabled\_plugins list within /etc/containerd/config.toml

```bash
sudo vi /etc/containerd/config.toml

...
disabled_plugins = ["cri"]
=>
disabled_plugins = []
```

To use the systemd cgroup driver in _/etc/containerd/config.toml_ with runc, set

```bash
[plugins."io.containerd.grpc.v1.cri".containerd.runtimes.runc]
  ...
  [plugins."io.containerd.grpc.v1.cri".containerd.runtimes.runc.options]
    SystemdCgroup = true
```

restart containerd

```bash
sudo systemctl restart containerd Change persistent data location
```

## Create persistent data location

```bash
mkdir /home/user/containerd
```

You will need to change the path in the _/etc/containerd/config.toml_

```bash
# persistent data location
# root = "/var/lib/containerd"
root = "/home/tas/containerd"
```

restart containerd

```bash
sudo systemctl restart containerd
```

## Install docker Engine

We need docker to build or compile other docker based package.

```bash
sudo apt-get install docker-ce docker-ce-cli docker-compose-plugin
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

## Reference

[https://kubernetes.io/docs/setup/production-environment/container-runtimes](https://kubernetes.io/docs/setup/production-environment/container-runtimes/)

[https://github.com/containerd/containerd/blob/main/docs/getting-started.md](https://github.com/containerd/containerd/blob/main/docs/getting-started.md)
