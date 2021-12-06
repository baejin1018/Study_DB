# 데이터베이스

## 데이터란?

### Data(자료) : 관찰, 검색 또는 측정을 통해 수집되는 사실이나 값

### 정보 : 자료의 유효한 해석, 지식

<br>

## 일괄 처리 시스템

### 데이터를 수집해서 분류하고 정렬시킨 다음에 일괄 처리하는 데이터 처리방법

<br>

## 온라인 처리 시스템

### 데이터가 생성되는 즉시 전송하여 컴퓨터가 즉시 처리하는 시스템

### 하나의 데이터베이스에서 처리

<br>

## 분산 처리 시스템

### 여러개의 데이터베이스에서 처리하고 통신 네트워크로 공유한다.

### 온라인 처리시스템보다 효율적이다

<br>

## 데이터베이스란?

### 여러응용 시스템들이 공용할 수 있도록 통합 저장된 운영 데이터

<br>

## 데이터베이스의 정의

### 저장데이터

- #### 문서보관이 아닌 하드디스크나 서버에 저장되어 있는 데이터의 의미

### 통합 데이터

- #### 여러 곳에서 사용하던 데이터를 통합하여 하나로 저장된 데이터를 의미
- #### 똑같은 데이터가 중복되어 있지 않다

### 공용데이터

- #### 공용으로 사용되는 데이터를 의미
- #### 여러 사용자들이 서로 다른 목적으로 데이터베이스의 데이터를 공동으로 이용
- #### 데이터의 양 대규모화

### 운영 데이터

- #### 조직의 목적을 위해 사용되는 데이터를 의미
- #### 단순한 입출력 데이터나 일시적으로 생성된 임시 데이터는 운영데이터가 아니다
<br>

## 데이터 베이스의 특성

### 실시간 접근성

- #### 데이터 베이스는 실시간 서비스다
- #### 사용자가 요청하는 순간 바로 서비스를 해준다

### 계속적인 변화

- #### 데이터는 계속 바뀐다
- #### 데이터베이스는 삽입 삭제 수정등의 작업으로 바뀐 값을 저장

### 동시 공용

- #### 서로 다른 사용자에게 동시에 공유된다
- #### 동시에 공유되기 때문에 종속성, 중복성, 해결해야함

### 내용에 의한 참조

- #### 저장된 데이터의 주소가 아닌 데이터 값을 참고
- #### 사용자가 조건(쿼리)를 제시하면 DB는 데이터를 검색 후 보내줌
<br>

## 파일 시스템

#### 각각 응용프로그램이 독립적으로 자료를 파일형태로 관리

<br>

## 데이터 중복성

#### 한 시스템내의 자료가 중복저장되어 추가적인 저장 공간필요, 자료를 비효율적으로 관리

<br>

## 데이터 종속성

#### 자료간의 상호 의존도가 높아서 하나의 파일을 변경하면 관련 파일도 변경해야 한다

# DBMS (데이터베이스 관리 시스템)

## DBMS의 장점

- #### 데이터를 공유하기 때문에 종속성 문제 해결
- #### 중복제거로 데이터 일관성 유지
- #### 데이터 복구, 보안이 쉬움
- #### 하나의 갱신작업만 수행해도 되기 때문에 경제성 좋음
<br>

## DBMS의 단점

- #### DBMS,CUP, 메모리 용량 등 비용발생
- #### 복잡한 백업과 회복
- #### 시스템 취약성
<br>

## DBMS 기능

### 데이터 정의

- #### 데이터의 구조를 정의하고 데이터 구조에 대한 삭제및 변경 기는 수행

### 데이터 정의어 (DDL)

- #### SQL의 `CREATE`, `ALTER`, `DROP` 과 같이 구조를 정의

### `CREATE` 기본형식

```
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  column2 datatype,
  ...
);
```

#### 자료형에는 `int` `varchar` `float`

### `PRIMARY KEY` 설정방법

```
CREATE TABLE 테이블이름(
   column1 datatype,
   column2 datatype,
   에트르뷰트명 타입 PRIMARY KEY
);
```

