# 객체
## 객체의 생성
```javascript
// 1. 객체 리터럴로 생성하는 법
var card = {suit: "하트", rank: "A"}

// 2. 생성자로 생성하는 법
function Card(Suit,rank) {
 this.suit = suit;
 this.rank = rank;
}
var card = new Card("하트","A");

// 3. Object.create로 생성하는 방법 
var card = Object.create(Object.prototype,{
    suit: {
       value: "하트",
       writable: true,
       enumerable: true,
       configurable: true
    },
    rank: {
       value: "A",
       writable: true,
       enumerable: true,
       configurable: true
    }
}); 
```

## 프로토타입
### 생성자 안에서 메서드를 정의하는 방식의 문제점 
- 생성자 안에서 this 뒤에 메서드를 정의하면 그 생성자로 생성한 모든 인스턴스에 똑같은 메서드가 추가 된다. 그래서 메모리를 많이 소비하게 된다. 

```javascript
function Circle(center,radius) {
    this.center = center;
    this.radius = radius;
    this.area = function() {
        return Math.PI*this.radius*this.radius;
    };
}
var c1 = new Circle({x:0, y:0}, 2.0);
var c2 = new Circle({x:0, y:1}, 3.0);
var c3 = new Circle({x:1, y:0}, 1.0);
```
- 각각의 인스턴스가 똑같은 메서드 area를 소유한다.
<p align="center"><img width="70%" src="https://user-images.githubusercontent.com/76654131/142760833-6e7c177d-3c42-4cde-bb5d-5f7e77771d22.png">
</p>

## 프로토타입 객체 
- 자바스크립트에서는 함수도 객체이므로 함수 객체가 기본적으로 prototype 프로퍼티를 갖고 있다. (__proto__ 프로퍼티랑은 다른거다!)
```javascript
function F() {};
console.log(F.prototype) // Object {}
```
- prototype 속성은 자신의 prototype 객체로 자식 객체(생성자로 생성한 인스턴스)가 참조하는 객체이다.

<p align="center"><img width="50%" src="https://user-images.githubusercontent.com/76654131/142761533-1a3ba4f8-2565-471d-b029-53a1d9152faa.png"></p>

- 프로토타입 객체의 프로퍼티는 생성자로 생성한 모든 인스턴스에서 그 인스턴스의 프로퍼티처럼 사용 가능하다.
```javascript
F.protoype.prop = "prototype value";
var obj = new F(); 
console.log(obj.prop); // prototype value
```
#### 🔥 프로토타입 객체의 프로퍼티는 읽기만 가능하고 수정이 불가능!!!
```javascript
// 인스터스의 프로퍼티에 값을 대입했을 때 이름이 같은 프로퍼티가 있으면 그 프로퍼티에 값을 대입.
obj.prop = "instance value"; //  그렇지 않은 경우 인스턴스에 그 이름으로 프로퍼티를 추가한 후에 값을 대입
console.log(obj.prop); // instance value
console.log(F.prototype.prop); // prototype value
```

### ✓ 이렇게 프로토타입 객체의 프로퍼티를 인스터스에서 참조할 수 있는 상황을 가리켜 '인스턴스가 프로토타입 객체를 상속하고 있다' 라고 한다.

#### 📌 앞에서 얘기한 생성자 안에서 메서드를 정의하는 방식의 문제점을 해결하는 법 (메모리 낭비 피하는 법)
```javascript
// Circle 생성자
function Circle(center,radius) {
    this.center = center;
    this.radius = radius;
}
// Circle 생성자의의 prototype 프로퍼티에 area 메서드를 추가
Circle.prototype.area = function() {
  return Math.PI*this.radius*this.radius;  // 메서드 안의 this는 생성자로 생성한 인스턴스를 가리킨다.
};
// Circle 생성자로 인스턴스를 생성
var c1 = new Circle({x:0, y:0}, 2.0);
var c2 = new Circle({x:0, y:1}, 3.0);
var c3 = new Circle({x:1, y:0}, 1.0);
console.log("넓이 = " + c1.area()); // 넓이 = 12.566370614359172
```

- 위의 코드에서 인스턴스 c1,c2,c3 안에는 area 메서드가 존재하지 않지만 프로토타입에 정의했기 때문에 area 메서드를 사용할 수 있다.
- 이처럼 생성자의 프로토타입 객체에 메서드를 추가하면 인스턴스에 메서드를 추가하지 않아도 인스턴스가 프로토타입 객체의 메서드를 상속 받아 사용 할 수 있어 메모리 낭비를 피할 수 있다.
<p align="center"><img width="70%" src="https://user-images.githubusercontent.com/76654131/142762495-2233e2be-ffc5-472e-9e80-bf7b9bbb7d99.png">
</p>

---

# 프로토타입 상속

## 상속
- 자바스크립트의 상속은 프로토타입 체인이라고 부른는 객체의 자료구조로 구현되어 있으며, '프로토타입 상속'이라고 부른다. 
- 상속을 하는 이유 : 상속을 사용하면 이미 정의된 프로퍼티와 메서드의 코드를 재사용할 수 있고 새로운 기능을 추가해서 확장된 객체를 만들 수 있다. 중복 코드를 작성하지 않아도 되므로 유지 보수성이 높은 프로그램을 만들 수 있다. 

