# Real Mysql 8.0
> [Inflearn | Real MySQL 시즌 1 - Part 1](https://www.inflearn.com/course/real-mysql-part-1)  
> [Inflearn | Real MySQL 시즌 1 - Part 2](https://www.inflearn.com/course/real-mysql-part-2)

### :paperclip: Contents
1. [CHAR vs VARCHAR](#1-char-vs-varchar)
2. [VARCHAR vs TEXT](#2-varchar-vs-text)
3. [COUNT(*) & COUNT(DISTINCT)](#3-count--countdistinct)

---

<br>

## 1. CHAR vs VARCHAR
### 공통점:
- 문자열 저장용 컬럼
- 최대 저장 가능 문자 길이 명시 (Byte 가 아님)
### 차이점:
- **CHAR**
  - 최대 255 문자
  - 저장된 문자의 길이와 상관 없이 최대 설정된 크기만큼 공간 할당
  - 저장된 값의 길이를 별도로 관리하지 않음
  - 가변길이 문자 set을 저장하는 경우 예약하는 공간을 바이트로 관리 (VARCHAR 형식과 비슷한 특성을 가짐)
    - e.g. `UTF8MB4 character set` & `CHAR(10)`
      1. _'한글'_ 이라는 문자를 저장했을 때 총 6byte 를 사용하므로 4byte 를 예약 공간으로 남겨둔다.
      2. _'한글연습'_ 이라는 문자를 저장했을 때 총 12byte 를 사용하므로 별도 예약 공간을 할당하지 않는다.
- **VARCHAR**
  - 최대 16383 문자
  - 저장된 문자의 길이 만큼만 저장 공간 할당
  - 저장된 값의 길이(byte 수)를 별도로 관리 (1~2 byte)
### 용도:
- 통용되는 (잘못된) 방식: ~고정된 길이의 값 저장은 CHAR, 그 외의 경우엔 VARCHAR~
- 저장되는 문자열의 최소, 최대 길이 가변 폭이 큰 경우엔 CHAR 타입은 공간 낭비가 심할 수 있음
- 저장되는 문자열의 가변길이 폭이 좁고 자주 변경되는 컬럼(특히 index)의 경우 CHAR 타입이 적합
  - VARCHAR 의 경우 가변적으로 레코드를 저장함으로 인해 성능의 저하가 존재
    - 문자열의 길이가 변경되었다면, 새로운 빈 공간에 레코드를 삽입 & 기존 레코드 삭제. (오히려 공간 효율이 떨어질 수 있음)
    - 데이터 페이지 내부 조각화 현상 발생 / 레코드 저장 구조가 변경됨으로 추후 compaction(page reorganize) 작업이 수반

## 2. VARCHAR vs TEXT

## 3. COUNT(*) & COUNT(DISTINCT)
