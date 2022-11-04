![docker](https://user-images.githubusercontent.com/89567475/199637693-4ba5d19f-dce0-4cbf-b898-9338900cc48e.png)

# 도커란 무엇인가?

-   컨테이너 기반의 오픈소스 가상화 플랫폼으로 컨테이너를 관리주는 프로그램

> 그게 뭔데 씹덕아.. 라고 할 수 있는데, 쉽게 풀어서 얘기하면 가상 환경에서 구성되어 각종 환경변수에 영향을 받지 않고 다양한 프로그램의 배포 및 관리를 단순하게 해주는 녀석이다.  
> Docker를 사용하므로써 백엔드 프로그램, DB서버 등 어떤 프로그램도 컨테이너로 추상화할 수 있고 window, macOS, Linux, Cloud(AWS, GCP, Azure) 등 docker와 프로그램이 동작할 최소한의 컴퓨팅 파워가 받쳐준다면 어떤 환경에서도 실행할 수 있다.

## 가상머신(VMware, VirtualBox) 랑 다른게 머임? 가상환경이면 같은거 아냐?

![스크린샷 2022-11-03 오후 2 31 21](https://user-images.githubusercontent.com/89567475/199653474-98cdf91e-bbe7-4b10-aaca-fb7c94bafde3.png)

가상머신과 같은 기존 가상화 방식들은 OS를 가상화해서 최상위 호스트 OS 위에
게스트 OS 전체를 가상화 해서 사용하는 방식이다.  
(예를들면 VirturalBox를 이용해 Linux를 가상화해서 호스트OS인 Windows 위에 Linux를 얹는 방식)  
하지만 기존의 가상화 방식은 OS전체를 가상화 한다는 장점과 동시에 무거워지고 느려지는 단점이 생긴다. 따라서 서버 단위의 운영환경에서는 사용하기 힘들다.

Docker를 조금 더 이해하기 위해서는 아래의 3가지 개념의 이해가 필요하다.

### Image, Doker Engine, Container

1. Image

-   image는 Docker 가상환경에 대한 설정과 설정해야할 Dependencis와 수행할 작업과 해당 프로젝트의 스냅 샷을 찍어 버전을 만들어 놓은 것이다. `docker build` 명령어를 통해 생성할 수 있다.

2. Docker Engine

-   Docker Engine은 Container를 생성하고 그 안에 Image를 담아서 실행한다.

3. Container

-   Container는 철저하게 구분된 가상환경에서 Docker Engine을 통해 실행되기 때문에 Host OS환경과는 무관하게 어떤 환경에서도 동일한 환경을 제공하는게 특징이다.
-   Container는 삭제되면 데이터는 사라진다. 따라서 Docker Volume을 적용해 저장해두어야 할 필요가 있다.

### Docker를 활용하면 어떤걸 할 수 있을까

> 그냥 내 로컬에서 환경 세팅해주듯이 서버 환경에서도 똑같이 세팅해주면 되는거 아냐?

-   위처럼 생각할수도 있을것 같다. 하지만 모든 서버는 개발환경과 전혀 다른 환경에서 빌드되고 배포된다. 서비스를 안정적으로 빌드하고 배포하기 위해서는 이 모든 변수를 제거해줄 필요가 있다.
-   또한 Docker를 사용하면 수행하고자 하는 작업과 서비스에 필요한 dependencies들을 미리 Dockerfile에 기록해 Image를 빌드하게된다. 그리고 빌드된 Image를 DockerHub에 올려두고 서버환경에서 해당 Image를 이용해 Container를 만들어 구동하면 Host에게 dependencies들이 없더라도 있는 것 처럼 동작할 수 있다.
-   위와 같은 이유와 더불어 Docker가 가지고 있는 장점을 활용해서 서버단위의 운영체제에서 많이 사용되는 것이다.
