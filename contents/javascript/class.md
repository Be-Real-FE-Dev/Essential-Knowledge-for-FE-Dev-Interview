# class

Class는 객체를 생성하기 위한 템플릿입니다. 클래스는 데이터와 이를 조작하는 코드를 하나로 추상화합니다. 자바스크립트에서 클래스는 프로토타입을 이용해서 만들어졌지만 ES5의 클래스 의미와는 다른 문법과 의미를 가집니다.

<br>

## constructor

class에서 인스턴스를 생성하고 초기화하기 위한 특수한 메서드이다.
constructor는 메서드로 해석되는 것이 아니라 클래스가 평가되어 생성한 함수 객체 코드의 일부이다.
그러므로 클래스가 평가되어 생성된 함수 객체나 클래스가 생성한 인스턴스 어디에도 constructor는 메서드가 보이지 않는다.

- constructor는 클래스 내에 최대 한 개만 존재할 수 있다.
- 프로퍼티가 추가되어 초기화된 인스턴스를 생성하려면 constructor 내부에서 this에 인스턴스
- 프로퍼티를추가한다.클래스 외부에서 인스턴스 프로퍼티의 초기값을 전달하려면 constructor에 매개변수를 선언해서 초기값을 전달한다.
- 인스턴스를 초기화하려면 contructor는 생략하면 안된다.

<br>

## 프로토타입 메서드

클래스 내부에 메서드를 선언하며 자동으로 프로토타입 메서드가 된다.

<br>

## 정적 메서드

static 키워드와 함께 정의되며 클래스의 인스턴스 없이 호출이 가능하며 클래스가 인스턴스화되면 호출할 수 없다.

<br>

## super

- super 키워드는 부모 클래스를 참조(Reference)할 때 또는 부모 클래스의 constructor를 호출할 때 사용한다.

- class 문법을 new연산자와 함께 호출 시 extends 키워드 여부로 [[constructorKind]] 내부슬롯에 Base, Derived 값을 설정하여 수퍼클래스인지 서브클래스인지를 판단한다.
  서브클래스에서 super 메서드를 만나는 순간 [[HomeObject]]가 참조하고 있는 수퍼클래스의 contructor가 실행되어 인스턴스 초기화를 한다.
  이후 super 메서드가 종료되고 제어흐름이 서브클래스로 돌아온다.

```js
// 부모 클래스
class Circle {
...
}

class Cylinder extends Circle {
  constructor(radius, height) {
    // ① super 메소드는 부모 클래스의 constructor를 호출하면서 인수를 전달한다.
    super(radius);
    this.height = height;
  }

  // 원통의 넓이: 부모 클래스의 getArea 메소드를 오버라이딩하였다.
  getArea() {
    // (원통의 높이 * 원의 둘레) + (2 * 원의 넓이)
    // ② super 키워드는 부모 클래스(Base Class)에 대한 참조
    return (this.height * super.getPerimeter()) + (2 * super.getArea());
  }

  // 원통의 부피
  getVolume() {
    // ② super 키워드는 부모 클래스(Base Class)에 대한 참조
    return super.getArea() * this.height;
  }
}

// 반지름이 2, 높이가 10인 원통
const cylinder = new Cylinder(2, 10);
```

> https://poiemaweb.com/es6-class
