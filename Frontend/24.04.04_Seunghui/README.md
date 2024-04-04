# 자바 스크립트 기본 배워보자
--------

### 1) 자바 스크립트에서 변수 선언
- 자바 스크립트는 파이썬과 다르게 변수 선언 시 앞에 붙여야 하는 것이 있다.

``` js
const a = 3;
let b = 5;

+) var c = 8;
```

여기서 const와 let의 차이는 무엇인가?

const는 constant(상수) 이다. 이는 즉, 변수의 값을 변경할 수 없다는 것을 의미하게 된다.

하지만 let 같은 경우, 한번 변수를 선언하고 난 후, 원할 때 변수의 값을 바꿀 수 있다.
이때, 한번 생성된 변수는 다음에 변수의 값을 변경(재할당) 할 때 let을 다시 쓰지 않는다. (let은 새로운 변수를 생성하는 것을 의미한다.)

+) C언어 같은 경우에도 변수 선언 시 앞에 붙여야 하는 것이 있는데, 이는 타입에 따라 int, char, double 등등이 있다. (const 또한 붙일 수 있음. 여기서의 const도 JS와 마찬가지로 한번 선언 후 값을 바꾸지 않는 것을 의미한다.)

++) 기존 버전에서의 자바 스크립트에는 오직 var 밖에 없었다고 한다. var은 변수의 값을 바꿔도 우리에게 알리지 않았기 때문에 값을 고정할 필요가 있는 경우에 문제가 생겼다. 그래서 const / let이 나오게 된 것이다.

#### 그렇다면 const와 let 중 어느것을 써야 할까?
- 대부분 const를 기본적으로 사용하고, 필요할때만 (만약 변수를 업데이트 하고 싶다면) let을 쓴다고 한다. // 모든 변수를 업데이트해야 하는 경우는 잘 없다. 프로그램에서 몇몇 중요한 부분만 업데이트를 한다고...

=> 솔직히 나는 let을 더 많이 쓸 줄 알았음. 값을 잘 안바꾸나...? << 실제로 C에서는 const를 그다지 많이 선호하지는 않았던 것 같음. (아닐수도...)

#### 결론은?
- 기본적으로 const를 쓰고 필요할 때만 let을 쓰되, var은 쓰지 말 것.

---

### 2) 콘솔에 출력하는 법
- 자바 스크립트는 콘솔에 출력할 수 있는 방법이 있다.

```js
console.log('hello world');
```

- 문자 그대로를 해석해보면 콘솔에 로그(기록)을 남긴다. 라는 의미인 것 같다.

----

### 3) 데이터 타입 - booleans

```js
const one = true;
const two = false;
const three = null;
let four;
```

- 데이터에도 여러 타입이 있다. python 에서도 있어서 잘 아는 booleans 타입인데, 거기에 null과 undefined도 첨가되었다.
- true / false 같은 경우, 이들은 값이 존재하고 있는 것이다. 각각 '참'과 '거짓'이라는 값이 존재한다.
- null 같은 경우, 비어있다는 것이 아니라 아무것도 없는 상태로 채워져있다는 것이 더 맞는 말인 것 같다.
- undefined 같은 경우, 영어의 뜻 그대로 변수는 존재하는데, 정의되지 않았다는 의미이다. 즉, 컴퓨터 메모리 안에는 존재하나(공간이 있으나), 값이 들어있지 않다는 것이다.

+) null 같은 경우, 자연적으로 발생하지 않는다. 우리가 변수 안에 어떤 것이 없다는 것을 확실히 하기 위해 사용하는 것.

------

### 4) Arrays(배열)

```js
const mon = 'mon';
const tue = 'tue';
const wed = 'wed';
const thu = 'thu';
const fri = 'fri';
const sat = 'sat';
const sun = 'sun';

const daysOfWeek = [mon, tue, wed, thu, fri, sat, sun];

const name = ['Ritsu', 'Roku', 1, null, true, 'my_name'];

// 배열에서 원하는 인자를 가져오는 법
console.log(name[0]);

// 배열에 인자를 추가하는 법
name.push('Yata');

// 배열에 없는 인덱스를 출력하려고 한다면?
console.log(name[10000]);
// ==> 인덱스 에러가 아니라 undefined가 나온다. 아직 정의되지 않았다! 이건 좀 신기한듯...
```

배열은 파이썬에서 리스트와 같은 의미이다. 명칭만 다를 뿐 파이썬과 자바스크립트 모두 배열을 만드는 방식은 똑같다. [] 안에 감싸져 있고 인자들은 쉼표(,)로 구분된다는 것.
인자는 숫자, 문자열, null, true 같은 다양한 데이터 타입 및 변수도 가능하다.

배열은 인덱스 0번부터 시작한다. 원하는 값을 얻기 위해서는 파이썬과 똑같이 '배열이름[인덱스번호]'로 찾으면 된다.

파이썬과 다른점은 배열에 인자를 추가하려면 append가 아니라 push를 이용한다는 것이다.

----

### 5) Objects(객체)

``` js
const player = {
    name:'seunghui',
    points: 10,
    age: 26,
    student: true,
};
console.log(player);
console.log(player.name);
console.log(player['name']);
```

자바 스크립트에서 object는 property(속성)을 가진 데이터를 저장하도록 해준다.

자바 스크립트에서의 object는 파이썬에서 딕셔너리 같은 존재인 것 같다.

출력하는 형식이 두 가지가 있는데, 하나는 파이썬 딕셔너리의 value 값을 출력하는 방식과 동일하였고 'player['name']', 다른 한가지 방식은 'player.name' 이었다.

``` js
console.log(player);
player.points = 20;
console.log(player);

player.home = 'Incheon';
console.log(player);
```

const로 지정을 하였어도 object 안에 있는 값은 바꿀 수 있다!
안에 있는 값만 바꾸는 것이지, object 자체는 변경하지 않았다는 것이다.
const는 object에게 적용된다는 것!

마찬가지로 object 안에 없는 내용을 추가하는 것도 할 수 있다! (이건 조금 헷갈릴수도... ...)