# JS 기본

JS의 간단한 사용법에 대해 알아봅니다.



https://developer.mozilla.org/ko/docs/Web/JavaScript

https://ko.javascript.info/

위 링크에서 더 자세한 자바스크립트의 강의를 확인할 수 있습니다.





## JS의 데이터 타입

JS에는 다양한 데이터 타입이 있습니다.

- Boolean
- Null
- Undefined
- Number
- Bigint
- String
- Symbol
- Object
  - Function
  - Array
  - Date
  - ...

자바스크립트에서는 타입을 선언하지 않고 변수를 선언할 수 있습니다.

JS에서는 아래 값들을 false로 취급합니다.

공백 문자열 : ''

빈 배열 : []

숫자 0 : 0



## JS의 변수 선언

JS에서는 var, let, const를 통해 변수를 선언할 수 있습니다.

이 때 var는 function scoped 또는 globally-scoped이며, let, const는 block scoped 입니다.



var는 function scoped 또는 globally-scoped 이므로, 아래의 코드가 동작합니다.

```js
if(true){
    var i = 3
}
console.log(i) // 3
```



let과 const는 block scoped 이므로 아래 코드는 Reference Error를 띄웁니다.

```js
if(true){
    const i = 3 // let i = 3
}
console.log(i) // Reference Error
```



## JS에서의 호이스팅

JS에서는 var, const, let, function등이 선언 되면 호이스팅이 동작합니다.

```js
console.log(x) // undefined
var x = 3
```

위의 코드는 에러없이 undefined를 출력합니다.

실제로 위 코드는 아래처럼 해석됩니다.

```js
var x
console.log(x)
x = 3
```



const나 let도 호이스팅 됩니다. 하지만 에러가 발생합니다.

```js
console.log(y) // Reference Error
const y = 3 // let y = 3
```

이는 var는 호이스팅 될 때 선언과 초기화가 일어나지만, const와 let은 선언만 이루어지기 때문에 에러가 발생합니다.



#### JS에서의 변수 사용 단계

1. 선언 : 스코프, 변수 객체가 생성되며 변수 객체를 참조한다. 

2. 초기화 : 변수 객체를 위한 메모리를 할당 받는다. 기본 값으로 undefined로 초기화한다.

3. 할당 : 변수 객체에 값을 할당한다.



var의 호이스팅은 1, 2가 일어나고, const, let의 호이스팅은 1만 일어난다.



## JS의 함수

JS의 함수는 일급 함수(First class)입니다.

이는 함수를 변수처럼 다룰 수 있음을 뜻합니다.

```js
function something(){
    // something
    console.log('hi')
}
const callback = something
callback() // 'hi'
```



### 일반 함수

일반적으로 함수는 아래와 같이 선언합니다.

```js
function functionName(param1, param2, ...params){
    // do something
    
    return something
}
```

return할 값이 없다면 return에 해당하는 줄을 삭제할 수 있습니다.



### 무명함수

```js
function(){
    // do something
    // return or not
}
```

무명함수도 선언할 수 있습니다. 주로 리턴 값이나 콜백으로 사용하며 단순 선언시 저장할 수 있습니다.

```js
const func = function(){
    //do something
}
```





### 화살표 함수

화살표 함수를 통해 함수를 선언할 수 있습니다.

```js
const functionName = (param1, ...params) => {
	// do something
    // return or not
}
```



화살표 함수에서 block을 없애면 값을 바로 리턴할 수 있습니다.

```js
// 아래 두 함수는 같은 함수 입니다.
const func = (num) => num+3

const func = (num) => {
    return num + 3
}
```

단 object를 리턴할 경우 ()로 감싸줍니다.

`const func => (param) => ({key: param})`



### 클로저 함수

일급 함수이기 때문에 클로저를 사용할 수 있습니다.

클로저는 다른 함수의 파라미터를 참조하는 함수를 뜻합니다.

```js
function person(name){
    return function(age){ // 이 함수는 부모 함수의 name 파라미터를 참조합니다.
        console.log(name, age)
    }
}

person('HongGilDong')(21) // HongGilDong, 21
```





### 커링 함수

일급 함수이기 때문에 역시 커링 함수를 사용할 수 있습니다.

위의 클로저 함수 처럼 함수가 함수를 리턴하는 경우를 커링이라고 부릅니다.

```js
function a(param1){
    return function b(param2){
        return function c(param3){
            console.log(param1 + param2 + param3)
		}
    }
}
a(1)(2)(3) // 6
```





## Javascript의 연산자

#### 비교 연산자

- ==, !=, ===, !==, >, >=, <, <=

비교 연산자에서 ==와 ===의 차이는

타입까지 비교하는지의 여부입니다.

0 == '0' => true

0 === '0' => false



#### 비트 연산자

- &, |, ^, ~, <<, >> , >>>

& = and

| = or

^ = xor

~ = not

<< = 좌측 시프트

\>\> = 우측 시프트(부호 유지)

\>\>\> = 우측 시프트(새 비트 0으로 고정)



