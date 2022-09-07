# SSH_setting

### Open SSH Server install

```sh
$ sudo apt update
$ sudo apt install openssh-server
```

### SSH server start

```sh
# ssh server 상태 확인
$ systemctl status ssh
```

ssh의 상태가 Active: active 가 아니라면 아래 명령어를 통해 실행

```sh
# ssh server 실행
$ sudo systemctl start ssh
# ssh server linux 시작시 자동실행
$ sudo systemctl enable ssh
```

### Client에서의 접속

ssh client가 설치되어 있지않다면

```sh
$ sudo apt-get install openssh-client
# ssh 접속
$ ssh username@ipv4_address
```
