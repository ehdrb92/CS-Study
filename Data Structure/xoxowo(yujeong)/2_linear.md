## 선형 자료 구조
    선형 자료 구조는 데이터가 일렬로 나열되어있는 자료 구조이다.
    대표적인 선형 자료 구조는 연결리스트, 배열가 있으며 백터, 스택, 큐가 선형 자료 구조에 해당한다.

### 연결 리스트
    데이터를 감싼 노드를 포인터로 연결하여 공간적인 효율성을 극대화한 자료구조.

    순차적으로 데이터를 탐색하기 때문에 랜덤 접근이 불가능하다.
    데이터 추가, 삭제가 빠르다.

### 배열
    같은 타입의 변수들로 이루어져있고 크기가 정해져있으며, 인접한 메모리 위치에 있는 데이터를 모아둔 집합이다.

    중복을 허용하면서 순서가 있다.
    데잍터 추가, 삭제에는 시간이 걸리기 때문에 탐색을 많이하는 것은 배열로 하는 것이 좋다.

    배열은 인덱스에 해당하는 원소를 빠르게 접근해야 하거나 간단하게 데이터를 쌓고 싶을 때 사용한다.

### 스택
    스택은 가장 마지막으로 들어간 데이터가 가장 첫 번째로 나오는 성질(LIFO)를 가진 자료 구조이며,
    재귀적 함수, 알고리즘에 사용되며 웹 브라우저 방문기록 등에 쓰인다.
    삽입 및 삭제에 O(1), 탐색에O(n)이 걸린다.

### 큐
    큐는 먼저 집어넣은 데이터가 먼저 나오는 성질(FIFO)을 지닌 자료구조이며,
    스택과 반대되는 개념을 가진다. 
    삽 입 및 삭제에 O(1), 탐색에O(n)이 걸린다.
    cpu 작업을 기다리는 프로세스, 스레드 행렬 또는 네트워크 접속을 기다리는 행렬, 너비 우선 탐색, 캐시 등에 사용된다.