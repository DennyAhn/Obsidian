

## 데이터베이스 시스템의 세계

#### *==1.0 데이터베이스 소개==*

==데이터베이스는 모든 사업에 있어서 필수적인 요소==
- 내부 기록의 보관 (모든 기관 ex. 학교 )
- 동적 웹 - 정보의 공개, 게시판
- 기업의 자료 - 인사, 회계, 재고, ...
- 은행 - 고객, 계좌, 거래 내역, 인터넷 뱅킹, 인터넷 은행
- 과학 및 천문학 - 우주 및 지구의 탄생 연구 데이터 분석
- 생물정보 genome 연구 - 생명의 기원, 유전병 치료
- 생화학자 - 단백질 연구, 신약 개발
- 기타 (IoT, 빅 데이터, Digital Universe)
- 쇼핑, 생활, 문화, 예술, 엔터테인먼트, 교육, 취업

데이터베이스 관련 용어 (Oxford 사전에서)
- 데이터 (data)
```
Data is the quantities, characters, or symbols on which operations are performed by a computer, being stored and transmitted in the form of electrical signals and recorded on magnetic, optical, or mechanical recording media.

Information in raw or unorganized form (such as alphabets, numbers, or symbols) that refer to, or represent conditions, ideas, or objects. Data is limitless and present everywhere in the universe.

데이터는 컴퓨터가 작업을 수행하는 양, 문자 또는 기호로, 전기 신호의 형태로 저장 및 전송되어 자기, 광학 또는 기계적 기록 매체에 기록되는 것입니다.  
  
조건, 아이디어 또는 대상을 참조하거나 나타내는 원시 또는 조직되지 않은 형태의 정보(알파벳, 숫자 또는 기호). 데이터는 무한하며 우주의 모든 곳에 존재합니다.

*** information(정보) ???
```

- ChatGpt에게 물어 봤을 때
```
In computer science, data and information are closely related concepts, but they have distinct meanings:

Data: Data refers to raw facts, symbols, or values that represent the content of information. Data is typically unprocessed and lacks context or meaning on its own. It can be in various forms, such as numbers, text, images, audio, or video. In essence, data is the input that computers process to generate meaningful output.

Information: Information, on the other hand, is the result of processing, organizing, and interpreting data to make it meaningful and useful. Information provides context, meaning, and relevance to data. It answers questions, solves problems, or facilitates decision-making. Information arises when data is analyzed, categorized, structured, and presented in a way that enables understanding or action.

컴퓨터 과학에서 데이터와 정보는 밀접하게 관련된 개념이지만 다음과 같은 뚜렷한 의미를 가지고 있습니다:  
  
데이터: 데이터는 정보의 내용을 나타내는 원시 사실, 기호 또는 값을 말합니다. 데이터는 일반적으로 처리되지 않고 그 자체로 맥락이나 의미가 부족합니다. 숫자, 텍스트, 이미지, 오디오 또는 비디오와 같은 다양한 형태가 될 수 있습니다. 본질적으로 데이터는 컴퓨터가 의미 있는 출력을 생성하기 위해 처리하는 입력입니다.  
  
정보: 반면 정보는 데이터를 의미 있고 유용하게 만들기 위해 데이터를 처리하고 정리하고 해석한 결과입니다. 정보는 데이터와 맥락, 의미, 관련성을 제공합니다. 질문에 답하고 문제를 해결하거나 의사 결정을 용이하게 합니다. 정보는 이해나 행동이 가능한 방식으로 데이터를 분석하고 분류하고 구조화하여 제시할 때 발생합니다.
```

==데이터베이스 - an 'organized' collection of data (정리된 자료집)==
- DBMS를 사용해야만 접근 가능

==데이터베이스 관리 시스템 (DBMS)==
- 데이터베이스를 관리하는 소프트웨어
- Oracle, IBM DB2, Sybase, MS SQL Server, MySQL, ..
- MS Access, SQLite, …

==데이터베이스 시스템==
- 데이터베이스 + DBMS

DBMS의 주요 기능 - 관계형 모델을 가정
1) 영구적인 저장 (Persistent storage)
- 대용량 데이터 관리에 효율적인 자료구조를 제공하는 저장 장치 제공, 파일시스템보다 우수 (개인용 DBMS는 제외)
2) 편리한 프로그래밍 인터페이스
- 우수한 질의 언어를 제공 - SQL
3) 트랜잭션 관리
- 데이터의 동시 접근 지원
- ACID 속성을 지원


#### *==1.1 데이터베이스 시스템의 발전==*

