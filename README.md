# Debian Repository for XLibre

```sh
sudo apt-get update
sudo apt-get install -y ca-certificates curl

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://mrchicken.nexussfan.cz/publickey.asc | sudo tee /etc/apt/keyrings/NexusSfan.asc
sudo chmod a+r /etc/apt/keyrings/NexusSfan.asc

cat <<EOF | sudo tee /etc/apt/sources.list.d/xlibre-debian.sources
Types: deb deb-src
URIs: https://xlibre-debian.github.io/debian/
Suites: main
Components: stable
Architectures: amd64
Signed-By: /etc/apt/keyrings/NexusSfan.asc
EOF

sudo apt-get update
sudo apt-get install xlibre xlibre-archive-keyring
```
