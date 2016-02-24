# Belajar Docker #

## Instalasi di Ubuntu ##

Semua langkah dilakukan dengan akun root

```
sudo -i
```

Update dulu database apt, dan pastikan https bekerja dengan baik

```
apt-get update
apt-get install apt-transport-https ca-certificates
```

Add GPG key docker

```
apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
```

Tambahkan repository docker

```
echo "deb https://apt.dockerproject.org/repo ubuntu-$(lsb_release -cs) main" > /etc/apt/sources.list.d/docker.list
```

Update lagi database apt

```
apt-get update
```

Uninstall docker jadul (kalau ada)

```
apt-get purge lxc-docker
```

Pastikan `apt-get` mengambil dari sumber yang benar

```
apt-cache policy docker-engine
```

Install paket `linux-image-extra` dan `apparmor`

```
apt-get install linux-image-extra-$(uname -r) apparmor
```

Install docker

```
apt-get install docker-engine
```

Start docker

```
service docker start
```

Test instalasi

```
docker run hello-world
```

Instalasi docker-machine

```
curl -L https://github.com/docker/machine/releases/download/v0.6.0/docker-machine-`uname -s`-`uname -m` > /usr/local/bin/docker-machine && \
chmod +x /usr/local/bin/docker-machine
```


## Instalasi di MacOSX ##

Instalasi aplikasi docker

```
brew install docker docker-machine docker-compose
```

Setup `default` machine, karena Docker tidak berjalan secara native di MacOSX

```
docker-machine create --driver virtualbox default
```

Stop machine (bila perlu)

```
docker-machine stop default
```

Start machine

```
docker-machine start default
```

Setup environment variable supaya bisa menjalankan Docker Client

```
eval $(docker-machine env)
```

Test instalasi (setelah `default` machine berjalan dan environment variable diset)

```
docker run hello-world
```

## Menjalankan Java di Docker ##

```
cd java-halo-docker
docker build -t halo-java .
docker run -rm halo-java
```