- 데이터베이스란 오랜 기간 동안 존재하는 정보의 모임이다.
- DBMS에 의해 관리
- DBMS의 기능
	1. 데이터베이스와 스키마의 생성 (DDL)
	2. Query (DML)을 사용하여 데이터의 검색 및 변경
	3. 대용량 데이터의 관리
		- 사고 및 인가되지 않은 접근으로부터 안전한 보호
		- 효율적인 접근 기능 - B-tree 색인
	4. 다중 사용자의 지원
		- 데이터의 손상이 발생되지 않게 - 동시성 제어

==1.1.1 초기 데이터베이스 관리 시스템==
- 지금까지 파일 시스템의 단점을 보완 (색인, 동시성, 지속성, 질의 언어 등의 결여)
- DBMS의 중요한 응용 - 주로 작은 크기의 (숫자, 문자) 많은 양의 데이터를 처리, 다양한 검색과 빈번한 데이터 변경이 일어나는 업무에 사용 
  (항공, 철도 등의 전산발매 시스템, banking system, 기업 및 단체의 인사, 재고, 고객 관리 등의  데이터관리)
- 위와 같은 업무에는 DBMS를 사용하는 것이 가장 효과적이다. (자료의 양이 중요)

==데이터 모델의 변화==
- 파일 - > 계층 모델, 네트워크 모델
- 관계형 모델 - 성공
- 객체 관계형 모델
- NoSQL 모델의 등장 - 여전히 관계형 모델

==NoSQL 모델==
- Not only SQL
- 비정형 데이터에 적합
- 스키마가 없다
- ACID 대신 BASE 개념을 사용
- MongoDB와 같은 상용 시스템의 등장
- 이 책의 대부분은 관계형 모델

```
E. “Ted” Codd (1923 – 2003)

- 수학자
- U. of Michigan에서 컴퓨터공학 박사
- IBM에서 데이터베이스 분야 연구
- 1970 “A Relational Model of Data for Large Shared Data Banks”
	- Data be stored independently from hardware
	- A programmer use nonprocedural language
- 1977 Larry Ellison이 Codd의 아이디어를 이용한 상용 DBMS Oracle을 만듦
- nBCNF 이론 정립
```

==1.1.2 관계형 데이터베이스 시스템==
- 데이터베이스를 relation(table)의 모임으로 표현
- 비절차식 고급 언어인 SQL을 사용
- relation - attribute - tuple
- table - field(column) - record

![[Pasted image 20240317153645.png]]

```
SELECT balance
FROM Accounts
WHERE accountNo = 67890;
```

```
SELECT accountNo
FROM Accounts
WHERE type =‘saving’ AND balance < 0;

위의 SQL 문장을 어떻게 수행할 것인지는 DBMS의 Query Processor가 결정한다
```

==1.1.3 소형화 되어가는 DB 시스템==
- Smaller and smaller 
	- 초기에는 대형 컴퓨터의 소프트웨어로 시작
	  지금은 PC, 스마트폰용으로도 개발 (MS Access, SQLite, ..)
![[Pasted image 20240317153912.png]]

==1.1.4 대형화 되어가는  시스템==
- Bigger and bigger
	- 다양한 멀티미디어 데이터 저장(이미지, 동영상)
	- 인공위성 사진, 신호
	- retail chain의 거래 실적
	- Social Media - SNS Facebook
- 엄청난 데이터를 처리하기 위한 방법
	- 3차 저장장치 - tertiary storage의 사용 (tape, CD, jukebox)
	- 병렬 연상 - parallel computing의 필요

==데이터 단위==
- Mega - Giga - Tera - Peta - Exa - Zetta - Yotta
- 10'3 씩 증가 = 2'10
- 1 Zetta = 2'10 Exa = 2'20 Peta
- GoTo PEZY 로 암기

==2025년 세계 디지털 데이터==
- Digital Universe의 크기는 1년에 2배 증가
- 2013년 4.4조 기가 바이트 -> 4.4 Zetta
- 2020년 44조 기가 바이트 -> 44 Zetta
- 2025년 175 Zetta

==데이터 성장 차트==
![[Pasted image 20240317154439.png]]

==1.1.5 Database 응용의 구조 변화==
- Client - server (2 계층)
	- Client - desktop window application
	- Server - database server
- Multi-tier
	- Client – web browser, mobile app
	- Web server, application server
	- Database server
	- 인터넷 응용에 많이 활용
	- 웹 서비스(REST)

Multi-tier (다계층)
![[Pasted image 20240317155851.png]]

