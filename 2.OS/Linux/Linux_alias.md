# alias setting

- alias?

리눅스 환경에 자주 쓰는 명령어나 여러 옵션을 사용하는 명령어를 간단한 단축어로 사용할 수 있도록 하는 명령어

```bash
# 등록되어 있는 모든 alias 출력
$ alias

# cd .. 을 .. 만 쳐도 실행될 수 있게 설정
$ alias ..='cd ..'

# 단축어 삭제
$ unalias ..
```

---

하지만 시스템을 재부팅 할때마다 초기화되므로 매번 등록하기에는 불편
영구적으로 설정하는 방법에는 두가지가 있다.

- .bashrc

bash 환경에서는 시스템이 켜질 때마다 .bashrc 파일에 저장된 환경정보를 읽고 참고해서 bash가 실행된다.  
따라서 .bashrc 파일에 환경변수를 저장

```bash
# vim을 통해 .bashrc open
$ vim ~/.bashrc

# alias 키워드 검색
$ /alias

# i 로 입력모드로 전환 후 환경변수 추가
$ alias ..='cd ..'
```

- .bash_aliases (추천)

.bash 파일의 환경변수를 읽어보면 .bash_aliases의 파일을 참고해서 단축어를 불러옴을 알 수 있다.  
따라서 직접적인 .bashrc 파일을 수정하기보다는 .bash_aliases파일을 수정하므로 의도치않은 환경변수의 추가로인한 에러를 방지할 수 있다.

```sh
# vim을 통해 .bash_aliases open or create
$ vim .bash_aliases

# 명령어 등록
$ alias ..='cd ..'
```

둘 중 어느것으로 해도 상관없으나 시스템을 재부팅하지 않고 적용하려면
```bash
# 파일 다시읽기
$ source ~/.bashrc
```