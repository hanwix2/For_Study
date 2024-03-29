# God Of Java - Book1

### :paperclip: Contents
1. [프로그래밍이란 무엇인가?](#1장-프로그래밍이란-무엇인가)
2. [Hello God Of Java](#2장-hello-god-of-java)
3. [자바를 제대로 알려면 객체가 무엇인지를 알아야 해요](#3장-자바를-제대로-알려면-객체가-무엇인지를-알아야-해요)
4. [정보를 어디에 넣고 싶은데](#4장-정보를-어디에-넣고-싶은데)
5. [계산을 하고 싶어요](#5장-계산을-하고-싶어요)
6. [제가 조건을 좀 따져요](#5장-제가-조건을-좀-따져요)
7. [여러 데이터를 하나에 넣을 수는 없을까요?](#7장-여러-데이터를-하나에-넣을-수는-없을까요)
8. [참조 자료형에 대해서 더 자세히 알아봅시다](#8장-참조-자료형에-대해서-더-자세히-알아봅시다)
9. [자바를 배우면 패키지와 접근 제어자는 꼭 알아야 해요](#9장-자바를-배우면-패키지와-접근-제어자는-꼭-알아야-해요)
10. [자바는 상속이라는 것이 있어요](#10장-자바는-상속이라는-것이-있어요)
11. [매번 만들기 귀찮은데 누가 만들어 놓은 거 쓸 수 없나요?](#11장-매번-만들기-귀찮은데-누가-만들어-놓은-거-쓸-수-없나요)
12. [모든 클래스의 부모 클래스는 Object에요](#12장-모든-클래스의-부모-클래스는-object에요)
13. [인터페이스와 추상 클래스, enum](#13장-인터페이스와-추상-클래스-enum)
14. [다 배운 것 같지만, 예외라는 중요한 것이 있어요](#14장-다-배운-것-같지만-예외라는-중요한-것이-있어요)
15. [String](#15장-string)
16. [클래스 안에 클래스가 들어갈 수도 있구나](#16장-클래스-안에-클래스가-들어갈-수도-있구나)
17. [어노테이션이라는 것도 알아야 한다](#17장-어노테이션이라는-것도-알아야-한다)
18. [이제 기본 문법은 거의 다 배웠으니 정리해 봅시다](#18장-이제-기본-문법은-거의-다-배웠으니-정리해-봅시다)

---

## 1장 프로그래밍이란 무엇인가?

* 프로그래밍: 어떠한 작업을 반복적으로 수행하면서 특정 기능을 만들어 내는 것
* 메소드(method): 어떤 값을 주고 결과를 넘겨주는 것

* **클래스(Class)**
    - 자바의 가장 작은 단위
    - 메소드는 클래스 안에 포함되어야 한다.
    - 클래스는 상태(state; 변수)와 행동(behavior; 메소드)이 있다.

* ‘프로그래밍의 기본은 = 를 이해하는 것’ – 수학과 달리 왼쪽에 대입할 변수를, 오른쪽에 계산식을 적는다.

* 자바 코드의 한 줄이 끝날 때에는 세미콜론(;) 명시한다. 
* 자바는 인덴트(indent, 코드 앞의 공백)가 중요하지 않지만 지켜주는 것이 예의.

* 예약어: public, class, int, return 등 이미 예약된 단어로, 클래스, 메소드, 변수의 이름으로 사용할 수 없다.

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 2장 Hello God Of Java

* **컴파일(Compile)**
    * 자바 컴파일 및 실행 절차: (소스; .java 파일)-> 컴파일러(javac) -(바이트 코드; .class 파일)-> 디스크 -(바이트 코드; .class 파일)-> JVM -(기계어)-> 운영체제(실행)
    * 대부분의 프로그래밍 언어는 텍스트로 된 파일을 실행할 수 없다. 내가 만든 프로그램 코드를 컴퓨터가 이해할 수 있도록 엮어주는 작업이 컴파일이다.

* **주석 처리**
    - //: 한 줄 주석
    - /* */: 블록 주석
    - /** */: 문서용 주석

* **메소드 구성**
    a. 제어자
    b. 리턴 타입
    c. 메소드 이름
    d. 매개 변수 목록
    e. 예외 목록
    f. 메소드 내용

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
 
## 3장 자바를 제대로 알려면 객체가 무엇인지를 알아야 해요

* 클래스(class) = 상태(state) + 행위(behavior)

* **객체(object)**: 실제 사물을 나타내기 위한 것. 인스턴스(instance)라고도 한다.
* **생성자(constructor)**: 객체를 생성하기 위한 도구. 매개변수가 없는 생성자는 만들지 않아도 된다.

* 클래스 자체만으로 일을 할 수 없고, 객체를 생성해야만 일을 할 수 있다. 

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
 
## 4장 정보를 어디에 넣고 싶은데

* **변수(variable)**: 내용을 담아 두는 곳. 이름 지정 필요.

* **변수의 종류**
    1. **지역 변수(local variable)**
        * 중괄호 내에서 선언된 변수.
        * 지역 변수를 선언한 중괄호 내에서만 유효.
    2. **매개 변수(parameters)**
        * 메소드에 넘겨주는 변수. 
        * 메소드가 호출될 때 생명이 시작되고, 메소드가 끝나면 소멸.
    3. **인스턴스 변수(instance variable)**
        * 메소드 밖, 클래스 안에 선언된 변수. (static 제외) 
        * 객체가 생성될 때 생명이 시작, 그 객체를 참조하는 다른 객체가 없으면 소멸.
    4. **클래스 변수(class variable)**
        * 인스턴스 변수처럼 클래스 안에 선언되었지만, static인 변수.
        * 클래스가 처음 호출될 때 생명이 시작, 자바 프로그램이 끝날 때 소멸.

* **변수 이름 규칙**
    * 길이 제한 없음
    * 첫 문자는 유니코드, 알파벳, ‘$’, ‘_’ 만 올 수 있다. 하지만 보통 ‘$’, ‘_’로 시작하지 않는다.
    * 두번째부터는 유니코드, 알파벳, 숫자, ‘$’, ‘_’ 중 아무거나 가능
    * 첫 문자는 소문자로 시작하는 단어, 두번째 단어의 첫 문자만 대문자
    * 상수(constant value)의 경우는 모두 대문자, 단어와 단어 사이는 ‘_‘로 구분
    * 상수가 아닌 일반적인 변수는 ‘_’로 구분하는 것 자제

* 자바의 자료형
    1. **기본 자료형(primitive data type)**: 총 8개. 초기화할 때 바로 값을 적어준다.
        * 정수형: byte, short, int, long, char
        * 소수형: float, double
        * 기타: boolean
    2. **참조 자료형(reference data type)**: 초기화할 때 new 예약어로 생성한다. (String은 예외)

* 각 타입이 나타낼 수 있는 숫자의 범위
    * byte: -27 ~ 27 – 1 
    * short: -215 ~ 215 – 1 
    * int: -231 ~ 231 – 1 
    * long: -263 ~ 263 – 1 

* 8비트와 byte 타입
    * byte = 부호가 있는(signed) 8bits
    * 맨 앞 비트는 부호, 나머지는 값.
    * 따라서 byte의 최대값은 28이 아닌 27 – 1 = 127
    * 하지만 맨 앞이 1이고 나머지가 0인 경우는 값이 0이 아니라 최소값 (byte에서는 -27 = -128)

* long의 경우 선언할 때 ‘L’을 붙여 주어야 한다. (if not, int로 인식)

* 소수점 처리
    * float: 32bits. 부호(1) + 지수(8) + 가수(23)
    * double: 64bits. 부호(1) + 지수(11) + 가수(52)

*돈 계산 같은 중요한 계산은 float나 double을 사용하면 안된다. 32 or 64비트가 제공하는 범위를 넘어서면 값의 정확성을 보장하지 못하기 때문. -> java.util.BigDecimal 클래스 사용!*


* char: 기본적으로 정수형 타입. 숫자와 문자가 매칭되어 있다. (ASCII, Unicode) / *범위: 0(\u0000) ~ 65,535(\uffff)*

* 기본 자료형의 기본값(default)
    * 자바의 모든 자료형은 값을 지정하지 않으면 기본값을 사용. 
    * 하지만 지역 변수로 기본 자료형을 사용하는 경우 기본값이 자동으로 적용되지 않는다. 
    * 기본값을 할당하는 버릇을 가지자! (간혹 기본값을 할당하지 않는 경우도 있음)

    * boolean의 기본값 = false
    
> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 5장 계산을 하고 싶어요

* **연산자(operator)**: +, -, *, /, %
* **복합 대입 연산자(compound Assignment Operator)**: +=, -=, *=, /=, %=
* **단항 연산자**: +, -, ++, --, !
* **비교 연산자**: ==, !=, >, >=, <, <=
* **논리 연산자**: &&, ||
* **삼항 연산자(conditional operator)**: [변수] = (boolean 조건식) ? [true일 때 값] : [false일 때 값] 

* **형 변환(casting)**
    * 범위가 큰 타입으로 변환(casting 연산 필요 없음) 시 문제가 없지만, 
    * 범위가 작은 타입으로 변환(casting 연산 필요)하면 예상 못한 값이 나올 수 있다.

    * 형 변환 불가능한 경우: boolean / 기본 자료형 ↔ 참조 자료형

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
 
## 6장 제가 조건을 좀 따져요

* **if**
    > if( 조건1 ) { 처리문장1; }
    > else if( 조건2 ) { 처리문장2; }
    > else { 처리문장3 }

    * 대입하는 조건일 때 
        > (조건) ? (true일 때 값) : (false일 때 값)

* **switch**
    > switch(비교대상변수) {
    > case 점검값1:
    > 	처리문장1;
    >	break;
    > case 점검값2:
    >	처리문장2;
    >	break;
    > default:
    >	처리문장3;
    >	break;
    > }

* 반복문
    * **while**
        > while (조건) {
        >  처리문장;
        > }  

    * break: 현재 중괄호에서 빠져나간다. (메소드 탈출용 X)
    * continue: 뒤에 있는 문장은 건너뛰고 조건문부터 새로 시작

    * **do while** : 적어도 한번은 반복문장 실행
        > do {
        >  처리문장;
        > } while(조건);

    * **for**
        > for(초기화; 종료조건; 조건 값 증가) {
        >  반복문장;
        > }

    * label: 두개 이상의 반복문이 있을 경우 바깥쪽 루프의 시작점으로 이동하려고 할 때 사용. 반복문 바로 앞에 원하는 이름을 입력하고 콜론(:)을 써주면 된다.

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
 
## 7장 여러 데이터를 하나에 넣을 수는 없을까요?

### 배열 	
- 한 변수에 여러 개의 값을 넣을 수 있는 것
- 모든 배열은 참조 자료형.
- new를 사용하여 선언
- 중간에 배열의 크기는=를 증가나 감소시킬 수 없다.
- 기본 자료형 배열의 기본값은 각 자료형의 기본값과 동일
- 기본 자료형 배열은 지역변수라 할지라도 기본값이 할당된다.
- 참조 자료형 배열은 초기화를 하지 않으면 null 값
- new 대신 중괄호를 이용하여 배열 선언 가능 (단, 변수 선언과 초기화를 동시에)
- 중괄호로 선언한 배열은 보통 변경되지 않는 값을 지정할 때 사용
   > 변경되지 않는 값을 클래스 내 인스턴스 변수로 선언할 수 있지만 매번 클래스를 생성할 때마다 불필요하게 생성되는 것을 방지하기 위해 static을 사용하여 클래스 변수로 사용하는 것이 좋다. 
    > (하지만 static은 남발하지 말고 신중히 사용할 것!)
- 배열의 길이를 구할 땐 “.length” 사용

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
	
## 8장 참조 자료형에 대해서 더 자세히 알아봅시다

### 생성자
    - 클래스의 객체(또는 인스턴스)를 생성하기 위해 존재
	- 메소드와 비슷하지만, 리턴 타입이 없고 메소드 이름 대신 클래스 이름
    - 생성자는 여러 개 가능

* 기본 생성자 	
    - 만들지 않아도 컴파일할 때 자동으로 생성된다.
    - 다른 생성자가 있는 경우엔 자동으로 만들어지지 않는다.

* **오버로딩(overloading): 메소드의 이름은 같게 하고 매개 변수들을 다르게 하여 만드는 것**

* 메소드가 종료되는 조건 	
    1. 메소드의 모든 문장이 실행되었을 때
	2. return 문장에 도달했을 때
	3. 예외가 발생(throw)했을 때

### static
- static 메소드는 객체를 생성하지 않아도 메소드를 호출할 수 있다.
- static 메소드는 클래스(static) 변수만 사용할 수 있다.
- 클래스 변수를 사용하게 되면 모든 객체에서 하나의 값을 바라보기 때문에 위험하다.
- 따라서 static을 사용할 때는 신중하게!

- static 블록
    - static { …. }
    - 객체는 여러 개를 생성하지만, 한 번만 호출되어야 하는 코드가 있다면 static 블록 사용.
    - 객체가 생성되기 전에 한 번만 호출되고, 그 이후에는 호출 하려해도 호출 불가능.
    - 클래스 내에 선언/ 메소드 내 선언 불가/ 여러 개 가능/ 순서 중요!

### Pass by value & Pass by reference
- Value
    - 기본 자료형은 모두 값을 전달한다.
    - 원래의 값은 변경되지 않는다.
- Reference
    - 참조 자료형은 객체에 대한 참조가 넘어간다.
    - 호출한 참조 자료형 안에 있는 객체는 호출된 메소드에서 변경한대로 데이터가 바뀐다.

### 매개 변수의 개수가 정해져 있지 않은 경우 매개 변수를 지정하는 방법
1. 배열을 넘겨준다.
    - 장점: 가장 쉬운 방법
    - 단점: 계산하려는 변수들을 모두 배열로 만든 후 넘겨야한다.
2. 임의 개수의 매개 변수(Arbitrary Number of Arguments)
    - 타입...변수명 *ex) int...numbers*
    - 매개 변수를 배열로 인식
    - 하나의 메소드에서는 한 번만 사용 가능
    - 여러 매개 변수가 있다면, 가장 마지막에 선언 *ex) String msg, int...num*

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 9장 자바를 배우면 패키지와 접근 제어자는 꼭 알아야 해요

### 패키지(package)
- 클래스들을 구분 짓는 폴더와 비슷한 개념
- 클래스명이 중복되거나 어떤 클래스가 어떤 일을 하는지 분류

- **패키지 선언 제약사항**
    - 소스의 가장 첫 줄에
    - 패키지 선언은 소스 하나당 하나
    - 패키지 이름과 위치한 폴더명은 동일하게
    - 'java'로 시작해선 안된다. (우리는 Oracle에서 자바를 개발하는 사람이 아니다.)

> *자바는 해당 패키지의 가장 상위(root) 디렉토리에서 실행 해야만 한다. (약속)*

- **패키지명 규칙**
    - 패키지명은 모두 소문자
    - 자바의 예약어 사용 금지

    |패키지 시작 이름| 내용                                 |
    | :-----------: | ----------------------------------  |
    |java           |자바 기본 패키지(Java 벤더에서 개발)   |
    |javax          |자바 확장 패키지(Java 벤더에서 개발)   |
    |org            |일반적으로 비 영리단체(오픈소스)의 패키지|
    |com            |일반적으로 영리단체(회사)의 패키지     |

- **import**를 이용하여 다른 패키지에 접근
    - 자바에서는 패키지가 있을 때, 같은 패키지의 클래스와 java.lang 패키지에 있는 클래스만 찾을 수 있다. (import 불필요)
    - **import "패키지명.클래스명"**을 명시하면 다른 패키지의 해당 클래스를 사용할 수 있다.
    - 패키지의 모든 클래스를 사용할 때는 **import "패키지명.*"** 명시. 하지만 해당 패키지의 하위 패키지의 클래스는 사용할 수 없다.
        
    - **import static**: 클래스 변수(static 변수)와 static 메소드를 사용할 때 용이 (아무 제약 없이 static 호출 가능)
    - import static을 사용하지 않고 static을 호출할 경우 **"클래스명.변수명"** 또는 **"클래스명.메소드명"**라고 명시
    - 만약 동일한 이름의 static 변수나 메소드가 있다면 현재 클래스의 것이 우선

### 자바의 접근 제어자(Access modifier)
1. **public**: 누구나 접근 가능
2. **protected**: 같은 패키지 내에 있거나 상속받은 경우에만 접근 가능
3. **pakage-private**: 아무런 접근 제어자를 적어주지 않은 때(default). 같은 패키지 내에 있을 때만 접근 가능
4. **private**: 해당 클래스 내에서만 접근 가능

|                | 해당 클래스 | 같은 패키지 | 상속 받은 클래스 | import한 클래스 |
| -------------- | :--------: | :---------: | :-------------: | :-------------: |
|public          | O          | O           | O               | O               |
|protected       | O          | O           | O               | X               |
|(pakage private)| O          | O           | X               | X               |
|private         | O          | X           | X               | X               |

- 접근 제어자 사용 이유
    - 중요한 메소드나 변수를 다른 사람이 마음대로 호출하는 것을 방지하기 위함
    - 변수의 경우 직접 접근해서 값을 변경 못하게 하고 메소드를 통해서만 변경이나 조회만 가능하게 한다.

- 클래스 접근 제어자 선언 시 유의점
    - 클래스를 선언할 때 반드시 파일 이름에 해당하는 클래스가 존재해야 한다. (여러 클래스 존재 가능)
    - public으로 선언된 클래스가 소스 내에 있다면, 그 소스 파일의 이름은 public인 클래스명과 동일해야 한다.

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 10장 자바는 상속이라는 것이 있어요

### 상속
- **자식 -> 부모** 상속 관계
    - 부모 클래스에서는 기본 생성자를 만들어 놓는 것 외에는 상속을 위해 아무런 작업을 할 필요가 없다.
    - 자식 클래스는 클래스 선언 시 **extends** 다음에 부모 클래스 이름을 적어준다.
    - 자식 클래스의 생성자가 호출되면, 자동으로 부모 클래스의 **기본 생성자**가 먼저 실행된다.
        > 만약 부모 클래스에 기본 생성자 없이 매개 변수를 받는 생성자만 있을 시 에러 발생 (기본 생성자를 자동으로 생성하지 않는다.)
        > - 해결방법1) 부모 클래스에 "매개 변수가 없는" 기본 생성자를 만든다.
        > - 해결방법2) 자식 클래스에 부모 클래스의 생성자를 명시적으로 지정하는 **super()**를 사용 
    - 자식 클래스는 부모 클래스에 선언되어 있는 public 및 protected 변수와 모든 메소드를 사용할 수 있다.
        > *부모 클래스에서 private으로 선언된 변수는 자식 클래스에서 사용 불가능*
    - 자식 클래스에서는 부모 클래스에 선언되지 않은 변수와 메소드를 선언할 수 있다.
    - 다중 상속은 불가능

    > 상속을 하는 이유: 하나의 클래스를 잘 만들어 놓은 게 있으면, 그 클래스를 상속받아 추가적인 기능을 넣을 수 있다.

<p align="center">
    <img src="./image/상속관계.png" alt="상속 관계" width="40%" height="40%" />
    <br/>
    상속 관계
</p>

### 메소드 **Overriding**
- 정의 및 설명
    - 자식 클래스에서 부모 클래스에 있는 메소드와 동일하게 선언하는 것
    - 접근 제어자, 리턴 타입, 메소드 이름, 매개 변수 타입 및 개수가 모두 동일 (동일한 시그니처)
    - 접근 제어자가 더 확대되는 것은 문제가 안되지만, 축소되는 것은 문제가 된다.
        > ex) 부모 클래스에서 public으로 선언한 것을 자식이 private으로 선언하면 안된다.

> **Overloading: 확장** (메소드의 매개 변수들을 확장)  
> **Overriding: 덮어 씀** (부모 클래스의 메소드 시그니처를 복제해서 자식 클래스에서 새로운 것을 만들어 부모의 기능을 무시하고 덮어 씀)

<br/>

### 참조 자료형의 형 변환
- 상속 관계가 성립되면 참조 자료형도 형변환 가능
    - **자식 타입의 객체를 부모 타입으로** 형 변환 하는 것은 자동으로 된다.
        - 사용 예: 부모 타입의 객체의 실제 객체를 자식 타입으로 선언
            ```java
            ParentCasting parent = new ChildCasting();
            ```
    - 반대로 **부모타입의 객체를 자식 타입으로** 형변환 할 때에는 명시적으로 지정해야 한다. 이때, **부모 타입의 실제 객체는 자식 타입**이어야 한다.
- **instanceof** 예약어로 객체의 타입 확인 가능
    - instanceof로 타입 확인시 부모 타입도 true라는 결과 반환
    - 따라서 타입을 점검할 때는 가장 하위에 있는 자식 타입부터 확인
    - 사용 예:
        ```java
        if(tempParent instanceof ChildCasting) {
            System.out.println("ChildCasting");
        } else if(tempParent instanceof ParentCasting) {
            System.out.println("ParentCasting");
        }
        ```

<br/>

### 다형성 (Polymorphism)
    '형태가 다양하다.'  
    형 변환을 하더라도, 실제 호출되는 것은 원래 객체에 있는 메소드가 호출된다.

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 11장 매번 만들기 귀찮은데 누가 만들어 놓은 거 쓸 수 없나요?

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 12장 모든 클래스의 부모 클래스는 Object에요

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 13장 인터페이스와 추상 클래스, enum

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 14장 다 배운 것 같지만, 예외라는 중요한 것이 있어요

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 15장 String

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 16장 클래스 안에 클래스가 들어갈 수도 있구나

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 17장 어노테이션이라는 것도 알아야 한다

- 기능:
    - 컴파일러에게 정보 알림
    - 컴파일할 때와 설치(deployment) 시의 작업을 지정
    - 실행할 때 별도의 처리가 필요할 때 사용

- 특징:
    - 클래스, 메소드, 변수 등 모든 요소에 선언 가능
    - 프로그램에 영향이 있는 것도 있고 없는 것도 있다.
<br>

### 미리 정해져 있는 어노테이션은 3개뿐
- **@Override**: 
    - 해당 메소드가 상위 클래스의 메소드를 Override한 것을 명시적으로 선언
    - "이 메소드는 Override된 거니까 만약에 내가 잘못 코딩했으면 컴파일러 니가 알려줘야 해~"
- **@Deprecated**:
    - 미리 만들어져 있는 클래스나 메소드가 더 이상 사용되지 않는 경우
    - 경고만 있을 뿐, 에러는 없다.
    - "얘는 더 이상 사용하지 않으니까 그렇게 알아줘. 그리고 나중에 누가 이거 쓰면 경고 한 번 해주고.."
- **@SupressWarning**:
    - 컴파일러에서 경고를 하지만, 프로그램에는 문제가 없는 경우 경고를 억제
    - 속성값 지정을 한다.
    - "얘는 내가 일부러 이렇게 코딩한 거니까 니가 경고를 해 줄 필요가 없어"

<br>

### 어노테이션을 선언하기 위한 메타 어노테이션

- 메타 어노테이션
    - **@Target**: 어노테이션을 어떤 것에 적용할지 선언
        - 선언 예:
            ```java
            @Target(ElementType.METHOD)
            ```
        - 적용 대상 목록:
            | 요소 타입 | 대상 |
            | ---------| ---- |
            | CONSTRUCTOR | 생성자 선언시 |
            | FIELD | enum 상수를 포함한 필드값 선언시 |
            | LOCAL_VARIABLE | 지역 변수 선언시 |
            | METHOD | 메소드 선언시 |
            | PACKAGE | 패키지 선언시 |
            | PARAMETER | 매개변수 선언시 |
            | TYPE | 클래스, 인터페이스, enum 등 선언시 |

    - **@Retation**: 얼마나 오래 어노테이션 정보가 유지되는지 선언
        - 선언 예:
            ```java
            @Retention(RetentionPolicy.RUNTIME)
            ```
        - 적용 대상 목록:
            |   | 대상 |
            | - | ---- |
            | SOURCE | 어노테이션 정보가 컴파일시 사라짐 |
            | CLASS | 클래스 파일에 있는 어노테이션 정보가 컴파일러에 의해서 참조 가능. 하지만 가상머신에서는 사라짐 |
            | RUNTIME | 실행시 어노테이션 정보가 가상머신에 의해서 참조 가능 |

    - **@Document**: 해당 어노테이션에 대한 정보가 Javadocs(API) 문서에 포함된다는 것 선언

    - **@Inherited**: 모든 하위 클래스에서 상위 클래스의 어노테이션을 사용가능하다는 것을 선언

    - **@Interface**: 어노테이션을 선언할 때 사용

<br>

- 어노테이션 선언 예:
    ```java
    package c.annotation;

    import ...;

    @Target(ElementType.METHOD)  // 메소드와 클래스에서 어노테이션을 사용하려면 "@Target({ElementType.METHOD, ElementType.TYPE})"으로 지정
    @Retention(RetentionPolicy.RUNTIME)
    public @interface UserAnnotaion { // @UserAnnotation으로 어노테이션 사용가능
        
        public int number(); 
        public String text() default "This is first annotation";

    }
    ```

- 어노테이션 사용 예:
    ```java
    package c.annotation;

    public class UserAnnotationSample {
        
        @UserAnnotaion(number=0)  // number는 기본값이 지정되어 있지 않으므로 반드시 값을 정해주어야 한다.
        public static void main(String[] args) {
            UserAnnotationSample sample = new UserAnnotationSample();
        }

        @UserAnnotation(number=1)
        public void annotationSample1(){
            // ...
        }

        @UserAnnotation(number=2,text="second")
        public void annotationSample2(){
            // ...
        }

        @UserAnnotation(number=3,text="third")
        public void annotationSample3(){
            // ...
        }
    }
    ```

<br>

### 어노테이션에 선언한 값은 어떻게 확인하지?

- 사용 예:
    ```java
    package c.annotation;

    public class UserAnnotationCheck {

        public static void main(String[] args) {
            UserAnnotationCheck sample = new UserAnnotationCheck();
            sample.checkAnnotations(UserAnnotationSample.class);
        }

        /* 
            'Class', 'Method'는 자바의 Reflection이라는 API에서 제공하는 클래스
            Class: 클래스의 정보를 확인하는 데 사용
            Method: 메소드의 정보를 확인하는 데 사용
        */

        public void checkAnnotations(Class useClass) {
            
            // 해당 클래스에 선언되어 있는 메소드의 목록을 배열로 리턴
            Method[] methods = useClass.getDeclaredMethods();  

            for(Method method : methods) {

                // 해당 메소드에 선언되어 있는 매개 변수로 넘겨준 어노테이션이 있는지 확인하고, 있을 경우 그 어노테이션의 객체를 리턴
                UserAnnotation annotation = method.getAnnotation(UserAnnotation.class);  

                if(annotation != null) {

                    // 어노테이션에 선언된 메소드를 호출하여 해당 값 리턴
                    int number = annotation.number();
                    String text = annotation.text();

                    System.out.println(method.getName() + "(): number=" + number + ", text=" + text);
                } else {
                    System.out.println(method.getName() + "(): annotation is null");
                }
            }
        }
    }
    ```

<br>

### 어노테이션도 상속이 안돼요

- 상속을 지원하지 않아 미리 만들어 놓은 어노테이션을 확장하는 것은 불가능하다.

<br>

- **어노테이션이 만들어지기 전**
    - 모든 자바 어플리케이션의 설정을 XML이나 properties 파일에 지정
    - 설정이 복잡해지고, 어떤 설정이 어디에 쓰이는지 이해하는데 많은 시간 소요된다.

<br>

- **어노테이션이 만들어진 후**
    - 각 설정이 필요한 위치에 관련 설정이 존재하면서 코드의 가독성이 좋아졌다.
    - 하지만 아직도 XML과 같은 설정파일들은 필요한 부분이 존재하기 때문에 남아 있다.
    - **롬복(lombok)**: 개발자가 필요한 작업을 어노테이션 선언만으로도 편하게 처리할 수 있게 도와준다.
        - 사용 예:
            - 기존 코드:
                ```java
                private boolean employed = true;

                public boolean isEmployed() {
                    return employed;
                }

                public void setEmployed(final boolean employed) {
                    this.employed = employed;
                }
                ```
            - 롬복 적용:
                ```java
                @Getter @Setter private boolean employed = true;
                ```
<br>

- **어노테이션의 용도**:
    - 제약사항 등을 선언하기 위해
        > @Deprecated, @Override, @NotNull
    - 용도를 나타내기 위해
        > @Entity, @TextCase, @WebService
    - 행위를 나타내기 위해
        > @Statefull, @Transaction
    - 처리를 나타내기 위해
        > @Column, @XmlElement

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>

## 18장 이제 기본 문법은 거의 다 배웠으니 정리해 봅시다

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#god-of-java---book1)  

<br/><br/>
