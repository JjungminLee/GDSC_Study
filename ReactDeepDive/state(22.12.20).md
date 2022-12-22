# state 올바르게 쓰기

- 불변성을 지켜야함
    - 직접 state를 수정하지 말것
    - set모듈러를 잘 사용해야한다
    - set모듈러는 기존의 주소값을 바꿔준다.
    
    ```jsx
    const[count,setCount]=useState({'a':'a'})
    
    onClick=()=>{
    	count.a='b'
    
    }
    
    ```
    
    - 이런 경우는 b로 바뀌지 않음 기존의 주소가 바뀌지 않았기 때문
    
    ```jsx
    const[count,setCount]=useState({'a':'a'})
    
    onClick=()=>{
    	setCount(count.a='b');
    
    }
    
    ```
    
- state업데이트가 비동기적일 수 있다
    - 한번 누를 때마다 1만 늘어남
    
    ```jsx
    const[count,setCount]=useState(0);
    
    onClick=()=>{
    	setCount(count+1)
    	setCount(count+1)
    
    }
    ```
    
    - state가 묶여있으면 하나로 묶어서 생각
    - state가 비동기적으로 이루어져 있다 → 1이 들어간게 아니라 0이 들어간거일수도 있다
    - 순서보장 어케?
    - set함수에 값이 아니라 함수를 넣어보자!
    
    ```jsx
    const[count,setCount]=useState(0);
    
    onClick=()=>{
    	setCount((prev)=>{return prev+1;});
    	setCount((prev)=>{return prev+1;});
    
    }
    ```
    
    - 리액트에서 setCount는 변하지 않는다는 것을 보장
- state병합
    
    ```jsx
    const[count,setCount]=useState(0);
    
    onClick=()=>{
    	setCount(4);
    	setCount(5);
    	setCount(6);
    
    }
    ```
    
    - 이러면 6만 count에 담김
- 데이터는 아래로 흐른다
    - 상태는 무조건 top-down방식
    - 부모부터 자식으로 가야한다.
    - 그래서 캡슐화가 가능한 것
        - props이랑 내가 가진 고유한 상태에만 집중할 수 있음(데이터가 아래로 흐르기 때문)
    - state를 항상 특정한 컴포넌트가 소유하고 있다.
        - 트리구조가 props들의 폭포 (하나의 컴포넌트가 하나의 부모노드가 되는격)
        - 각 컴포넌트의 state는 임의의 점에서 만나지만 동시에 아래로 흐르는 부가적인 수원
- 함수형에서 리랜더링은 함수가 호출되는 것

## state를 어디에 두고, state를 어디까지 끌어올려야 할까?

- 리랜더링
    - 리액트가 평가하는 과정 → 원래 바뀌어야 하는게 뭔지 뽑아서 dom에 반영
- 부모 컴포넌트에서만 state를 쓰는가?
- 전역 state를 어디에 쓰는가?
- 한 컴포넌트에 state가 10개씩 있는게 바람직한가?
- state 툴 중에 Redux,Recoil등이 있는데 어떤게 좋은지
    - Redux ⇒ Redux toolkit을 사용
    - 요즘 쓰는 상태관리 라이브러리
        - redux → zustand
        - recoil → jotai
        - mobx → valtio
    - zustand,jotai 써보자
- react query
    - 서버상태를 전역으로 두지 않으면 어디서 데이터를 쓰는지 개발자가 다 찾아야 함
    - 서버 상태를 맨 위로 올려서 어디서든 참조할 수 있게 함 (서버 상태를 한 곳에서만 쓰지 않는 경우)
    - 서버 전역 state → react query
    - 캐싱도 가능
    - 예를들어 실시간으로 유지될 필요가 없는 경우 (top 100 , 5초마다 호출하게 끔)
    - 클라이언트 전역 state → redux
    - NextJS에서는 swr이 치고 올라옴