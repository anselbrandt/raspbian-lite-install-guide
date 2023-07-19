# Installing Docker

```
# update software repositories

Submit sudo apt update

# install necessary packages for https apt calls

Submit sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

# add docker GPG key

Submit curl -fsSL https://download.docker.com/linux/raspbian/gpg | sudo apt-key add -

# add docker software repository

Submit echo "deb [arch=armhf] https://download.docker.com/linux/raspbian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker-ce.list

# install docker

Submit sudo apt update
Submit sudo apt install docker-ce docker-ce-cli containerd.io

# start docker service

Submit sudo systemctl start docker

# enable docker service on startup

Submit sudo systemctl enable docker

# create a docker group

Submit sudo groupadd docker

# add the current user to the docker group

Submit sudo usermod -aG docker $USER
```

```
sudo docker run hello-world
```
