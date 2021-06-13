# Effective Java

### :paperclip: Contents

2. [객체 생성과 파괴](#2장-객체-생성과-파괴)
3. [모든 객체의 공통 메서드](#3장-모든-객체의-공통-메서드)
4. [클래스와 인터페이스](#4장-클래스와-인터페이스)
5. [제네릭](#5장-제네릭)
6. [열거 타입과 애너테이션](#6장-열거-타입과-애너테이션)
7. [람다와 스트림](#7장-람다와-스트림)
8. [메서드](#8장-메서드)
9. [일반적인 프로그래밍 원칙](#9장-일반적인-프로그래밍-원칙)
10. [예외](#10장-예외)
11. [동시성](#11장-동시성)
12. [직렬화](#12장-직렬화)

---

## 2장 객체 생성과 파괴

### Item 1 - "생성자 대신 정적 팩토리 메서드를 고려하라"

**Static Factory Method**
생성자와는 별도로 해당 클래스의 인스턴스를 반환  
ex)
```java
public static Boolean valueOf(boolean b) {
    return b ? Boolean.TRUE : Boolean.FALSE;
}
```

- 정적 팩토리 메서드가 생성자 보다 좋은 점
    1. **이름을 가질 수 있다.**
        - 반환될 객체의 특성을 쉽게 묘사할 수 있다.
        - ex) 
            ```java
            BigInteger.probablePrime  // 값이 소수인 BigInteger 반환
            ```
    2. **호출될 때마다 인스턴스를 새로 생성하지 않아도 된다.**
        - 인스턴스를 미리 생성, 재활용 함으로 불필요한 객체 생성 방지
    3. **반환 타입의 하위 타입 객체를 반환할 수 있는 능력이 있다.**
        - 인터페이스 구현 클래스의 인스턴스를 public으로 공개하지 않고도 그 객체를 반환할 수 있어 API를 작게 유지 가능
        - 클라이언트가 API를 사용하기 위해 익혀야 하는 개념적인 무게도 낮춤
        - 인터페이스 기반 프레임워크를 만드는 핵심 기술
        - ex) `java.util.Collections`
        - 팩토리를 사용하는 코드가 구현체가 아닌 인터페이스 타입으로 코딩 가능
        > - **Java 8** 부터 인터페이스는 **public static method** 를 가질 수 있다.  
        > - **Java 9** 부터는 **private static method** 가능 But, 정적 필드와 정적 멤버 클래스는 여전히 public
    4. **입력 매개변수에 따라 매번 다른 클래스의 객체를 반환할 수 있다.**
        - 3번의 연장선
        - 클라이언트는 팩토리가 건네주는 객체가 어느 클래스의 인스턴스인지 알 수 없고 알 필요도 없음
        - JDK의 변화나 릴리즈가 달라져 새로운 타입을 만들거나 없애도 문제가 되지 않음
        - ex) `EnumSet`클래스는 public 생성자 없이 정적 팩토리만 제공. 원소의 수에 따라 `RegularEnumSet` 또는 `JumboEnumSet` 인스턴스 반환
    5. **정적 팩토리 메서드를 작성하는 시점에는 반환할 객체의 클래스가 존재하지 않아도 된다.**
        - 3번 부터 연장되는 '유연함'에 대한 설명
        - **Service Provider Framework** 을 만드는 근간
        - 제공자는 서비스의 구현체. 이 구현체들을 클라이언트에 제공하는 역할을 프레임웍이 통제하여, 클라이언트를 구현체로부터 분리
        - 서비스 제공자 프레임 워크의 핵심 컴포넌트:
            - 

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 3장 모든 객체의 공통 메서드

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 4장 클래스와 인터페이스

### item 15 - "클래스와 멤버의 접근 권한을 최소화하라"

- 잘 설계된 컴포넌트의 특징: **정보은닉 & 캡슐화**
    - 클래스 내부 데이터와 내부 구현 정보를 외부 컴포넌트부터 잘 숨김
    - API를 통해서만 다른 컴포넌트와 소통. 내부 동작 방식에 개의치 않음.
- public 클래스의 인스턴스 필드는 되도록 public이 아니어야 한다.
    - 꼭 필요한 최소한의 공개 API만 public으로 선언
    - protected 멤버는 공개 API 임
    - 테스트만을 위해 클래스, 인터페이스, 멤버를 공개 API로 만들어서는 안된다.
    - 가변적인 public 인스턴스는 일반적으로 thread-safe 하지 않다.
        - 예외: 상수(public static final) - 반드시 기본 타입이나 불변 객체 참조
            > ex) public static final 배열은 변경 가능하므로 주의
- 정보 은닉의 장점:
    1. 시스템 개발 속도를 높인다
    2. 시스템 관리 비용을 낮춘다.
    3. 성능 최적화에 도움
    4. 소프트웨어 재사용성을 높인다.
    5. 큰 시스템을 제작하는 난이도를 낮춘다.

<br/>



<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 5장 제네릭

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 6장 열거 타입과 애너테이션

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 7장 람다와 스트림

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 8장 메서드

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 9장 일반적인 프로그래밍 원칙

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 10장 예외

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 11장 동시성

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>

## 12장 직렬화

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#Effective-Java)  

<br/><br/>