## 프로토타입 체인
### 내부 프로퍼티 [[Prototype]]
- 모든 객체는 내부 프로퍼티 [[Prototype]]을 가지고 있다. ❗️이것은 함수 객체의 prototype 프로퍼티와는 다른 객체다❗️
- ES5까지는 사용자가 내부 프로퍼티 [[Prototype]]을 읽거나 쓸 수 없었지만, ES6부터는 __proto__ 프로퍼티에 [Prototype]]의 값이 저장된다.

그러므로 이 포스팅에서는 [[Prototype]] 대신에 __proto__로 표기하겠다.

### 프로토타입 체인
객체의 __proto__ 프로퍼티는 그 객체에게 상속을 해준, 즉 유전자를 물려준 부모 객체를 가리킨다.   
따라서 객체는 __proto__ 프로퍼티가 가리키는 부모 객체의 프로퍼티를 물려 받아서 사용할 수 있다. 

자바스크립트는 특정 객체의 프로퍼티나 메소드에 접근하려고 할 때 해당 객체에 접근하려는 프로퍼티 또는 메소드가 없다면 [[Prototype]]이 가리키는 링크를 따라 자신의 부모 역할을 하는 프로토타입 객체의 프로퍼티나 메소드를 차례대로 검색한다. 이것을 '프로토타입 체인'이라 한다.

```javascript
var objA = {
    name: "Tom",
    sayHello: function() { console.log("Hello! " + this.name); }
};
var objB = {
    name : "Huck"
};
objB.__proto__ = objA;
var objC = {};
objC.__proto__ = objB;
objC.sayHello(); // "Hello! Huck"
```
위의 코드에 등장한 객체 세 개는 __proto__ 프로퍼티를 사용한 연결고리로 묶여 있음을 알 수 있다.
<p align="center"><img width="80%" src="https://user-images.githubusercontent.com/76654131/142810215-b0a5b029-b7f7-43b8-8cec-d0a71a9ab3de.png"></p>

---

#### 지금까지 프로토타입 상속에 관해 설명했지만 실제로 프로그래밍을 할 때는 __proto__ 프로퍼티 값을 직접 입력해서 상속하지 않는다!   
일반적으로 다음과 같은 방법으로 상속한다.
- 생성자로 객체를 생성할 때 생성자의 prototype 프로퍼티에 추가하는 방법
- Object.create 메서드로 상속을 받을 프로토타입을 지정하여 객체를 생성하는 방법

### 프로토타입 가져오기 
- 객체의 프로토타입은 Object.getPrototypeOf 메서드로 가져올 수 있다. 
(물론 지원하는 웹브라우저에서는 obj.__proto__로도 프로토타입을 가져올 수 있다.)
```javascript
function F() {}
var obj = new F();
console.log(Object.getPrototypeOf(obj)); // Object {}
```

## new 연산자와 생성자 함수
- 유사한 객체 여러 개를 쉽게 만들 때 new 연산자와 생성자 함수를 사용한다.

### 생성자 함수
- 생성자 함수(constructor function)와 일반 함수에 기술적인 차이는 없습니다. 다만 생성자 함수는 아래 두 '관례'를 따른다.
1. 함수 이름의 첫 글자는 대문자로 시작
2. 반드시 'new' 연산자를 붙여 실행

잠깐! 모든 함수는 생성자 함수가 될 수 있다는 점을 잊지 말자. new를 붙여 실행한다면 어떤 함수라도 위와 같이 알고리즘이 작동된다.
이름의 '첫글자가 대문자인' 생성자 함수는 new를 붙여 실행한다는 것은 공동의 약속, 관례일 뿐이다.

```javascript
function User(name) {
  this.name = name;    // this는 바로 생성자 함수 자신을 가리킨다. 이렇게 this에 저장된 것들은 new를 통해 객체를 만들 때 그 객체에 적용된다.
  this.isAdmin = false;
}

let user = new User("보라");

alert(user.name); // 보라
alert(user.isAdmin); // false
```

❓ 생성자를 new 연산자로 호출해서 인스턴스를 생성하면 내부적으로 어떤 작업을 할까?

위의 코드 new User(...)를 써서 함수를 실행하면 아래와 같이 알고리즘이 작동한다.

1. 빈 객체를 만들어 this에 할당한다.
2. 생성자의 prototype 프로퍼티 값을 생성된 객체의 __proto__ 프로퍼티 값으로 대입. (이 때, 생성자의 prototype 프로퍼티 값이 객체가 아니면 Obejct.prototype을 프로토타입으로 설정)
4. 함수 본문을 실행한다. this에 새로운 프로퍼티를 추가해 this를 수정한다.(객체의 초기화)
5. this를 반환한다.

```javascript
function User(name) {
  // this = {};  (빈 객체가 암시적으로 만들어지고)
  
  // this.__proto__ = User.prototype (생성자의 prototype 프로퍼티를 생성된 객체의 프로토타입으로 설정)
  
  // 새로운 프로퍼티를 this에 추가함 (객체의 초기화)
  this.name = name;
  this.isAdmin = false;

  // return this;  (this가 암시적으로 반환됨)
}
```

#### 📌 2번에서 생성자의 prototype 프로퍼티 값을 생성된 객체의 __proto__ 프로퍼티 값으로 대입하는 부분을 주목하자!   
#### 이를 이용해 인스턴스의 프로토타입 체인이 정의되며, 생성자로 생성한 모든 인스턴스가 생성자의 프로토타입 객체의 프로퍼티를 사용할 수 있게 되는 것이다.







