# Debian Repository for XLibre

```sh
sudo apt-get update
sudo apt-get install -y ca-certificates curl

sudo install -m 0755 -d /usr/share/keyrings
curl -fsSL https://mrchicken.nexussfan.cz/publickey.asc | gpg --dearmor | sudo tee /usr/share/keyrings/NexusSfan.pgp > /dev/null
sudo chmod a+r /usr/share/keyrings/NexusSfan.pgp

cat <<EOF | sudo tee /etc/apt/sources.list.d/xlibre-debian.sources
Types: deb
URIs: https://xlibre-debian.github.io/debian/
Suites: main
Components: stable
Architectures: amd64
Signed-By: /usr/share/keyrings/NexusSfan.pgp
EOF

sudo apt-get update
sudo apt-get install xlibre xlibre-archive-keyring
```

If you wish to uninstall XLibre and return to Xorg:
```sh
sudo apt-get update
sudo apt remove xlibre xserver-xlibre*
sudo apt install xorg
sudo rm /etc/apt/sources.list.d/xlibre-debian.sources /usr/share/keyrings/NexusSfan.pgp
```
