---
layout: post
title: Interface and Abstract
categories: Interview
---

## Interface != class ?

#### define : interface , implement : implements(포함, 구현)

실제 코드는 만들지 않더라도 어떤 메소드들이 있어야 하는지를 정의하려고 할 때 인터페이스를 사용하면 된다.

인터페이스를 구현할 경우 반드시 인터페이스에 정의된 메소드들의 몸통을 만들어 주어야만 한다.
즉, 구현하는 모든 클래스에 대해 특정한 메서드가 반드시 존재하도록 강제한다.

즉, 메소드들을 구현해야만 한다.

## Abstract class == class !

#### define : abstract , implement : extends(상속)

일부 완성되어 있는 Abstract 클래스로 즉, 미완성된 클래스이다.

Abstract 클래스는 자바에서 마음대로 초기화하고 실행할 수 없다.

Abstract 클래스를 구현해 놓은 클래스로 초기화 및 실행이 가능하다 ?

Abstract 클래스는 혼자로는 클래스의 역할을 다 못하지만, 새로운 클래스를 작성하는 데 있어 그 바탕이 되는 부모 클래스로서 중요한 의미를 갖는다.

추상 클래스는 여러 기존의 클래스에서 공통된 부분을 추상화 한 것이다.
즉, 상속을 받아서 기능을 확장시키는 데 목적이 있다

#### 추상 클래스의 목적

- 기존의 클래스에서 공통된 부분을 추상화하여 상속하는 클래스에게 구현을 강제화
- 메서드의 동작을 구현하는 자식 클래스로 책임을 위임
- 공유의 목적


---
다형성(polymorphism) 의 종류로 오버로딩과 오버라이딩이 있습니다.

인터페이스 : 오버로딩(Overloading) - 기존에 없는 새로운 메서드를 정의하는 것(new)

추상 클래스 : 오버라이딩(Overriding) - 상속받은 메서드의 내용을 변경하는 것(change, modify)


## 추상 클래스 (Abstract 클래스) = 상속의 개념

클래스는 크게 일반 클래스와 추상 클래스로 나뉜다.

자바는 다중 상속을 지원하지 않는다. 오직 '단일 상속'만을 지원한다

왜 ? 다중 상속의 모호성 때문에 하나만 상속이 가능하게 했다.

추상 클래스는 모든 메서드를 구현할 필요 없이 Abstract로 선언된 것들만 구현하면 된다.
그리하여 상속과 확장을 할 때 사용된다.

작업의 레벨 분할을 위해서 사용한다.

상속은 주로 새로 개발할 클래스를 쉽게 만들 수 있도록 해준다.
결국 이미 구축된 부모 클래스들이 자식들을 돕게 된다.

## Interface = 다형성의 개념

인터페이스는 모든 메소드가 추상 메소드인 경우 선언하는 경우가 많다.

인터페이스를 쓰는 가장 큰 이유는 다중상속을 지원하지 않는 자바에서 다중상속의 장점을 가져오기 위함이다.
다중상속이 가져오는 단점인 다중상속의 모호함을 배제하고 오직 장점(다형성)만을 취하기 위해서 인터페이스를 사용한다.

인터페이스는 메서드의 구현을 강제한다 (overriding)
구현 객체의 같은 동작을 보장할 수 있다.

여러 개의 인터페이스 구현이 가능하다.

인터페이스가 클래스가 아닌 이유는 객체를 생성할 수 없기 때문이다.
인터페이스는 인스턴스를 만들 수 없지만 인터페이스를 구현한 클래스를 통하면 인스턴스화가 가능하다.

공동 작업을 위한 상호 간의 인터페이스를 위해 사용한다.

구현은 인터페이스가 제시하는 요건을 충족시켜야 한다. 즉 부모가 제시하는 엄격한 규칙에 맞도록 무엇인가를 만들어줘야 하는 것으로 자식보다는 부모가 할 일이 편해진다. 즉 자식들의 다양성 때문에 부모들도 그때 그때 새롭게 개발을 하거나 할 필요가 없어지기 때문에 보다 추상화되고 규격화될 수 있다.

