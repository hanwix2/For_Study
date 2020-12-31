# Web Programming

> 서적: *최범균의 JSP 2.3 웹 프로그래밍 기초부터 중급까지*

### :paperclip: Contents
[ 2. 웹 프로그래밍 기초](#2장-웹-프로그래밍-기초)  
[ 3. JSP로 시작하는 웹 프로그래밍](#3장-jsp로-시작하는-웹-프로그래밍)  
[ 9. 클라이언트와의 대화 1 - 쿠키](#9장-클라이언트와의-대화-1---쿠키)  
[10. 클라이언트와의 대화 2 - 세션](#10장-클라이언트와의-대화-2---세션)  

---

## 2장 웹 프로그래밍 기초

### URL과 웹 페이지
- **URL** (Uniform Resource Locator): 웹 브라우저의 주소줄에 표시되는 것. 일종의 주소
- **웹 페이지** (web page): 웹 브라우저 출력된 URL에 해당하는 내용.
    - 웹 사이트(혹은 홈페이지)는 웹 페이지의 묶음

- URL의 주요 구성 요소
    1. **프로토콜**: 웹 브라우저가 서버와 내용을 주고받을 때 사용할 규칙 이름. 웹 페이지의 주소를 표현할 때는 'http' 사용.
    2. **서버 이름**: 웹 페이지를 요청할 서버 이름. 도메인 이름이나 IP 주소를 입력할 수 있다.
    3. **경로**: 웹 페이지의 상세 주소. 웹 페이지마다 다른 경로를 갖는다.
    4. **쿼리 문자열**: 추가로 서버에 보내는 데이터. 같은 경로라 하더라도 입력한 값에 따라 다른 결과를 보여줘야 할 때 사용.

<br/>

### 웹 브라우저와 웹 서버

- 웹 브라우저에 URL을 입력하면 웹 서버라 불리는 프로그램이 웹 브라우저에 웹 페이지를 제공
    - 요청: 웹 브라우저가 웹 서버에 웹 페이지를 달라고 하는 것
    - 응답: 요청한 웹 페이지를 웹 브라우저에 제공

- **IP 주소**
    - 웹 브라우저가 웹 서버에 연결하려면, 웹 서버가 실행 중인 컴퓨터의 주소를 알아야한다. 이 주소를 **IP 주소**라고 부른다.
    - 각 컴퓨터는 고유한 IP 주소값을 가진다.
    - IP 주소는 숫자로 구성되어 있어 외우기 쉽지 않다. 사람이 기억하기 좋은 **도메인 이름**을 IP 주소 대신 사용한다.
    - **DNS (Domain Name Server)**: 도메인 이름을 IP 주소로 변환해 준다

- 웹 브라우저와 웹 서버의 통신 과정
    1. 웹 브라우저는 도메인 이름에 해당하는 IP 주소를 DNS에 요청
    2. DNS는 IP 주소를 응답으로 제공
    3. 웹 브라우저는 DNS로 부터 받은 IP 주소를 이용해서 웹 브라우저에 연결 후 URL에 해당하는 웹 페이지 요청
    4. 웹 서버에서 웹 브라우저로 HTML 응답

<p align="center">
    <img src="./images/웹 브라우저와 웹 서버의 통신 과정.png" alt="웹 브라우저와 웹 서버의 통신 과정" width="30%" height="30%"/>
    <br/>
    웹 브라우저와 웹 서버의 통신 과정
</p>

- **포트 (Port)**
    - 서버 프로그램을 구분하는 용도
    - IP 주소는 연결할 컴퓨터를 구분. IP 주소만으로 다양한 컴퓨터의 서버 프로그램 중 어떤 것을 실행 할지 알 수 없다.
    - 웹 서버가 기본으로 사용하는 포트 번호는 80

<br/>

### HTML과 HTTP

- **HTML (HyperText Markup Language)**
    - 웹 페이지를 만들 때 사용하는 표준
    - HTML 문서라고도 한다.
    - 웹 서버는 URL에 해당하는 HTML 문서를 전송하는데, HTML 문서를 받은 웹 브라우저는 정해진 규칙에 따라 HTML 문서를 분석해서 알맞은 화면을 생성한다.
    - **렌더링(rendering)**: HTML 문서로 부터 알맞은 화면을 생성하는 과정

- **HTTP (HyperText Transfer Protocol)**
    - 웹 브라우저와 웹 서버가 HTML을 비롯해 이미지, 동영상, XML 문서 등 다양한 데이터를 주고받을 때 사용하는 일종의 규칙
    - 데이터 구성 규칙
        - 요청 규칙: 웹 브라우저 -> 웹 서버 (요청)
        - 응답 규칙: 웹 서버 -> 웹 브라우저 (전송)
        - 구성
            1. 요청/응답 줄
            2. 헤더
            3. 몸체

        <p align="center">
        <img src="./images/http 요청, 응답 데이터.png" alt="http 요청, 응답 데이터" />
        <br/>
        http 요청, 응답 데이터
        </p>

        - **요청 데이터**
            - 요청 줄: GET이나 POST와 같은 HTTP 요청 방식(method)과 요청하는 자원의 경로를 지정
            - 헤더: 서버가 응답을 생성하는데 참조할 수 있는 정보. ex) 브라우저의 종류, 언어 등
            - 몸체: 정보를 전송해야 할 때 사용. ex) 파일 업로드 시 몸체 영역에 파일을 담아 웹 서버에 전송
        - **응답 데이터**
            - 응답 줄: 요청에 대해 200이나 404 같은 응답 코드 전송. (200은 정상 처리를 의미)
            - 헤더: 응답에 대한 정보. ex) 응답에 대한 몸체의 데이터 종류, 길이 등
            - 몸체: 웹 브라우저가 요청한 자원의 내용. ex) HTML 문서, 이미지 파일 데이터 등

