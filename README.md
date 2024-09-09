# uwb-launchpad

Public repo with documentation for setting up our UWB experiment code.

## Quickstart
```bash
# update
sudo apt update
sudo apt upgrade
sudo ubuntu-drivers install

# uninstall automatic updates
sudo apt purge update-manager update-notifier unattended-upgrades
sudo apt purge ubuntu-release-upgrader-core ubuntu-release-upgrader-gtk ubuntu-release-upgrader-qt

# connect to wifi
nmtui

# install ssh, start, start by default, and confirm 
sudo apt install ssh
sudo systemctl start ssh.service
sudo systemctl enable ssh.service
ssh 127.0.0.1

# add ssh access w/ `robot.pub`
echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCnDl0aTGWXZoalqrOpB8o9LQcqj4I7r22hXsdF3NJtQ0j/b+y573DCh2nW41Rluq4Gj0/fpBGH14ftoQ8u7vgYI+Y9XVt4odOyD+K7s6lx4HkkrKaCgjhXbxYSbIuiyecIWdu0fv6gCHJFR4noofMkvmYq5Mk2PRsnai7TRiwUEz7XXT9AA+V5tq+inHq4hlU3ff4pJYYkSp7WMWScIgRsNw1sr5ZDE65VDWg6k1CRMWDxsKtk6aOT/ajaMQtNa23PDh/ryIb+9IabAo43Xey4kYH/XEIxnF6nEzKCoq2CZdokkNmQL0X2uYw5oBykwVLRu5zg5EiAtyXjHyeKDXuzIro20sI9N8KA4B47W4rdGosUDLbcH64+tEjsThQoiQ2IKRhJMnb2sxfw3sK5qeQhU8WyffVnvJIwjI4J+7a3e2W05quGHnMYxHQeaOpkr/Csby8lorZuZZ6LFIQq0XmiPibJ3OgoTGEI4tKFCGnj8TcanzR5kPjoBeYyW09qsdM= swarm@robot" >> ~/.ssh/authorized_keys

# get ssh key for GitHub
scp fishberg@aldrin.local:~/.ssh/acl-alphabet* ~/.ssh
echo -e "Host github.com\n    IdentityFile ~/.ssh/acl-alphabet" >> ~/.ssh/config

# set workspace location
echo -e '\n# research workspace\nexport WORKSPACE=~/workspace' >> ~/.bashrc
source ~/.bashrc

# clone repos
sudo apt install git
mkdir -p $WORKSPACE/repos
cd $WORKSPACE/repos
git clone git@github.com:fishberg/px4-raspi-devel.git

# navigate to install directory
cd $WORKSPACE/repos/px4-raspi-devel/install
```

## Sample ~/.ssh/config Entry
```
Host quadrotor
    HostName quadrotor.local
    Port 22
    User swarm
    IdentityFile ~/.ssh/robot
```

## Relevant Repos
* [px4-raspi-devel](https://github.com/fishberg/px4-raspi-devel)
* [nooploop-uwb-tools](https://github.com/fishberg/nooploop-uwb-tools)
* [uwb-drone-px4-experiments](https://github.com/MarineRoboticsGroup/uwb-drone-px4-experiments)