### `ALTER` 자료형수정

```
ALTER TABLE [테이블명]
MODIFY [컬럼명] [타입];
```

#### MODIFY : 컬럼 속성변화

### `ALTER` 속성 추가

```
ALTER TABLE [테이블명]
ADD [컬럼명] [타입];
```

#### ADD : 컬럼 추가

#### 가장 앞에 추가하고 싶다면

```
ALTER TABLE [테이블명]
ADD [컬럼명] [타입] first;
```

이렇게사용

### `ALTER` 속성 제거

```
ALTER TABLE [테이브러명]
DROP [컬럼명]
```

### `ALTER` 속성 변경

```
ALTER TABLE [테이블명] CHANGE
[변경 전 컬럼명] [변경후 컬러명] [컬럼타입]
```

### `DROP` 활용

`DROP TABLE [테이블명];

### 데이터 조작

- #### 데이터의 검색 삽입 수정 삭제 작업을 지원

### 데이터 조작어 (DML)

- #### SQL의 `SELECT`, `INSERT`, `DELETE`,`UPDATE` 문과 같이 데이터를 검색, 삽입, 삭제, 수정하는데 사용

#### `SELECT` 기본형식

```
SELECT 애트리 뷰트명
FROM 테이블명
WHERE 조건 ;
```

#### `INSERT` 기본형식

```
INSERT
INTO 테이블명 (애트리뷰트)
VALUES(값);
```

#### `UPDATE` 기본형식

```
UPDATE 테이블명
SET 애트리뷰트명
WHERE 조건;
```

#### `DELETE` 기본형식

```
DELETE
FROM 테이블명
WHERE 조건;
```

### 데이터 제어

- #### 데이터베이스 사용자를 생성하고 모니터링하며 접근을 제어 백업과 회복, 동시성 제어

### 데이터 제어어 (DCL)

- #### SQL의 `GRANT`, `REVOKE` 문과 같이 데이터의 사용 권한을 관리
<br>

## DBMS의 사용자들

### 일반 사용자

- #### 데이터의 검색 삽입 수정을 하는 사용자 ( web이나 app에서 클릭만을 조회하는 사람)

### 응용프로그래머

- #### 일반 사용자가 사용할수 있도록 프로그램을 만드는사람
- #### SQL 번역해서 일반사용자가 원하는 데이터를 DBMS에 접근하도록 도와주는 사람

### DBA (database administrator)

- #### 데이터베이스 총괄 책임자
- #### 데이터 설계, 구현, 유지보수 전 과정 담당
- #### 사용자 통제, 보안, 성능 모니터링, 데이터 관리

### 사용자별 갖추어야 할 지식

|                | SQL언어 | 프로그래밍언어 | DBMS 지식 | 데이터 구성 |
| -------------- | ------- | -------------- | --------- | ----------- |
| 일반사용자     | X       | X              | X         | X           |
| 응용프로그래머 | O       | X              | O         | O           |
| DBA            | O       | O              | O         | O           |

<br>

# 스키마

### 데이터 베이스의 구조와 제약조건에 관해명세

![title](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMDA0MDFfMjcg%2FMDAxNTg1NzM0NDE5MjU1.w83w5QL7N10P_Ld0FxNioVvHq-dgNi7ZIlMwLmNO3jAg.GBGqtgTPFTZgFEFeIe2eCi1EZDf_vjrUvuwTrjzzZCUg.PNG.dg2610%2F1.PNG&type=sc960_832)

### 개념 스키마 : 전체 데이터베이스의 정으를 말하며 하나만 존재

### 외부 스키마 : 각 사용자나 응용프로그래머가 각자 필효한 논리적 구조를 정의

### 내부 스키마 : 물리적 저장 위치에 데이터 베이스의 저장위치 명세

# 릴레이션

### 릴레이션 : 테이블(표)

### 릴레이션 스키마 : 속성들의 집합

### 릴레이션 인스턴스 : 데이터들의 집합![title](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMTA0MTNfMjI4%2FMDAxNjE4MzEzMzAxNDc3.81EZ7OVMAp5HvljHe9Ir6BQztW4jgSQR_WN-0nQfZqcg.tnGJ1FztAkiD6VSATiJVFPAq9Z12Tw8wfDIWjyZKJvgg.PNG.vic9309%2Fimage.png&type=sc960_832)

# Key

### 식별한다는 의미 키로인해 특정 튜플을 식별할때 사용하는 속성을 말함

## 키의 종류

- ### 슈퍼키
  #### 튜플을 유일하게 식별할수 있는 속성 집합
- ### 후보키
  #### 튜플을 유일하게 식별할 수 있는 속성의 최소 집합
- ### 기본키
  #### 여러 후보키중 하나를 선정하여 사용하는 대표키
  #### 후보키중 마음대로 선택
  #### 튜플을 식별할수 있는 고유한 값
  #### NULL 값 허용 X
  #### 키 값 변동 X
  #### 최대한 적은 수의 속성을 가진것
- ### 대체키

  #### 기본키를 제외한 나머지 후보키

  ![title](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMDA1MjZfMTk3%2FMDAxNTkwNDYxMDc1MjUz.5YMxdUOK6kz794jicKzPzHJIvE4XNVnSUtEbesNiVZQg.rYbEE28v_aqhChfBV8onYAGmC-c7oZJI6oiP2PQlyJQg.PNG.dlwnsgud0210%2F%25B1%25D7%25B8%25B21.png&type=sc960_832)

- ### 외래키
  #### 다른 릴레이션을 참조할때 참조하는 기본키
  ![title](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2F20140508_95%2Fsooyeonly_13995607197508Joqo_JPEG%2F%25BF%25DC%25B7%25A1%25C5%25B01.jpg&type=sc960_832)

### 외래키 조건 사용법

`FOREIGN KEY 고객번호 REFERENCES 고객(고객번호) ON DELETE ~~` <br>
REFERENCES 테이블 이름 (애트리뷰트) , ON DELETE 삭제 시 조건 , ON UPDATE 수정시 조건

### FOREIGN KEY 사용법

- #### RESTRICT 변경/삭제할 경우 연산 취소
- #### CASCADE 변경/삭제할 경우 함께 변경/삭제
- #### NO ACTION restrict와 동일하게 동작
- #### SET NULL 부모 릴레이션에서 값 변경/삭제 시 자식 릴레이션 값 NULL로 세팅

# 무결성 제약조건

### 도메인 무결성 제약

![title](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSMe_krYFdS0cFVkZOK_W1Z8aPvoPbAlB7I8A&usqp=CAU)

#### 각 애트리뷰트(속성)들의 도메인의 지정된 값 만을 가져야함

#### SQL 작성할때 Type, NULL, default,check 등을 사용 해 지정

# 개체 무결성 제약조건

#### 기본키의 조건을 지켜야한다는 제약조건

# 참조 무결성 제약조건

#### 외래키의 조건을 지켜야 한다는 제약조건

#### 부모릴레이션의 기본키를 그대로 사용

![title](data:image/jpeg;base64,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)

# 관계대수

#### 관계형 데이터베이스 내에서 원하는 정보를 어떻게 찾아낼수 있는가를 기술하는 절차적 언어

## 셀렉트 (σ)

#### 릴레이션에서 주어진 조건에 만족하는 튜플을 선택하는 연산자

![title](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTD8jbfOAUm3SdEfbYyp8C-yEG0dfsE-iJgTw&usqp=CAU)

## 프로젝트 (π)

#### 필요한 속성들만 추출하는 연산

#### 중복 제거

![title](https://t1.daumcdn.net/cfile/tistory/23791E495920693728)

## 디비전

#### 2개의 릴레이션에서 피연산 릴레이션의 속성값을 모두 가진 연산 릴레이션의 속성을 제외한 속성만을 구하는 연산

![title](https://t1.daumcdn.net/cfile/tistory/2458C23C59206A6810)

## 합집합 (유니온 , U)

#### 두 릴레이션 합하여 하나의 릴레이션으로 반환

#### 중복 제거

## 교집합 (U거꾸로)

#### 두 릴레이션 모두 속한 튜플로 이루어진 릴레이션

![title](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTxRXkIG9WqKsrRDepjJncd-gHh7xyH4ZG8dg&usqp=CAU)

## 차집합(-)

#### 피연산 릴레이션에 속하지 않은 튜플로 이루어진 릴레이션![title](https://t1.daumcdn.net/cfile/tistory/2252CB4E59206AD11D)

## 카티션 프로덕트 (X)

#### 연산릴레이션과 피연산 릴레이션 곱하는것

#### 중복 허용

![title](https://t1.daumcdn.net/cfile/tistory/2306D34859206B670F)

### 조인이 필요한 이유

#### 카티션 프로덕트를 하면 매우 많은 튜플이 새성됨

#### 필요한 자료만 보기위해 조인 사용

## 자연조인

#### 동등 조인 결과로 얻어진 불필요한 애트리뷰트 제외한 조인

#### 중복 애트리뷰트 제거![title](https://t1.daumcdn.net/cfile/tistory/262DCE3E592069E423)

## 세타조인

#### 조인 연산시 조건이 붙는 조인

#### Ex) <,>,=,<>,<=,>=![title]

## 동등조인

#### 세타 조인의 종류중 조건이 = 일 경우

## 세미조인

#### 자연조인 한후 두 릴레이션중 한쪽 릴레이션 결과만 반환

#### 기호가 닫힌 쪽 튜플만 반환

## 외부조인

#### 조인연산 시 외부조인 하는 릴레이션의 정보를 버리지 않고 보여줌

#### 꼭 필요한 정보둘울 넘겨두기 위해 사용

#### 해당 정보가 없는 곳은 NULL 채움

![title](https://mblogthumb-phinf.pstatic.net/MjAxNjExMjZfOTEg/MDAxNDgwMTU4NzI1MDUx.2Wp6eD7uN-BeegJWrBuT9yNkc-HB_tEuad8UiDygunAg.F8vxXS0DwnF_ff5qEgqW0BXtg5AZg5lrmh1gG_0xPIsg.JPEG.zxy826/7.PNG?type=w2)  
![title](https://mblogthumb-phinf.pstatic.net/MjAxNjExMjZfMTMy/MDAxNDgwMTU4ODU3MTQ5.GRZY5fetkytHr2PitU6TwdOJOfma1uavoz9o4jg6e6Eg.A6u0qOaz1ejlK8_KHeYgFISPXWfKmMWDODp6_KvnFRcg.JPEG.zxy826/8.PNG?type=w2)

# 집계함수

## `SUM` 기본형식

```
SELECT SUM(애트리뷰트명)
FROM 테이블명
WHERE 조건;
```

### Ex)

### test

| title1 | title2 | title3 |
| ------ | ------ | ------ |
| 1      | 2      | 3      |
| 4      | 5      | 6      |
| 7      | 8      | 9      |

### select sum(title1) from test;

| sum(title1) |
| ----------- |
| 12          |

## `AVG` 기본형식

```
SELECT AVG(애트리뷰트명)
FROM 테이블명
WHERE 조건;
```

### Ex)

### test

| title1 | title2 | title3 |
| ------ | ------ | ------ |
| 1      | 2      | 3      |
| 4      | 5      | 6      |
| 7      | 8      | 9      |

### select AVG(title2) from test;

| sum(title2) |
| ----------- |
| 5           |

## `MIN` `MAX` 기본형식

```
SELECT MIN(애트리뷰트명)
FROM 테이블명
WHERE 조건;
```

### Ex)

### test

| title1 | title2 | title3 |
| ------ | ------ | ------ |
| 1      | 2      | 3      |
| 4      | 5      | 6      |
| 7      | 8      | 9      |

`select min(title1), max(title2) from test`
| min(title1) | max(title2) |  
| --- | --- |
| 1 | 8 |

## `COUNT` 기본형식

```
SELECT COUNT(애트리뷰트명)
FROM 테이블명
WHERE 조건;
```

### Ex)

### test

| title1 | title2 | title3 |
| ------ | ------ | ------ |
| 1      | 2      | 3      |
| 4      | 2      | 6      |
| 7      | 8      | 9      |

`SELECT count(_) from test where title2=2;
| count(_) |
| --- |
| 2 |