<br/>

### 정적 자원과 동적 자원

- **정적(static) 자원**
    - 웹 서버들이 URL의 경로와 일치하는 파일을 읽어와 응답으로 전송하는데, 파일이 바뀌기 전까지 항상 같은 내용을 웹 브라우저에 전송한다.
    - 고정된 결과가 출력되는 URL에 해당하는 자원을 정적 페이지 또는 정적 자원이라고 표현
    - 보통 이미지 파일이나 HTML 파일과 같이 자주 바뀌지 않는 것들을 정적 자원으로 제공
- **동적(dynamic) 자원**
    - 정적 자원과 달리 파일을 바꾸지 않아도 조건에 따른 다른 응답 데이터를 전송하는 경우도 있다.
    - 시간이나 특정 조건에 따라 응답 데이터가 달라지는 것을 동적 자원이라고 표현
    - JSP, PHP, ASP.net 등: 동적 페이지를 만드는데 사용되는 프로그래밍 기술

<br/>

### 웹 프로그래밍과 JSP

- 웹 프로그래밍이란?
    - 웹 서버가 웹 브라우저에 응답으로 전송할 데이터를 생성해주는 프로그램을 작성하는 것
    - 웹 서버의 종류에 따라 사용할 기술은 다르다.
        - JSP
        - PHP (아파치 웹 서버)
        - ASP.net (윈도우 IIS 웹 서버)

- **JSP (JavaServer Pages)**
    - 동적 페이지를 작성하는데 사용되는 자바의 표준 기술
    - HTML, XML, JSON, 바이너리 파일 등의 응답을 생성하는데 필요한 기능 제공
- **WAS (Web Application Server)**

    <p align="center">
    <img src="./images/WAS.png" alt="WAS는 클라이언트의 요청이 오면, 알맞은 프로그램을 실행해서 응답을 생성한다." width="60%" height="60%"/>
    <br/>
    WAS는 클라이언트의 요청이 오면, 알맞은 프로그램을 실행해서 응답을 생성한다.
    </p>

    - JSP를 이용해 만든 프로그램을 실행하기 위한 서버 프로그램
    - 단순 웹 서버가 정적인 HTML 파일이나 이미지를 제공하는 것과 달리
    - 웹을 위한 연결, 프로그래밍 언어, 데이터베이스 연동 등 어플리케이션을 구현하는데 필요한 기능 제공
    - 웹 브라우저로부터 요청이 오면 알맞은 프로그램을 찾아 실행하고, 프로그램의 실행 결과를 응답으로 전송한다.
    - 종류: Tomcat, Jetty, JBoss EAP

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#web-programming)  
> https://coding-start.tistory.com/348
> https://m.blog.naver.com/PostView.nhn?blogId=moongmoong_2&logNo=221356141557&proxyReferer=https:%2F%2Fwww.google.com%2F

<br/><br/>

