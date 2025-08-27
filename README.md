# mariaDB

- 관계형 DB 관리 : `SQL 문법` 사용
- MySql(mariaDB 와 매우 비슷한데 유료임), Oracle, PostfreSQL(supabase) 등
- 참고로 비관계형 DB 관리 : `NoSql`
  - Firebase, MongoDB, Redis 등

## 1. 설치

- 참조 : https://tlseoqja.tistory.com/85
- https://mariadb.org/download/?t=mariadb&p=mariadb&r=11.6.2&os=windows&cpu=x86_64&pkg=msi&mirror=blendbyte

## 2. 설치 이후 확인

- `power shell` 에서 진행

```bash
  mysql --version
```

## 3. Maria DB 서버 접속하기

- `power shell` 에서 진행

```bash
  mariadb -u root -p 엔터
```

## 4. 다양한 명령어

- `power shell` 에서 진행

### 4.1. 접속 종료하기

```bash
exit 또는 ctrl +c 입력
```

### 4.2. 시스템 안에 어떤 데이터베이스가 있는지 파악하기

```bash
 SHOW DATABASES;
 반드시 ; 을 입력해서 실행.
```

### 4.3. 나만의 데이터 베이스(파일이라과 생각.. scheme) 만들기

```bash
 CREATE DATABASE board;
 반드시 ; 을 입력해서 실행.
```

### 4.4. 나만의 데이터 베이스(파일이라과 생각.. scheme) 삭제하기

```bash
 DROP DATABASE board;
 반드시 ; 을 입력해서 실행.
```

### 4.5. 나만의 데이터 베이스(파일이라과 생각.. scheme) 만들고 사용하기

```bash
# 만들기
 CREATE DATABASE board;
#  만들어졌는지 확인
 SHOW DATABASES;
#  만든거 사용하기
 USE board;

 반드시 ; 을 입력해서 실행.
```

### 4.6. 나만의 데이터 베이스(파일이라과 생각.. scheme) 이미 존재하는 TABLE 목록 보기

```bash
#  만들어진 테이블 확인
 SHOW TABLES;
# 종료하기
ctrl + c

 반드시 ; 을 입력해서 실행.

```

## 5. 편리한 도구 workbench 설치하기

- [사전설치필요](https://12716.tistory.com/entry/MySQL-MySQL-Workbench-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%98%A4%EB%A5%98-%EB%B0%9C%EC%83%9D%EC%8B%9C-%ED%95%B4%EA%B2%B0)
- https://dev.mysql.com/downloads/workbench/

### 5.1. 커넥션을 생성해 준다.

### 5.2. Query Editor 가 PowerShell 이라고 생각하자.

- 기본은 `SQL 명령어 입력`하고 `;` 을 입력하고 `ctrl + enter` 로 실행

## 6. 실습

```bash
USE board;
```

### 6.1. author 테이블 만들기

- `작가(author)` 라는 테이블 만들기

  - id : 자동 증가 및 PK 역할을 한다.
  - name : 255자
  - email : 255자
  - password : 255자

```sql
  use board;
  -- 작가 테이블 생성
  create table authors(
  id int primary key,
  name varchar(225),
  email varchar(255),
  password varchar(255)
  );
  -- 생성된 테이블의 정보보기
  describe authors;
  -- 실행되어진 테잉블 생성 코드 보기
  show create table authors;
```
