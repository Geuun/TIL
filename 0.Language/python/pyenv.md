# Pyenv

### pyenv

- python 버전관리 모듈
- pyenv 로 여러버전의 python을 사용 가능
- 추가로 venv로 가상환경구성 가능

### pyenv setting

```zsh
$ brew install pyenv
```

```zsh
# 환경 변수 추가 (zsh 환경)
$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc

$ source ~/.zshrc
```

```zsh
# 설치가능한 python 버전확인
$ pyenv install --list

# pyenv 를 이용해 python 설치
$ pyenv install 3.9.4

# pyenv에서 관리하고 있는 python버전 목록 확인
$ pyenv versions

# pyenv 를 이용한 특정 버전 활성화
$ pyenv global 3.9.4
```