## 3장 JSP로 시작하는 웹 프로그래밍

### JSP에서 HTML 문서를 생성하는 기본 코드 구조
 JSP 코드를 작성하는 주된 목적은 웹 브라우저에 보여 줄 HTML 문서를 생성하는 것.  
 JSP를 사용해서 파일 다운로드를 구현할 수 있고, XML과 같은 다른 종류의 문서를 응답으로 제공할 수도 있지만, 대부분의 JSP 코드는 HTML을 생성한다.  

- 일반적인 JSP 코드 예:
    ```jsp
    <%@ page contentType = "text/htmll; charset=utf-8" %>
    <html>
    <head>
        <title>HTML 문서의 제목</title>
    </head>
    <body>
        <%
            String bootTitle = "JSP 프로그래밍";
            String author = "최범균";
        %>
        <b><%= bookTitle %></b>(<%= author %>)입니다.
    </body>
    </html>
    ```

    - 1행: **설정 부분** - JSP 페이지에 대한 설정 정보
        - 정보:
            - JSP 페이지가 생성하는 문서의 타입(종류)
            - JSP 페이지에서 사용할 커스텀 태그
            - JSP 페이지에서 사용할 자바 클래스 지정
            > *예시 코드에서는 문서의 타입(HTML)과 캐릭터 셋(UTF-8)을 나타낸다.*
        - **<%@ page ... %>**: page 디렉티브 - JSP 페이지에 대한 정보를 설정할 때 사용

    - 나머지행: **생성 부분** - HTML 코드 및 JSP 스크립트
        - 스크립트 코드: HTML 문서를 생성하는 데 필요한 데이터를 생성하고 출력하는 데 사용

<br/>

### JSP 페이지의 구성 요소

- **디렉티브 (Directive)**
    - JSP 페이지에 대한 설정 정보를 지정할 때 사용.
    - 선언:
        ```
        <%@ 디렉티브이름 속성1="값1" 속성2="값2" ... %>
        ```
    - JSP가 제공하는 디렉티브
        | 디렉티브 | 설명 |
        | :------: | --- |
        | page     |JSP 페이지에 대한 정보를 지정. JSP가 생성하는 문서의 타입, 출력 버퍼의 크기, 에러 페이지 등 JSP 페이지에서 필요한 정보를 설정한다.|
        | taglib   |JSP 페이지에서 사용할 태그 라이브러리를 지정. |
        | include  |JSP 페이지의 특정 영역에 다른 문서를 포함.|


- **스크립트 요소**
    JSP 문서의 내용을 동적으로 생성하기 위해 사용되는 것이 스크립트 요소.  
    데이터베이스 연동, 자바가 제공하는 다양한 기능을 사용할 수 있다.

    - **표현식(Expression)**: 값을 출력
    - **스크립트릿(Scriptlet)**: 자바 코드를 실행
    - **선언부(Declaration)**: 자바 메서드(함수)를 만든다.

- **기본 객체 (Implicit Object)**
    - JSP는 웹 어플리케이션 프로그래밍을 하는 데 필요한 기능을 제공하는 '기본 객체'를 제공한다.  
    - **request(요청 파라미터 읽어오기)**, **response(응답 결과 전송)**, **session(세션 처리)**, application(웹 어플리케이션 정보 읽어오기), page 등 존재

- **표현 언어 (Expression Language)**
    JSP 스크립트 요소는 자바 문법을 그대로 사용할 수 있기 때문에 자바 언어의 특징을 그대로 사용할 수 있다는 장점이 있다.  
    하지만 스크립트 요소를 사용하면 JSP 코드가 다소 복잡해진다.  
    **표현 언어를 사용하면 복잡한 코드를 간결하게 작성할 수 있다.**

    - JSP 스크립트 요소 예시:
        ```JSP
        <%
            int a = Integer.parseInt(request.getParameter("a"));
            int b = Integer.parseInt(request.getParameter("b"));
        %>
        a * b = <%= a * b %>
        ```

    - 표현 언어 사용 예시:
        ```JSP
        a * b = ${param.a * param.b}
        ```

