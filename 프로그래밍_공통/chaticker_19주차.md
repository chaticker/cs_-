## Module Bundler란?

여러 개의 나누어져 있는 파일들을 하나의 파일로 만들어주는 라이브러리(wepback, Parcel 등)

### 왜 나옴?

모듈 번들러 개념이 없었을 때 웹페이지에 접속했다고 가정

→ 이때 웹페이지에서는 페이지를 보여주기 위한 수 많은 자바스크립트 파일을 서버에 요청

→ 이를 통해 웹페이지를 보여주기 위해 서버와 여러 번 통신하게 되는 게 비효율적임

위와 같은 문제를 해결하기 위해 생김

하지만 지원을 안 해주는 브라우저들도 있기 때문에 웹팩과 같은 모듈 번들러 라이브러리가 브라우저들이 지원할 수 있는 코드로 변환해야 함

---

## 자바스크립트 반복문의 종류와 사용법에 대해 설명해주세요.

### 1. for in : 객체의 프로퍼티 키 열거 전용

```javascript
var obj = {
  a: 1,
  b: 2,
  c: 3,
};

for (var item in obj) {
  console.log(item); // a, b, c
}

//만약 for ...of 를 쓴다면
var obj = {
  a: 1,
  b: 2,
  c: 3,
};

for (var item of obj) {
  console.log(item); // Uncaught TypeError: obj is not iterable
}
```

## 2. for of : 배열 이터러블 순회 전용

```javascript
var arr = [1, 2, 3];

for (var item of arr) {
  console.log(item); // 1, 2, 3
}

//만약 for ...in 를 쓴다면
var arr = [1, 2, 3];

for (var item in arr) {
  console.log(item); // 0, 1, 2
}
```

## 3. Object 객체 메서드: 객체 순회 전용

```javascript
1) Object.keys(객체)
: 객체의 프로퍼티 '키'를 배열로 반환

Object.keys({name:'curryyou', job:'engineer'});
// [ 'name', 'job' ]


2) Object.values(객체)
: 객체의 프로퍼티 '값'을 배열로 반환

Object.values({name:'curryyou', job:'engineer'});
// [ 'curryyou', 'engineer' ]


3) Object.entries(객체)
: 객체의 프로퍼티 [키, 값]을 배열로 반환

Object.entries({name:'curryyou', job:'engineer'});
// [ [ 'name', 'curryyou' ], [ 'job', 'engineer' ] ]
```

## 4. Array.prototye 메서드 : 배열 전용(4종류)

```javascript
1) 배열.forEach( (value, index, array)=>{...반복 수행 코드...} )
: 배열의 length만큼 반복하여 콜백함수를 호출한다.
: 콜백함수의 매개변수로 value에 요소값, index에 인덱스, array에 원본배열이 들어온다.

[1, 2, 3, 4].forEach((value, index, array)=>{
    console.log(value);  // 1, 2, 3, 4 출력
})


2) 배열.map( (value, index, array)=>{...반복 수행 코드...} )
: forEach와 동일(순회 방식, 콜백함수 매개변수 등)
: 다른점 => 각 콜백함수에서 return 하는 값들으로 새로운 배열을 만들어 반환한다.

const map_reuslt = [1, 2, 3, 4].map((value, index, array)=>{
    console.log(value); // 1, 2, 3, 4 출력
    return value*10; // 각 요소에 10을 곱한 값을 배열로 반환
})

console.log(map_reuslt);
// [ 10, 20, 30, 40 ]


3) 배열.filter( (value, index, array)=>{...반복 수행 코드...} )
: forEach와 동일(순회 방식, 콜백함수 매개변수 등)
: 다른점 => 각 콜백함수에서 return하는 값이 true일 때만, 그때의 value 값들로 새로운 배열을 만들어 반환한다.

const filter_result = [1, 2, 3, 4].filter((value, index, array)=>{
    console.log(value); // 1, 2, 3, 4 출력
    return value%2 == 0; // value가 짝수인 값들을 배열로 반환
})

console.log(filter_result);
// [ 2, 4 ]


4) 배열.reduce( (previousValue, currentValue, currendIndex, array)=>{...반복 수행 코드...}, initialValue )
: 두번째 매개변수인 initialValue값을 시작으로,
: 각 콜백함수가 return하는 값이 다음에 실행되는 콜백함수의 previousValue로 들어간다.
: 최종적으로 마지막 콜백함수가 return하는 값을 반환한다.(아래의 코드를 보면 이해가 잘 됨.)

const reduce_result = [1, 2, 3, 4].reduce((pv, cv, idx, arr)=>{
    return pv + cv; // 이전 콜백함수가 리턴한 값에 현재의 요소 값을 더함(누적 개념)
}, 100); // 100을 초기값으로 줌

console.log(reduce_result);
// 110 (100 + 1 + 2 + 3 + 4 결과)
```

---

## 위에서 파생된 질문: 객체 배열에서 속성들 중 최대 값을 찾으려면, 어떻게 코드를 짜는 것이 효율적인가요? (data는 주어진다고 가정)

```javascript
/* data 👇🏻
[
  {
    "x": "8/11/2009",
    "y": 0.026572007
  },
  {
    "x": "8/12/2009",
    "y": 0.025057454
  },
  {
    "x": "8/13/2009",
    "y": 0.024530916
  },
  {
    "x": "8/14/2009",
    "y": 0.031004457
  }
]
*/

답변

1) reduce 사용

const max = data.reduce(function(prev, current) {
    return (prev.y > current.y) ? prev : current
})

2) map 사용
const maxValueOfY = Math.max(...arrayToSearchIn.map(o => o.y), 0);

```
