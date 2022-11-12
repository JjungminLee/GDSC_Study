# 캐시란?

캐시란 CPU와 메인메모리 사이에 위치하며 자주 사용하는 데이터나 값을 미리 복사해놓는 임시 장소를 가리킨다.

### 캐시 메모리의 사용 목적

![Untitled](https://user-images.githubusercontent.com/85864699/200165934-6cbaf95f-239f-4e9e-a190-62a38f0e3f35.png)

- CPU와 메모리 사이에서 연산 속도에 비해 데이터를 가져오는 속도가 느려서 퍼포먼스가 잘 안나오는 병목현상이 발생하는데, 이를 줄이기 위해 사용한다.
- 또한 CPU가 메인메모리의 특정 주소에 접근할 때 그 주변까지 캐시메모리로 읽어내서 향후 비슷한 곳 찾아갈때 접근 속도를 높이는 것이 사용목적이다.   → 이것이 메인 메모리 접근 속도를 향상시킨다(시험문제)

### 언제 캐시를 사용하면 좋을까?

- 업데이트가 자주 발생하지 않는 데이터
- 반복적으로 동일한 결과를 돌려주는 경우
- 자주 조회되는 데이터

### 캐시 메모리의 동작과정

![Untitled](https://user-images.githubusercontent.com/85864699/200165972-d5635633-e413-48ae-8fb3-81fe154226c3.png)

1. CPU가 메인메모리에 있는 데이터 읽어야 할 때는 먼저 캐시메모리부터 조사한다.
2. 캐시메모리에 데이터가 있으면 바로  CPU로 전달.
3. 데이터가 없으면 메인메모리를 보통 블록단위로 가져온다.
4. CPU에는 워드단위로 전송한다.

### 캐시의 구조

![Untitled](https://user-images.githubusercontent.com/85864699/200165985-36264e14-6dff-437a-99bc-1a9065247486.png)

- block: 캐시로 데이터를 저장할 때 참조의 지역성 때문에 한번 퍼낼 때 인접한 곳까지 한꺼번에 캐시메모리에 저장하는 이때 단위를 블록이라고 한다.
- tag: 메인메모리의 몇번째 블록인지 알려준다.

### 캐시의 종류

CPU에는 캐시 메모리가 2~3개 정도 사용되는데 L1,L2,L3캐시 메모리가 있다.속도와 크기에 따라 분류한 것으로 일반적으로 L1캐시부터 사용된다. L1캐시에서 데이터를 찾지 못하면 L2로 또 데이터를 못찾으면 L3로 향한다.

- L1: CPU내부에 존재
- L2: CPU와 RAM사이에 존재
- L3: 보통 메인보드에 존재한다고 한다.

### 캐시적중, 캐시미스

- 캐시적중: CPU에 원하는 정보가 캐시메모리에 존재하는 상황이다.
- 캐시 미스: 원하는 정보가 존재하지 않는 상황이다.
- 캐시 적중률= 캐시적중횟수/전체 기억장치 참조수

# 지역성

- 캐시가 효율적으로 동작하려면 캐시의 적중률을 극대화 시켜야한다.
- 캐시에 저장할 데이터가 지역성을 가져야한다.
- 캐시메모리는 지역성의 원칙을 따르고 지역성에는 시간적,공간적 지역성이 있다.

### 시간적 지역성

- 한번 사용한 정보는 곧 다시 쓰일 가능성이 높다는 의미
- 상대적으로 작은 크기의 캐시를 사용해도 효율성을 꾀할 수 있다.

### 공간적 지역성

- 한번 사용된 적 있는 정보의 주변부가 다시 사용될 가능성이 높다는 의미
- CPU캐시나 디스크 캐시의 경우 한 메모리 주소에 접근할 때 그 주소뿐 아니라 해당 블록을 전부 캐시에 가져오게 된다.
- 이미 저장된 블록의 데이터를 접근하게 되므로 캐시의 효율성이 크게 향상된다.

## 캐시메모리의 매핑방법

### 캐시메모리와 메인메모리의 차이점

![Untitled](https://user-images.githubusercontent.com/85864699/200165999-2b286fa1-402c-498c-8365-7b1ef7b588f6.png)

- 캐시메모리와 메인 메모리의 차이점은 메인메모리는 주소값으로 접근을 하고(랜덤 접근), 캐시 메모리는 내용물로 접근을 한다. 이런 내용물을 Associative Memory(연관 사상 메모리) 라고 한다. 여기서 내용은 테그에 해당한다.

### 직접 매핑

![Untitled](https://user-images.githubusercontent.com/85864699/200166108-99e472de-9c05-4569-9e59-8d997f44413f.png)

이미지출처:[http://itnovice1.blogspot.com/2019/09/cache.html](http://itnovice1.blogspot.com/2019/09/cache.html)

- 메모리 가장 뒷부분(붉은색)이 블럭의 크기를 의미하고, 같은 라인에 위치하는 데이터는 파란색 색칠한 영역에 의해 구별이 가능하다.
- 직접 매핑은 캐시에 저장된 데이터들이 메미인 메모리에서와 동일한 배열을 가지도록 매핑하는 방법
- [장점] 매우 단순하고 탐색이 쉽다
- [단점] 적중률이 낮다.

### 연관 매핑

![Untitled](https://user-images.githubusercontent.com/85864699/200166119-7f322eb8-633a-411e-bdfb-56243b3e8111.png)

- 직접 매핑의 단점을 보완하기 위해 등장
- 캐시에 저장된 데이터들은 메인 메모리의 순서와 아무런 관련이 없다.
- 캐시를 전부 뒤져서 태그가 같은 데이터가 있는 확인해야한다.
- [장점] 적중률이 높다
- [단점] 병렬로 검사하기 위해 복잡한 회로를 가지고 있어 시간이 오래 걸린다.

출처: 컴퓨터시스템개론(정기철) , 컴퓨터 시스템개론 수업 pdf

[https://gyoogle.dev/blog/computer-science/computer-architecture/캐시 메모리.html](https://gyoogle.dev/blog/computer-science/computer-architecture/%EC%BA%90%EC%8B%9C%20%EB%A9%94%EB%AA%A8%EB%A6%AC.html)

[http://itnovice1.blogspot.com/2019/09/cache.html](http://itnovice1.blogspot.com/2019/09/cache.html)