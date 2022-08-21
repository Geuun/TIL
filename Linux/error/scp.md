# scp permission denied

```bash
$ scp -P 8080 로컬파일경로 유저명@ip주소:리모트파일경로

> Permission denied, please try again.
```

포트 설정 및 권한설정이 제대로 되었음에도 scp 가 안됐으나  
아래와 같이 디렉토리에 파일명까지 명시해주니 해결

```bash
$ scp -P 8080 로컬파일경로 유저명@ip주소:리모트파일경로및파일명
```
