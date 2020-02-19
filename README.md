# 오브젝트 - 코드로 이해하는 객체지향 설계

## 01 객체, 설계 
 
 - 객체 사이의 의존성이 과한 경우를 가리켜 결합도(coupling)가 높다고 말한다. 반대로 객체들이 합리적인 수준으로 의존할 경우에는 결합도가 낮다고 말한다. 두 객체 사이의 결합도가 높으면 높을수록 함계 변경될 확률도 높아지기 때문에 변경하기 어려워진다. 따라서 **설계의 목표는 객체 사이의 결합도를 낮춰 변경이 용이한 설계를 만드는 것이다.**
 - 개념적이나 물리적으로 객체 내부의 세부적인 사항을 감추는 것을 캡슐화(encapsulation)라고 부른다. 캡슐화의 목적은 변경하기 쉬운 객체를 만드는 것이고, 캡슐화를 통해 객체 내부로의 접근을 제한하면 객체와 객체 사이의 결합도를 낮출 수 있기 때문에 설계를 좀 더 쉽게 변경할 수 있게 된다. 
- **객체 내부의 상태를 캡슐화하고 객체 간에 오직 메시지를 통해서만 상호작용하도록 만들어야 한다.**
- 밀접하게 연관된 작업만을 수행하고 연관성 없는 작업은 다른 객체에게 위임하는 객체를 가리켜 응집도(cohesion)가 높다고 말한다. 자신의 데이터를 스스로 처리하는 자율적인 객체를 만들면 결합도를 낮출 수 있을뿐더러 응집도를 높일 수 있다. 
- 데이터와 프로세스가 동일한 모듈 내부에 위치하도록 프로그래밍하는 방식을 객체지향 프로그래밍(object-Oriented Programming)이라고 부른다.   
- **설계란 코드를 배치하는 것이다.**

## 02 객체지향 프로그래밍

- 진정한 객체지향 패러다임으로의 전환은 클래스가 아닌 객체에 초점을 맞출 때에만 얻을 수 있다.
	- 어떤 클래스가 필요한지를 고민하기 전에 어떤 객체들이 필요한지 고민하라. 
	- 객체를 독립적인 존재가 아니라 기능을 구현하기 위해 협력하는 공동체의 일원으로 봐야 한다.
- 의미를 좀 더 명시적이고 분명하게 표현할 수 있다면 객체를 사용해서 해당 개념을 구현하면 도메인의 의미를 풍부하게 표현 할 수 있다. (Money 클래스)  
- 부모 클래스에 기본적인 알고리즘의 흐름을 구현하고 중간에 필요한 처리를 자식 클래스에게 위임하는 디자인 패턴을 **TEMPLATE METHOD 패턴**이라고 부른다.
- 생성자의 파라미터 목록을 이용해 초기화에 필요한 정보를 전달하도록 강제하면 올바른 상태를 가진 객체의 생성을 보장할 수 있다.
- 상속을 구현 상속(implementation inheritance)과 인터페이스 상속(interface inheritance)으로 분류할 수 있다. 
	- 순수하게 코드를 재사용하기 위한 목적으로 사용하는 것을 구현 상속이라고 부른다.
	- 다형적인 협력을 위해 부모 클래스와 자식 클래스가 인터페이스를 공유할 수 있도록 상속을 이용하는 것을 인터페이스 상속이라고 부른다. 
	- 상속은 구현 상속이 아니라 인터페이스 상속을 위해 사용해야 한다. 
	- 구현을 재사용할 목적으로 상속을 사용하면 변경에 취약한 코드를 낳게 될 확률이 높다. 
- 상속은 코드를 재사용할 수 있는 가장 널리 알려진 방법이지만 캡슐화의 측면에서 합성이 더 좋은 방법이다. 
- 유연한 객체지향 프로그램을 위해서는 컴파일 시간 의존성과 실행 시간 의존성이 달라야 한다. 하지만 그럴수록 코드만으로 이해 할 수 있는 복잡도는 높아진다.  

## 03 역할, 책임, 협력

