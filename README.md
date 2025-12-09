# Debian Repository for XLibre

```sh
sudo apt-get update
sudo apt-get install -y ca-certificates curl

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://keys.openpgp.org/vks/v1/by-fingerprint/22075A919DAEB177E874C5D1D79CD6F1B52394FA | sudo tee /etc/apt/keyrings/xlibre-debian.asc
sudo chmod a+r /etc/apt/keyrings/xlibre-debian.asc

cat <<EOF | sudo tee /etc/apt/sources.list.d/xlibre-debian.sources
Types: deb deb-src
URIs: https://xlibre-debian.github.io/debian/
Suites: main
Components: stable
Architectures: amd64
Signed-By: /etc/apt/keyrings/xlibre-debian.asc
EOF

sudo apt-get update
sudo apt-get install xlibre
```
