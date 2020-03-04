---
layout: post
title: ÇözümPark İzmir Docker Eğitimi - Etkinlik Notları
---

ÇözümPark İzmir Docker Eğitimi etkinliğinde aldığım notlarım.

Güray Yıldırım - DevSecOps Founder/Head @peptr [Peptr Blog](https://blog.peptr.net)

## Docker Nedir?

Docker uygulamaların birbirinden bağımsız olarak çalışmasını sağlar, sanallaştırıp daha hafif olmasına sağlayan teknoloji. Sanal makine değildir. Yazdığın yazılıı build edip ship edebilip gönderir. **Build, Ship, Run, Any App Anywhere** [Infographic OneDocker](https://www.docker.com/sites/default/files/Infographic_OneDocker_09.20.2016.pdf)


## Docker Alternatifi var mı?

Containered ve CRI-O bunlardan ikisi.


<hr>

#### Kargoculuk ile Docker Karşılaştırması

##### Kargo

* Tırlar konteyner taşımak için yapılmış.
* Vinç konteyner taşımak için yapılmış.
* Gemi de konteyner taşımak için yapılmış. İçinde ne olacağından bağımsız.

Özel gemi, vinç, tıra gerek yok.

##### Docker

Uygulamayı oluştur. konteyner at. Sunucu konteyner'ı çalıştırsın. Server amacı sadece konteyner çalıştırması.

## Docker Çalışması

1. Tek seferlik Dockerfile yazılır.
2. Docker image üretilir. Uygulama kendisi ve gereksinimleri.
3. Çalıştır.

## Docker Temel Kodları

* docker version

```
docker version
```
* docker pull

Docker image'lerı indirmemize sağlar.

```
docker pull ubuntu
```

```
➜  ~ sudo docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
423ae2b273f4: Pull complete 
de83a2304fa1: Pull complete 
f9a83bce3af0: Pull complete 
b6b53be908de: Pull complete 
Digest: sha256:04d48df82c938587820d7b6006f5071dbbffceb7ca01d2814f81857c631d44df
Status: Downloaded newer image for ubuntu:latest

```

* DockerHub

Docker imagelerinin hub'ı (Github gibi).


* alpine

linux kernal hariç her kod linux kodu. 

```
docker pull alpine
```

```
docker run -it alpine   
```

### Docker Run

```
➜  ~ sudo docker run -it alpine   
/ # 
```

Dockerdan container çalışmasını sağlar.

`-it` Anlamı

i interaktif
t terminal

`/ # ` docker run çalıştığını gösteriyor.

Şu anda **alpine** sayesinde izole bir terminal çalıştı.


```
➜  ~ sudo docker run -it alpine   
/ # ls
bin    dev    etc    home   lib    media  mnt    opt    proc   root   run    sbin   srv    sys    tmp    usr    var
```

İzole olduğunun kanıtı

Ctrl+D - End of Line (Yazılacak herhangi bir şey kalmadı. Ne yapak istersen yap komudu. Ama çıkmak zorunda değil, ne yaparsan yao demekmiş). 

Exit ile çıkış yapılır.

<hr>

## Dockerfile


* FROM

Her zaman ilk satırda yazılır

```
FROM ubuntu:18.04
```

```
FROM centos:8
```


* RUN

Çalışacak kodlar.

```
RUN apt update
RUN apt install python3-minimal -y
```
`-y` Yes demektir. Yes/No sorusu gelmez. Gelirse hata verir.


```
FROM alpine

RUN apk update
RUN aok add python3
```

* Dockerfile Oluşturma

Örnek Terminal Kodları
```
➜  ~ mkdir dockerDev
➜  ~ cd dockerDev
```
Yukarıda `dockerDev` adlı bir klasör oluşturdum ve içine **Dockerfile** oluşturdum.

* Bu kodları **Dockerfile** adlı bir dosyaya girin.

```
FROM ubuntu:18.04

RUN apt update
RUN apt install python3-minimal -y
```

* Dockerfile build 

```
docker build -t cozpy .
```

Sonuç olarak

```
...
Successfully built b46d137c33f4
Successfully tagged cozpy:latest
```


* COPY

```
FROM nginx

COPY index.html /usr/share/nginx/html
```

Yukarıdaki kod index.html'i alır ve nginx kurar. index.html yayına alır.


* Örnek Flask Projesi

```
FROM alphine

RUN apk update
RUN apk add python3 py3-pip
RUN pip3 install flask

COPM ./app

CMD python3 main.py
```

`CMD python3 main.py` container açıldığında RUNTIME'da çalışacak koddur.


### Örnek Proje

```
git clone https://github.com/gurayyildirim/rastgeleSayi.git
cd rastgeleSayi
docker build -t rastgele . 
```

`-t`= tag demektir.
`.` = burası demektir (ihtiyacın olan her şey buradaki dizindedir).


[play-with-docker](http://play-with-docker.com/) 4 Saatlik docker veriyor, istenilen her şey yapılabilir. 4 saat sonra siliniyor.

* WORKDIR = Çalışma dizinidir.

```

```

* Dockerfile Dockerhub olarak build etmek

```
sudo docker build -t canokay/rastgele .
```

DockerHub'daki **canokay** kullanıcı adı altında **rastgele** image'ı olarak build ediyor. 


```
➜  rastgeleSayi git:(master) sudo docker build -t canokay/rastgele .

...
Successfully built d485f0640020
Successfully tagged canokay/rastgele:latest
```

Tekrardan build edilmedi çünkü eskiden build edilmişti. DockerHub'a göndermek için hazır.

* docker login

```
docker login
```
Dockerhub username ve password kullanarak giriş yapar.


```
docker push canokay/rastgele
```

Dockerhub canokay kullanıcısı altındaki rastgele'ye yollar.


```
docker run -p 80:80 canokay/rastgele
```

* Soldaki 80 sunucunun dışarıdaki açılan portudur.
* Sağdaki 80 container hangi portu dinliyorsa girilir. Güvenlik problemi çıkmaması için yazılır. İçerdeki porttur. 

## docker ps

```
docker ps
```

Container listeler.

```
➜  rastgeleSayi git:(master) sudo docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
892c0cec1b9a        canokay/rastgele    "/bin/sh -c 'gunicor…"   7 minutes ago       Up 7 minutes        0.0.0.0:80->80/tcp   quirky_chaplygin
```

## docker stop

```
sudo docker stop 892c0cec1b9a
```
10 saniye bekler ve kapanır.

```
➜  rastgeleSayi git:(master) sudo docker stop 892c0cec1b9a
892c0cec1b9a
```

## docker kill

```
sudo docker kill 892c0cec1b9a
```
Direkt yokolur, stopda 10 saniye bekler

### docker ps -a

```
➜  rastgeleSayi git:(master) sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                       PORTS               NAMES
7cbd1e783b06        canokay/rastgele    "/bin/sh -c 'gunicor…"   3 minutes ago       Created                                          gallant_cerf
87272f3992dc        canokay/rastgele    "/bin/sh -c 'gunicor…"   4 minutes ago       Created                                          zealous_chebyshev
892c0cec1b9a        canokay/rastgele    "/bin/sh -c 'gunicor…"   10 minutes ago      Exited (137) 2 minutes ago                       quirky_chaplygin
27e9eec5ac60        alpine              "/bin/sh"                2 hours ago         Exited (0) 2 hours ago                           angry_galois
```

* Docker name generate golang


```
➜  rastgeleSayi git:(master) sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                       PORTS               NAMES
7cbd1e783b06        canokay/rastgele    "/bin/sh -c 'gunicor…"   3 minutes ago       Created                                          gallant_cerf
87272f3992dc        canokay/rastgele    "/bin/sh -c 'gunicor…"   4 minutes ago       Created                                          zealous_chebyshev
892c0cec1b9a        canokay/rastgele    "/bin/sh -c 'gunicor…"   10 minutes ago      Exited (137) 2 minutes ago                       quirky_chaplygin
27e9eec5ac60        alpine              "/bin/sh"                2 hours ago         Exited (0) 2 hours ago                           angry_galois

➜  rastgeleSayi git:(master) sudo docker rm angry_galois 7cbd1e783b06
angry_galois
7cbd1e783b06
➜  rastgeleSayi git:(master) sudo docker ps -a                       
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                       PORTS               NAMES
87272f3992dc        canokay/rastgele    "/bin/sh -c 'gunicor…"   7 minutes ago       Created                                          zealous_chebyshev
892c0cec1b9a        canokay/rastgele    "/bin/sh -c 'gunicor…"   14 minutes ago      Exited (137) 5 minutes ago                       quirky_chaplygin

```

`➜  rastgeleSayi git:(master) sudo docker rm angry_galois 7cbd1e783b06` bu name ve id silindi.

<hr>

```
➜  rastgeleSayi git:(master) sudo docker run -it -p 80:80 canokay/rastgele
[2020-03-04 12:54:17 +0000] [6] [INFO] Starting gunicorn 19.7.1
[2020-03-04 12:54:17 +0000] [6] [INFO] Listening at: http://0.0.0.0:80 (6)
[2020-03-04 12:54:17 +0000] [6] [INFO] Using worker: sync
[2020-03-04 12:54:17 +0000] [10] [INFO] Booting worker with pid: 10
```

Artık docker çalışıyor.

Browser üzerinden [http://localhost/number](http://localhost/number) çalışacaktır.

* `-it` ile çalıştığı için Ctrl+C ile çıkılır.

* `-d` detech'dir. Terminal kapansa bile çalışmaya devam eder. Serverda arka planda çalışması içindir.

* `docker run --restart=always -d -p 80:80 canokay/rastgele` 

* `docker run --name web -d -p 80:80 canokay/rastgele` image a name verildi (Çok kullanılan bir yöntem değildir).

<hr>

[https://github.com/gurayyildirim/rastgeleSayi/blob/master/rastgele.py#L6](https://github.com/gurayyildirim/rastgeleSayi/blob/master/rastgele.py#L6)

```
docker run --name web - WAIT_TIME=0 -d -p 80:80 canokay/rastgele
```

* Bind mount

```
docker run -it -v mydata:/foto alpine
```

## docker volume

```
docker run -it -v mydata:/foto alpine
```


```
docker volume inspect mydata
```

```
➜  rastgeleSayi git:(master) sudo docker volume inspect mydata
[
    {
        "CreatedAt": "2020-03-04T16:35:36+03:00",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/mydata/_data",
        "Name": "mydata",
        "Options": null,
        "Scope": "local"
    }
]
```

## docker network

Örnek:

```
docker network create frontside
docker network create dbnet

docker run -d --network dbnet --name db alpine ping 8.8.8.8
docker run -d --network dbnet --name backed alpine ping 8.8.8.8
```

```
docker run --network
```
<hr>

```
docker-compose up-d
```

<hr>

### Nginx Proxy

[nginx-proxy](https://github.com/nginx-proxy/nginx-proxy)

```
$ docker run -d -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro jwilder/nginx-proxy
```


### portainer.io

Docker yönetim web sitesi. Komut satırı ile aynı ama web üzerinden yapılır.