- 객체지향 패러다임의 관점에서 핵심은 역할(role), 책임(responsibility), 협력(collaboration)이다. 
- 객체들이 애플리케이션의 기능을 구현하기 위해 수행하는 상호작용을 **협력**이라고 한다. 객체가 협력에 참여하기 위해 수행하는 로직은 **책임**이라고 부른다. 객체들이 협력 안에서 수행하는 책임들이 모여 객체가 수행하는 **역할**을 구성한다. 
- 객체의 책임은 하는 것(doing)과 아는것(knowing)의 두 가지 범주로 나누어 볼 수 있다. 
- 객체에게 책임을 할당하는 데 필요한 메시지를 먼저 식별하고 메시지를 처리할 객체를 나중에 선택한다.
- 역할은 다른 것으로 교체할 수 있는 책임의 집합으로 일종의 슬롯으로 생각할 수 있다.
- 동일한 책임을 수행하는 역할을 기반으로 두 개의 협력을 하나로 통합 할 수 있고, 역할을 이용하면 불필요한 중복 코드를 제거할 수 있다. 
- 협력에 적합한 책임을 수행하는 대상이 한 종류라면 간단하게 객체로 간주한다. 만약 여러 종류의 객체들이 참여할 수 있다면 역할이라고 부르면 된다. 
- 동일한 역할을 수행하는 하나 이상의 객체들이 존재 할 수 있다. 이것은 협력 관점에서 동일한 역할을 수행하는 객체들은 서로 대체 가능하다는 것을 의미한다. 
- 객체는 다양한 역할을 가질 수 있다. 객체는 협력에 참여할 때 협력 안에서 하나의 역할로 보여진다. 객체가 다른 협력에 참여할 때는 다른 역할로 보여진다. 

## 04 설계 품질과 트레이드 오프 

- 훌륭한 객체 지향 설계는 데이터가 아니라 책임에 초점을 맞춰야 한다. 
- 데이터 중심의 설계란 객체 내부에 저장되는 데이터를 기반으로 시스템을 분할하는 방법이다. 
- 변경될 가능성이 높은 부분을 **구현**이라고 부르고 상대적으로 안정적인 부분을 **인터페이스**라고 부른다. 
- **캡슐화**는 외부에서 알 필요가 없는 부분을 감춤으로써 대상을 단순화하는 추상화의 한 종류다.
- 일반적으로 좋은 설계란 높은 응집도와 낮은 결합도를 가진 모듈로 구성된 설계를 의미한다. 
- 단일 책임 원칙(Single Responsibility Principle, SRP) : 클래스는 단 한 가지의 변경 이유만 가져야 한다. 
- 객체는 스스로의 상태를 책임져야 하며 외부에서는 인터페이스에 정의된 메서드를 통해서만 상태에 접근할 수 있어야 한다. 
- 객체를 설계할 때는 이 객체가 어떤 데이터를 포함해야 하는지와 데이터에 대해 수행해야 하는 오퍼레이션은 무엇인지 생각해야 한다. 
- 데이터 중심의 설계는 본질적으로 너무 이른 시기에 데이터에 관해 결정하도록 강요한다. 
- 데이터 중심의 설계에서는 협력이라는 문맥을 고려하지 않고 객체를 고립시킨 채 오퍼레이션을 결정한다. 
- 데이터 중심의 설계에서의 초점은 객체의 외부가 아니라 내부로 향하기 때문에 내부에 너무 많은 것을 녹여내면서 외부로 노출하게 되고 이는 추후에 객체 외에 것들에도 많은 변경을 야기하게 된다.  
- 데이터 중심의 설계는 행동보다 데이터를 먼저 결정하고 협력이라는 문맥을 벗아나 고립된 객체의 상태에 초점을 맞추기 때문에 캠슐화를 위반하기 쉽고, 요소들 사이의 결합도가 높아지며, 코드를 변경하기 어려워진다. 

## 05 책임 할당하기

- 데이터보다 행동을 먼저 결정하라. 
- 협력이라는 문맥 안에서 책임을 결정하라. 
- 객체를 결정하기 전에 객체가 수신할 메시지를 먼저 결정한다. 
- 메시지는 메시지를 수신할 객체가 아니라 메시지를 전송할 객체의 의도를 반영해서 결정해야 한다. 
- 책임을 수행하는데 필요한 정보를 가지고 있는 객체에게 할당하라.
- 설계의 전체적인 결합도가 낮게 유지되도록 책임을 할당하라. 
- 낮은 응집도가 초래하는 문제를 해결하기 위해서는 변경의 이유에 따라 클래스를 분리해야 한다. 
- 설계를 개선하는 작업은 변경의 이유가 하나 이상인 클래스를 찾는 것으로부터 시작하는 것이 좋다. 
- 자신이 소유하고 있는 데이터를 자기 스스로 처리하도록 만드는 것이 자율적인 객체를 만드는 지름길이다. 

## 06 메시지와 인스턴스 