- **표준 액션 태그(Action Tag)와 태그 라이브러리(JSTL)**
    - **액션 태그**
        - JSP 페이지에서 특별한 기능을 제공한다.
        - **&lt;jsp:액션태그이름&gt;**
        - ex) &lt;jsp:include&gt; 태그: 특정한 페이지의 실행 결과를 현재 위치에 포함
            ```JSP
            <%@ page contentType = "text/htmll; charset=utf-8" %>
            <html>
            ...
            <jsp:include page="header.jsp" flush="true" />
            ...
            </html>
            ```
    - **커스텀 태그**
        - JSP를 확장시켜주는 기능. 액션 태그와 마찬가지로 태그 형태로 기능 제공
        - 액션 태그와 달리 **개발자가 직접 개발해주어야 한다.**
        - 일반적으로 JSP 코드에서 중복되는 것을 모듈화하거나 스크립트 코드를 사용할 때 발생하는 소스 코드의 복잡함을 없애기 위해 커스텀 태그를 사용한다.
    - **태그 라이브러리(JSTL)**
        - 커스텀 태그 중 자주 사용하는 것들을 별도로 표준화한 태그 라이브러리

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#web-programming)  

<br/><br/>

## 9장 클라이언트와의 대화 1 - 쿠키

### 쿠키란?

- **쿠키(cookie)**
    - 웹 브라우저가 보관하는 데이터
    - 웹 브라우저가 서버에 요청을 보낼 때 쿠키를 함께 전송
    - 웹 서버는 받은 쿠키를 사용해서 필요한 데이터를 읽을 수 있음
    - 웹 서버와 웹 브라우저 양쪽에서 생성 가능 (JSP에서 생성하는 쿠키는 서버 쪽)

    <p align="center">
    <img src="./images/쿠키의 동작 방식.png" alt="쿠키의 동작 방식" width="47%" height="47%"/>
    <br/>
    쿠키의 동작 방식
    </p>
    <br/>

    - **쿠키 생성 단계**: JSP 프로그래밍에서 쿠키는 웹 서버 측에서 생성. 생성한 쿠키를 응답 데이터의 헤더에 저장해서 웹 브라우저에 전송한다.
    - **쿠키 저장 단계**: 웹 브라우저는 응답 데이터에 포함된 쿠키를 쿠키 저장소에 보관한다. 쿠키의 종류에 따라 메모리나 파일에 저장한다.
    - **쿠키 전송 단계**: 웹 브라우저는 저장한 쿠키를 요청이 있을 때마다 웹 서버에 전송한다. 서버는 받은 쿠키를 사용해서 필요한 작업을 수행한다.

    > 일단 웹 브라우저에 크키가 저장되면, 웹 브라우저는 쿠키가 삭제되기 전까지 서버에 쿠키를 전송한다. 따라서 웹 어플리케이션을 사용하는 동안 지속적으로 유지해야 하는 정보는 쿠키를 사용해서 저장하면 된다.

<br/>

1. **쿠키의 구성**
    - **이름**: 각각의 쿠키를 구별하는 데 사용되는 이름
    - **값**: 쿠키의 이름과 관련된 값
    - **유효시간**: 쿠키의 유지 시간
    - **도메인**: 쿠키를 전송할 도메인
    - **경로**: 쿠키를 전송할 요청 경로

2. **쿠키 생성하기**
    - JSP에서는 **Coockie** 클래스 사용하여 쿠키 생성
    - **response.addCookie()** 메소드를 사용하여 쿠키 추가. 
    - response 기본 객체는 웹 브라우저에 쿠키 정보 전송.
    - 코드 사용 예:
        ```JSP
        <%
            Cookie cookie = new Cookie("name", URLEncoder.encode("value", "UTF-8"));
            response.addCookie(cookie);
        %>
        ```

3. **쿠키 값 가져오기**
    - 쿠키를 생성하면 그 이후부터 해당 쿠키를 사용할 수 있다.
    - 웹 브라우저는 요청 헤더에 쿠키를 저장해서 보내며, JSP는 request.getCookie() 메소드를 사용해서 쿠키 값을 읽어올 수 있다.
    - 코드 사용 예:
        ```JSP
        <%
        Cookie[] cookies = request.getCookies();

        if(cookies != null && cookies.length > 0) {
            for(int i = 0; i < cookies.length; i++) {
        %>
                <%= cookies[i].getName() %> = 
                <%= URLDecoder.decode(cookies[i].getValue, "UTF-8") %><br>
        <%
            }
        } else {
        %>
            쿠키가 존재하지 않습니다.
        <%
        }
        %>
        ```

