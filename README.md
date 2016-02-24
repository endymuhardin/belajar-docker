# Belajar Docker #

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
cd java-halo-docker
docker build -t halo-java .
docker run -rm halo-java
```


