## PCB & Context Switching

CPU가 프로세스가 여러개일 때 CPU 스케줄링을 통해 관리를 해야함.

이때 CPU는 각 프로세스를 알아야 하고 이런 `Meta Data`는 `PCB(Process Control Block)` 이라는 곳에 저장이 된다.

### PCB 특징

- 하나의 PCB안에는 하나의 프로세스 정보가 담겨있다.
- Linked List 방식으로 관리된다.
- 프로세스가 생성될 때 PCB가 생성되고, 프로세스 완료시 제거된다.

### Context Switching

- CPU가 이전 프로세스 상태를 PCB에 보관하고 다른 PCB를 읽어 레지스터에 적재하는 과정
- 이러한 과정이 필요한 것은 결국 여러 개의 프로세스를 동시적으로 처리할 수 있는 것처럼 보이도록 CPU를 점유하는 것을 변경하는 것
- 그리고, 이때 PCB를 통해서 어떤 프로세스인지 구분하고 처리를 이어나갈 수 있는 것

### Process VS Thread

참고로 프로세스가 Context Switching에 쓰이는 비용이 많이 든다고 합니다. Thread는 Stack 영역을 제외한 모든 메모리를 공유하기에 Context Switching 발생 시 Stack 부분만 동작하면 돼서 그렇다고 합니다.