4. **쿠키 값 변경 및 쿠키 삭제하기**
    - 변경
        - 쿠키 값을 변경하려면 같은 이름의 쿠키를 새로 생성해서 응답 데이터로 보내면 된다.
        - 같은 이름의 쿠키가 존재하지 않으면 새로운 쿠키가 생성되고, 존재한다면 기존에 존재하던 쿠키의 값이 변경된다.
        - 따라서 다음 코드처럼 존재 여부를 확인한 후 값을 변경해주면 된다.
            ```java
            Cookie[] cookies = request.getCookies();
            if(cookies != null && cookies.length > 0) {
                for (int i = 0; i < cookies.length; i++) {
                    if(cookies[i].getName().equals("name")) {
                        Cookie cookie = new Cookie(name, newValue);
                        response.addCookie(cookie);
                    }
                }
            }
            ```
    - 삭제
        - 쿠키를 삭제하는 별도의 기능은 없다. 
        - 다만, 쿠키 유효시간을 0으로 지정하여 응답 헤더에 추가하면 웹 브라우저가 관련 쿠키를 삭제한다.
        - Cookie 클래스의 **setMaxAge()** 메소드를 호출할 때 인자 값으로 0을 주면 된다.

5. **쿠키의 도메인**
    - 기본적으로 쿠키는 그 쿠키를 생성한 서버에만 전송된다.
    - 하지만 같은 도메인을 사용하는 모든 서버에 쿠키를 보내야 할 때가 있다.
    - **setDomain()**: 생성한 쿠키를 전송할 수 있는 도메인을 지정
        - **.somehost.com**: 점으로 시작하는 경우 관련 도메인에 모두 쿠키를 전송
            > *ex) mail.somehost.com, www.somehost.com, javacan.somehost.com 모두 쿠키를 전송*
        - **www.somehost.com**: 특정 도메인에 대해서만 쿠키 전송
    - 도메인 지정시 주의점: 현재 서버의 도메인 및 상위 도메인만 전달 가능
        > JSP 페이지가 실행되는 서버의 주소가 "mail.somehost.com" 일 때, setDomain()에 줄 수 있는 값은 "mail.somehost.com"이나 ".somehost.com" 이다.  
        > "www.somehost.com"과 같은 다른 주소를 값으로 주는 경우 쿠키가 생성되지 않는다.

6. **쿠키의 경로**
    - 도메인이 쿠키를 공유할 도메인 범위를 지정한다면, 경로는 쿠키를 공유할 기준 경로를 지정한다.
    - 경로는 URL에서 도메인 이후의 부분
    - 쿠키에서 사용하는 경로는 디렉터리 수준의 경로를 사용한다.
    - **setPath()** 메소드 사용
        > 일반적으로 쿠키는 웹 어플리케이션에 포함된 다수의 JSP와 서블릿에서 사용하기 때문에 쿠키 경로를 "/"로 지정한다.

7. **쿠키의 유효시간**
    - 쿠키는 유효시간을 갖는다.
    - 유효시간을 지정하지 않으면 웹 브라우저를 종료할 때 쿠키를 함께 삭제한다. (유효시간을 음수로 지정했을 때 포함)
    - 웹 브라우저 종료 후 다시 실행하면 삭제한 쿠키는 서버에 전송되지 않는다.
    - 쿠키의 유효시간을 정해놓으면 그 시간 동안 쿠키가 존재하며, 웹 브라우저를 종료해도 유효시간이 지나지 않았으면 쿠키를 삭제하지 않는다.
    - **setMaxAge()** 메소드 사용. (초 단위로 유효시간 지정)
        > *ex) 아이디 기억하기 기능 - 사용자가 로그인에 성공하면 아이디를 값으로 저장하는 쿠키의 유효시간을 1달 정도 여유롭게 잡아 다음에 웹 브라우저를 실행할 때 아이디를 저장하고 있는 쿠키를 사용할 수 있다. 비슷하게 자동 로그인 기능도 구현 가능*

8. **쿠키와 헤더**
    - response.addCookie()로 쿠키를 추가하면 실제로 Set-Cookie 헤더를 통해 전달된다.
    - 한 개의 Set-Cookie 헤더는 한 개의 쿠키 값을 전달
    - Set-Cookie 헤더의 구성
        ```
        쿠키이름=쿠키값; Domain=도메인값; Path=경로값; Expires=GMT형식의만료일시
        ```
    - 쿠키는 응답 헤더를 사용해서 웹 브라우저에 전달하기 때문에 출력 버퍼가 플러시(flush)된 이후에는 새롭게 추가할 수 없다. 따라서 쿠키는 출력 버퍼를 플러시하기 전에 추가해야 한다.

