# abstract-node

# Update your system
```
sudo apt update && sudo apt upgrade -y
```

# Docker Install & Install docker-compose
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
# Install the Docker packages
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
# Install docker-compose
```
sudo apt-get install docker-compose
```
# Start docker
```
sudo systemctl start docker
```
# Enable Docker
```
sudo systemctl enable docker
```
# 1. Clone the github repository
```
git clone https://github.com/Abstract-Foundation/abstract-node
```
# 2. Move to abstract directory
```
cd abstract-node/external-node
```
# 3. Start the node
```
docker compose --file testnet-external-node.yml up -d
```
4. Check the logs
```
docker logs -f --tail=0 <container name>
```
- `testnet-node-external-node-1`
- `testnet-node-postgres-1`
- `testnet-node-prometheus-1`
- `testnet-node-grafana-1`

# 5. Save your private key
```
cd configs
cat testnet_consensus_secrets.yaml
```
