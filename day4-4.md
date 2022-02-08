# Grid 실습

grid의 속성을 직접 사용해봅니다.



실습은 아래 텍스트를 문서로 만들어 진행합니다.

```html
<!DOCTYPE html>
<html lang="ko">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grid Practice</title>
  <link rel="stylesheet" href="https://web.esllo.com/css/day4-1.css" />
</head>

<body>
  <main>
    <!-- SECTION 1 -->
    <section>
      <div class="grid-box section1">
        <div class="box box1">
          box1
        </div>
        <div class="box box2">
          box2
        </div>
        <div class="box box3">
          box3
        </div>
        <div class="box box4">
          box4
        </div>
        <div class="box box5">
          box5
        </div>
        <div class="box box6">
          box6
        </div>
        <div class="box box7">
          box7
        </div>
      </div>
    </section>
    <!-- SECTION 1 -->
    <!-- SECTION 2 -->
    <section>
      <div class="grid-box section2">
        <div class="box box1">
          box1
        </div>
        <div class="box box2">
          box2
        </div>
        <div class="box box3">
          box3
        </div>
        <div class="box box4">
          box4
        </div>
        <div class="box box5">
          box5
        </div>
        <div class="box box6">
          box6
        </div>
        <div class="box box7">
          box7
        </div>
      </div>
    </section>
    <!-- SECTION 2 -->
    <!-- SECTION 3 -->
    <section>
      <div class="grid-box section3">
        <div class="box box1">
          box1
        </div>
        <div class="box box2">
          box2
        </div>
        <div class="box box3">
          box3
        </div>
        <div class="box box4">
          box4
        </div>
        <div class="box box5">
          box5
        </div>
        <div class="box box6">
          box6
        </div>
        <div class="box box7">
          box7
        </div>
      </div>
    </section>
    <!-- SECTION 3 -->
    <!-- SECTION 4 -->
    <section>
      <div class="grid-box section4">
        <div class="box box1">
          box1
        </div>
        <div class="box box2">
          box2
        </div>
        <div class="box box3">
          box3
        </div>
        <div class="box box4">
          box4
        </div>
        <div class="box box5">
          box5
        </div>
        <div class="box box6">
          box6
        </div>
        <div class="box box7">
          box7
        </div>
      </div>
    </section>
    <!-- SECTION 4 -->
  </main>
</body>

</html>
```







## 구현부 링크

https://web.esllo.com/day4grid.html

위 사이트를 참고하여 진행합니다.



## 섹션 1



grid-template을 이용하여 열 기준 3 : 3 : 1 의 비율로 정렬해 봅니다.

grid-template와 반복을 이용하여 행 기준 100px * 3 으로 정렬해 봅니다.

각 공간 사이에는 10px 만큼의 공간을 넣어 봅니다.





## 섹션 2

반복과 특정 키워드를 사용하여 최소10%, 최대 자동 너비의 반복을 설정하고, 남은 여백은 꽉 채우도록 만듭니다.

grid-auto를 이용하여 높이는 100px로 정렬합니다.





## 섹션 3

grid-template과 반복을 사용하여 열은 25%로 4개, 행은 50px로 4개를 만듭니다.

빈 공간은 채우도록 설정합니다.

box3은 행 기준 1부터 3칸의 너비를 가지고, 열 기준 2 부터 4까지 차지합니다.

box4는 자신의 위치로 부터 2칸의 너비를 가집니다.





## 섹션 4

align, justify, place의 items, content, self 를 사용해봅니다.

그리드의 cross축 기준으로는 좌우 균등한 여백을 넣습니다.

아이템의 cross축 기준으로는 중앙에, main축 기준으로는 시작부분에 정렬합니다.