<br/>

### 쿠키 처리를 위한 유틸리티 클래스

    앞서 소개한 특정 쿠키를 읽는 방법은 Cookie 목록을 가져와 if-else 블록에서 쿠키 이름을 비교하여 필요한 쿠키를 구한다.  
    이런 구조는 사용할 쿠키가 많아질수록 코드가 복잡해지는 문제가 있다. 

- 편리하게 쿠키를 사용할 수 있도록 도와주는 보조 유틸리티 클래스 예시:
    ```java
    package util;

    import java.io.IOException;
    import java.net.URLDecoder;
    import java.net.URLEncoder;
    import java.util.Map;

    import javax.servlet.http.Cookie;
    import javax.servlet.http.HttpServletRequest;

    public class Cookies {

        private Map<String, Cookie> cookieMap = new java.util.HashMap<String, Cookie>();

        public Cookies(HttpServletRequest request) {
            Cookie[] cookies = request.getCookies();
            if (cookies != null) {
                for (int i = 0; i < cookies.length; i++) {
                    cookieMap.put(cookies[i].getName(), cookies[i]);
                }
            }
        }

        public Cookie getCookie(String name) {
            return cookieMap.get(name);
        }

        public String getValue(String name) throws IOException {
            Cookie cookie = cookieMap.get(name);

            if (cookie != null) {
                return null;
            }

            return URLDecoder.decode(cookie.getValue(), "UTF-8");
        }

        public boolean exists(String name) {
            return cookieMap.get(name) != null;
        }

        public static Cookie createCookie(String name, String value) throws IOException {
            return new Cookie(name, URLEncoder.encode(value, "UTF-8"));
        }

        public static Cookie createCookie(String name, String value, String path, int maxAge) throws IOException {
            Cookie cookie = new Cookie(name, URLEncoder.encode(value, "UTF-8"));
            cookie.setPath(path);
            cookie.setMaxAge(maxAge);
            return cookie;
        }

        public static Cookie createCookie(String name, String value, String domain, String path, int maxAge) throws IOException {
            Cookie cookie = new Cookie(name, URLEncoder.encode(value, "UTF-8"));
            cookie.setDomain(domain);
            cookie.setPath(path);
            cookie.setMaxAge(maxAge);
            return cookie;
        }
    }
    ```

<br/>

### 쿠키를 사용한 로그인 상태 유지

로그인하지 않은 상태에서 접근하면 로그인하도록 유도하는데, 이는 로그인했는지 여부를 확인하는 방법이 필요하다.  
로그인 상태를 확인할 때 가장 많이 사용하는 방법이 쿠키를 이용하는 것

- 방법
    1. 로그인에 성공하면 특정 이름을 갖는 쿠키 생성
        > 웹 브라우저는 요청을 보낼 때마다 쿠키를 전송
    2. 해당 쿠키가 존재하면 로그인한 상태라고 판단
    3. 로그아웃하면 해당 쿠키 삭제 

- 주의사항
    - 아이디를 평문 형태로 쿠키값으로 사용하면 보안에 문제 발생
        - 웹 브라우저의 자체적인 개발도구를 사용하면 쿠키 값을 쉽게 변경할 수 있다.
        - 이때 다른 아이디로 서버에 접근 가능
    - 다양한 암호화 방식을 혼합해서 저장해야 한다.

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#web-programming)  

<br/><br/>

## 10장 클라이언트와의 대화 2 - 세션

    서버 세션을 사용하면 클라이언트의 상태를 저장할 수 있다.  
    쿠키와의 차이점은 세션은 웹 브라우저가 아니라 서버에 값을 저장한다는 점이다.  
    서버는 세션을 사용하여 클라이언트 상태를 유지할 수 있기 때문에, 로그인한 사용자 정보를 유지하기 위한 목적으로 세션을 사용한다.

<br/>

