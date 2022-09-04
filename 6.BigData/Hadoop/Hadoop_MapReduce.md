# Hadoop MapReduce

### 맵리듀스란 무엇인가?

- 2004년 구글에서 발표한 Large Cluster에서 Data Processing을 하기 위한 알고리즘
- Hadoop MapReduce는 구글 알고리즘 논문을 소프트웨어 프레임워크로 구현한 구현체
- **Key-Value 구조가 핵심**

### 맵리듀스 알고리즘 구성

- Map Function : (ket1, value1) -> (key2, value2)
- Reduce Function : (key2, List of value2) -> (key3, value3)
  - HDFS에 분산 저장되어 있는 데이터를 병렬로 처리하여 취합
  - job에 대한 구동 및 관리는 Hadoop이 알아서함

### 맵리듀스 장점/단점

- 장점
  - 알고리즘이 단순하고 사용이 편리
  - 특정 데이터모델이나 스키마, 질의에 의존적이지 않은 유연성
  - 데이터 복제에 기반한 내구성과 재수행을 통한 내고장성 확보
  - 개발자는 비즈니스 로직에 집중할 수 있음

- 단점
  - 고정된 단일 데이터 흐름
  - 기존 DBMS보다 불편한 스키마 질의
  - 단순한 스케줄링
  - 작은 데이터에는 적합하지 않음
  - 개발도구 불편
  - 오픈소스이므로 기술지원의 어려움 (기업입장)

### 맵리듀스(MapReduce) 구동방식

- Local : 단일 JVM에서 전체 Job 실행
- Classic : Hadoop 1.0의 분산 처리방식으로 Job Tracker와 Task Tracker를 사용하는 MapReduce 버전
- YARN (Yet Another Resource Negotiator) : Hadoop 2.0버전 이상에서 사용하는 분산 처리방식으로 MapReduce 이외의 워크로드 수용이 가능한 버전
