Note: Since you cannot ssh, you will have to either copy the text through a USB or just manually type it in lol

```
# wget raw.githubusercontent.com/LaiYanKai/EE4308/main/rubiker.sh
# source rubiker.sh
sudo sh -c "echo 'APT::Periodic::Update-Package-Lists "0";' > /etc/apt/apt.conf.d/20auto-upgrades"
sudo sh -c "echo 'APT::Periodic::Unattended-Upgrade "0";' >> /etc/apt/apt.conf.d/20auto-upgrades"

# netplan
sudo sh -c "echo 'network:' > /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '  version: 2' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '  ethernets:' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '    eth0:' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '      dhcp4: true' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '      optional: true' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#  wifis:' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#    wlan0:' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#      dhcp4: true' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#      optional: true' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#      access-points: ' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#        <WIFI_SSID>: ' >> /etc/netplan/50-cloud-init.yaml"
sudo sh -c "echo '#          password: <WIFI_PASSWORD>' >> /etc/netplan/50-cloud-init.yaml"
sudo reboot
```
After restart

```
systemctl mask systemd-networkd-wait-online.service
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
sudo apt update
sudo apt upgrade --yes
```