- **세션**
    - 웹 브라우저에 정보를 보관할 때 쿠키를 사용한다면, 세션은 웹 컨테이너에 정보를 보관할 때 사용한다.
    - 세션은 오직 서버에만 생성된다.

        <p align="center">
        <img src="./images/세션의 기본 개념.PNG" alt="세션의 기본 개념" width="50%" height="50%"/>
        <br/>
        세션은 웹 브라우저와 연관된 서버 영역 저장 공간이다.
        </p>
        <br/>

    - 웹 컨테이너는 기본적으로 한 웹 브라우저마다 한 세션을 생성한다. 
        > 같은 JSP 페이지라도 웹 브라우저에 따라 서로 다른 세션을 사용한다.
    - 웹 브라우저마다 세션이 따로 존재하기 때문에 웹 브라우저와 관련된 정보를 저장하기에 알맞은 장소
        > 쿠키가 클라이언트 측의 데이터 보관소라면 세션은 서버측의 데이터 보관소
    - 쿠키와 마찬가지로 세션도 생성을 해야만 정보를 저장할 수 있다.

<br/>

- **쿠키 VS 세션**  
    - 쿠키 대신 세션을 사용하는 가장 큰 이유는 세션이 쿠키보다 보안성이 좋다는 것.  
        - 쿠키의 데이터는 네트워크를 통해 전달되며 HTTP프로토콜을 사용하는 경우 중간에 누군가 쿠키 값을 읽을 수 있다.
        - 세션의 값은 서버에만 저장된다.
    - 웹 브라우저가 쿠키를 지원하지 않거나 강제적으로 막는 경우 쿠키를 사용할 수 없지만, 세션은 쿠키 설정 여부에 관계없이 사용가능하다.
        - 서블릿/JSP는 쿠키를 사용할 수 없는 경우, URL 재작성 방식을 사용해서 세션 ID를 웹 브라우저와 웹 서버가 공유할 수 있다.
    - 세션은 여러 서버에서 공유할 수 없다. 
        - 반면에 쿠키는 도메인을 이용해서 여러 도메인 주소에 공유할 수 있다.

<br/>

### 세션 사용하기: session 기본 객체

1. **세션 생성하기**
    - JSP에서 세션을 생성하려면 page 디렉티브의 session 속성을 true로 지정
        ```JSP
        <%@ page session = "true" %>
        ```
    - 서버 프로그램에 웹 브라우저가 처음 접속할 때 세션을 생성하고, 이후로는 이미 생성된 세션을 사용한다.

2. **session 기본 객체**
    - 세션을 사용한다는 것은 session 기본 객체를 사용한다는 것
    - session 기본 객체가 제공하는 세션 정보 관련 메소드:
        | 메소드 | 리턴 타입 | 설명 |
        | :----: | :------: | ---- |
        | getId() | String   | 세션 고유 ID를 구한다. |
        | getCreationTime() | long     | 세션이 생성된 시간. 1970/1/1 이후 흘러간 시간이며, 단위는 1/1000초 |
        | getLastAccessedTime() | long | 웹 브라우저가 가장 마지막에 세션에 접근한 시간. 1970/1/1 이후 흘러간 시간이며, 단위는 1/1000초 |

    - **세션 ID**
        - 세션을 구분하는 고유 ID
        - 웹 서버는 웹 브라우저에 세션 ID를 전송
        - 웹 브라우저는 웹 서버에 연결할 때마다 매번 세션 ID를 보내서 서버가 어떤 세션을 사용할지 판단할 수 있게 한다.
        - 웹 서버와 웹 브라우저는 쿠키를 사용하여 세션 ID를 공유한다.
            > *쿠키명: JSESSIONID*

3. **기본 객체의 속성 사용**
    한 번 생성된 세션은 지졍한 유효 시간 동안 유지. 따라서, 웹 어플리케이션을 실행하는 동안 지속적으로 사용해야 하는 데이터의 저장소로 세션이 적당.  
    request 객체가 하나의 요청을 처리하는 데 사용되는 JSP 페이지 사이에서 공유된다면,  
    session 기본 객체는 웹 브라우저의 여러 요청을 처리하는 JSP 페이지 사이에서 공유된다.  
    따라서, 로그인한 회원 정보 등 웹 브라우저와 일대일로 관련된 값을 저장할 때에는 쿠키 대신 세션을 사용할 수 있다.

    - 세션에 값을 저장할 때는 속성을 사용한다.
        - **setAttribute()**: 속성에 값 저장
        - **getAttribute()**: 속성 값 읽기

