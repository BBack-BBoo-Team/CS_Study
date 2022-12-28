# 스프링

### 목차

[1. 스프링이란](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%8A%A4%ED%94%84%EB%A7%81/README.md#1-%EC%8A%A4%ED%94%84%EB%A7%81%EC%9D%B4%EB%9E%80) <br>
[2. ORM](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%8A%A4%ED%94%84%EB%A7%81/README.md#2-orm)<br>
[3. JPA](https://github.com/BBack-BBoo-Team/CS_Study/edit/master/%EC%9D%B4%EB%A1%A0%EC%A0%95%EB%A6%AC/%EC%8A%A4%ED%94%84%EB%A7%81/README.md#3-jpa)<br>

---

## 1. 스프링이란?
* 객체를 관리할 수 있는 컨테이너를 제공하는 자바 기반 프레임워크
* 순수 자바로 사용 가능

### 1-1. 특징
* 중복 코드의 사용률 감소
* 오픈소스를 좀더 효율적으로 사용할 수 있는 구조
* Java를 이용한 기술들을 쉽게 사용할 수 있게 도움
* 특정 기술에 종속되지 않음

### 1-2. 4가지의 주요 특징
* IoC(Inversion of Control, 제어반전)
  * 인스턴스(객체)의 생성부터 소멸까지 객체 생명주기 관리를 컨테이너(스프링)가 대신 해주는 것
  * 본래 Java 개발자는 new 연산자, 인터페이스 호출, 데이터 클래스 호출 방식으로 직접 객체를 생성하고 소멸시킴
* DI(Dependency Injection, 의존성 주입)
  * 컨테이너가 의존 관계를 자동으로 연결
  * 구성요소 간의 의존 관계가 소스코드 내부가 아닌 외부의 설정파일을 통해 정의되느 방식
  * 코드 재사용율 항셩, 모듈간의 결합도 감소
* AOP(Aspect Object Programming, 관점 지향 프로그래밍)
  * 로깅, 트랜잭션, 보안 등 여러 모듈에서 공통적으로 사용하는 기능을 분리하여 관리
  * 여러 객체에 공통으로 적용할 수 있는 기능을 구분함으로써 재사용성을 높여주는 프로그래밍 기법
* POJO(Plain Old Java Object)
  * 객체 지향적인 원리에 충실하면서 환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 오브젝트

<br>
  
## 2. ORM
* Object Relational Mapping
* 관계형 데이터베이스를 OOP언어로 변환해주는 기술
* 객체와 테이블 매핑
  
> RDBMS : 관계형 데이터베이스

<br>

## 3. JPA
* ORM을 위해 자바에서 제공하는 API
* 인터페이스
* JPA를 구현한 대표적인 오픈소스는 Hibernate

> Q. ORM, JPA, Hibernate 장.단점은 무엇인가요? <br> A. 비즈니스 로직에 집중하고, 객체중심의 개발을 할 수 있게 됩니다. <br> 그리고 메서드를 호출하는 것만으로 쿼리를 수행해서 생산성이 향상되고 유지보수 비용이 감소합니다. <br> 그리고 특정 데이터베이스에 의존하지 않습니다. <br> 하지만 단점으로는 직접 SQL을 호출하는것보다 느리고, 복잡한 쿼리같은 것은 메소드로 처리가 힘들다는 단점이 있습니다.
 