==1.1.6 multimedia data==
- video, audio, radar signal, ….
- 기존의 데이터보다 크기가 훨씬 커졌다.
- 내용 기반 유사 검색의 지원
	- 노래의 일부 - > 무슨 노래인지(네이버)
	- QbSH (Query by Singing/Humming)
- 데이터의 저장은 데이터베이스 분야에서
- 데이터의 분석은 python, R, .. 분석 전문 패키지들을 활용

==1.1.7 Information Integration==
- 현존하는 분산된 데이터의 통합 – 서로 구조가 다르며 또 다른 용어를 사용 – legacy database
- 데이터웨어하우스 – 데이터베이스 위에 구축

![[Pasted image 20240317160047.png]]

DW에서의 연산 - OLAP
![[Pasted image 20240317160140.png]]

==데이터마이닝, Knowledge Discovery==
- 숨어 있는 유익한 패턴을 발견
- Data analysis - 연관 분석
- 빅 데이터 활용


#### *==1.2 Overview of DBMS (DBMS의 개요)==*

==1.2.0==
- DBA - DDL (Data Definition Language)
- 일반 사용자 - DML (Data Manipulation Language)

![[Pasted image 20240317160432.png]]

![[Pasted image 20240317160534.png]]

Overview of DBMS - SQLite3
![[Pasted image 20240317160557.png]]

==1.2.1 데이터 정의 명령어들==
- 스키마 생성 및 변경 (DDL)
	- CREATE TABLE ...
	- CREATE INDEX ...
	- ALTER TABLE ...
- DDL도 뒤에 나오는 쿼리와 같은 방식으로  실행

==1.2.2 질의(DML) 처리의 개요==
```
SELECT *
FROM Movie
WHERE title = ‘Star Wars’ AND year = 1997;
```
- 질의 -> 질의 컴파일러 -> 최적화된 질의 계획 생성
- 생성된 질의계획 (plan)은 실행 엔진으로 전달
- storage manager, transaction manager의 협력으로 실행

