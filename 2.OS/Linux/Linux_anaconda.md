# Linux 에 Anaconda install

### install

```bash
# 다운로드
$ wget https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
```

```bash
#설치 스크립트 실행
$ bash Anaconda3-2020.02-Linux-x86_64.sh
# 또는
$ bash Anaconda3-2020.02-Linux-x86_64.sh -b -p /data/anaconda
```

```bash
# PATH 설정 및 재로딩(바로적용)
$ /data/anaconda/bin/conda init
$ source ~/.bashrc
# 확인
$ conda --version
```