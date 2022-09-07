# SCP

---

### ssh 통신을 통해 파일을 전송하거나 불러올때 사용

사용시 로컬에서 사용해야함.

---

Option

-   -r : 디렉토리 복사 (디렉토리 안을 읽으면서 복사)
-   -c : 압축해서 복사
-   -v : 복사과정 출력
-   -P : 포트번호 지정

---

### Local to Remote

```shell
$ scp [옵션] [보낼파일] [remoteuser]@[remoteip]:[저장위치]

# ex) scp -v /home/* root@192.168.1.1:/home/remote/
# /home/ 에 있는 모든 파일을 원격지 /home/remote/ 로 복사, 복사과정 출력

# ex) scp -rP 8080 ./origin root@192.168.1.1:/home/remote/
# 현재위치에 있는 origin 폴더 전체를 원격지 /home/remote/에 8080 포트를 이용하여 복사
```

---

### Remote to Local

```shell
$ scp [옵션] [원격지로그인ID]@[원격지 IP]:[가져올파일] [받을위치]

# ex) scp -v root@192.168.1.1:/home/remote/* /home/
# 원격지에 /home/remote/아래있는 모든 파일을 로컬 /home/로 복사, 복사과정 출력
```