#### 논리 연산자

- &&, ||, !



## JS의 배열

JS에서 배열은 아래처럼 선언합니다.

```js
const array1 = []
const array2 = [1, 2, 3]
const array3 = new Array(3) // [emtpy * 3] => [undefined, undefined, undefined]
```

- unshift : 값 추가(좌측에 추가)

- push : 값 추가 (우측에 추가)

- pop : 값 가져오기 (우측값 가져오기)

- shift : 값 가져오기 (좌측값 가져오기)

- splice(n, m, ...args) (값 제거 및 삽입)

  n번 째 인덱스에서 m개만큼 제거 후 args를 삽입합니다. args가 없으면 삭제만 합니다.

  

pop과 shift는 가져온 값을 리턴하며 배열에서 해당값이 사라집니다.



### 배열 순회

배열 순회는 다양한 방법으로 할 수 있습니다.

```js
const array = [2, 4, 8, 10]
```



#### for in

index를 순회합니다.

```js
for(index in array) console.log(index) // 0, 1, 2, 3
```



#### for of

value를 순회합니다.

```js
for(value of array) console.log(value) // 2, 4, 8, 10
```



#### .forEach

callback을 받아 순회합니다.

```js
array.forEach((value, index) => {console.log(index, value)})
// 0 2
// 1 4
// 2 8
// 3 10
```



#### .map

callback을 받아 순회하고 리턴합니다.

```js
const arr = array.map((value, index) => index+' '+value)
console.log(arr) // ['0 2', '1 4', '2 8', '3 10']
```



#### .reduce

callback을 받아 특정 값을 리턴합니다.

```js
const result = array.map((total, current, index) => {
    return total + current
}, 0) // array.map((previous, current, index), defaultValue)
console.log(result) // 24
```



#### .find / .findIndex

조건식의 callback을 받아 객체를 찾습니다. 없으면 undefined를 리턴합니다.

findIndex를 객체의 인덱스값을 리턴합니다.

```js
const result = array.find((value) => value === 4)
console.log(result) // 4
```



#### .filter

조건식의 callback을 받아 객체를 찾습니다. find가 한개를 찾는다면 모든 값을 찾아 filter는 배열을 리턴합니다.

```js
const result = array.filter((value) => value < 7)
console.log(result) // [2, 4]
```



#### .some

조건식의 callback을 받아 해당 요소가 하나라도 있는지 찾습니다.

```js
const result1 = array.some((value) => value === 4)
const result2 = array.some((value) => value === 3)
console.log(result1, result2) // true, false
```



#### .every

조건식의 callback을 받아 해당 요소가 모두 해당하는지 체크합니다.

```js
const result1 = array.every((value) => value < 12)
const result2 = array.every((value) => value < 10)
console.log(result1, result2) // true, false
```



### 기타 배열 함수

#### .includes

해당 값을 갖는지 체크합니다.

```js
array.includes(4) // true
array.includes(5) // false
```



#### .indexOf, .lastIndexOf

해당 값을 갖는지 체크 후 첫 값 또는 마지막 값의 인덱스를 리턴합니다. 

```js
const array2 = [1, 2, 3, 2, 4]
array.indexOf(2) // 1
array.lastIndexOf(2) // 3
```



#### .join

배열을 특정 문자열을 통해 합칩니다.

```js
array.join('-') // 2-4-8-10
```



#### .concat

배열 두개를 합칩니다.

```js
const array2 = [1, 2, 3]
const array3 = array1.concat(array2)
console.log(array3) // [2, 4, 8, 10, 1, 2, 3]
```



#### .sort

배열을 정렬합니다.

```js
const array2 = [4, 2, 3, 1]
array2.sort() // 1, 2, 3, 4
```



#### .reverse

배열을 역순으로 만듭니다.

```js
const array2 = [4, 2, 3, 1]
array2.reverse() // 1, 3, 2, 4
```



#### .flat

배열의 평탄화 합니다.

```js
const array2 = [1, [2, [3, [4]]]]
array2.flat() // flat(1) => [1, 2, [3, [4]]
array2.flat(2) // [1, 2, 3, [4]]
array2.flat(Infinity) // [1, 2, 3, 4]
```



#### .slice

배열을 특정 부위만큼 얕은 복사합니다.

```js
array.slice(0, 2) // [2, 4]
array.slice(2) // [8, 10]
array.slice(2, 3) // [8]
```





## JS의 객체

JS에서 객체는 아래처럼 선언합니다.

```js
const object1 = {}
const object2 = {
    key: 'value'
}
const object3 = new Object() // {}
```



값에 접근할 때에는 두가지 방법을 사용할 수 있습니다.

```js
const obj = {}
// 아래 두가지는 동일
obj.name = 'obj1'
obj['name'] = 'obj1'
```

['key'] 형식을 사용하면 변수의 값을 통한 key 접근이 가능합니다.

```js
const key = 'name'
const obj = {}
obj[key] = 'obj1'
```
