## ERD의 중요성
ERD(Entity Relationship Diagram): 데이터베이스를 구축할 때 가장 기초적인 뼈대 역할로, 릴레이션 간의 관계들을 정의한 것.  
- 서비스 구축시 가장 먼저 신경 써야 할 부분
- 시스템의 요구 사항을 기반으로 작성
- ERD를 기반으로 데이터베이스를 구축
- 관계형 구조로 표현할 수 있는 데이터를 구성하는 데 유용
- 비정형 데이터를 충분히 표현할 수 없다는 단점이 있음
<img src="https://user-images.githubusercontent.com/91110192/200160167-4d8aeb09-2a3a-4e9e-892f-4240b4a8a5f5.png" width="60%">

## 정규화 과정
정규화 과정: 릴레이션 간의 잘못된 종속 관계로 인해 데이터베이스 이상 현상이 일어나서 이를 해결하거나, 저장 공간을 효율적으로 사용하기 위해 릴레이션을 여러 개로 분리하는 과정.  
- 정규화 과정은 정규형 원칙을 기반으로 정규형을 만들어가는 과정
- 기본 정규형: 제1정규형, 제2정규형, 제3정규형, 보이스/코드 정규형
- 고급 정규형: 제4정규형, 제5정규형  

_데이터베이스 이상 현상: 회원이 한 개의 등급을 가져야 하는데 세 개의 등급을 갖거나 삭제할 때 필요한 데이터가 같이 삭제되고, 데이터를 삽입해야 하는데 하나의 필드 값이 NULL이 되면 안 되어서 삽입하기 어려운 현상_  

### 정규형 원칙
1. 같은 의미를 표현하는 릴레이션이지만 좀 더 좋은 구조로 만들어야 한다.
2. 자료의 중복성은 감소해야 한다.
3. 독립적인 관계는 별개의 릴레이션으로 표현해야 한다.
4. 각각의 릴레이션은 독립적인 표현이 가능해야 한다.  

### 제1정규형
제1정규형: 테이블의 컬럼이 원자값(Atomic Value, **하나의 값**)을 갖도록 테이블을 분해하는 것.  
예를 들어 아래와 같은 고객 취미 테이블이 존재한다고 하자.  
  
