---
layout: post
title:  "SQL vs NoSQL"
date:   2021-10-19 22:19:00 +000
categories: Database
---
SQL vs NoSQL (MySQL vs MongoDB)

---
### Description
토이 프로젝트를 시작하면서, 관계형과 비관계형 DB에 대한 차이를 학습하고 기록한 블로그 입니다.
---
### Index
# 1. 들어가며
> 상황에 맞게 DBMS 를 선택하고, 활용하기 위해 차이점을 이해하고 사용 합니다.

# 2. SQL vs NoSQL
> |		|	SQL 데이터베이스	|	NoSQL 데이터베이스	|
> |	---	|	---	|	---	|
> |	데이터 저장 모델	|	행과 열이 고정된 테이블	|	문서: JSON 문서, 키-값: 키-값 쌍, 와이드 열: 행과 동적 열이 있는 테이블, 그래프: 노드 및 가장자리	|
> |	개발 이력	|	데이터 중복 감소에 중점을 두고 1970년대에 개발됨	|	2000년대 후반에 확장에 중점을 두고 애자일 및 DevOps 방식에 따라 신속한 애플리케이션 변경을 허용하도록 개발되었습니다.	|
> |	예	|	Oracle, MySQL, Microsoft SQL Server 및 PostgreSQL	|	문서: MongoDB 및 CouchDB, 키-값: Redis 및 DynamoDB, 와이드 컬럼: Cassandra 및 HBase, 그래프: Neo4j 및 Amazon Neptune	|
> |	주요 목적	|	범용	|	문서: 범용, Key-value: 단순 조회 쿼리로 대용량 데이터, Wide-column: 예측 가능한 쿼리 패턴으로 대용량 데이터, Graph: 연결된 데이터 간의 관계 분석 및 탐색	|
> |	스키마	|	엄격한	|	유연한	|
> |	스케일링	|	수직(더 큰 서버로 확장)	|	수평(일반 서버 전반에 걸쳐 확장)	|
> |	다중 레코드 ACID 트랜잭션	|	지원	|	대부분은 다중 레코드 ACID 트랜잭션을 지원하지 않습니다. 그러나 MongoDB와 같은 일부는 그렇게 합니다.	|
> |	조인	|	일반적으로 필수	|	일반적으로 필요하지 않음	|
> |	데이터-객체 매핑	|	ORM(객체 관계형 매핑) 필요	|	많은 경우 ORM이 필요하지 않습니다. MongoDB 문서는 가장 널리 사용되는 프로그래밍 언어의 데이터 구조에 직접 매핑됩니다.	|


# 3. 장/단점 



### Reference 
> - [siyoon210]
> - [mongoDB]

[siyoon210]: https://siyoon210.tistory.com/130
[mongoDB]: https://www.mongodb.com/nosql-explained/nosql-vs-sql