- 훌륭한 객체지향 코드를 얻기 위해서는 클래스가 아니라 객체를 지향해야 한다. 다시 말해 렵력 안에서 객체가 수행하는 책임에 초점을 맞춰야 한다. 
- 한 객체가 다른 객체에게 도움을 요청하는 것을 **메시지 전송(message sending)**또는 **메시지 패싱(message passing)**이라고 부른다.
- 메시지를 수신했을 때 실제로 실행되는 함수 또는 프로시저를 **메서드**라고 부른다.
- 객체가 의사소통을 위해 외부에 공개하는 메시지의 집합을 **퍼블릭 인터페이스**라고 부른다. 
- 퍼블릭 인터페이스에 포함된 메시지를 **오퍼레이션(operation)**이라고 부른다. 오퍼레이션은 수행 가능한 어떤 행동에 대한 추상화다.
- 오퍼레이션(또는 메서드)의 이름과 파라미터 목록을 합쳐 **시그니처(signature)**라고 부른다.
- 디미터 법칙(Law of Demeter)이란 객체의 내부 구조에 강하게 결합되지 않도록 협력 경로를 제한하는 것이다.
- 디미터 법칙을 따르도록 코드를 개선하면 메시지 전송자는 더 이상 메시지 수신자의 내부 구조에 대해 묻지 않고, 자신이 원하는 것이 무엇인지를 명시하고 단순히 수행하도록 요청한다.
- 절차적인 코드는 정보를 얻은 후에 결정한다. 객체지향 코드는 객체에게 그것을 하도록 시킨다. 
- 어떻게 하느냐가 아니라 무엇을 하느냐에 따라 메서드의 이름을 짓는 패턴을 **의도를 드러내는 선택자(Intention Revealing Selector)**라고 부른다. 
- 어떤 절차를 묶어 호출 가능하도록 이름을 부여한 기능 모듈을 **루틴(routine)**이라고 한다.
- 프로시저는 정해진 절차에 따라 내부의 상태를 변경하는 루틴의 한 종류다.
- 함수는 어떤 절차에 따라 필요한 값을 계산해서 반환하는 루틴의 한 종류다.

## 07 객체 분해 

- 불필요한 정보를 제거하고 현재의 문제 해결에 필요한 핵심만 남기는 작업을 **추상화**라고 부른다.
- **프로시저 추상화**는 소프트웨어가 무엇을 해야 하는지를 추상화한다.
- **데이터 추상화**는 소프트웨어가 무엇을 알아야 하는지를 추상화한다. 
- 하향식 기능 분해의 문제점
	- 시스템은 하나의 메인 함수로 구성돼 있지 않다.
	- 기능 추가나 요구사항 변경으로 인해 메인 함수를 빈번하게 수정해야 한다.
	- 비즈니스 로직이 사용자 인터페이스와 강하게 결합된다.
	- 유연성과 재사용성이 저하된다.
	- 데이터의 형식이 변경될 경우 파급효과를 예측할 수 없다.
- 현대적인 시스템은 동등한 수준의 다양한 기능으로 구성된다.
- 데이터와 함께 변경되는 부분을 하나의 구현 단위로 묶고 외부에서는 제공되는 함수만 이용해 데이터에 접근해야 한다. 즉, 잘 정의된 퍼블릭 인터페이스를 통해 데이터에 대한 접근을 통제해야 한다.
- 하향식 분해는 작은 프로그램과 개별 알고리즘을 위해서 유용하게 사용 할 수 있지만 실제로 동작하는 커다란 소프트웨어를 설계하는 데 적합한 방법은 아니다. 
- 정보 은닉은 외부에 감춰야 하는 비밀에 따라 시스템울 분할하는 모듈 분할 원리다.
- 모듈은 다음과 같은 두 가지 비밀을 감춰야 한다. 
	- 복잡성 : 외부에 모듈을 추상화할 수 있는 간단한 인터페이스를 제공해서 모듈의 복잡도를 낮춘다.
	- 변경 가능성 : 변경 발생시 하나의 모듈만 수정하면 되도록 변경 가능한 설계 결정을 모듈 내부로 감추고 외부에는 쉽게 변경되지 않을 인터페이스를 제공한다.
- 객체 지향은 **절차 추상화(procedural abstraction)**다.

## 08 의존성 관리하기

- 런타임 의존성이 다루는 주제는 객체 사이의 의존성이다.
- 컴파일타임 의존성이 다루는 주제는 클래스 사이의 의존성이다.
- 어떤 클래스의 인스턴스가 다양한 클래스의 인스턴스와 협력하기 위해서는 협력할 인스턴스의 구체적인 클래스를 알아서는 안 된다. 실제로 협력할 객체가 어떤 것인지는 런타임에 해결해야 한다.
- 바람직한 의존성이란 설계를 재사용하기 쉽게 만드는 의존성이다.
- 의존성은 명시적으로 표현돼야 한다. 
- 어떤 객체와 협력하느냐에 따라 객체의 행동이 달라지는 것은 유연하고 재사용 가능한 설계가 가진 특징이다.