## `GROUP BY` , `HAVING` 기본형식

```
SELECT 애트리뷰트명
FROM 테이블명
GROUP BY 애트리뷰트명
HAVING 조건 ;
```

<br>

# JOIN

### `JOIN` 기본형식

```
SELECT 애트리뷰트명
FROM 테이블명 JOIN 조인할 테이블명
USING (애트리뷰트명);
```

### `INNER JOIN` 사용법

```
SELECT 애트리뷰트명
FROM 조인할 TABLE INNER JOIN 조인할 TABLE
ON 조인에 사용될 애트리뷰트조건
```

## 자연조인 사용법

```
SELECT 애트리뷰트명
FROM 조인할 TABLE NATURAL JOIN 조인할 TABLE;
```

### 자연조인 유의점

- #### 조인에 참여하는 애트리뷰트 중 이름이 같은 모든 애트리뷰트를 활용하여 조인
- #### 동등조인과의 차이점 중복되는 애트리뷰트 하나만 출력

# 외부조인 (OUTER JOIN)

#### 조인연산시 외부조인 하는 릴레이션의 정보를 버리지 않고 보여줌

#### 꼭 필요한 정보들을 남겨두기 위해 사용

#### 해당 정보가 없는 곳은 null 값 채움

```
SELECT 애트리뷰트명
FROM 조인할 TABLE OUT JOIN 조인할 TABLE
ON 애트리뷰트 = 애트리뷰트;
```

