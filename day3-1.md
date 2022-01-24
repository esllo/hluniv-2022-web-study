# CSS 기본 1

CSS 기본 유닛 및 선택자에 대해 알아봅니다.



CSS의 속성 목록은 https://www.w3schools.com/cssref/ 에서 확인가능합니다.



## 단위 유닛

CSS에는 절대적인 단위와 상대적인 단위가 있습니다.

#### 절대 단위

절대 단위로는 cm, mm, in, px, pt, pc 등이 있습니다.

> px = 1 / 96 in
>
> pt = 1 / 72 in
>
> pc = 1 / 6 in
>
>  
>
> px은 디바이스의 크기를 기준으로 합니다. dpi가 낮은경우 1px은 디바이스의 1픽셀 입니다.



#### 상대 단위

상대 단위로는 em, ex, ch, rem, vw, vh, vmin, vmax, %가 있습니다.

>em = 현재 엘리먼트의 폰트 사이즈 기준
>
>ex = 'x'의 높이 기준
>
>ch = '0' 문자열의 너비 기준
>
>rem = 루트 엘리먼트(html)의 폰트 사이즈 기준
>
>vw = 1/100 뷰포트 너비
>
>vh = 1/100 뷰포트 높이
>
>vmin = vw와 vh중 작은 값
>
>vmax = vw와 vh중 큰 값
>
>% = 부모의 너비 또는 높이 기준



## 선택자

### * 

모든 요소



### tagName

tagName의 태그 요소



### .class

class를 가진 요소



### .class1.class2

class1과 class2를 모두 가진 요소



### .class1 .class2

class1을 조상으로 가지며 class2를 가진 요소



### #id

id를 가진 요소



### tagName#id

tagName의 태그가 id를 가진 요소



### tagName.class

tagName의 태그가 class를 가진 요소



### 선택자1, 선택자2

선택자1 요소와 선택자 2 요소



### 선택자1 선택자2

선택자1을 조상으로 가지는 선택자2 요소




### 선택자1 > 선택자2

선택자 1을 부모로 가지는 선택자 2 요소

조상이 아닌 바로 윗 부모여야함




### 선택자1 + 선택자2

선택자1 바로 다음에 오는 첫 선택자2 요소

같은 부모를 가지고 있어야함



### 선택자1 ~ 선택자2

선택자1 뒤에 오는 모든 선택자2 요소

같은 부모를 가지고 있어야함



### [속성]

속성을 가진 요소



### [속성=값]

속성이 값인 요소



### [속성~=값]

속성의 값이 "값"을 포함하는 요소



### [속성|=값]

속성의 값이 "값" 이거나 "값-"으로 시작하는 요소



### [속성^=값]

속성의 값이 "값"으로 시작하는 요소



### [속성$=값]

속성의 값이 "값"으로 끝나는 요소



### [속성*=값]

속성의 값이 "값"을 문자열로 포함하는 요소



#### ~= 와 *=의 차이점

`~=`는 값이 포함되어야 하고, `*=`는 값의 문자열이 포함되면 된다.

| class        | [class~="apple"] | [class*="apple"] |
| ------------ | ---------------- | ---------------- |
| apple        | O                | O                |
| apple banana | O                | O                |
| apple-banana | X                | O                |



### :active

링크가 선택된 순간 (마우스 클릭된 상태)



### :visited

이미 방문한 링크 요소



### :hover

마우스가 올라가있는 순간의 요소



### :focus

포커스가 들어와있는 요소



### ::after

요소의 끝부분에 새로운 요소 추가



### ::before

요소의 앞부분에 새로운 요소 추가



### :checked

input type="checkbox"에서 checked 된 경우의 요소



### :required

required를 포함하는 요소



### ::placeholder

placeholder 요소



### ::selection

selection으로 선택된 요소



### :disabled

disabled된 요소



### :empty

텍스트 노드(textContent) 또는 자식 요소(element) 노드가 없는 요소



### :enabled

enabled된 요소



### :first-child

한 부모에서 첫 요소



### :last-child

한 부모에서 마지막 요소



### :first-of-type

한 부모에서 첫 해당 타입의 요소



### :last-of-type

한 부모에서 마지막 해당 타입의 요소



### :nth-child(n)

한 부모에서 n 번째 요소 (1로 시작)



### :nth-of-type(n)

한 부모에서 n 번째 해당 타입의 요소



### :nth-last-child(n)

한 부모에서 뒤에서 n 번째 요소



### :nth-last-of-type(n)

한 부모에서 뒤에서 n 번째인 해당 타입의 요소



### :only-child

한 부모에서 자식이 자신뿐인 요소



### :only-of-type

한 부모에서 해당 타입의 자식이 자신뿐인 요소



### :not(selector)

해당 선택자가 아닌 요소



### ::marker

리스트의 마커 요소



### ::first-letter

해당 요소의 첫 글자



### ::first-line

해당 요소의 첫 줄

