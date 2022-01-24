# JAVASCRIPT 기본

javascript는 html 문서를 더 동적으로 만들어주며 다양한 기능을 구현하는데 사용됩니다.

아래 부터는 JAVASCRIPT를 JS라고 부르겠습니다.



## JS의 사용

자바스크립트는 두가지 형태로 사용이 가능합니다.

- 인라인 스크립트 형식

```html
<script>
  const hello = "hello world!"
  console.log(hello)
</script>
```



- 외부 스크립트 형식

```js
/* script.js */
const hello = "hello world!"
console.log(hello)
```

```html
<!-- index.html -->
<script src="script.js"></script>
```



외부 스크립트 형식으로 불러올 때에는 인라인 형태로 사용할 수 없습니다.

```html
<script src="script.js">
  console.log('이 함수는 실행되지 않고 script.js의 내용으로 대체 됩니다.')
</script>
```





## JS의 변수

JS의 변수에는 명시적인 형이 없습니다. 값을 할당할 때에 적절한 타입으로 할당되며 다른 형의 값을 새로 할당할 수 있습니다.

자료형으로는 크게 아래와 같습니다.

- ##### 원시형

  - boolean
  - null
  - undefined
  - number
  - bigint
  - string
  - symbol

- ##### 객체형



또한 JS 에는 세가지 변수 타입이 있습니다.

- ##### var

  var는 초기 부터 있던 변수 타입으로 잘 사용하지 않지만 브라우저 호환성을 위해 사용 되기도 합니다.

  바벨 컴파일러 등으로 ie 호환성을 넣게 되면 let이나 const도 var로 변환됩니다.

- ##### let

  let은 새로 추가된 변수 타입으로 가장 일반적인 변수 타입니다.

- ##### const

  const는 상수를 선언할 때 사용합니다. 한번 선언된 값은 변경할 수 없습니다.

  ex) PI = 3.14



## JS의 함수 선언

js에서 함수는 아래와 같이 선언합니다.

```js
function functionName(){
    // ...
}

function voidFunction (param1){
    // ...
}

function returnFunction(param1, param2){
    return returnValue
}
```

함수의 리턴타입은 따로 지정하지 않으며 리턴은 할 수도 있고 안 할 수도 있습니다.

리턴하지 않는 함수는 undefined가 리턴됩니다.



JS에서 함수는 일급함수입니다. 이는 함수를 변수처럼 다룰 수 있음을 의미합니다.

이로인해 아래와 같은 방식이 가능합니다.

```js
function someFunction(){
    console.log('hello world!')
}

const callback = someFunction
setTimeout(callback, 1000) // 1초 후 someFunction이 호출되어 hello world!가 출력됩니다.
```





## JS의 요소 찾기

js에서는 요소를 찾아 변수로 저장할 수 있으며 스타일을 바꾸거나 기타 작업을 수행할 수 있습니다.

js에서 요소를 찾는 흔한 방법으로는 아래가 있습니다.



- ##### document.getElementById

  아이디로 요소를 한개 찾습니다.

- ##### document.getElementsByClassName

  클래스를 가진 모든 요소를 찾습니다.

- ##### document.getElementsByTagName

  해당 태그의 모든 요소를 찾습니다.

- ##### document.querySelector

  쿼리에 해당하는 가장 첫 요소를 찾습니다.

- ##### document.querySelectorAll

  쿼리에 해당하는 모든 요소를 찾습니다.



```html
<p id="pid" class="pClass"> 요소 </p>
<script>
const pid = document.getElementById('pid')
const pClass = document.getElementsByClassName('pClass')[0]
const pTag = document.getElementsByTagName('p')[0]
const pQuery = document.querySelector('p') // #pid 또는 .pClass 도 사용 가능
const pQueryAll = document.querySelectorAll('p')[0] // querySelector와 동일
</script>
```

위의 `pid` `pClass` `pTag` `pQuery` `pQueryAll` 은 모두 같은 p 태그를 바라봅니다.



## JS의 요소 스타일 변환

js에서 요소를 저장하면 style 프로퍼티를 통해 스타일을 변경할 수 있습니다.

이 때 스타일 속성키는 케밥 케이스에서 카멜 케이스로 변경됩니다. 

```text
font-size => fontSize
background-color => backgroundColor
border-radius => borderRadius
```



pid라는 id를 가진 p태그의 글자 색상을 빨간색으로 변경하는 것은 아래와 같습니다.

```html
<p id="pid"> pid 요소입니다. </p>
<script>
  const p = document.getElementById('pid')
  p.style.color = 'red'
</script>
```



위의 객체를 보이지 않게 만드는 방법은 아래와 같습니다.

```html
<p id="pid"> pid 요소입니다. </p>
<script>
  const p = document.getElementById('pid')
  p.style.display = 'none'
</script>
```





## JS의 이벤트 받기

js에서 이벤트를 받는 방법으로 두가지 방법이 있습니다.

- 단일 리스너로 받기

  단일 리스너로 받게 되면 다른 리스너가 할당될 때 기존 리스너는 사라집니다.

  ```html
  <p onclick="someFunction()"> </p>
  <!-- 또는 -->
  <script>
  const p = document.querySelector('p')
  p.onclick = someFunction
  </script>
  ```

  

- 요소의 이벤트 리스너에 추가하기

  이벤트 핸들러로 추가하면 언제든지 다시 이벤트 수신을 제거할 수 있고, 여러개의 핸들러를 할당할 수도 있습니다.

  ```html
  <p id="pid"></p>
  <script>
  const p = document.getElementById('pid')
  p.addEventListener('click', someFunction)
  // 이벤트 리스너 해제
  // p.removeEventListener('click', someFunction)
  </script>
  ```

  

## 브라우저에서 콘솔 열기

일반적으로 브라우저에서 자바스크립트를 디버깅 하기 위해 콘솔을 사용합니다.

F12 또는 ctrl + shift + i 를 통해 콘솔을 엽니다.

Mac의 경우 opt + cmd + i 를 통해 열 수 있습니다.