REQUIREMENT PACKAGES:
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common

GPG REPO:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

APT REPO SOURCES:
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

UPDATE INTERNAL REPO SYSTEM
sudo apt update

verify repo from docker:
apt-cache policy docker-ce

INSTALL:
sudo apt install docker-ce

CHECK STATUS:
sudo systemctl status docker

ROOTLESS:
sudo usermod -aG docker ${USER}

Check Rootless: 
groups

check docker access:
docker info
