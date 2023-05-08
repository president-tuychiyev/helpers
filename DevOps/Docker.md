# Get Started with Docker

We have a complete container solution for you – no matter who you are and where you are on your containerization journey. [🚀 Get started](https://docs.docker.com/)

## Download and install

- [Get Docker](https://docs.docker.com/get-docker/)

### Install Docker Engine on Ubuntu

- Uninstall old versions

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

- Update the apt package index and install packages to allow apt to use a repository over HTTPS:

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
```

- Add Docker’s official GPG key:

```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

- Use the following command to set up the repository:

```bash
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker Engine

- Update the <code>apt</code> package index:

```bash
sudo apt-get update
```

- <b>Install Docker Engine, containerd, and Docker Compose.</b>
- To install the latest version, run:

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

- Verify that the Docker Engine installation is successful by running the <code>hello-world</code> image.

```bash
sudo docker run hello-world
```

[View docs](https://docs.docker.com/engine/install/ubuntu/)

<hr>

## Remove old Docker containers

- Since [Docker 1.13.x](https://github.com/moby/moby/blob/master/CHANGELOG.md#1130-2017-01-18) you can use [Docker container prune](https://docs.docker.com/engine/reference/commandline/system_prune/):

```bash
docker container prune
```

This will remove all stopped containers and should work on all platforms the same way.

- There is also a [Docker system prune](https://docs.docker.com/engine/reference/commandline/system_prune/):

```bash
docker system prune [OPTIONS]
```

## The basic steps to stop/remove all containers and images

- List all the containers

```bash
docker ps -aq
```

- Stop all running containers

```bash
docker stop $(docker ps -aq)
```

- Remove all containers

```bash
docker rm $(docker ps -aq)
```

- Remove all images

```bash
docker rmi $(docker images -q)
```

<b>Note:</b> First you have to stop all the running containers before you remove them. Also before removing an image, you have to stop and remove its dependent container(s).

[View docs](https://stackoverflow.com/questions/17236796/how-to-remove-old-docker-containers)