## 09 유연한 설계 

- **소프트웨어 개체(클래스, 모듈, 함수 등등)는 확장에 대해 열려 있어야 하고, 수정에 대해서는 닫혀 있어야 한다.**
- 개방-폐쇄 원칙의 핵심은 **추상화에 의존하는 것**이다. 추상화란 핵심적인 부분만 남기고 불필요한 부분은 생략함으로써 복잡성을 극복하는 기업이다.
- 동일한 클래스 안에서 객체 생성과 사용이라는 두 가지 이질적인 목적을 가진 코드가 공존하지 않도록 한다.
- 시스템을 객체로 분해하는 데는 크게 두 가지 방식이 존재한다.
	- **표현적 분해(representational decomposition)** : 도메인에 존재하는 사물 또는 개념을 표현하는 객체들을 이용해 시스템을 분해한다.
	- **행위적 분해(behavioral decomposition)** 
- 사용하는 객체가 아닌 외부의 독립적인 객체가 인스턴스를 생성한 후 이를 전달해서 의존성을 해결하는 방법을 **의존성 주입(Dependency Injection)**이라고 부른다.
- 숨겨진 의존성(service locator)은 이해하기 어렵고 디버깅하기 어렵기 때문에 사용하지 않도록 한다.
- **의존성 역전 원칙(Dependency Inversion Principle)**
	- 상위 수준의 모듈은 하위 수준의 모듈에 의존해서는 안 된다. 둘 모두 추상화에 의존해야 한다. 
	- 추상화는 구체적인 사항에 의존해서는 안 된다. 구체적인 사항은 추상화에 의존해야 한다.
-  훌륭한 객체지향 설계를 위해서는 의존성을 역전시켜야 한다. 그리고 의존성을 역전시켜야만 유연하고 재사용 가능한 설계를 얻을 수 있다.
- **추상화 대상은 클라이언트가 속한 패키지에 구성하고 재사용될 필요가 없는 클래스들은 별도의 독립적인 패키지에 모아야 불필요한 재컴파일을 막을 수 있다.** 

## 10 상속과 코드 재사용 