![https://blog.kakaocdn.net/dn/bNbQUm/btqT18yag04/pTXJX3wB23ouk8az7EgWQ1/img.png](https://blog.kakaocdn.net/dn/bNbQUm/btqT18yag04/pTXJX3wB23ouk8az7EgWQ1/img.png)  

위의 테이블에서 추신수와 박세리는 여러 개의 취미를 가지고 있기 때문에 제1 정규형을 만족하지 못하고 있다. 그렇기 때문에 이를 제1 정규화하여 분해할 수 있다.  
제1 정규화를 진행한 테이블은 아래와 같다.
  
![https://blog.kakaocdn.net/dn/bMlNZj/btqT17FWVot/jUKTAUyOdrH83pRraKw3K0/img.png](https://blog.kakaocdn.net/dn/bMlNZj/btqT17FWVot/jUKTAUyOdrH83pRraKw3K0/img.png)

### 제2정규형
제2정규형: 제1 정규화를 진행한 테이블에 대해 부분 함수의 종속성을 제거하기 위해 테이블을 분해하는 것.  
부분 함수의 종속성 제거란 기본키의 부분집합이 결정자가 되어선 안된다는 것 즉, 기본키가 아닌 모든 속성이 기본키에 완전 함수 종속정인 것을 의미한다.  
예를 들어 아래와 같은 수강 강좌 테이블을 살펴보자.  
  
![https://blog.kakaocdn.net/dn/ylbaZ/btqT8Jc4K3s/0VFTPoKKFkbxZghKWDwKo1/img.png](https://blog.kakaocdn.net/dn/ylbaZ/btqT8Jc4K3s/0VFTPoKKFkbxZghKWDwKo1/img.png)
  
이 테이블에서 기본키는 (학생번호, 강좌이름)으로 복합키이다. 그리고 (학생번호, 강좌이름)인 기본키는 성적을 결정하고 있다. (학생번호, 강좌이름) --> (성적)  
그런데 여기서 강의실이라는 컬럼은 기본키의 부분집합인 강좌이름에 의해 결정될 수 있다. (강좌이름) --> (강의실)  
즉, 기본키(학생번호, 강좌이름)의 부분키인 강좌이름이 결정자이기 때문에 위의 테이블의 경우 다음과 같이 기존의 테이블에서 강의실을 분해하여 별도의 테이블로 관리하여 제2 정규형을 만족시킬 수 있다.  
  
이 때 주의할 점은 릴레이션을 분해할 때 동등한 릴레이션으로 분해해야 하고, 정보 손실이 발생하지 않는 무손실 분해로 분해되어야 한다는 것이다.

![https://blog.kakaocdn.net/dn/bluCnc/btqT7VEOf04/Me8DfY7rtycgJPYlYQKEWK/img.png](https://blog.kakaocdn.net/dn/bluCnc/btqT7VEOf04/Me8DfY7rtycgJPYlYQKEWK/img.png)

### 제3정규형
제3 정규화란 제2 정규화를 진행한 테이블에 대해 이행적 종속을 없애도록 테이블을 분해하는 것이다. 여기서 이행적 종속이라는 것은 A -> B, B -> C가 성립할 때 A -> C가 성립되는 것을 의미한다.
예를 들어 아래와 같은 계절 학기 테이블을 살펴보자.

![https://blog.kakaocdn.net/dn/enwN1N/btqUeiMyErd/sP8NKCe70NKsZncGuhO9uK/img.png](https://blog.kakaocdn.net/dn/enwN1N/btqUeiMyErd/sP8NKCe70NKsZncGuhO9uK/img.png)

기존의 테이블에서 학생 번호는 강좌 이름을 결정하고 있고, 강좌 이름은 수강료를 결정하고 있다. 그렇기 때문에 이를 (학생 번호, 강좌 이름) 테이블과 (강좌 이름, 수강료) 테이블로 분해해야 한다.이행적 종속을 제거하는 이유는 비교적 간단하다. 예를 들어 501번 학생이 수강하는 강좌가 스포츠경영학으로 변경되었다고 하자. 이행적 종속이 존재한다면 501번의 학생은 스포츠경영학이라는 수업을 20000원이라는 수강료로 듣게 된다. 물론 강좌 이름에 맞게 수강료를 다시 변경할 수 있지만, 이러한 번거로움을 해결하기 위해 제3 정규화를 하는 것이다.
즉, 학생 번호를 통해 강좌 이름을 참조하고, 강좌 이름으로 수강료를 참조하도록 테이블을 분해해야 하며 그 결과는 다음의 그림과 같다.

![https://blog.kakaocdn.net/dn/ci1le3/btqUeXnPnpD/yKkURqr8cZl21f5erx42QK/img.png](https://blog.kakaocdn.net/dn/ci1le3/btqUeXnPnpD/yKkURqr8cZl21f5erx42QK/img.png)

### 보이스/코드 정규형
BCNF 정규화란 제3 정규화를 진행한 테이블에 대해 모든 결정자가 후보키가 되도록 테이블을 분해하는 것이다. 예를 들어 다음과 같은 특강수강 테이블이 존재한다고 하자.특강수강 테이블에서 기본키는 (학생번호, 특강이름)이다. 그리고 기본키 (학생번호, 특강이름)는 교수를 결정하고 있다. 또한 여기서 교수는 특강이름을 결정하고 있다.
그런데 문제는 교수가 특강이름을 결정하는 결정자이지만, 후보키가 아니라는 점이다. 그렇기 때문에 BCNF 정규화를 만족시키기 위해서 위의 테이블을 분해해야 하는데, 다음과 같이 특강신청 테이블과 특강교수 테이블로 분해할 수 있다.

![https://blog.kakaocdn.net/dn/bBN6xu/btqT6IlqRF4/MvBoxYMxtgS1JT7t1AymnK/img.png](https://blog.kakaocdn.net/dn/bBN6xu/btqT6IlqRF4/MvBoxYMxtgS1JT7t1AymnK/img.png)

![https://blog.kakaocdn.net/dn/3cbHr/btq3mNylPan/c6b2lBuH4OkdDNmrzGHWUk/img.png](https://blog.kakaocdn.net/dn/3cbHr/btq3mNylPan/c6b2lBuH4OkdDNmrzGHWUk/img.png)
