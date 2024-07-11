# Real Mysql 8.0
> [Inflearn | Real MySQL 시즌 1 - Part 1](https://www.inflearn.com/course/real-mysql-part-1)  
> [Inflearn | Real MySQL 시즌 1 - Part 2](https://www.inflearn.com/course/real-mysql-part-2)

### :paperclip: Contents
1. [CHAR vs VARCHAR](#1-char-vs-varchar)
2. [VARCHAR vs TEXT](#2-varchar-vs-text)
3. [COUNT(*) & COUNT(DISTINCT)](#3-count--countdistinct)
4. [페이징 쿼리](#4-페이징-쿼리)
5. [Stored Function](#5-stored-function)

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

## 4. 페이징 쿼리

페이징 쿼리를 사용하는 이유: DB 및 어플리케이션 리소스 효율 증가 및 처리 시간 단축

1. **LIMIT & OFFSET**
    - 특정 위치(offset)에서 특정 수(limit) 만큼 데이터를 가져오는 방법
    - 한계:
      - DB 에 더 부하가 있을 수 있다
      - 특정 offset 이후 데이터만 가져올 수 없음. 해당 위치까지 순차적으로 모든 레코드를 읽어야 함
      - 페이지가 늘어날 수록 더 많은 데이터를 읽어야 하고 점점 부하가 더 커짐
2. **범위 기반 방식**
    - where 절에서 숫자 또는 날짜의 범위를 직접 지정
    - 단순하고 부하가 적음
    - 주로 배치 또는 migration 작업에 사용
    - 쿼리 성능 향상을 위해 범위를 설정하는 컬럼에 대해 인덱스를 생성하는 것이 좋음
3. **데이터 개수 기반 방식**
    - 지정된 데이터 건 수 만큼 결과 데이터를 반환
    - ORDER BY & LIMIT 절이 함께 사용
    - 처음 쿼리와 N회차 쿼리가 다름 (WHERE 절에 사용되는 조건(동등, 범위) 타입에 따라 쿼리 형태가 다름)
    - 저장된 데이터와 서비스 요구사항에 따라 적절한 쿼리가 수행되도록 처리하는 것이 중요
    - 적절히 인덱스를 사용하는 것이 중요
      - 여러 컬럼의 조건을 사용하면서 인덱스를 지정했을 때 order by 에도 동일한 인덱스를 사용할 수 있도록 유의
    - e.g.
      - 1번째 쿼리:
      ```
      SELECT *
      FROM payments
      WHERE user_id = ?
      ORDER BY id
      LIMIT 30
      ```
      - N회차 쿼리:
      ```
      SELECT *
      FROM payments
      WHERE user_id = ?
      AND id > {이전 데이터의 마지막 id}
      ORDER BY id
      LIMIT 30
      ``` 

## 5. Stored Function

### DETERMINISTIC vs NOT DETERMINISTIC

- DETERMINISTIC
    - 동일 상태와 동일 입력으로 호출 -> 동일한 결과 반환
        - 여기서 입력이란, 함수의 인자 뿐만 아니라 함수가 참조하는 데이터도 포함
    - if not -> NOT DETERMINISTIC

