# JPA

## :memo: Contents
- [JPA란?](#jpa란)
- [JPA 사용법](#jpa-사용법)
- [JpaRepository 구조 (상속)](#jparepository-구조-상속)
- [QueryMethod 활용](#querymethod-활용)

---

## JPA란?
- **ORM (Object Relational Mapping):**
    - 객체와 데이터베이스 사이의 관계를 연결해 주는 것
    - 우리가 정의한 객체를 사용하는 것 만으로 ORM을 통해 자연스럽게 데이터를 연결해서 사용 가능
    - ORM이 없다면 어떤 정보인지 직접 일일이 매핑 필요

- **Java Persistence API:**
    - 현재 자바 진영의 ORM 표준
    - persistence 영역, 즉 데이터에 접근하기 위한 API 규격
    - 인터페이스로 정의 (ex. EntityManager)
    > Jakarta Persistence API (2019년 이후의 JPA 명칭)

- **Hibernate:**
    - JPA에 대한 실제 구현체 (implementation)
        > Eclipse Link 등 다른 JPA Provider 존재

- **Spring Data JPA:**
	- Spring에서 Hibernate를 더 간편하게 사용할 수 있도록 추상 객체를 한번 더 감싸서 만들어 놓은 것
	- Hibernate의 자주 사용하는 기능을 다시 한 번 더 묶음으로 제공
	- EntityManager에 접근하지 않고도 데이터에 대한 접근을 좀 더 쉽고 객체지향적으로 처리 가능

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#jpa)

<br>

## JPA 사용법
- Domain
    - ```@Entity``` 어노테이션: 객체를 entity로 선언
    - 반드시 Primary Key가 필요
        - ```@Id```: PK 지정
        - ```@GeneratedValue```: 순차적으로 데이터를 증가
- Repository
    - JpaRepository 인터페이스 선언
    - ```extends JpaRepository<Entity타입, PK(Id 값)>```

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#jpa)

<br>

## JpaRepository 구조 (상속)
- PagingAndSortingRepository
    - CrudRepository (일반적으로 사용하는 대부분의 메소드 존재)
    > 메소드: save, saveAll, findById, existsById, findAll, findAllById, count, deleteById, delete, deleteAllById, deleteAll
- QueryByExampleExecutor
    > 메소드: findOne, findAll, count, exists

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#jpa)

<br>

## QueryMethod 활용
- 실제 서비스에서 사용하는 쿼리는 복잡한 where 조건을 가진다.
- 네이밍 베이스로 메소드를 선언하기만 하면 자동으로 쿼리를 생성해준다.
	- 쿼리 메소드에서는 리턴 타입을 고정해서 사용해야만 하는 것이 아니라 DB 설계상 레코드가 한 개만 존재하는지, N개가 존재하는지에 따라 개발자가 정의해 주는 대로 데이터를 리턴타입에 맞추어 반환
	- 적당한 리턴타입을 지정하면 SpringDataJpa에서 자동으로 데이터를 랩핑해서 반환
	- 편리하지만 런타임시에 오류가 날 수 있으므로 적절히 오류 처리 필요
- 간단한 만큼 기본적으로 제공하는 키워드(네이밍 규칙)가 뭐가 있는지 학습 필요
	- Query subject keyword
	> find…By / read…By / get…By / query…By / search…By / stream…By / count…By / delete…By / remove…By / First<number> / Top<number> / Distinct  
	> AND / OR / …

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#jpa)

<br>