==1.2.3 저장 및 버퍼 관리==
- 일반적으로 데이터는 2차 저장장치에 저장
- DBMS의 저장관리기가 하드디스크를 관리
- DBMS의 버퍼관리기는 캐쉬 기능 수행
- DBMS의 구성 요소들이 필요로 하는 정보의 종류
	- 데이터
	- 메타 데이터 – 데이터의 구조, 제약 조건(키, unique,..
	- 통계 정보 – 데이터 히스토그램 (각 컬럼의 값의 분포)
	- 색인 – B-tree

==1.2.4 Transaction Processing==
- DBMS에서 가장 어려운 부분
-  ACID 속성을 제공하기 위해  DBMS 다른 부분들과 서로 협동

- Transaction - 데이터베이스에 가해지는 일의 단위로 ACID 속성을 가진다. ( DBMS가  ACID  속성을 가지게 한다.)
- 프로그래머는 트랜잭션 범위만 정해주면 된다.
```
Atomicity  원자성
Consistency 일관성
Isolation 고립성, 독립성
Durability 지속성
```

==Atomicity (원자성)==
- all-or-nothing의 속성
- 전부 일어나든지, 전혀 일어나지 않은 상태로 남아야 한다
- 데이터의 변화가 부분적으로만 수행되는 일은 없어야 한다
- Commit, Rollback 2개의 선택만을 가지게 된다
- Logging 을 이용
```
**계좌 A 에서 계좌 B 로 현금 이체

W = 이체 액수
BEGIN Transaction
A = A -W; (update A)
-
-
B = B + W;  (update B)
END Transaction (Commit)

**전혀 이체가 되지 않든지, 정상적으로 이체가 되든지
```

==Isolation (고립성)==
- 비록 어떤 트랜잭션이 다른 트랜잭션(변경시키는 데이터에 중복이 있는)과 동시에 수행이 되더라도 다른 트랜잭션이 변경 중에 있는 데이터는 볼 수 없어야 한다. 이 성질은 일반적으로 Locking을 이용하여 지원한다.
- Isolation level은 (고립성의 정도)

==SQL 표준의 isolation level==
- READ UNCOMMITTED
	- 다른 트랜잭션에 의해 변경 중인 데이터를 볼 수도 있다.
- READ COMMITTED
	- 다른 트랜잭션이  커밋한 데이터만 볼 수 있다.
	- 하지만 non-repeatable read가 발생할 수 있다.
- REPEATABLE READ
	- non-repeatable read는 막는다.
	- phantom read가 발생할 수 있다.
- SERIALIZABLE
	- 가장 강한 조건이다.
	- phantom read를 막는다.

```
- Isolation이 지켜지지 않으면
ex) 계좌 A에 100,000원이 있을 경우

(Transaction T1)
BEGIN TR
-
A = A - 10,000원
-
END TR

(Transaction T2)
BEGIN TR
-
A = A - 20,000원
-
END TR
```


```
- Isolation 올바른 동작
ex) 계좌 A에 100,000원이 있을 경우

(Transaction T1)
BEGIN TR
-
A = A - 10,000원
-
END TR

(Transaction T2)
BEGIN TR
-
A = A - 20,000원
-
END TR
```

==Durability (지속성)== 
-  트랜잭션이 정상적으로 종료하면 그 트랜잭션이 변화 시킨 데이터의 영향은 다른 트랜잭션에 의한 데이터의 변화 없이는  보존되어야 한다.  커밋된 내용은 시스템을 다시 부팅해도 변화되지 않아야 한다.

```
- Durability
ex) 계좌 A에서 계좌 B로 현금 이체

W = 이체 액수
BEGIN Transaction
A = A - W; (updata A)
-
-
B = B + W; (updata B)
END Transaction (Commit)

** 다른 트랜잭션이 A,B를 변경하지 않는 이상 A, B의 값은 변화되지 않는다
```

==Consistency 일관성==
- 트랜잭션의 수행은 consistant 상태에  있는 데이터베이스를 다시 consistant 상태로 변화시킨다.(프로그래머와 DBMS 모두의 책임)
- (프로그래머가 올바르게 프로그램 했다고 가정)

```
- Consistency
ex) 계좌 A에서 계좌 B로 현금 이체

W = 이체 액수 (상태 A + B = P)
BEGIN Transaction
A = A - W; (updata A)
-
-
B = B + W; (updata B)           ## B = B + (W - 10)
END Transaction (Commit)

** (상태 A + B = P)
```

Locking and Logging
- Locking - 2개 이상의 서로 다른 트랜잭션이 같은 데이터를 동시에 변경하는 경우 - 데이터의 무결성을 유지하기 위한 방법이 필요 - locking으로 해결
- Logging - 데이터의 변경이 발생할 때 마다 변경된 내용을 기록하여 데이터를 원상 복귀하는데  사용한다. 급작스러운 정전이나 사고 시에도 로그는 보존되어야 하므로 일반적으로 nonvolatile storage (하드디스크, 테이프)에 보관된다.

```
- 트랜잭션 예제 C# .NET 프로그램

oracleConnection1.Open();
oralceTransaction txn = oracleConnection1.BeginTransaction();
String str1 = “UPDATE myTable SET bal = bal – 10,000 WHERE a_id = :input1";
String str2 = “UPDATE myTable SET bal = bal + 10,000 WHERE a_id = :input2”;

oralceCommand1.Transaction = txn; // 2개의 SQL이 1개의 트랜잭션 txn에 연결
oralceCommand2.Transaction = txn;
oracleCommand1.commandText = str1;
oracleCommand2.commandText = str2;
…
int recordAffect = oracleCommand1.ExecuteNonQuery(); // 실제 트랜잭션 시작
if (recordAffect == 1) // command1이 잘 실행되었으면
{
  recordAffect = oracleCommand2.ExecuteNonQuery();
  if (recordAffect == 1)
       txn.Commit(); // Commit
  else
       txn.Rollback(); // 롤백 – 처음 시작한 상태로 되돌린다.
}
```

==1.2.5 질의 처리기==
```
SELECT EMP.ID, DEPT.DNAME
FROM DEPT, EMP
WHERE EMP.DEPTID = DEPT.ID
	AND EMP.ID > 5000;
```
- 질의 컴파일러
	- 질의 파서
	- 질의 전처리기 - 의미 조사, 여러개의 플랜을 생성
	- 질의 최적화기 - 플랜 중에서 가장 빠를 것 같은 것을 선택

==1.2.6 DB 과목에서 다루는 내용==
- Database design (데이터베이스 설계)
	-   DB에 어떤 정보를 저장할 것인가, 데이터를 어떤 형태로 구성 할 것인가
- Database Programming
	 -  데이터베이스에 대한 연산을 위한 window, query, transaction, 또는 trigger를 어떻게 작성 할 것인가
- Database system implementation
	 -  DBMS 즉 query processor, transaction manager, storage manager를 어떻게 만들 것인가

** database design과 database programming을 위한 내용을 주로 설명

==데이터베이스 디자인과 프로그래밍==
- 이미 존재하고있는 유형,무형의 데이터를 컴퓨터상의 데이터구조로 만드는 작업 – 디자인
- 관계형 데이터베이스를 사용하는 경우
	- 분석 – ER Diagram – 테이블 설계 – 구현