4. **세션 종료**
    - 세션을 유지할 필요가 없으면 **session.invalidate()** 메소드를 사용해서 세션을 종료한다.
    - 세션을 종료하면 현재 사용 중인 session 기본 객체를 삭제하고 해당 기본 객체에 저장했던 속성 목록도 함께 삭제한다.

5. **세션 유효 시간**
    - 세션은 마지막 접근 이후 일정 시간 이내 다시 세션에 접근하지 않는 경우 자동으로 세션을 종료한다.
    - 세션 유효 시간 설정 방법:
        1. WEB-INF\web.xml 파일에 &lt;session-config&gt; 태그를 사용하여 유효 시간 지정
            ```xml
            <session-config>
                <session-timeout>50</session-timeout>
            </session-config>
            ```
        2. session 기본 객체가 제공하는 **setMaxInactiveInterval()** 메소드 사용
            ```jsp
            <%
                session.setMaxInactiveInterval(60 * 60);
            %>
            ```
            > 시간은 초 단위  
    - 메모리 부족 방지를 위한 세션 타임아웃 시간 지정
        > &lt;session-timeout&gt;의 값을 0이나 음수로 설정하면 세션은 유효 시간을 갖지 않는다.  
        > 이 경우 명시적으로 invalidate() 메소드를 호출하기 전까지 세션 객체가 서버에 유지된다.  
        > 유효시간이 없는 상태에서 invalidate() 메소드를 실행하지 않으면 세션 객체가 계속 메모리에 남게 되어 메모리 부족 현상이 발생한다.

6. **request.getSession()을 이용한 세션 생성**
    - HttpSession을 생성하는 또 다른 방법: request.getSession()
        - 현재 요청과 관련된 session 객체 리턴
    - 사용 예:
        ```jsp
        <%@ page session="false" %>
        <%
            HttpSession httpSession = request.getSession();
            List list = (List)httpSession.getAttribute("list");
            list.add(productId);
        %>
        ```
    - request.getSession() 메소드는 session이 존재하면 해당 객체를 리턴하고, 존재하지 않으면 새롭게 session을 생성하여 리턴한다.
    - session이 존재하는 경우에만 객체를 구하고 싶다면 메소드의 인자로 false를 전달하면 된다. 
        > 만약 존재하지 않는다면 null 리턴

<br/>

### 세션을 사용한 로그인 상태 유지

- 방법
    1. 로그인에 성공하면 session 기본 객체의 특정 속성에 데이터 기록
    2. 이후로 session 기본 객체의 특성 속성이 존재하면 로그인한 것으로 간주
    3. 로그아웃할 경우 session.invalidate() 메소드를 호출하여 세션 종료
        > session.invalidate()를 호출하지 않고 session.removeAttribute() 메소드로 session 기본 객체를 삭제할 수 있다.  
        > 하지만, 로그인할 때 session 기본 객체에 추가하는 속성이 늘어나면 로그아웃 코드도 함께 변경해야 하므로 session.invalidate() 메소드를 사용하는 것 추천

<br/>

### 연관된 정보 저장을 위한 클래스 작성

- 앞서 사용자 정보를 세션에 저장하는 방법
    - 예시 코드: 
        ```jsp
        <%
            session.setAttribute("MEMBERID", memberId);
            session.setAttribute("NAME", name);
        %>
        ```
- **문제점**: 속성에 저장되는 값의 개수나 변수명의 개수가 증가할수록 코드를 분석하고 관리하는 데 어려움이 있음
- **해결방법**: 
    - 연관된 정보는 "클래스"에 묶어서 세션에 저장한다.
    - 각 정보를 개별 속성으로 저장하는 것이 아닌 한 개의 속성을 이용해서 저장

<br/>

### 서블릿 컨텍스트와 세션

- 같은 웹 브라우저라 하더라도 세션 ID 값을 갖는 쿠키는 서로 다른 경로에 있을 때 서로 다른 값을 갖는다.
- 같은 서버에서 서로 다른 경로가 서로 다른 JSESSIONID 값을 사용하는 이유는 두 경로가 서로 다른 웹 어플리케이션이기 때문이다. (같은 웹 브라우저라도 session 기본 객체가 다르다.)
- 다시 말하면, **서로 다른 웹 어플리케이션은 세션을 공유하지 않는다**는 것을 의미한다.

<br/>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#web-programming)  

<br/><br/>
