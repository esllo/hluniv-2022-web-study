# CSS Flex

flex에 대해 알아봅니다.



## flex, inline-flex

display: flex

display: inline-flex 형식으로 사용할 수 있습니다.

inline-flex의 경우 flex와 동일하게 동작하지만, inline 처럼 동작하여 자식의 크기를 감싸게됩니다.



flex에는 main axis와 cross axis가 있습니다.



## flex의 정렬



### flex-direction

flex의 방향을 지정합니다.

##### row, row-reverse

- x축이 main axis, y축이 cross axis

##### column, column-reverse

- x축이 cross axis, y축이 main axis





### flex-wrap

flex의 자식 요소의 줄넘김을 설정합니다.

- wrap: 줄을 넘깁니다.
- wrap-reverse: 줄을 넘기지만 역순으로 넘깁니다.
- nowrap: 줄넘김을 하지 않습니다.

 

### flex-flow

flex-direction과 flex-wrap을 한번에 지정합니다.

` flex-flow: {flex-direction} {flex-wrap};`



### justify-content

main axis를 기준으로 정렬을 지정합니다.

- flex-start : 시작 부분에 정렬

- flex-end : 끝 부분에 정렬

- center : 중앙 정렬

- stretch : 늘려서 정렬

- space-evenly: 요소들의 앞, 뒤, 사이에 균등하게 간격으로 정렬

  -A-B-C-

- space-around: 요소들의 좌, 우에 각각 간격으로 정렬

  -A--B--C-

- space-between: 요소들의 사이에 균등하게 간격으로 정렬

  A-B-C

`-`는 간격



### align-content

cross axis 기준으로 wrap이 일어났을 때의 정렬을 지정합니다.

justify-content와 값을 공유합니다.



### align-items

cross axis를 기준으로 정렬을 지정합니다.

- flex-start : 시작 부분에 정렬
- flex-end : 끝 부분에 정렬
- center : 중앙 정렬
- stretch : 늘려서 정렬
- baseline: 텍스트의 베이스라인 기준으로 정렬



### align-self

cross axis를 기준으로 정렬을 지정합니다.

align-items는 display:flex를 가진 부모에 지정한다면,

align-self는 자식에게 지정하여 해당 자식만 적용되도록 합니다.

```css
.parent{
    display: flex;
    align-items: center;
}

.child{
    align-self: flex-start;
}
```



## flex의 자식 속성

### flex-grow

flex 자식이 어느 배율로 가중치를 가질지 지정합니다.

0이 기본값이며, 이 때 가변적으로 늘어나지 않습니다.

0 보다 큰 수가 오게되면 해당 가중치 만큼의 비율로 부모의 남은 영역을 채우게 됩니다.



### flex-shrink

flex 자식이 계산된 크기가 지정한 크기 보다 작아질 수 있는지 지정합니다.

1이 기본값이며, 이 때 지정 크기보다 작아질 수 있습니다.

0이 오면 작아지지 않습니다.

여기서 지정한 크기는 flex-basis또는 width / height에 해당합니다.



### flex-basis

flex 자식의 기본 시작 너비(row) 또는 높이(column)를 지정합니다.

auto가 기본값이며, 값을 지정하게 되면 해당 크기가 지정 크기가 됩니다.

flex-basis값이 지정되면 해당 크기가 최소로 보장되며, 계산된 영역의 크기가 basis보다 크면 해당 크기로 그려집니다.



### flex

flex-grow, flex-shrink, flex-basis를 한번에 지정합니다.

`flex: {flex-grow} {flex-shrink} {flex-basis} ` 형식으로 지정하며, 

`flex: 1` 이라고 지정하면 grow:1, shrink: 1, basis: 0으로 지정됩니다.



### order

flex 에서 배치되는 순서를 지정합니다.

DOM 순서는 변하지 않으나, 그리는 위치만 변경됩니다.