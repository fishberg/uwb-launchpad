# uwb-launchpad

Public repo with documentation for setting up our UWB experiment code.

## Quickstart
```bash
# get ssh key
scp fishberg@aldrin.local:~/.ssh/acl-alphabet* ~/.ssh
echo -e "Host github.com\n    IdentityFile ~/.ssh/acl-alphabet" >> ~/.ssh/config
sudo apt install git

mkdir -p ~/dirs
cd ~/dirs
git clone git@github.com:fishberg/px4-raspi-devel.git
git clone git@github.com:fishberg/nooploop-uwb-tools.git
git clone git@github.com:MarineRoboticsGroup/uwb-drone-px4-experiments.git
```

## Relevant Repos
* [px4-raspi-devel](https://github.com/fishberg/px4-raspi-devel)
* [nooploop-uwb-tools](https://github.com/fishberg/nooploop-uwb-tools)
* [uwb-drone-px4-experiments](https://github.com/MarineRoboticsGroup/uwb-drone-px4-experiments)