1. 설계자는 Interface 만 생성한다.
2. 개발자는 Interface 를 구현한다


Abstract class는 말씀하신대로 공통 구현을 상위 클래스에 뽑아내려고 사용하는거고(이것도 상속보다는 Composition이 선호되지요), 인터페이스는 어떤 행위를 기술하기 위해서 사용하지요.

자바에서는 기존에 만들어진 객체를 활용하는 멋진 방법이 있는데 대표적인 것이 콤포지션이라는 방법이고, 그 다음으로 많이 쓰이는 것이 상속이라는 것입니다.

---

## 상속

하위 클래스는 상위 클래스를 확장한다.

B라는 클래스가 A라는 클래스를 확장하면 B클래스는 A클래스 입니다.
상속 구조를 잘 만들었는지 알 수 있는 방법은 "상속에서의 'A 는 B 다' 관계는 한 방향으로만 작동한다는 것."

1. 어떤 클래스가 다른 클래스(상위 클래스, 추상 클래스)를 더 구체화한 형식이라면 상속을 활용한다.
2. 여러 클래스에서 공유해야 하는 어떤 행동이 있다면 상속을 활용한다. --> 클래스의 관리와 확장이 용이해진다.

상속의 잘못된 사용의 예
1. 어떤 코드를 다른 클래스에서 재사용할 수 있다는 이유만으로 상속을 사용하면 안된다.
2. 하위 클래스와 상위 클래스 사이에서 'A는 B다'관계가 성립하지 않으면 상속을 사용하면 안된다.

상속의 장점
1. 코드가 중복되는 것을 방지할 수 있습니다.
2. 코드를 한 군데만 고치면 그 행동을 상속받은 모든 클래스에서 새로운 변동사항이 자동으로 반영됩니다.
3. 하위 클래스는 전혀 건드릴 필요가 없습니다.
4. 일련의 클래스를 위한 공통적인 규약(프로토콜)을 정의합니다.
- 상속을 사용하면 특정 상위 클래스 밑에 모여있는 모든 클래스에, 상위클래스에 들어있는 모든 메소드가 들어가게 할 수 있습니다.
- 즉, "내 형식에 속하는 모든 하위클래스에서는 다음과 같은 메소드를 써서 이런일을 할 수 있습니다."라고 알려주는 일종의 규약입니다.

다형성의 예제
``` java
Dog myDog = new Dog();
1. Dog myDog ; 레퍼런스 변수 선언
2. new Dog(); 객체를 만듭니다.
3. = ; 객체와 레퍼런스를 연결합니다.
중요한 것은 레퍼런스 유형과 객체 유형이 똑같아야 합니다.

하지만 다형성을 활용하면 레퍼런스와 객체가 다른 유형이어도 됩니다.
Animal myDog = new Dog();
```

다형성을 사용하면 레퍼런스 유형을 실제 객체 유형의 상위클래스 유형으로 지정할 수 있습니다.

다형적인 인자를 사용하는 코드를 만들면, 즉 메소드 매개변수를 상위 클래스 유형으로 선언하면 실행할 대 어떤 하위 클래스의 객체도 전달할 수 있습니다.

다형성을 활용하면 새로운 하위클래스 형식을 프로그램에 추가하더라도 코드를 굳이 바꿀 필요가 없습니다.

오버라이딩 : 오버라이드하는 메소드의 인자와 리턴 형식은 외부에서 보기에 상위 클래스에 있는 오버라이드를 당하는 메소드와 완벽하게 일치해야 한다.

오버로딩 : 이름이 같고 인자 목록이 다른 메소드 두 개를 만드는 것입니다.
이 때, 오버로딩할 때는 인자 목록을 반드시 변경해야 합니다.

## 다형성

다형성이란 하나의 메소드나 클래스가 있을 때 이것들이 다양한 방법으로 동작하는 것을 의미한다.

다형성을 제대로 사용하려면 인터페이스가 필요하다.

코드의 융통성과 확장성은 간단한 상속을 뛰어넘어 인터페이스 규격을 설계하고 코딩하는 것을 통해서만 얻을 수 있다.

