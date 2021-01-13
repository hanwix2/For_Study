# Spring 이론

### :paperclip: Contents
- [Maven vs Gradle](#maven-vs-gradle)

---

## Maven vs Gradle

### Maven
- **Maven 이란?**
    프로젝트를 진행하게 되면 단순히 자신이 작성한 코드만으로 개발하는 것이 아니라 많은 라이브러리들을 활용해서 개발을 한다. 이 때 사용되는 라이브러리의 수가 수십개를 훌쩍 넘어버리는 일이 발생해 이 많은 라이브러리들을 관리하는 것이 힘들어지는 경우가 종종 발생한다. Maven은 내가 사용할 라이브러리 뿐 아니라 해당 라이브러리가 작동하는데 필요한 다른 라이브러리까지 관리하여 네트워크를 통해 자동으로 다운받아 준다.  
    <br>
    Maven은 프로젝트의 전체적인 lifecycle을 관리하는 도구이며, 많은 편리함과 이점이 있어 널리 사용된다. 기존에는 Ant가 많이 사용되었지만 Maven이 Ant를 넘어서 더 많은 개발자들이 사용하게 되었고 비교적 최근에는 Gradle이 새롭게 나와 사용되고 있다.
    <br> 

    - 빌드를 쉽게 (Making the build process easy)
    - pom.xml을 이용한 정형화된 빌드 시스템 (Providing a uniform build system)
    - 뛰어난 프로젝트 정보 제공 (Providing quality project information_
        - Change log document created directly from source control
        - Cross referenced sources
        - Mailing lists
        - Dependency list
        - Unit test reports including coverage
    - 개발 가이드 라인 제공 (Providing guidelines for best practices development)
        - Keeping your test source code in a separate, but parallel source tree
        - Using test case naming conventions to locate and execute tests
        - Have test cases setup their environment and don’t rely on customizing the build for test preparation.
    - 새로운 기능을 쉽게 설치할 수 있고 업데이트할 수 있음 (Allowing transparent migration to new features)

<br>
 
- **Maven의 Lifecycle**
    Maven에서는 미리 정의하고 있는 빌드 순서가 있으며 이 순서를 라이프사이클이라고 한다. 라이프사이클의 빌드 단계를 phase라고 하는데 이런 phase들은 의존관계를 가지고 있다.
    - **Clean**: 이전 빌드에서 생성된 파일들을 삭제하는 단계
    - **Validate**: 프로젝트가 올바른지 확인하고 필요한 모든 정보를 사용할 수 있는지 확인하는 단계
    - **Compile**: 프로젝트의 소스코드를 컴파일하는 단계
    - **Test**: 유닛(단위) 테스트를 수행하는 단계(테스트 실패시 빌드 실패로 처리, skip 가능)
    - **Package**: 실제 컴파일된 소스 코드와 리소스들을 jar 등의 배포를 위한 패키지로 만드는 단계
    - **Verify**: 통합 테스트 결과에 대한 검사를 실행하여 품질 기준을 충족하는지 확인하는 단계
    - **Install**: 패키지를 로컬 저장소에 설치하는 단계
    - **Site**: 프로젝트 문서를 생성하는 단계
    - **Deploy**: 만들어진 Package를 원격 저장소에 release하는 단계
    위의 9개 라이프사이클 외 더 많은 종류의 라이프사이클이 존재한다. 이를 크게 **Clean, Build, Site** 세가지 라이프사이클로 나누고 있다. 각 단계를 모두 수행하는 것이 아니라 원하는 단계까지만 수행할 수도 있으며 test 단계는 큰 프로젝트의 경우에 몇시간이 소요될 수도 있으니 수행하지 않도록 skip 가능하다.  
<br>

- **Phase와 Goal**
    Phase는 Maven의 Build Lifecycle 각각의 단계를 의미한다. 각각의 phase는 의존관계를 가지고 있어 해당 phase가 수행되려면 이전 단계의 phase가 모두 수행되어야 한다.  
    Maven에서 제공되는 모든 기능은 plug-in 기반으로 동작하는데, Maven은 라이프사이클에 포함되어 있는 phase마저도 플러그인을 통해 실질적인 작업이 수행된다. 즉, 각각의 phase는 어떤 일을 할지 정의하지 않고 어떤 플러그인의 Goal을 실행할지 설정한다.  
    Maven에서는 하나의 플러그인에서 여러 작업을 수행할 수 있도록 지원하며, 플러그인에서 실행할 수 있는 각각의 기능을 goal이라고 한다.

- **POM - Project Object Model**
    Project Object Model의 정보를 담고 있는 pom.xml 파일을 말하며, Maven의 기능을 이용하기 위해 사용된다.
    - **프로젝트 정보**: 프로젝트 이름, 개발자 목록, 라이센스 등
    - **빌드 설정**: 소스, 리소스, 라이프사이클 별 실행한 플러그인(goal) 등 빌드와 관련된 설정
    - **빌드 환경**: 사용자 환경마다 달라질 수 있는 프로파일 정보
    - **POM 연관 정보**: 의존 프로젝트(모듈), 상위 프로젝트, 포함하고 있는 하위 모듈 등

<br>

### Gradle

- **Gradle 이란?**
    빌드 배포 도구(Build Tool). 안드로이드 앱을 만들 때 필요한 공식 빌드 시스템.  
    빌드툴인 Ant Builde와 Groovy Script를 기반으로 구축되어 기존 Ant의 역할과 배포 스크립트의 기능을 모두 사용가능하다.  
    <br>
    Maven의 경우 XML로 라이브러리를 정의하고 활용하도록 되어있으나, Gradle의 경우 별도의 빌드 스크립트를 통하여 어플리케이션의 버전, 라이브러리의 항목을 설정할 수 있다.  
    장점으로는 스크립트 언어로 구성되어 있기 때문에 XML과 달리 변수 선언, if, else, for 등의 로직이 구현 가능하여 간결하게 구성 가능하다.
    <br>

    - Ant처럼 유연한 범용 빌드 도구 (A very flexible general purpose build tool like Ant.)
    - Maven을 사용할 수 있는 변환 가능 컨벤션 프레임 워크 (Switchable, build-by-convention frameworks a la Maven. But we never lock you in!)
    - 멀티 프로젝트에 사용하기 좋음 (Very powerful support for multi-project builds.)
    - Apache Ivy에 기반한 강력한 의존성 관리 (Very powerful dependency management (based on Apache Ivy))
    - Maven과 Ivy 레파지토리 완전 지원 (Full support for your existing Maven or Ivy repository infrastructure.)
    - 원격 저장소나, pom, ivy 파일 없이 연결되는 의존성 관리 지원 (Support for transitive dependency management without the need for remote repositories or pom.xml and ivy.xml files.)
    - 그루비 문법 사용 (Groovy build scripts.)
    - 빌드를 설명하는 풍부한 도메인 모델 (A rich domain model for describing your build.)

<br>

- **Gradle이 Maven 보다 좋은 점**
    - Build 라는 동적인 요소를 XML로 정의하기에는 어려운 부분이 많다.
        - 설정 내용이 길어지고 가독성이 떨어짐
        - 의존관계가 복잡한 프로젝트를 설정하기에는 부적절
        - 상속 구조를 이용한 멀티 모듈 구현
        - 특정 설정을 소수의 모듈에서 공유하기 위해서는 상위 프로젝트를 생성하여 상속하게 해야함 (상속의 단점 발생)
    - Gradle은 Groovy를 사용하기 때문에 동적인 빌드는 Groovy 스크립트로 플러그인을 호출하거나 직접 코드를 짜면 된다.
        - Configuration Injection 방식을 사용하여 공통 모듈을 상속해서 사용하는 단점 커버
        - 설정 주입 시 프로젝트의 조건을 체크할 수 있어 프로젝트별로 주입되는 설정을 다르게 할 수 있다.
    - Gradle이 Maven 보다 최대 100배 빠르다.
        - Gradle은 캐시를 사용하기 때문에 테스트 반복 시 차이가 더 커진다.

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#spring-이론)  
> https://hyojun123.github.io/2019/04/18/gradleAndMaven/  
> https://bkim.tistory.com/13

<br/><br/>