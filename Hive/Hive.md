# Hive

### 하이브란?

- 하이브는 SQL을 하둡에서 사용하기 위한 프로젝트로 시작 되었다.
- 페이스북에서 자사의 데이터 분석을 위해 개발하여 아파치 오픈소스 프로젝트로 오픈했다.
- 하둡에 저장되는 데이터 중 정형 데이터의 비중이 높을 수록 활용도가 높다
- 최근에는 Spark SQL을 많이 사용하지만, 큰 데이터 처리에는 여전히 유용한 엔진이다.

### 버전별 특징

Hive 1.0
- SQL을 이용한 맵리듀스 처리
- 파일 데이터의 논리적 표현
- 빅데이터의 배치 처리를 목표

Hiv 2.0
- TEZ엔진
- LLAP(Live Long and Process) rnwh cnrk
- Spark 지원 강화
- CBO(Cost Based Optimization) 강화
- HPLSQL 추가

### TEZ 엔진

- Apache Tez는 MapReduce와 동일하게 YARN 기반으로 실행되는 데이터 처리를 위한 프레임워크이다. 따라서 역시 Tez도 YARN으로부터 컨테이너를 할당받아서 작업을 수행한다.
- Tez는 Map단계에서 처리 결과를 메모리에 저장하고, 이를 Reduce 단계로 바로 전달한다. 그리고 이렇게 결과를 전달받은 Reduce는 Map단계를 다시 거치지 않고 바로 다음 Reduce 단계로 전달하여 IO 오버헤드를 줄여서 속도를 향상을 볼 수 있다.