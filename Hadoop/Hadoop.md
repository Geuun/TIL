# Hadoop & Hive

---

### Glossary ( 용어사전)

Distribute File System (분산파일 시스템)

- 네트워크를 통해 주변에 있는 스토리지를 관리하는 파일 시스템
- 네트워크 기반이 때문에 네트워크 프로그래밍의 모든 복잡성이 포함됨

Hadoop

- 파일 시스템의 병렬처리 프레임워크에서 실행되는 플랫폼
- 데이터가 로드되기 전에 스키마를 노출할 필요가 없다

HDFS

- 블록 파일 시스템이나 디스크 블록을 생각하면 되지만 그보단 훨씬 더 큰 시스템이다.
- 기본 블록의 크기는 파일시스템 (KB단위) 또는 디스크 블록 (512B) 보다 큰 128MB이다.
- 파일 시스템 블록과 마찬가지로 블록 덩어리로 분할되어 독립적인 단위로 저장된다.

Namenode

- 메타데이터(디렉토리 구조)의 스냅샷을 유지하고 클러스터에서 위치를 추적
- HDFS 내의 모든 파일에 대한 블록과 해당 위치를 리스트함
- Namenode를 마스터라 부르고 이는 Hadoop 클러스터에서 single point of failure이다.

Datanode

- 모든 데이터를 HDFS에 저장
- Namenode에 저장된 블록 목록과 아직 살아 있음을 알리는 것이 유일한 임무 따라서 Slave라고 부름
- 다운되면 Datanode는 다운되고 마스터는 Datanode의 내용을 다른서버에 복제한다.

YARN

- Hadoop 2.0의 핵심기능
- 클러스터 리소스를 요청하고 작업하기 위한 API를 제공하지만, 사용자 코드에서 직접 사용하지 않는다.
→ 다시 말해서 사용자가 YARN 기반으로 하는 API에 작성하고 리소스 처리 세부 정보를 사용자에게 숨겨야한다.

Resource Manager

- 클러스터 애플리케이션 작업 예약 및 리소스 모니터링을 담당

Node Manager

- 컨테이너와 해당 리소스 사용량(cpu, 메모리, 디스크)을 시작 및 모니터링하고 Resource Manager에게 다시 보고하는 역할

Container

- 특정 리소스가 할당된 응용 프로그램 특정 프로그램을 실행하는 역할

MapReduce(MR)

- 구글에서 도입한 데이터 처리 알고리즘
- 클러스터 환경에서 대용량 데이터를 병렬으로 처리하는데 매우 효과적이다.

MR과 Spart의 차이점

- MR은 영구 저장소를 사용하지만 Spark는 메모리에서 RDD를 사용한다.