클래스 중에는 인스턴스를 만들면 안 되는 것도 있습니다.

어떤 클래스의 인스턴스를 만들 수 없게 하는 간단한 방법
즉 특정 유형에 대해 "new" 키워드를 쓸 수 없게 하는 방법
그것은 바로 클래스를 "abstract"로 지정하면 된다.

컴파일러에서는 추상 클래스의 인스턴스를 만드는 것을 허용하지 않는다.
즉, 추상 클래스는 클래스의 새로운 인스턴스를 만들 수 없는 클래스를 의미한다.

추상 클래스는 확장하지 않으면 거의 쓸모도 없고, 가치도 없고, 삶의 목적도 없습니다.

추상 클래스를 만들었을 때 실제 실행 중에 일을 처리하는 것은 추상 클래스의 "하위 클래스 인스턴스" 입니다.

추상 클래스는 반드시 확장해야 하는 클래스를 의미합니다.
추상 메소드는 반드시 오버라이드해야 하는 메소드를 의미합니다.

추상 메소드에는 몸통이 없습니다.
추상 메소드를 만들 때는 클래스도 반드시 추상 클래스로 만들어야 합니다.
추상 클래스가 아닌 클래스에 추상 메소드를 집어넣을 수는 없습니다.

추상 메소드를 만드는 이유는 실제 메소드 코드를 전혀 집어넣지는 않았더라도 일련의 하위 클래스를 위한 규약(프로토콜)의 일부를 정의하기 위한 것이다.

추상 메소드의 장점은 다형성이다.
추상 메소드는 다형성을 활용하기 위해 "이 유형에 속하는 모든 하위클래스 유형에는 이 메소드가 있어야 한다."는 것을 지정하기 위해 필요한 것이다.

추상 메소드는 모두 구현해야만 한다.
추상 메소드를 구현하는 것은 메소드를 오버라이드하는 것과 같다.

추상 메소드는 몸통이 없다. 다형성을 위해 존재할 뿐이다.

## 다형성 in google

다형성은 같은 모양의 메서드가 혹은 같은 이름의 행위가 다른 행위를 하는 것을 나타냅니다.

예를 들어, "누른다."라는 이름의 행위는 비교적 이해하기 쉽습니다. 키보드의 키를 누른다, 휴대폰의 아이콘을 누른다, 자판기의 버튼을 누른다.
이렇게 많은 누른다가 존재하지만 각각의 누른 후의 결과는 다르다는 것을 알 수 있습니다. 키를 누르면 글자가 입력이 되고 휴대폰의 애플리케이션을 누르면 앱이 실행이 되고, 자판기의 음료 버튼을 누르면 음료가 나옵니다.

#### OOP가 다형성을 구현하는 방법

Overriding : 상위 클래스를 상속받은 하위 클래스에서 상위 클래스의 (추상) 메소드의 같은 이름, 같은 반환값, 같은 인자로 메소드 내의 로직들을 새롭게 정의하는 것을 말합니다.

Overloading : 하나의 클래스에서 같은 이름의 메소드들을 여러 개 가질 수 있게 합니다. 단, 메서드의 인자들은 달라야 합니다. 인자 목록이 다르다면 리턴 유형을 마음대로 바궈도 됩니다.

#### OOP가 다형성을 구현한 이유

1. 여러 타입의 객체를 하나의 타입으로 관리하니 유지보수가 좋다.
2. 메소드의 매개변수로 상위 클래스, 추상 클래스, 인터페이스 등이 온다면, 그 하위 클래스, 인터페이스를 구현한 클래스 등이 인자로 들어갈 수 있어 좀 더 유연한 프로그래밍을 할 수 있다. 이 부분도 프로그램의 유지보수 차원에서 좋다.
3. 확장성이 좋은 코드를 작성할 수 있고, 결합도가 강하지 않은 프로그래밍을 할 수 있다.

## Object 객체

