# JS 실습



## 기본 실습

### 실습 1

1. "클릭" 이라는 버튼을 만듭니다.
2. 해당 버튼을 button이라는 상수에 저장합니다.
3. button의 textContent를 "클릭됨"으로 변경하는 함수를 만듭니다.
4. button에 3번의 함수를 지정하고 버튼을 클릭해 봅니다.



### 실습 2

1. "토글"이라는 텍스트와 "클릭" 이라는 버튼을 만듭니다.
2. 해당 텍스트를 text로, 버튼을 button이라는 상수에 저장합니다.
3. text가 보이면 숨기고 숨겨져 있으면 보이게 하는 함수를 만듭니다.
4. button에 3번의 함수를 지정하고 버튼을 클릭해 봅니다.



### 실습 3

1. 화면 전체를 채우는 div#wrap를 만듭니다.
2. 해당 div안에  div#cursor를 만듭니다.
3. div#wrap에서 마우스가 이동할 때 div#cursor가 따라다니게 만들어 봅니다.
4. div#wrap에서 마우스가 클릭될 때 div#cursor가 빨간색으로 변하게 만들어 봅니다.

```css
#wrap {
    width: 100vw;
    height: 100vh;
    position: fixed;
    left: 0;
    top: 0;
    cursor: none;
}

#cursor {
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: black;
    position: fixed;
    transform: translate(-50%, -50%)
}
```



마우스 이벤트 리스터의 파라미터에서 clientX, clientY를 받아 사용합니다.

```js
const eventListener = (e) => {
    const {clientX, clientY} = e
    // ...
}
```





### 실습 4

1. 실습 3의 노드를 그대로 사용합니다.
2. div#wrap에서 키보드 이벤트를 수신하여 wasd를 통해 이동하도록 만들어 봅니다.
3. w 위, s 아래, a 왼쪽, d 오른쪽



키보드 이벤트 리스너의 파라미터 key를 이용합니다.

```js
const eventListener = (e) => {
    const {key} = e
    // key === 's', ...
}
```

