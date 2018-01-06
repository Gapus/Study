# Sql

> SELECT - 선택
```SQL
SELECT column1, column2, ...
FROM table_name;

SELECT * FROM table_name;
```

> LIMIT - 제한 (mssql : TOP, oracle : rownum)
```SQL
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;

SELECT * FROM Customers
LIMIT 3;
```
> MIN - 선택된 값중 가장 작은수를 반환
```SQL
SELECT MIN(column_name)
FROM table_name
WHERE condition;

SELECT MIN(Price) AS SmallestPrice
FROM Products;
```
> MAX - 선택된 값중 가장 큰수를 반환
```SQL
SELECT MAX(column_name)
FROM table_name
WHERE condition;

SELECT MAX(Price) AS LargestPrice
FROM Products;
```

> COUNT - 선택된 rows의 갯수를 반환
```SQL
SELECT COUNT(ProductID)
FROM Products;
```

> AVG - 선택된 숫자 컬럼의 평균값 반환
```SQL
SELECT AVG(Price)
FROM Products;
```

> SUM - 선택된 숫자 컬럼의 합 반환
```SQL
SELECT SUM(Quantity)
FROM OrderDetails;
```

> DISTINCT - 중복제거
```SQL
SELECT DISTINCT column1, column2, ...
FROM table_name;

SELECT DISTINCT Country FROM Customers;
```

> INSERT INTO - 추가
```SQL
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

> UPDATE - 업데이트

```SQL
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
```

> DELETE - 삭제
```SQL
DELETE FROM table_name
WHERE condition;

DELETE FROM Customers
WHERE CustomerName='Alfreds Futterkiste';
```

> WHERE - 조건
```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition;

SELECT * FROM Customers
WHERE CustomerID=1;
```

Operator|Description|EX
--|--|--
=|같으면 | WHERE column = 1
<>, !=| 같지 않으면 | WHERE column != 1
\> | 크면 | WHERE column > 1
<| 작으면 | WHERE column < 1
\> =| 크거나 작으면 | WHERE column >= 1
<=| 작거나 같으면 | WHERE column <= 1
BETWEEN | ~ 사이 ~, NOT 절사용가능 | WHERE column (NOT) BETWEEN 10 AND 20
LIKE | 패턴 검색, NOT 절사용가능 | WHERE column LIKE 'a%'; WHERE column LIKE '%or%';
IN | 제공된 값에 포함되는가, NOT 절사용가능| WHERE column (NOT) IN ('Germany', 'France', 'UK') WHERE column (NOT) IN (SELECT Country FROM Suppliers)
WildCards | 정규식 | SELECT * FROM column WHERE City LIKE '[bsp]%'; SELECT * FROM column WHERE City LIKE '[a-c]%';
AND | 둘다 참 | WHERE column1 AND column2
OR | 하나만 참 | WHERE column1 OR column2
NOT | 결과 반전 | WHERE NOT column = 1;
IS NULL | 널 확인 | WHERE column_name IS (NOT) NULL;

> ORDER BY - 정렬
```SQL
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

-- 기본적으로 오름차순 ASC 정렬
SELECT * FROM Customers
ORDER BY Country;

-- 명시적으로 내림차순 DESC 정렬
SELECT * FROM Customers
ORDER BY Country DESC;
```

> HAVING - Group By 절의 결과에 필터를 적용한다.
```SQL
```

> Aliases - 별칭
```SQL
SELECT CustomerID as ID, CustomerName AS Customer
FROM Customers;

SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;

SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
FROM Customers;

SELECT o.OrderID, o.OrderDate, c.CustomerName
FROM Customers AS c, Orders AS o
WHERE c.CustomerName="Around the Horn" AND c.CustomerID=o.CustomerID;

SELECT Orders.OrderID, Orders.OrderDate, Customers.CustomerName
FROM Customers, Orders
WHERE Customers.CustomerName="Around the Horn" AND Customers.CustomerID=Orders.CustomerID;
```
> INNER JOIN - 둘다 참 
```SQL
```

> LEFT JOIN - 좌측이 참
```SQL
```

> RIGHT JOIN - 우측이 참
```SQL
```

> FULL JOIN - 둘다 참
```SQL
```

> SELF JOIN - 자기자신과 조인함
```SQL
```

> UNION - 두 쿼리의 결과를 합하여 리턴한다.
```SQL
```

> EXISTS - 하위쿼리의 결과값이 있는지 확인한다.
```SQL
```

> Any - 하위 쿼리 값 중 하나가 조건을 충족하면 ANY 연산자는 true를 반환
```SQL
```

> All - 모든 하위 쿼리 값이 조건을 충족하면 true를 반환
```SQL
```

>SELECT INTO - 테이블의 데이터를 새 테이블로 복사
```SQL
```

>INSERT INTO SELECT - 한 테이블의 데이터를 복사하여 다른 테이블에 삽입
```SQL
```

> NULL Functions - 표현값이 NULL인경우 대체값을 반환 
```SQL
```

>CREATE DATABASE - DB 생성
```SQL
```
>DROP DATABASE - DB 삭제
```SQL
```
>CREATE TABLE - 테이블 생성
```SQL
```
>DROP TABLE - 테이블 삭제
```SQL
```
>ALTER TABLE - 기존 테이블 수정
```SQL
```
>NOT NULL - NULL 제한
```SQL
```
>UNIQUE - 유니크키
```SQL
```
>PRIMARY KEY - 기본키
```SQL
```
>FOREIGN KEY - 외래키
```SQL
```
>CHECK - 커럼의 제약조건
```SQL
```
>DEFAULT - 기본값
```SQL
```
>INDEX - 인덱스
```SQL
```
>AUTO_INCREMENT - 자동증가
```SQL
```
>VIEW - 가상테이블 
```SQL
```