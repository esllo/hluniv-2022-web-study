# JS 기본

JS의 간단한 사용법에 대해 알아봅니다.



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



## Object 함수



### .defineProperty(target, prop, descriptor)

객체에 새로운 속성을 정의하거나 존재하는 속성을 수정합니다.

prop은 속성의 이름을 뜻하며 descriptor는 속성을 기술합니다.

##### descriptor

- configurable\<boolean> : 속성의 변경이 가능하고 삭제할 수 있는지 여부 (false)
- enumerable\<boolean> : 속성이 열거 가능한지 여부 (false)
- value\<any> : 속성의 값 (undefined)
- writable\<boolean> : 속성의 값 변경 가능한지 여부 (false)
- get\<function> : 접근자(getter)
- set\<function> : 설정자(setter)

###### object.key = value 형태로 지정하면 모든 속성이 true입니다.

```js
const a = {}
Object.defineProperty(a, 'b', {
    value: 3,
    writable: false,
    configurable: false,
    enumerable: false,
})
```





### .defineProperties(target, props)

객체에 속성을 여러개 지정합니다.

```js
const  a = {};
Object.defineProperties(a, {
    a: {
        value: 1
    },
    b: {
        value: 2,
        configurable: false
    }
})
```





### .getOwnPropertyDescriptor(target, prop)

객체의 속성에 대한 descriptor를 반환합니다.



### .getOwnPropertyDescriptors(target)

객체의 모든 속성에 대한 descriptor를 반환합니다.





### .assign(target, source)

target의 object에 source를 합쳐서 target을 리턴합니다.

```js
const a = {
    a: 1
}
const b = {
    b: 1
}
const c = Object.assign(a, b) // {a:1, b:1}
console.log(a==c) // true
```



### .freeze(target)

객체를 더 이상 변경할 수 없도록 만듭니다.

```js
const a = {
    a: 1
}
Object.freeze(a)
console.log(a.a) // 1
a.a = 3
console.log(a.a) // 1
```





### .isFrozen(target)

객체의 freeze 여부를 리턴합니다.





### .seal(target)

객체에 새로운 속성을 추가할 수 없고, writable 하지 않은 속성을 설정 불가능으로 만듭니다.

```js
const a = {
    a: 1
}
Object.seal(a)
console.log(a.a) // 1
a.b = 3
console.log(a.b) // undefined
```





### .isSealed(target)

객체의 seal 여부를 리턴합니다.





### .entires(target)

객체를 [키, 값] 형태의 값을 가지는 배열로 리턴합니다.

```js
const a = {
    a: 1,
    b: 2
}
Object.entires(a) // [["a", 1], ["b", 2]]
```





### .fromEntires(target)

[키, 값] 형태의 값을 가지는 배열을 객체로 변환합니다.

```js
const a = [['a', 1], ['b', 1]]
Object.fromEntires(a) // {a: 1, b: 1}
```





### .keys(target)

객체의 열거 가능한 키 배열을 리턴합니다.

```js
const a = {
    a: 1,
}
Object.defineProperty(a, 'b', {value: 2})
Object.keys(a) // ['a']
```





### .getOwnPropertyNames(target)

객체의 키 배열을 리턴합니다.

```js
const a = { a: 1 }
Object.defineProperty(a, 'b', {value: 2})
Object.getOwnPropertyNames(a) // ['a', 'b']
```





### .getOwnPropertySymbols(target)

객체의 심볼 키 배열을 리턴합니다.

```js
const a = {}
a[Symbol('a')] = 1
Object.getOwnPropertySymbols(a) // [Symbol('a')]
```





### .values(target)

객체의 열거 가능한 값 배열을 리턴합니다.

```js
const a = {
    a: 1,
    b: 2
}
Object.values(a) // [1, 2]
```





