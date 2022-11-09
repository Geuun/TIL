# What is JPA...?

-   JPA란 Java Persistence API의 약어로 Java ORM 기술에 대한 표준 명세이다.
-   조금 풀어말하면 Java Application에서 관계형 데이터베이스(RDB)를 사용하는 방식을 정의한 **인터페이스**이다.
    -   JPA는 말 그대로 인터페이스일 뿐 라이브러리가 아니다.
    -   왜냐하면 Java는 객체지향 언어이기 때문에 POJO(Plane Old Java Object)를 따르기 위해서 스프링의 PSA(Portable Service Abstraction)에 의해 표준 인터페이스를 정의했는데, 그 중 ORM을 사용하기 위해 만든 인터페이스가 JPA이다. (POJO에 대해서는 추가로 작성해 둘 필요가 있어보인다.)

# ORM 그게 먼대... 왜 쓰는건데...

-   내가 현재 배운 Java로 DB를 조작할 수 있는 종류가 크게 두 가지가 있다.

    1. SQL Mapper
    2. ORM (Object - Relation Mapping)

-   이 두가지의 차이점에 대해 알아보고 언제 어떤게 필요한지에 대해 알아두자.

## 만약 둘다 없었다면...?

![4a2d87de1951](https://user-images.githubusercontent.com/89567475/200341516-7c375e3f-b83b-47d1-9646-c81e5da3fa2e.jpg)

## SQL Mapper

-   SQL <- `Mapping` -> Object
-   SQL문에 Object필드를 매핑해서 SQL query문으로 직접 DataBase를 조작할 수 있다.
-   SQL query문을 Mapping하기 때문에 보다 세세한 설정이 가능하다.
-   ex) jdbcTemplate, _Mybatis_

### JDBC

![jdbc-datalayer](https://user-images.githubusercontent.com/89567475/200344922-8f264b79-b72a-45ce-bfd0-0c6f1240382b.png)

-   JDBC는 Java에서 DataBase에 접근할 때 기본적으로 제공하는 API이다.
-   따라서 모든 Java Data Access Persistance Framework들은 내부적으로 JDBC를 기반으로 이루어진다.

## ORM (Object - Relation Mapping)

-   DataBase Table <- `Mapping` -> Object
    -   객체를 통해서 간접적으로 DataBase를 다룰 수 있다.
    -   객체와 DataBase 데이터를 자동으로 매핑해준다.
    -   객체간 관계를 바탕으로 SQL문을 자동으로 생성한다.
    -   ex) JPA, Hibernate

> 자 SQL Mapper 방식과 ORM 방식의 차이점에 대해 알았고 JPA가 뭔지도 대충 알았으니  
> 이제 JPA라는 ORM이 DataBase랑 통신하는 방식에 대해 조금 알아보자.

### JPA는 단순 기술 명세이다.

-   앞서 맨 처음에 JPA에 대해 설명할 때 인터페이스라고 설명했듯이 JPA는 단순 기술 명세이기 때문에 특정 기능을 하는 라이브러리가 아니다.
-   **따라서 구현체가 없기 때문에 직접적으로 특정 기능을 하지는 않는다.**

### 그럼 JPA는 어떻게 사용하는건데??

-   개발을 직접해보거나 관련 문서들을 접하다보면 Hibernate라는 단어를 Console에서 직 간접적으로 본적이 있을 것이다.

-   이 Hibernate가 JPA의 구현체로써 JPA 인터페이스들을 직접 구현한 라이브러리이다.

-   따라서 JPA와 Hibernate는 자바의 interface와 해당 interface를 구현한 Class와 같은 관계라고 생각하면 된다.

-   Hibernate는 JPA의 구현체 중 하나이기 때문에 Hibernate의 사용이 강제되지 않는다. 따라서 다른 구현체를 사용해도 좋고 직접 구현체를 만들어서 사용해도 된다. 하지만 사람들이 그렇게 하지 않는 이유는 잘 만들어진 구현체이기 때문일 것이다.

### 그럼 JPA가 아니라 Hibernate를 사용한다 말해야 하는거아님?

<img width="500" alt="jpa-layer" src="https://user-images.githubusercontent.com/89567475/200828744-4568cf06-0619-497b-a820-e8900640397f.png")

-   멀리멀리 돌아 이제 진짜 우리가 다룰 **Spring Data JPA**에 대해 얘기할 단계이다..!

-   Spring Data JPA는 Spring에서 제공하는 모듈 중 하나인데, 개발자가 JPA를 조금 더 편하게 사용할 수 있게 도와준다.
-   이는 JPA를 한 단계 더 추상화시킨 `Repository` 라는 인터페이스를 제공함으로써 이루어지는데,
    `Repository` 인터페이스에 정해진 규칙대로 메소드만 입력하면 Spring에서 알아서 내부적으로 해당 메소드에 적합한 쿼리를
    DataBase에 날리는 구현체를 만들어서 Bean으로 등록해준다. (진짜 짱인거같다.)
-   따라서 JPA를 사용한다 함은 위 첨부된 이미지의 과정을 거쳐서 DataBase와 소통하는 과정을 말한다.