- **DRY 원칙** : Don`t Repeat Yourself!. 동일한 지식을 중복하지 말라!
- 상속을 사용할때는 super 호출을 제거할 수 있는 방법을 찾아 결합도를 제거해야한다. 
- 상속받은 부모 클래스의 메서드가 자식  클래스의 내부 구조에 대한 규칙을 깨트릴 수 있다. 
- 자식 클래스가 부모 클래스의 메서드를 오버라이딩할 경우 부모 클래스가 자신의 메스드를 사용하는 방법에 자식 클래스가 결합될 수 있다.
- 클래스를 상속하면 결합도로 인해 자식 클래스와 부모 클래스의 구현을 영원히 변경하지 않거나, 자식 클래스와 부모 클래스를 동시에 변경하거나 둘 중 하나늘 선택할 수 밖에 없다.

## 11 합성과 유연한 설계 

- 합성을 이용하면 포함된 객체의 내부 구현이 변경되더라도 영향을 최소화할 수 있기 때문에 변경에 더 안정적인 코드를 얻을 수 있게 된다. 
- 상속 관계는 컴파일타임에 결정되고 고정되기 때문에 코드를 실행하는 도중에는 변경할 수 없다. 
- 합성을 사용하면 구현이 아닌 퍼블릭 인터페이스에 대해서만 의존할 수 있기 때문에 런타임에 객체의 관계를 변경할 수 있다.
- **믹스인(mixin)**은 객체를 생성할 때 코드 일부를 클래스 안에 섞어 넣어 재사용하는 기법을 가리킨다. 
- 코드 재사용을 목적으로 상속을 사용하면 변경하기 어렵고 유연하지 못한 설계에 이를 확률이 높아진다. 상속의 목적은 코드 재사용이 아니라 타입 계층을 구조화하기 위해 사용해야 한다.

## 12 다형성

- 다형성이란 여러 타입을 대상으로 동작할 수 있는 코드를 작성할 수 있는 방법이다. 
- 일반적으로 super는 자식 클래스 내부에서 부모 클래스의 인스턴스 변수나 메서드에 접근하는 데 사용된다. 정확하게 말하면 가시성이 public이나 projected인 인스턴스 변수와 메서드만 접근이 가능하다. 가시성이 private인 경우에는 접근이 불가능하다.
- **데이터 관점의 상속**이 자식 클래스의 인스턴스 안에 부모 클래스의 인스턴스를 포함하는 개념이라면 **행동 관점의 상속**은 부모 클래스가 정의한 일부 메서드를 자식 클래스의 메서드로 포함시키는것을 의미한다. 
- **업캐스팅** : 부모 클래스 타입으로 선언된 변수에 자식 클래스의 인스턴스를 할당하는 것. 
- 부모 클래스의 인스턴스를 자식 클래스 타입으로 변환하기 위해서는 명시적인 타입 캐스팅이 필요한데 이를 **다운캐스팅**이라고 부른다. 
- self 전송이 메시지를 수신하는 객체의 클래스에 따라 메서드를 탐색할 시작 위치를 동적으로 결정하는 데 비해 super 전송은 메시지를 전송하는 클래스의 부모 클래스에서부터 시작된다.

## 13 서브클래싱과 서브타이핑 

- 개념 관전에서 타입이란 공통의 특징을 공유하는 대상들의 분류다. 
- 프로그래밍 언어 관점에서 타입이란 동일한 오퍼레이션을 적용할 수 있는 인스턴스들의 집합이다. 
- 객체의 퍼블릭 인터페이스가 객체의 타입을 결정한다. 따라서 동일한 퍼블릭 인터페이스를 제공하는 객체들은 동일한 타입으로 분류된다. 
- **일반화**는 다른 타입을 완전히 포함하거나 내포하는 타입을 식별하는 행위 또는 그 행위의 결과를 가리킨다. **특수화**는 다른 타입 안에 전체적으로 포함되거나 완전히 내포되는 타입을 식별하는 행위 또는 그 행위의 결과를 가리킨다. 
- **슈퍼타입**이란 서브타입이 정의한 퍼블릭 인터페이스를 일반화시켜 상대적으로 범용적이고 넓은 의미로 정의한 것이다. 
- **서브타입**이란 슈퍼타입이 정의한 퍼블릭 인터페이스를 특수화시켜 상대적으로 구체적이고 좁은 의미로 정의한 것이다. 
- 서브타입의 인스턴스는 슈퍼타입의 인스턴스로 간주될 수 있다. 
- 상속을 사용해야 하는 경우 
	- 상곡 관계가 is-a 관계를 모델링하는 경우 : 일반적으로 [자식 클래스]는 [부모 클래스]다 라고 말해도 이상하지 않다면 상속을 사용할 후보로 간주할 수 있다.
	- 클라이언트 입장에서 부모 클래스의 타입으로 자식 클래스를 사용해도 무방한 경우 : 상속 계층을 사용하는 클라이언트의 입장에서 부모 클래스와 자식 클래스의 차이점을 몰라야 한다. 이를 자식 클래스와 부모 클래스 사이의 **행동 호환성**이라고 부른다. 
- 두 타입 사이에 행동이 호환될 경우에만 타입 계층으로 묶어야 하고 행동의 호환 여부를 판단하는 기준은 **클라이언트의 관점**이다. 클라이언트가 두 타입이 동일하게 행동할 것이라고 기대한다면 두 타입을 타입 계층으로 묶을 수 있다.
- 서브클래싱 : 다른 클래스의 코드를 재사용할 목적으로 상속을 사용하는 경우를 가리킨다. 구현상속 또는 클래스 상속이라고 부르기도 한다. 
- 서브타이핑 : 타입 계층을 구성하기 위해 상속을 사용하는 경우를 가리킨디ㅏ. 인터페이스 상속이라고 부르기도 한다. 
- 리스코프 치환 원칙 : 서비스타입은 그것의 기반 타입에 대해 대체 가능해야 하며, 클라이언트가 "차이점을 인식하지 못한 채 파생 클래스의 인터페이스를 통해 서브클래스를 사용할 수 있어야 한다." 
- **대체 가능성을 결정하는 것은 클라이언트다.**
- 서브타입에 더 강력한 사전조건을 정의할 수 없다.
- 서브타입에 슈퍼타입과 같거나 더 약한 사전조건을 정의할 수 있다.
- 서브타입에 슈퍼타입과 같거나 더 강한 사후조건을 정의할 수 있다.
- 서브타입에 더 약한 사후조건을 정의할 수 없다.


## 14 일관성 있는 협력

- 객체는 협력을 위해 존재한다. 협력은 객체가 존재하는 이유와 문맥을 제공한다. 잘 설계된 애플리케이션은 이해하기 쉽고, 수정이 용이하며, 재사용 가능한 협력의 모임이다. 객체지향 설계의 목표는 적잘한 책임을 수행하는 객체들의 협력을 기반으로 결합도가 낮고 재사용 가능한 코드 구조를 창조하는 것이다.