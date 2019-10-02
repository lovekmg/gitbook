---
description: Dockerfile 관련 정리해뒀던거 기록.
---

# \[memo\] Dockerfile-1

## 정리하자~

Docker 실행 명령

```
$ docker run -it --name=ubuntu_base ubuntu:16.04 /bin/bash
```

{% hint style="info" %}
 port, share dir 등 추가 옵션이 많으니 그건  필요할때 검색하여 사용하자.
{% endhint %}

Once you're strong enough, save the world:

```

apt update && apt upgrade

# 기본 tool 설치
apt install -y wget curl vim locales tzdata python-software-properties software-properties-common apt-transport-https net-tools

# php repository 등록
add-apt-repository ppa:ondrej/php

apt update
apt install -y php7.2-fpm

# dpkg-reconfigure tzdata       # 타임존 변경하려면...

# nginx
docker run -it --rm --name=nginx -p 8080:80 -v /home/lovekmg/docker/php-versions/conf/nginx/conf:/etc/nginx -v /home/lovekmg/docker/php-versions/conf/nginx/log:/var/log -v /home/lovekmg/docker/php-versions/src/laravel-app/public:/var/www/html nginx:0.1 /bin/bash
docker run -it --rm --name=nginx2 -p 8081:80 nginx:0.1 /bin/bash

# php 7.0
docker run -it --name=php-7.0 -v /home/lovekmg/docker/php-versions/7.0/run/php:/run/php -v /home/lovekmg/docker/php-versions/7.0/var/log:/var/log ubuntu:16.04 /bin/bash



./configure  --prefix=/usr/local/php --with-mysqli --with-gd --with-jpeg-dir --with-png-dir --with-freetype-dir --enable-ftp --enable-sockets --enable-mbstring --disable-debug --with-tsrm-pth --enable-fpm --with-curl --with-mcrypt --with-mhash --enable-soap --enable-zip --with-openssl --enable-exif --with-gettext

./configure  --with-pdo-mysql=/usr/local/mysql --with-mysqli --with-gd --with-jpeg-dir --with-png-dir --with-zlib-dir=/usr/local/zlib --with-freetype-dir --enable-ftp --enable-sockets --enable-mbstring --disable-debug --with-tsrm-pth --enable-fpm --with-curl --with-mcrypt --with-mhash --enable-soap --enable-zip --with-openssl --with-iconv-dir=/usr/local/libiconv-1.14 --enable-exif --with-gettext --enable-bcmath
```



