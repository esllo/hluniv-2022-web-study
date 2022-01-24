# CSS 기본 2

CSS의 색상 및 다양한 속성에 대해 알아봅니다.



## CSS의 네임드 색상

웹에서는 red blue green aqua 같은 알려진 색상 이름을 사용할 수 있습니다.



기본 색상으로는 아래 색상들이 있습니다.

| 색이름  | HEX 코드 | RGB 값      |
| ------- | -------- | ----------- |
| black   | #000000  | 0,0,0       |
| silver  | #C0C0C0  | 192,192,192 |
| gray    | #808080  | 128,128,128 |
| white   | #FFFFFF  | 255,255,255 |
| maroon  | #800000  | 128,0,0     |
| red     | #FF0000  | 255,0,0     |
| purple  | #800080  | 128,0,128   |
| fuchsia | #FF00FF  | 255,0,255   |
| green   | #008000  | 0,128,0     |
| lime    | #00FF00  | 0,255,0     |
| olive   | #808000  | 128,128,0   |
| yellow  | #FFFF00  | 255,255,0   |
| navy    | #000080  | 0,0,128     |
| blue    | #0000FF  | 0,0,255     |
| teal    | #008080  | 0,128,128   |
| aqua    | #00FFFF  | 0,255,255   |

이외에도 기타 다양한 색상이 있습니다.

해당 색상은 아래에서 확인할 수 있습니다.

https://www.w3.org/wiki/CSS/Properties/color/keywords





## 기본 속성

대부분의 요소에는 기본적인 속성이 달려 있습니다.

다음 내용들은 해당 속성 중 일부입니다.

- html 문서의 기본 여백
- h1~h6의 순서 별 크기 및 폰트 타입
- ul, ol의 앞에 오는 마커
- p 태그의 마진 값
- mark 태그의 노란색 배경
- 기타 등등



해당 속성 목록에 대해선 아래 링크에서 확인할 수 있습니다.

https://www.w3schools.com/cssref/css_default_values.asp



### 기본 속성 초기화

기본 속성을 초기화하고 디자인 하기 위해 직접 위의 속성을 초기화할 수 있습니다.

하지만 이를 편하게 하기 위해 다른 이들이 작성해둔 reset.css 또는 normalize.css, html5 doctor reset을 활용할 수도 있습니다.

#### reset.css

기본적인 css 초기화입니다. 업데이트하며 html5도 지원합니다.

https://meyerweb.com/eric/tools/css/reset/

#### normalize.css

기본적인 css 초기화에 약간의 스타일이 추가되어있습니다.

https://necolas.github.io/normalize.css/

#### html5doctor reset.css

reset.css를 기반으로 작성되었으나 지원하지 않는 html4에 대한 내용을 빼고 html5 호환성을 고려하였습니다.

http://html5doctor.com/html-5-reset-stylesheet/





## CSS 엔티티

일부 문자를 출력하기 위해 CSS 엔티티를 사용할 수 있습니다. 

ex)

- © => 00A9
- ® => 00AE
- ≈ => 2248
- ⊘ => 2298
- 기타 등등



사용시에는 content 속성에 문자열로 넣습니다.

```css
.copyright::after {
    content: '\00A9'
}
```





지원하는 엔티티 목록은 아래 링크에서 확인할 수 있습니다.

https://www.w3schools.com/cssref/css_entities.asp





## CSS 속성

### initial, inherit

initial은 해당 태그가 가진 해당 속성의 기본값을 적용합니다.

inherit은 해당 태그의 부모가 가진 해당 속성의 값을 상속받습니다.



### 속성 목록

#### position

배치 타입을 지정할 수 있습니다.

- fixed : 화면 기준 위치
- absolute : 문서 기준 위치
- static : (기본값) 문서의 흐름상의 위치
- relative : 이것의 일반 위치 기준의 상대적 위치



#### top, right, bottom, left

position을 기준으로 배치할 때 배치되는 위치 입니다.



#### display

렌더링 타입을 지정합니다.

