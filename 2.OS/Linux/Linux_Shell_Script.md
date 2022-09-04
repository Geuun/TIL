# Linux Shell Script

### 쉘 스크립트란?

- **.sh** 확장자 파일에 스크립트를 작성하여 쉘에게 어떤 명령을 할지 알려주는 것
- 반복을 줄이기 위함

---

하둡 하이브 실습하면서 경로로 들어가서 실행하기 귀찮기도 하고 배운거 한 번 리마인드 하자는 생각으로
얼마전 배운 쉘 스크립트를 간단하게 이용(?)해서 홈 디렉토리에 있는 파일 실행으로 간단하게 켜고 끄게 해보았다.

hadoop_start_all 의 경우

```bash
# 파일 생성
$ touch hadoop_start_all.sh
```

```bash
# 생성한 파일에 권한 부여
$ chmod 755 hadoop_start_all.sh
```

```bash
# 쉘 스크립트 작성
$ vi ./hadoop_start_all.sh
```

```bash
# 아래 내용 작성 후 저장

#!/bin/bash
cd $HADOOP_HOME/sbin && ./start-all.sh
```

```bash
# 확인
$ cat ./hadoop_start_all.sh
 
#!/bin/bash
cd $HADOOP_HOME/sbin && ./start-all.sh
```

```bash
$ ./hadoop_start_all.sh

WARNING: Attempting to start all Apache Hadoop daemons as ubuntu in 10 seconds.
WARNING: This is not a recommended production deployment configuration.
WARNING: Use CTRL-C to abort.
```