![title](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2Fdata17%2F2006%2F5%2F30%2F185%2Fouterjoin_01-jinsol1.gif&type=a340)  
<br>

# LIKE , %, -

### 1. 특정문자로 시작하는 데이터 검색

`SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '특정문자열%'`

#### 뒤에 자리수는 상관 X 문자열만 있어도 검색

### 1. 특정문자로 끝나는 데이터 검색

`SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '%특정문자열'`

#### 뒤에 자리수는 상관 X 문자열만 있어도 검색

### 1. 특정문자를 포함하는 데이터 검색

`SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '%특정문자열%'`

#### 앞,뒤에 자리수는 상관X 문자열만 있어도 검색

### 1. 특정문자로 시작하는 데이터 검색

`SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '_특정문자열%'`

#### 앞자리수는 1칸 상관없이 , 나머지 문자열중 해당 문자열만 있어도 검색

<br>

# EXISTS와 IN의 차이

#### `EXISTS` 연산자의 처리순서는 `메인쿼리` -> `서브쿼리`

#### 서브쿼리에서 메인의 정보를 가져올 수 없기 때문에 조건을 각각 설정

#### `IN` 연산자의 처리순서는 `서브쿼리` -> `메인쿼리`

#### 서브에서 메인의 정보를 가져와 모든 조건을 한번에 정리

#### `IN`과 `EXISTS` 는 기능상 차이점은 없지만 수행 시간 관점에서는 차이점이 보임

#### `NOT IN`과 `NOT EXISTS`는 같은 결과가 나올것 같지만 `NOT IN`은 NULL이 포함될 경우 값을 반환하지 못함

# ANY, SOME, ALL

### 서브쿼리와 값비교

### `ANY`,`SOME` : 서브쿼리의 값중 조건에 하나라도 만족할 경우 참

### `ALL` : 서브쿼리의 값 중 조건에 모두 다 만족할경우 참

# IF, CASE

### `IF`와 `CASE`는 `SELECT` 절에 쓰인다

### `IF`는 C언어 3항연산자와 비슷

`IF(조건, 참 ,거짓)`

### `CASE`사용법

```
CASE
    WHEN(조건) THEN 결과
    WHEN(조건) THEN 결과
    ...
END (AS 애트리뷰트명)
```

# CONCAT

### 문자열 연결

```
CONCAT(속성'연결할 문자' 속성)
```