- inline : 인라인으로 설정합니다. 가로로 나열됩니다.
- block : 블록으로 설정합니다. 세로로 나열됩니다.
- flex : 가변적인 flex로 설정합니다.
- grid : 가변적인 grid로 설정합니다.
- inline-block : 인라인으로 나열하되 화면을 벗어나면 블록으로 넘긴 후 다시 인라인으로 나열합니다.
- table : 테이블로 설정합니다. \<table> 처럼 동작합니다.
- none : 해당 객체를 그리지않습니다.



#### visibility

렌더링시 그리는 여부를 지정합니다.

- visible : 렌더링합니다.
- hidden : 해당 요소를 그리지 않습니다.

##### display:none;과 visibility:hidden;의 차이

 display:none은 해당 요소가 완전히 사라진 것 처럼 보이지만, visibility:hidden은 영역은 차지하나 그려지지만 않습니다.



#### width

요소의 너비를 지정합니다.



#### height

요소의 높이를 지정합니다.



#### margin

외부 여백을 지정합니다.



#### padding

내부 여백을 지정합니다.



#### margin-{left | right | top | bottom}

해당 방향의 외부 여백을 지정합니다.



#### padding-{left | right | top | bottom}

해당 방향의 내부 여백을 지정합니다.



#### cursor

요소에 올려진 마우스 커서의 모양을 지정합니다.



#### color

요소의 폰트 색상을 설정합니다.



#### background

요소의 배경을 지정합니다. 이미지 또는 색상 등이 올 수 있습니다.



#### background-image

요소의 배경 이미지를 지정합니다. background 이후에 오면 기존에 이미지 설정 시 덮어씁니다.



#### background-color

요소의 배경 색을 지정합니다. background 이후에 오면 기존에 배경색 설정 시 덮어씁니다.



#### background-repeat

배경의 반복 여부를 지정합니다.



#### background-blend-mode

배경이 여러개 주어졌을 때 색상 혼합 모드를 설정합니다.



#### background-clip

배경이 요소 내에서 얼마나 확장되어야 하는지 지정합니다.



#### background-position

배경에서 위치를 지정합니다.



실습은 https://www.w3schools.com/cssref/css3_pr_background.asp 에서 할 수 있습니다.



#### border

테두리를 지정합니다.



#### border-style

solid, dashed, dotted, double, groove, ridge, inset, outset, unset, none 등이 있습니다.



#### border-radius

테두리의 둥근 반지름을 지정합니다.



#### border-width

테두리의 두께를 지정합니다.



#### border-color 

테두리의 색상을 지정합니다.



#### border-image

테두리로 사용할 이미지를 지정합니다.



#### border-{left | right | bottom | top}

테두리의 해당 방향에 대해 지정합니다.



#### border-{left | right | bottom | top}-{width | color | style}

테두리의 해당 방향에 해당 속성을 지정합니다.



#### border-{bottom | top}-{left | right}-radius

테두리의 해당 방향의 둥근 반지름을 지정합니다.



#### text-align

텍스트의 정렬 위치를 지정합니다

left, right, center, justify 가 있습니다.



#### font-size

폰트의 크기를 지정합니다.



#### font-family

폰트의 종류를 지정합니다.



#### font-weight

폰트의 두께를 지정합니다.



#### line-height

텍스트의 줄 높이를 지정합니다.



#### letter-spacing

문자의 간격을 지정합니다.



#### text-decoration

텍스트의 꾸밈을 설정할 수 있습니다.

line-through, overline, underline 등이 있습니다.



#### text-indent

텍스트의 들여쓰기를 설정할 수 있습니다.



#### text-shadow

텍스트의 그림자를 설정합니다.

```
text-shadow: horizontal vertical blur-radius color|none
```



#### text-transform

텍스트의 대소문자를 지정할 수 있습니다.

uppercase : 대문자로 변경, lowercase : 소문자로 변경, capitalize : 첫 글자만 대문자로 변경



#### vertical-align

요소의 수직 정렬을 지정합니다.



#### white-space

화이트 스페이스를 처리하는 방법을 지정합니다.

normap, nowrap, pre, pre-line, pre-wrap 등이 있습니다.

pre* 를 사용하면 \<pre>와 동일하게 출력됩니다.



#### word-break

하나의 단어의 줄바꿈을 지정합니다.

break-all : 단어 여부 없이 무조건 줄바꿈합니다.

