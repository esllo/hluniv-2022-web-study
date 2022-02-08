# JS 기본

DOM 엘리먼트에 접근하고 제어해봅니다.



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



## JS의 스타일 변경

js에서 요소를 저장하면 style 프로퍼티를 통해 스타일을 변경할 수 있습니다.

이 때 스타일 속성키는 케밥 케이스에서 카멜 케이스로 변경됩니다. 

```html
<p id="pid"> pid 요소입니다. </p>
<script>
  const p = document.getElementById('pid')
  p.style.color = 'red'
</script>
```



자세한 내용은 day1-5에서 확인 가능합니다.



## JS의 요소 클래스 설정

js에서 요소의 클래스를 설정하는데에는 두가지 방법이 있습니다.

- #### className

  클래스를 한번에 정의합니다. ex) "box box5"

- #### classList

  클래스를 배열로 관리합니다. ex) ["box", "box5"]

  ##### add : 클래스를 추가합니다.

  ##### remove : 클래스를 제거합니다.

  ##### toggle : 클래스가 있으면 제거하고 없으면 추가합니다.

  ##### contains : 클래스의 존재 유무를 리턴합니다.





## JS의 동적 노드 생성 및 추가

js에서는 동적으로 노드를 생성하고 추가할 수 있습니다.



기본적으로 요소는 노드의 하위집합입니다.

```
---- 노드(node)
  |---- 요소 노드(element_node)
  |---- 텍스트 노드(text_node)
  |---- ...
```





### 노드 생성

#### document.createElement("tagname")

tagname의 요소를 생성합니다.

#### document.createTextNode('text')

'text'를 가지는 텍스트 노드를 생성합니다.



### 노드 추가

#### parent.appendChild(child)

parent 요소의 마지막에 child를 추가합니다.



#### parent.insertBefore(child, sibling)

parent 요소의 sibling 자식 앞에 child를 추가합니다.



## 기타 노드 함수

#### node.childNodes

노드의 자식 배열을 리턴합니다.



#### node.firstChild

노드의 첫 자식을 리턴합니다. 없으면 null을 리턴합니다.



#### node.lastChild

노드의 마지막 자식을 리턴합니다. 없으면 null을 리턴합니다.



#### node.textContent

노드의 텍스트를 리턴 또는 지정합니다.



#### node.nextSibling

노드의 다음 형제 노드을 리턴합니다.



#### node.previousSibling

노드의 이전 형제 노드를 리턴합니다.



#### node.parentElement

노드의 부모 엘리먼트를 리턴합니다.



#### node.parentNode

노드의 부모 노드를 리턴합니다.



## 기타 요소 속성

#### element.nextElementSibling

요소의 다음 형제 요소 노드를 리턴합니다.



#### element.previousElementSibling

요소의 이전 형제 요소 노드를 리턴합니다.



#### element.innerHTML

요소의 내부 HTML을 리턴 또는 지정합니다.



#### element.attributes

요소의 속성을 담은 Map을 리턴합니다.



#### element.getAttribute(name)

요소의 name의 속성을 가져옵니다.



#### element.setAttribute(name, value)

요소의 name의 속성을 value로 지정합니다.



#### element.getBoudingClientRect()

요소의 화면상 x, y, width, height 값을 리턴합니다.



#### element.hidden

요소의 숨김 여부를 리턴하거나 지정합니다.



## JS의 이벤트

js에는 다양한 이벤트가 있습니다.



### 마우스 이벤트

- click : 좌클릭
- contextmenu : 우클릭
- mouseout : 마우스가 요소를 벗어났을 때 (자식 이벤트 시 이벤트 갱신)
- mouseover : 마우스가 요소에 들어왔을 때 (자식 이벤트 시 이벤트 갱신)
- mouseleave : 마우스가 요소를 벗어났을 때
- mouseenter : 마우스가 요소에 들어왔을 때
- mousemove : 마우스가 요소에서 이동할 때
- mouse down : 클릭이 눌릴  때
- mouse up : 클릭이 떼질 때



mouseout mouseover와 mouseleave mouseenter의 차이는 아래에서 확인할 수 있습니다.

https://recoveryman.tistory.com/51



### 키보드 이벤트

- keydown : 키를 누르는 순간
- keyup : 키를 떼는 순간
- keypress : 키가 입력된 순간



## JS의 이벤트 수신

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

  