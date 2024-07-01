# Real Mysql
> [Inflearn | Real MySQL 시즌 1 - Part 1](https://www.inflearn.com/course/real-mysql-part-1)  
> [Inflearn | Real MySQL 시즌 1 - Part 2](https://www.inflearn.com/course/real-mysql-part-2)

### :paperclip: Contents
1. [CHAR vs VARCHAR](#1-char-vs-varchar)
2. [VARCHAR vs TEXT](#2-varchar-vs-text)
3. [COUNT(*) & COUNT(DISTINCT)](#3-count--countdistinct)

---

<br>

## 1. CHAR vs VARCHAR
- 공통점:
    - 문자열 저장용 컬럼
    - 최대 저장 가능 문자 길이 명시
        - 바이트 수가 아님
- 차이점:
    - CHAR
        - 최대 255 문자
        - 저장된 문자의 길이와 상관 없이 최대 설정된 크기만큼 공간 할당
        - 저장된 값의 길이를 별도로 관리하지 않음
    - VARCHAR
        - 최대 16383 문자
        - 저장된 문자의 길이 만큼만 저장 공간 할당
        - 저장된 값의 길이(byte 수)를 별도로 관리 (1~2 byte)

## 2. VARCHAR vs TEXT

## 3. COUNT(*) & COUNT(DISTINCT)
