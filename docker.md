# Installing Docker

```
# update software repositories

sudo apt update

# install necessary packages for https apt calls

sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

# add docker GPG key

curl -fsSL https://download.docker.com/linux/raspbian/gpg | sudo apt-key add -

# add docker software repository

echo "deb [arch=armhf] https://download.docker.com/linux/raspbian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker-ce.list

# install docker

sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io

# start docker service

sudo systemctl start docker

# enable docker service on startup

sudo systemctl enable docker

# create a docker group

sudo groupadd docker

# add the current user to the docker group

sudo usermod -aG docker $USER
```

```
sudo docker run hello-world
```
