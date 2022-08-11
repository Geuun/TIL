# Linux 기초

## SSH 접속

- 첫 접속 : `$ ssh -i /{Keyfile_path}/{Keyfile_name.pem} ubuntu@IPv4`
- 이후 접속 : `ssh username@IPv4`


---

## 명령어 정보

### date

- `$ date`

현재 시간 확인 가능  
처음 설정은 UST or PST 이므로 변경이 필요하므로 변경  
`$ls -al /usr/share/zoneinfo/Asia` 명령어를 통해 Seoul 위치확인
심볼릭 링크를 통해 시간 변경 가능
`sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime`


---

## DataBase

### mysql

install : `sudo apt install mysql-server`
2가지 방법으로 mysql-server 접속가능
1. 관리자 모드 (설정 초기)
2. 사용자 모드 (DB User 원격 IP주소)