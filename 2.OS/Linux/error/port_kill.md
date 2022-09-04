# 특정 Port kill

express를 이용해 개발 중 5000번 포트가 사용이 안됨

```shell
# 5000 번 포트를 어떤게 사용하고 있는지 확인
$ sudo lsof -i :5000

> COMMAND
- ControlCe
- ControlCe
```

ControlCe : 맥 Airplay 수신 모드

다른 포트를 이용하도록 하자..