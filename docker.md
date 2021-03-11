# Docker

## .NET on Windows

## Install on WSL

Use the windows docker demon with the linux client
(For e.g. better tty handling)

Open up the docker daemon for tcp on the windows host - (settings, check Expose ... locahost:2375 withput TLS)
install docker

- Install packages to allow apt to use a repository over HTTPS

```console
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

- Add Docker's official GPG key

```console
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

- Set up the repository

```console
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

- Update source lists

```console
sudo apt-get update
```

- Install Docker

```console
sudo apt-get install docker-ce
docker images
```

- Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?

```console
docker -H tcp://0.0.0.0:2375 images
```

- Add the above option to the shell

```console
echo "export DOCKER_HOST='tcp://0.0.0.0:2375'" >> ~/.bash_tune
```

## Windows WSL 2 - move docker storage

<https://stackoverflow.com/questions/62441307/how-can-i-change-the-location-of-docker-images-when-using-docker-desktop-on-wsl2>

default location: %USERPROFILE%\AppData\Local\Docker\wsl\data\ext4.vhdx

```dos
> dir %USERPROFILE%\AppData\Local\Docker\wsl\data
```

```console
$ ls $USERPROFILE/AppData/Local/Docker/wsl/data
```

First: stop all docker related services using task manager

```dos
wsl --list -v

--------------------------------------------------
  NAME                   STATE           VERSION
* docker-desktop         Stopped         2
  docker-desktop-data    Stopped         2
--------------------------------------------------

mkdir D:\Docker\wsl\data
wsl --export docker-desktop-data "D:\Docker\wsl\data\docker-desktop-data.tar"
wsl --unregister docker-desktop-data
wsl --import docker-desktop-data "D:\Docker\wsl\data" "D:\Docker\wsl\data\docker-desktop-data.tar" --version 2
```
