
# JION
여러 테이블에 흩어져 있는 정보 중 사용자가 필요한 정보만 가져와 하나의 테이블처럼 만들고 결과를 보여주는 것 <br>

정규화를 통해 조회 테이블이 너무 많이 쪼개져 있으면 작업이 불편하기 때문에성능을 향상시키기 위해서 JOIN을 통해 한번에 조회한다.

# 내부 조인(INNER JOIN)
조건이 정확히 일치하는 값만 합쳐서 조회
<pre><code>
FROM 테이블명A INNER JOIN 테이블B
ON 조건
</code></pre>

- 등가 조인
ON 절에 등호(=)가 있을 때 두 테이블 간에 관계가 있다면(PK, FK관계) 부모테이블의 PK와 자식 테이블의 FK를 등호로 비교가 가능하기 때문에 등가조인 사용이 가능하다.

- 비등가 조인
ON절에 등로(=)가 없을 때

# SQL 실행 순서
<pre><code>
FROM > ON > JOIN > WHERE > GROUP BY > HAVING > SELECT > ORDER BY
</code></pre>

- ON절의 조건은 JOIN이 되면서 실행되고, WHERE절의 조건은 JOIN이 끝나고 실행된다.
- ON과 WHERE를 같이 사용할 때와, ON만 사용할 때의 결과가 같다면 ON만 사용하는게 일반적으로 좋다.

# 외부 조인(OUTTER JOIN)
외부 조인은 내부 조인과 다르게 한쪽에만 값이 있어도 테이블을 합쳐서 보여준다.


### TBL_GRADE 
| GRADE_ID(PK) | NAME |
|----|----|
|1|VVIP|
|2|VIP|
|3|NORMAL|

### TBL_USER
|USER_ID(PK)|LOGIN_ID|GRADE_ID(FK)|
|----|----|----|
|1|A|1|
|2|B|2|


## INNER JOIN
  TBL_GRADE G JOIN TBL_USER U
  
  ON G.GRADE_ID = U.GRADE_ID

|GRADE_ID(PK)|NAME|USER_ID(PK)|LOGIN_ID|GRADE_ID(FK)|
|----|----|----|----|----|
|1|VVIP|1|A|1|
|2|VIP|2|B|2|


## OUTER JOIN
  TBL_GRADE G LEFT OUTER JOIN TBL_USER U
  
  ON G.GRADE_ID = U.GRADE_ID
  
|GRADE_ID(PK)|NAME|USER_ID(PK)|LOGIN_ID|GRADE_ID(FK)|
|----|----|----|----|----|
|1|VVIP|1|A|1|
|2|VIP|2|B|2|
|3|NORMAL|NULL|NULL|NULL|

## LEFT OUTER JOIN
우선 왼쪽 테이블의 정보를 전부 가져온 뒤 ON조건 과 일치하는 행을 병합한다.

## RIGHT OUTER JOIN
우선 오른쪽 테이블의 정보를 전부 가져온 뒤 ON조건 과 일치하는 행을 병합한다.

























