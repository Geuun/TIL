### WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! 

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

sol)  
예전 IP로 인증했던 정보를 가지고 새로운 IP에서 로그인 하려고 해서 생기는 오류

```bash
$ ssh-keygen -R [ IP or DomainName]

# ex) ssh-keygen -R 127.0.0.1
```