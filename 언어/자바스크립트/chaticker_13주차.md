## .forEach 루프와 .map() 루프 사이의 주요 차이점을 설명할 수 있나요? 왜 둘 중 하나를 선택할 것인가요?​

forEach

배열의 요소를 반복하며, 각 요소에 대해 콜백을 실행하지만 값을 반환하지 않는 특징이 있다.

```javascript
const a = [1, 2, 3];
const doubled = a.forEach((num, index) => {
    ...
});
// doubled = undefined
```

map

배열의 요소를 반복하며, 각 요소에서 함수를 호출하여 결과로 새 배열을 작성하여 각 요소를 새 요소에 매핑한다.

```javascript
const a = [1, 2, 3];
const doubled = a.map((num) => {
    return num \* 2;
});
// doubled = [2, 4, 6]
```

.forEach와 .map()의 가장 큰 차이점은 .map()이 새로운 배열을 반환한다는 것이다. 결과가 필요하지만 원본 배열을 변경하고 싶지 않으면 .map(), 단순히 배열을 반복할 필요가 있다면 forEach가 좋은 선택이다.

---

## function foo() {}와 var foo = function() {} 사이에서 foo 사용의 차이에 대해 설명하세요.​

전자는 함수 선언인 반면, 후자는 함수 표현식이다. 주요한 차이점은 함수 선언은 함수바디가 호이스트되지만, 함수 표현식의 바디는 호이스트되지 않는다.(변수와 동일한 호이스팅 동작을 가짐). 함수 표현식을 정의하기 전에 호출하려고 하면 Uncaught TypeError : XXX is not function 에러가 발생한다.

함수 선언

```javascript
foo(); // 'FOOOOO'
function foo() {
  console.log("FOOOOO");
}
```

함수 표현식

```javascript
foo(); // Uncaught TypeError: foo는 함수가 아닙니다
var foo = function () {
  console.log("FOOOOO");
};
```

---

## "attribute"와 "property"의 차이점은 무엇인가요?​

attribute는 HTML 마크업에 정의되지만 property는 DOM에 정의된다. 차이점을 설명하기
위해 HTML에 다음 텍스트 필드가 있다고 가정해 보면,

```html
<input type="text" value="Hello" />
```

```javascript
const input = document.querySelector("input");
console.log(input.getAttribute("value")); // Hello
console.log(input.value); // Hello
```

    그러나 텍스트 필드에 "World!"를 입력하면 아래와 같이 된다.

```javascript
console.log(input.getAttribute("value")); // Hello
console.log(input.value); // Hello World!
```
