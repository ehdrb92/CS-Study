## 비선형 자료 구조
    비선형 자료 구조는 데이터가 일렬로 나열되지 않고 자료 순서나 관계가 복잡한 구조이다.
    일반적으로 트리나 그래프를 말한다.
    

### 그래프
    비선형 자료 구조인 그래프는 **정점**과 **간선**으로 이루어진 자료 구조를 말한다.

- 정점 : '노드'라고도 하며 어떤 위치가 된다.
- 간선 : 노드까지 연결하는 선을 의미한다.

### 트리
    트리는 그래프 중 하나로 트리 구조로 배열된 계층적 데이터의 집합이다.
    루트 노드, 내부 노드, 리프 노드 등으로 구성되며, 이 트리고 이루어진 집합을 숲이라고 한다.

#### 트리 특징
1. 부모, 자식 계층 구조를 가진다
2. V - 1 = E 라는 특징이 있다. 간선 수는 노드 수 -1 이다.
3. 임의의 두 노드 사이의 경로는 반드시 있다. (트리 내의 어떤 노드와 어떤 노드까지의 경로는 반드시 있다.)


#### 이진 트리
    자식의 노드 수가 **두 개 이하**인 트리를 의미하며, 정이진 트리, 완전 이진 트리, 변질 이진트리, 포화 이진트리, 균형 이진트리 5개로 분류한다.

#### 이진 탐색 트리
    이진 탐색 트리는 노드의 오른쪽 하위 트리에는 '노드 값보다 큰 값' 이 있는 노드만 포함되고, 왼쪽 하위 트리에는 '노드 값보다 작은 값'이 들어있는 트리를 말한다.

#### AVL 트리
    스스로 균형을 잡는 이진 탐색 트리이다. 두 자식 서브트리의 높이는 항상 최대 1만큼 차이 난다는 특징이있다.

#### 레드 블랙 트리

### 힙
    힙은 완전 이진 트리 기반의 자료 구조이며, 최댓값이나 최솟값을 빠르게 찾아내도록 만들어졌다.
    **최소힙과 최대힙** 두가지가 있고 해당 힙에 따라 특정한 특징을 지킨 트리를 말한다.

- 최대힙 (Max Heap) : 부모 노드의 키 값이 자식 노드의 키 값보다 크거나 같은 완전 이진 트리
- 최소힙 (Min Heap) : 부모 노드의 키 값이 자식 노드의 키 값보다 작거나 같은 완전 이진 트리

### 우선순위 큐
    우선순위 큐는 우선순위 대기열이라고도 하며, 대기열에서 우선순위가 높은 요소가 우선 순위가 낮은 요소보다 먼저 제공되는 자료 구조이다.
    이 우선순위 큐는 힙을 기반으로 구현된다.

### 맵
    키와 맵핑된 값(벨류)의 조합으로 형성된 자료 구조이다. 
    1 : One, 2 : Two 이런식 예..
    이 맵을 사용 할때는 map<string, int>이런 형태로 구현한다. 

### 셋
    셋은 특정 순서에 따라 고유한 요소를 저장하는 컨테이너이며, 중복된 요소는 없고 오로지 희소한 값만 저장하는 자료구조이다.

### 해시 테이블
    무한에 가까운 데이터들을 유한한 개수의 해시 값으로 매핑한 테이블이다.
    삽입, 삭제, 탐색 시 평균적으로 O(1)의 시간 복잡도를 가지며 unordered_map으로 구현한다.
