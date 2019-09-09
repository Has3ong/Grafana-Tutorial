# Grafana-Tutorial


## Install

#### Ubuntu 18.04

```
# The command add-apt-repository isn’t a default app on Debian 9 and requires
$ apt-get install -y software-properties-common

# Install the repository for stable releases
$ sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"

$ wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -

$ sudo apt-get update
$ sudo apt-get install grafana

$ sudo apt-get install -y apt-transport-https

$ sudo service grafana-server start

Connect localhost:3030

id : admin, password : admin
```

#### Mac

* with Docker

```
$ docker --version
Docker version 19.03.2, build 6a30dfc

$ docker run -d --name=grafana -p 3000:3000 grafana/grafana
Unable to find image 'grafana/grafana:latest' locally
latest: Pulling from grafana/grafana
35c102085707: Pull complete
251f5509d51d: Pull complete
8e829fe70a46: Pull complete
6001e1789921: Pull complete
9b5d32881363: Pull complete
7578291176cf: Pull complete
4dbdac071e30: Pull complete
9e6e4c211d56: Pull complete
fb609ed0062a: Pull complete
Digest: sha256:308be67d578c1603901fc12a544aa3968ee5cde572d478c84a96783cdeeef983
Status: Downloaded newer image for grafana/grafana:latest
a075a51cdff14627f3dd8aba4f1db97fcc94c32442b64fe81d3f6ff4f3199bde


$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                    NAMES
a075a51cdff1        grafana/grafana     "/run.sh"           8 seconds ago       Up 6 seconds        0.0.0.0:3000->3000/tcp   grafana
```

* Homebrew

```
$ brew update
$ brew install grafana


# To start Grafana using homebrew services first make sure homebrew/services is installed.
$ brew tap homebrew/services


# Then start Grafana using:
$ brew services start grafana


# Shutdown server
$ brew services stop grafana
Stopping `grafana`... (might take a while)
```
