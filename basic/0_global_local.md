# 지역변수 & 전역변수

```javascript
// 전역변수
var name = '짱구'

function test () {
  // 지역변수
  var name = '철수'
  name = '철수로 바꾸자!'
}

test()
console.log(name) // 짱구
```
- test내의 name은 해당 함수 스코프 범위에서 변수가 선언되었으므로 해당 함수 스코프 내에서만 접근할 수 있습니다.
- `전역 실행 컨텍스트`(아무 함수에도 속하지 않은 범위, 전역)에 선언된 name 변수는 test 함수 스코프 내에 있는 name 변수를 참조하지 못합니다.

```javascript
var a = 10
function b () {
  console.log('test')
}

console.log(this.a) // 10
console.log(this.b) // [Function: b]
```

- 전역 실행 컨텍스트에서 변수나 함수를 선언하면 Global 객체에 선언됩니다.
- 웹 브라우저의 Global 객체는 [window](https://developer.mozilla.org/ko/docs/Web/API/Window) 입니다.
- Node.js 환경의 경우 [여기](https://nodejs.org/api/globals.html#globals_global_objects) 참고.
- 웹, Node.js 공통으로 전역 실행 컨텍스트에서의 `this`는 전역 객체를 참조합니다.
  - 웹: this === window
  - Node.js: this === Node.js 전역 객체

Write : `2019.04.11`  
Update: `-`