자바에서 모든 클래스는 Object라는 클래스를 확장한 것이다.
우리도 모르게 처음부터 object 클래스의 하위클래스를 만들었던 것이다.
어떤 클래스를 만들더라도 그 클래스는 반드시 Object클래스를 확장한 클래스로 만들어진다.

## 인터페이스

상위 클래스를 두 개 사용하는 접근법에는 한 가지 문제점이 있습니다.
다중 상속이라고 부르는 접근법은 죽음의 다이아몬드라고 알려져 있는 문제가 있습니다.

죽음의 다이아몬드 문제(The Deadly Diamond of Death)

동물을 확장해서 개와 고양이 클래스를 만들었습니다.
그리고 새로운 동물인 개고양이과 동물인 상상의 동물 유니콘 클래스를 만들었습니다. 물론 상속은 2개를 받았습니다.
이 때 유니콘은 eat()을 호출할려고 합니다. 동물 클래스에 정의되어 있던 eat()이 있다면, 유니콘은 개의 eat()을 호출할지 고양이의 eat()을 호출할지 어떤 메소드가 실행이 될지 "애매한" 상황이 발생하게 된다.

인터페이스는 죽음의 다이아몬드 때문에 생기는 부작용없이 다중 상속의 다형적인 장점을 대부분 누릴 수 있게 해 줌으로써 다중 상속 문제를 해결해줍니다.

인터페이스를 사용하여 죽음의 다이아몬드를 비켜가는 간단한 방법은 바로
"모든 메소드를 추상 메소드로 만드는 것입니다."

#### 인터페이스 in google

인터페이스와 추상클래스의 차이
1. 추상클래스는 구현된 메소드를 포함할 수 있고 인터페이스는 그렇지 못하다
2. 추상클래스로 정의된 타입을 구현하는 클래스는 반드시 추상클래스의 하위 클래스가 되어야 한다.
이와 달리 인터페이스를 구현하는 클래스의 경우는, 인터페이스에 정의된 모든 메소드를 구현하고 인터페이스 구현 계약을 지키면 된다.
이건 클래스 상속과는 무관하다.

인터페이스의 장점
1. 개발 시간을 단축시킬 수 있다.
양쪽에서 동시에 개발을 진행할 수 있다.

2. 표준화가 가능하다.
프로젝트의 기본 틀을 인터페이스로 작성한다.
그 후 개발자들에게 인터페이스를 구현하여 프로그램을 작성하도록 함으로써 보다 일관되고 정형화된 프로그램의 개발이 가능하다.

3. 서로 관계없는 클래스들에게 관계를 맺어 줄 수 있다.
4. 독립적인 프로그래밍이 가능하다.
클래스의 선언과 구현을 분리시킬 수 있기 때문에 실제 구현에 독립적인 프로그램을 작성하는 것이 가능하다.

## 결론

### 클래스
- 클래스를 새로 만들려고 할 때 그 클래스가 다른 어떤 유형에 대해서도 'A느 B다' 테스트를 통과할 수 없다면 그냥 클래스를 만듭니다.

### 상속을 통한 하위 클래스
- 어떤 클래스의 더 구체적인 버전을 만들고 어떤 메소드를 오버라이드하거나 새로운 행동을 추가해야 한다면 하위클래스를 만듭니다.

### 추상 클래스
- 일련의 하위 클래스에서 사용할 템플릿(template)을 정의하고 싶다면, 그리고 모든 하위클래스에서 사용할 구현 코드가 조금이라도 있다면 추상 클래스를 사용합니다.
- 그 유형의 객체를 절대 만들 수 없게 하고 싶다면 추상클래스로 만듭니다.

### 인터페이스
- 상속 트리에서의 위치에 상관없이 어떤 클래스의 역할을 정의하고 싶다면 인터페이스를 사용하면 됩니다.

### 확장은 한 개밖에 할 수 없지만 구현은 여러 개를 할 수 있습니다.
부모는 하나밖에 없습니다. 부모는 자식이 어떠해야 하는지를 정의하게 됩니다. 상태든, 행동이든...

인터페이스는 그 클래스가 어떤 역할을 할 수 있는지를 정의합니다.
