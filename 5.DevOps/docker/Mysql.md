# Docker 에 mysql 서버 설치하고 접속하기

## Docker 설치

-   docker 공식 홈페이지에서 OS와 환경에 맞는 Docker Desktop을 설치
-   `linux` 는 CLI로 설치 가능
-   설치했다면 터미널에서 아래의 명령어를 입력해서 잘 설치됬는지 확인

```bash
$ docker -v

>> Docker version 20.10.18, build b40c2f6
```

## Mysql Image 다운로드(pull)하기

```bash
$ docker pull mysql

>>>
ubuntu@ip-172-31-20-85:~$ sudo docker pull mysql
Using default tag: latest
latest: Pulling from library/mysql
Digest: sha256:3c1aab708f6e57fc4dccafe36baccc7219acfb4ec450f3fb6d370ea89409e906
Status: Image is up to date for mysql:latest
docker.io/library/mysql:latest
```

-   잘 설치 되었는지 확인해보자.

```bash
$ docker images

>>>
ubuntu@ip-172-31-20-85:~/dev$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED      SIZE
mysql        latest    dbaea59d1b41   2 days ago   449MB
nginx        latest    51086ed63d8c   5 days ago   142MB
```

## 다운받은 Image로 Container 생성하기

```bash
$ docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=`password` -d -p 3306:3306 mysql

>>
7328534e871756be5a3bad46782ff545b42e43960236ecac94915452a25aff63
```

> -   명령어 설명  
>     `--name` : 생성할 컨테이너의 이름  
>     `-e` : 환경 변수 (Password) 설정  
>     `-d` : daemon 모드로 실행 (백그라운드에서 실행)  
>     `-p` : 포트 설정 (외부포트 : Docker 내부포트)

-   잘 생성이 되었는지 확인해보자

```bash
$ docker ps - a

>>>
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                   PORTS                                                  NAMES
7328534e8717   mysql     "docker-entrypoint.s…"   22 minutes ago   Up 22 minutes            0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   mysql-container
1752aa3678ea   nginx     "/docker-entrypoint.…"   2 hours ago      Exited (0) 2 hours ago                                                          elegant_bardeen
```

-   `docker ps -a` 명령어를 통해 모든 container를 볼 수 있다.
-   `-a` 를 제외하면 현재 실행 중인 컨테이너만 확인 가능하다.

## Container 중지 및 시작

```bash
# 컨테이터 중지
$ docker stop mysql-container
$ docker stop `container ID`
```

```bash
# 컨테이너 시작
$ docker start mysql-container
$ docker start `container ID`
```

## Container에 접속하기

-   실행 중인 Container에 접속해서 Mysql을 조작 가능하다.

```bash
$ docker exec -it mysql-container bash
```

-   `-it` : Interactive Terminal Mode

## 관리자 모드로 Mysql 접속하기

```bash
$ mysql -u root -p

>>>
Enter password: (본인의 패스워드 입력)

>>>
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.30 MySQL Community Server - GPL

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```
