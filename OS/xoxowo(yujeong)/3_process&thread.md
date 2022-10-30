## 프로세스와 스레드
    프로세스 : 컴퓨터에서 실행되고 있는 프로그램 의미, CPU 스케줄링의 대상이 되는 작업(task) 용어와 거의 같은 의미 
    스레드 : 프로세스 내 작업의 흐름 지칭

### 프로세스와 컴파일 과정
    프로세스는 프로그램으로 부터 인스턴스화 된 것을 말한다.
    예를들면 게임 프로그램과 같은 게임 실행 파일을 실행하면 게임의 프로세스가 시작되는 것.

    프로그램은 컴파일러가 컴파일 과정을 거쳐 컴퓨터가 이해할 수 있는 언어로 번역되어 실행가능한 파일이 되는 것을 의미한다.


### 프로세스의 상태
    프로세스는 여러가지 상태 값을 갖는다.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Process_states.svg/1280px-Process_states.svg.png">

#### 생성 상태
    프로세스가 생성된 상태를 의미. fork() 또는 exec() 함수를 통해 생성. 이때 PCB가 할당된다.

* fork() : 부모 프로세스의 주소 공간을 그대로 복사하여, 새로운 자식 프로세스를 생성하는 함수 (주소 공간만 복사하며 부모 프로세스의 비동기 작업 등을 상속하지 않는다.)
* exec() : 새로 프로세스를 생성하는 함수를 의미

#### 대기 상태
    메모리 공간이 충분하면 메모리를 할당받으며, 아닐 경우 대기하며 CPU스케줄러로부터 기다리는 상태

#### 대기 중단 상태
    메모리 부족으로 일시 중단 상태

#### 실행 상태
    CPU 소유권과 메모리를 할당 받아 인스트럭션을 수행중인 상태 (≒ CPU burst가 일어났다고도 표현)

#### 중단 상태
    어떤 이벤트 발생한 이후 기다리며 프로세스가 차단된 상태
    예를 들면 어떤 작업 버튼을 눌렀을 때 잠깐 멈춘 듯한 상태

#### 일시 중단 상태
    대기 중단 상태와 유사하지만, 중단 상태에서 프로세스가 실행되려했지만 메모리 부족으로 일시 중단된 상태

#### 종료 상태
    CPU 소유권과 메모리를 모두 놓고가는 상태. 자연스럽게 종료될 경우도 있지만 비자발적으로 종료되는 경우도 있다.



### 프로세스의 메모리 구조
    운영체제는 프로세스에 적절한 메모리를 할당하는데 **스택**, **힙**, **데이터영역**, **코드영역**으로 나눠진다.
    스택은 위 주소부터 할당되고, 힙은 아래 주소부터 할당된다.

<img src="https://images.velog.io/images/moon-yerim/post/38d6fc92-c342-4a19-baf5-9aa148ae70ca/image.png">

#### 스택 (Stack)
    지역변수, 매개변수, 함수가 저장되고 컴파일 시에 크키가 결정되며 **동적**인 특징을 갖는다.

    스택 영역은 함수가 함수를 재귀적으로 호출하면서 크키가 늘어날 수 있는데 이때 힙과 스택의 메모리 영역을 침범하면 안되기 때문에 힙과 스택 사이의 공간을 비워놓는다.

#### 힙 (Heap)
    동적 할당할 때 사용되며 런타임시 크기가 결정된다. **동적**인 특징을 가짐

#### 데이터 영역 (Data segment, BSS segment)
    데이터 영역은 전역변수, 정적변수가 저장되며 **정적**인 특징을 갖는 프로그램이 종료되면 사라지는 변수가 들어있는 영역이며, BSS영역과 Data영역으로 나뉜다.

#### 코드 영역 (Code segment)
    프로그램에 내장된 소스 코드가 들어가있는 영역으로 수정 불가능한 기계어로 저장되어 **정적**인 특징을 가진다.

### PCB (Process Control Block)
    운영체제가 프로세스 실행을 제어하기 위해 프로세스 정보가 필요한데 이 프로세스 정보는 *메타 데이터를 저장한 '데이터'인 프로세스 제어 블록이 가지고 있다.

    즉, 프로세스를 관리하기 위해 유지되는 데이터 블록이다. 

    프로세스가 생성될 때 프로세스 제어 블록이 만들어지며, 프로세스의 실행이 종료되면 블록도 같이 삭제된다.

* 메타 데이터 : 데이터에 관한 구조화된 데이터이며 데이터를 설명하는 작은 데이터

#### PCB의 구조

<img src="https://woovictory.github.io/img/PCB_os.png">