keep-all : CJK(중국, 일본, 한국) 언어에 한해 유지합니다. CJK가 아닌 언어에는 normal과 동일합니다.

normal : 단어는 유지하되 하이픈 등에는 줄바꿈합니다.



#### word-spacing

띄어쓰기의 길이를 지정합니다.



#### tab-size

탭의 크기를 지정합니다.



#### z-index

요소의 스택 순서(렌더링 순서)를 지정합니다. 

z-index가 클수록 나중에 그려져 앞에 있습니다.



#### tranform

요소의 변형을 정의합니다.



#### transition

요소의 값 변화시 애니메이팅 방식을 지정합니다.



#### overflow

요소를 벗어났을 때 처리 방식을 선택합니다.

hidden: 요소의 넘치는 부분을 숨깁니다, visible: 요소의 넘치는 부분을 그립니다. scroll : 요소를 벗어나면 스크롤 처리합니다.



#### text-overflow

텍스트가 요소를 벗어났을 때 처리하는 방식을 선택합니다.

clip : 잘리는 대로 그립니다, ellipsis : 넘치는 부분을 ... 으로 처리합니다.



#### filter

요소에 필터를 적용합니다.



#### list-style

리스트의 마커 속성을 지정합니다.



#### list-style-type

리스트 마커의 모양을 지정합니다.

sqaure, circle 등이 있으며 자세한건 https://www.w3schools.com/cssref/pr_list-style-type.asp 에서 확인할 수 있습니다.



#### list-style-position

리스트 마커의 위치를 지정합니다.

outside : 외부에 표기합니다. 기본값입니다.

inside: 내부에 표기합니다.



### display: flex

정렬을 동적으로 만들어주는 display 타입입니다.

개인적으로 가장 자주 사용하는 display 타입으로 간단한 정렬 및 비율 배치가 가능합니다.



#### flex-direction

기본적으로 row로 되어있으며 가로로 나열합니다.

- row : 가로로 나열
- column : 세로로 나열
- row-reverse : 가로 역순 나열
- column-reverse : 세로 역순 나열



#### align-items

축의 수직 방향으로 정렬을 지정합니다.

- flex-start : 시작 부분에 정렬
- flex-end : 끝 부분에 정렬
- center : 중앙 정렬
- stretch : 늘려서 정렬



#### justify-content

축의 수평 방향으로 정렬을 지정합니다.

- flex-start : 시작 부분에 정렬
- flex-end : 끝 부분에 정렬
- center : 중앙 정렬
- stretch : 늘려서 정렬



#### gap 

요소간의 간격을 지정합니다.



#### flex-wrap

자식 요소가 넘칠 때 wrap 여부를 지정합니다. (inline-block 처럼 wrap할지 여부)



#### flex

display:flex의 자식의 크기를 지정하는데 사용합니다.

`flex: 1 0 0;` 형태로 사용하며 앞에서부터 flex-grow, flex-shrink, flex-basis입니다.

flex-grow는 가중치를 의미하며, flex-shrink는 객체의 너비가 줄어들지 여부, flex-basis는 시작 너비 입니다.



#### flex-grow

가중치를 의미합니다.

한 flex의 자식에 flex-grow가 2, 1 으로 있으면 부모의 너비를 100%로 가정할 때 각각 2:1의 비율로 66.6%:33.3% 크기가 지정됩니다.

3개의 자식이 있고 하나의 width가 100px 나머지의 flex-grow가 1, 4이면, 첫 요소는 100px, 나머지 요소는 100%에서 100px을 뺀 부분을 1:4로 나누어 크기가 지정됩니다.



#### flex-shrink

요소가 그려져야하는 기준 너비가 있을 때 flex-grow 시스템에 의해 지정되는 너비가 기준 너비보다 작을 때 줄어들지 말지 여부입니다.

1이면 최소 너비보다 작아지고, 0이면 더이상 줄어들지 않습니다.



#### flex-basis

요소를 그리는 기준 너비입니다. 기본적으로 auto값이며, 0으로 지정시 flex-shrink가 1일 때 공간이 부족하면 가려질 수 있습니다.

공간이 넉넉하면 flex-basis를 시작 크기로 잡습니다.

