# '객체지향의 사실과 오해'를 읽고

> 객체지향프로그래밍이란 무엇인가요?

자바(Java)가 주력 언어인 나는 면접, 선배, 후임개발자, 동기... 다양한 자리에서 위와 같은 질문을 받은 적이 있다.

> 실제 세계는 객체로 이루어져 있으며 발생하는 모든 사건들은 사물간의 상호작용한다는 객체지향 이론을 프로그래밍에 적용한 것으로, 객체지향 프로그래밍을 함으로써 코드의 재사용성이 높아지고 중복이 줄어듭니다. 그럼으로써 오류가 줄어들고 유지보수가 용이해집니다. 대표적인 특징으로는 캡슐화, 상속, 추상화, 다형성 등이 있습니다.

그 때마다 이 정도의 형식적인 암기문을 '낭독' 했을 뿐이고, 좀 더 말을 많이 하고 싶은 날이라면 컴퓨터의 눈 높이에 맞춰 코드를 작성해야 했던 1세대 언어와 사람의 눈 높이에 맞춰 코드를 작성할 수 있는 3세대 언어의 비교정도도 곁들였던 것 같다.

OOP(Object-Orientation Programming) 의 기본 개념은 (적어도) 내가 공부 했던 자바, 스프링프레임워크의 기본서와 개발자 면접 예상 질문 후보 목록에서 항상 볼 수 있다.

## 객체란 무엇인가

> 객체란 인간이 분명하게 인지하고 구별할 수 있는 물리적인 또는 개념적인 경계를 지닌 어떤 것이다.
> 
> 조영호 저. 객체지향의 사실과 오해. 위키북스. 2015. 41페이지

객체지향이라는 개념 자체를 프로그래밍 입문서에서 처음 본 사람이라면(나 같이), 당장 언어의 문법이 궁금하지 그런 개념에는 크게 개의치 않을 것이다. 그래서 '객체'를 잘못 이해하고, 그 잘못 이해한 '객체'를 잘못된 방향으로 지향하게 되고.. 자바를 처음 배울 때 `객체 = 클래스` 라는 식으로 대입하여 이해를 시키기 때문에, 익숙해져버린 이 개념을 쉽게 벗어나기 어렵다.

객체라는 개념은 우리 인간들에게 크게 낯설지 않을 것이다. 물리적인 또는 개념적으로 묶어서 인식할 수 있는 것을 하나의 것으로 인식한다. 그리고 객체는 상태와 행동을 가진다. 

## 그래서 객체를 지향한다는게 무엇인가

> 아쉽게도 실세계의 모방이라는 개념은 객체지향의 기반을 이루는 철학적인 개념을 설명하는 데는 적합하지만 유연하고 실용적인 관점에서 객체지향 분석, 설계를 설명하기에는 적합하지 않다. 애플리케이션을 개발하면서 객체에 직접적으로 대응되는 실세계의 사물을 발견할 확률은 그다지 높지 않다.
> 
> 조영호 저. 객체지향의 사실과 오해. 위키북스. 2015. 20페이지

그럼에도 불구하고 자꾸 실세계의 모방이라는 개념을 객체지향프로그래밍을 설명하기 위해 이야기 하는 이유는, 이 비유가 객체지향의 개념을 처음 학습하는데 효과적이기 때문이라고 한다. 

내 생각은 이 객체지향 이라는 개념은 따로 공부가 필요한 영역이라는 것이다. 단순히 객체지향 언어로 프로그래밍을 하면서 몸에 베고 익숙해지는 것이 아니라. 또한 솔직히 말하자면 객체지향 설계의 원칙인 [S.O.L.I.D 원칙](https://www.wikiwand.com/ko/SOLID) 을 지키는 잘 설계 된 구조 아래에서 개발을 하고 있는 사람들이 얼마나 될까 하는게 의문이다. 그런 사람들이 부럽기도 하다.



역할, 책임, 협력

