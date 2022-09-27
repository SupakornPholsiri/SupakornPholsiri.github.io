```shell
sudo curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```
```shell
sudo apt-get install -y nodejs git make g++ gcc
```
```shell
node --version
npm --version
```
```shell
sudo mkdir /opt/zigbee2mqtt
sudo chown -R ${USER}: /opt/zigbee2mqtt
```
```shell
git clone --depth 1 https://github.com/Koenkk/zigbee2mqtt.git /opt/zigbee2mqtt
```
```shell
cd /opt/zigbee2mqtt
npm ci
```
