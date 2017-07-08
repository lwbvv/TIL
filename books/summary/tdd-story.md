# TDD 이야기를 읽고

내 성격의 장점이자 단점은 지나친 꼼꼼함이다. 외출 전, 항상 두고 가는 것이 없는지 방 안을 다섯번쯤 되돌아 본다. 직장에서 퇴근 전에도 내 자리를 여러 번 돌아 본다. 물론, 코드를 버전 관리 시스템에 커밋하게 전에도 수차례 다시 확인한다. 하지만 수백줄, 수천자를 확인하다 보면 항상 놓치는 부분이 발생했고 점점 내 코드를 신뢰할 수 없고 커밋 하기를 주저하게 되었다. 



화면부터 서버단까지 End-to-End 를 모두 완성하고 나서 UI를 통해 몇 번 CRUD를 해본 후, 내 할 일을 다 마쳤다고 말하기는 뭔가 찝찝했다. 내 코드를 검증해 줄 무언가가 있으면 좋겠다고 생각했다. 대안은 단위테스트라고 생각했다. 아쉽게도 근무하는 환경에서는 코드리뷰나 테스트와 관련 된 프로세스가 없었기에 이에 대한 갈증은 갈수록 더 심해졌지만 막상 적용을 하려해도  Spring 프레임워크에서 만드는 웹어플리케이션에서는 복잡하게 얽혀 있는 의존성이 많아 쉽지 않았다.



하지만 이에 대해 계속해서 갈망하고 스터디 모임, 관련 서적, 세미나 영상등을 참고해서 현재는 내가 회사에서 개발하는 환경에 어느 정도 단위테스트를 적용할 수 있게 되었다. 현재 참여하고 있는 프로젝트에서 단위 테스트 코드를와 함께 코드를 작성하고 있고, 학습에도(자바8 등) 단위 테스트 하고 있다. 테스트 코드를 먼저 작성하며 세부 기능을 완성해 가는 TDD(Test Triven Development)를 시도해보려고 하지만 아직은 낯설고 쉽지 않았다.

- [TDD라이브 -최범균님](https://www.youtube.com/watch?v=AE7K-16dEjo)
- [클린 코더스 강의 16.1 advanced tdd 1 - 백명석님](https://www.youtube.com/watch?v=czjWpmy3rkM)



나는 위 두 영상의 TDD 라이브를 보면서 참 감명 받았는데, 특히 테스트 작성 - 실패 - 성공 - 리팩토링 의 싸이클을 빠르게 돌며 진행 되는 개발리듬이 참 좋았다. 하지만 막상 실제로 적용하려해도 그냥 개발을 할 때 보다 더 많은 지식과 이해가 동반되어야 해서 쉽지 않았다.



어쨋든, 최근 가장 관심을 가지고 있는 부분이 테스트와 더불어 소프트웨어 품질 향상에 관한 것이다. 그러던 중 SNS에서 [TDD이야기](http://book.naver.com/bookdb/book_detail.nhn?bid=7422964) 라는 책의 추천 글을 보고 읽어보게 되었다. 이 책은 TDD 입문자를 위한 책은 아니고 어느 정도 경험 해본 개발자를 위한 책이다. 책에서도 대상을 아래와 같이 쓰고 있다.

- TDD를 공부했으나, 여러가지 풀리지 않는 문제점으로 인해 끙끙대는 프로그래머
- TDD 도입에 실패했지만 다른 방법을 모색하여 도입에 성공하고 싶은 프로그래머
- TDD를 두 번 다시 하고 싶지 않은 프로그래머

책 전반에 걸쳐 일반적으로 테스트주도개발에 대해 잘못 알려져 있는 오해들을 바로 잡고 장점들을 설명한다.



## 테스트하기 좋은 코드가 좋은 코드다

> 테스트 코드를 작성하기 어렵다는 것은 대부분 설계가 잘못되었다는 것을 암시한다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 14페이지



> 세분화 하지 않으면 테스트 코드의 구현 자체가 어려워진다. 요구사항이 비대하거나 다른 객체와의 결합도가 높을 때 복잡하고 세분화해야 하는 대상이 발생하기 때문이다. 따라서 요구 사항이 부족하다면 더 자세하고 잘게 나누어야 하며 결합도가 높다면 그 대상부터 리팩토링해야 한다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 35페이지
>
> 

나는 최근 리팩토링토링을 학습하며 느낀 것들 때문에 위 인용 구절에 동감한다. 객체지향 프로그램에서는 단일 책임 원칙이라 하여 하나의 객체는 하나의 책임만을 가져야 하는데, 그런 책임의 분리 없이 한 곳에 모든 것을 구현해 놓아 너무 비대한 클래스(또는 메소드)는 테스트가 어려웠다. 그리고 그런 객체들의 책임을 적절하게 세분화할수록 테스트를 작성하기 쉬웠고 코드는 훨씬 보기 좋아졌다.



## 코드 커버리지에 대한 잘못된 생각

> 코드 커버리지는 관리적인 측면이나 구현체의 가이드로서 매우 도움이 되는 '좋은 도구'다. 하지만 코드 커버리지의 준수율에 얽매이는 순간부터 좋은 도구의 의미는 왜곡된다. 나아가 오용되기 시작하면 순기능적 측면이 차츰 없어지고 개발자의 목을 조이기만 하는 '나쁜 도구'로 변모하고 말 것이다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 20페이지

학습코드나 개인 프로젝트를 모두 [Github](https://github.com/iamkyu)에 올리는데, 저장소에 CI 도구나 테스트 커버리지 레포트를 생성해주는 도구를 연동해놓았다. 그래서 해당 저장소에 들어가면 첫 페이지에 커버리지가 나타나도록 해놓았다. 이렇게 세팅을 해놓으니 나도 모르게 커버리지를 높이는 것에 집착하게 되었고, 이를 위해 테스트를 작성하는데 시간을 많이 낭비하였다. 문제는 단지 커버리지율을 높이기 위해 불필요한 테스트를 작성하게 된다는 것. 너무 커버리지 측면에 얽매이지 않도록 주의해야겠다.



## 객체지향

> 테스트 코드를 먼저 작성하는 것은 목표를 시각화하는 작업이다. 테스트를 작성하면 주어진 입력 값에 대해 기대하는 결과 값이 무엇인지를 먼저 고민하게 되기 때문이다. (중략) 더불어 테스트를 먼저 작성함으로써 구현보다 인터페이스에 집중할 수 있는데, 그 이유는 구현 이전에 기대하는 입출력 값과 시그니처를 고민하기 때문이다. 구현보다 인터페이스를 고민하는 것은 대부분의 경우 도움이 되고, 이러한 현상은 모듈을 개발하는 사람과 사용자 모두에게 이득이 된다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 27페이지



> TDD를 하기 위해서 해당 클래스를 만들고, 해당 클래스의 메소드를 만드는 것부터 시작하게 된다. 우리가 테스트하기 위한 기능은 로그인 기능이다. 따라서 서비스클래스 객체를 만들고 인스턴스화 되었을 때 접근자에 대한 사고를 하게 된다. 그리고 그 객체를 사용하는 관점에서 '이 객체가 어떻게 만들어졌는지'는 관심사가 아니다. '무엇을 얻어가야하는지'가 관심사기 때문에, 테스트 코드는 '무엇'에 집중할 수 있다. 더불어 불필요한 인터페이스를 방지하고 메소드 이름과 파라미터 리턴 타입에 좀 더 관심을 가지게 된다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 34페이지



TDD를 익히면서 객체지향프로그래밍과 참 잘 맞는다는 생각이 든다. OOP에서 객체들은 서로 유기적으로 얽혀서 각자 역할의 책임을 가진다. 자신이 할 수 없는 일은 다른 객체에 '무엇을' 해야 하는지 메세지를 보낸다. '어떻게' 할지는 메세지를 보내는 측에서 알 필요가 없는 부분이다. 메세지를 받는 객체가 알아서 할 일이다. 이와 같이 어떤 메세지를 받아야 하고 어떤 응답을 받을지 시그니처에 집중하는 것이다. 인터페이스를 만드는 것은 객체의 설계도를 미리 그리는 것과 같다고 생각한다.



## private 메서드 테스트

현재 프로젝트에서 단위 테스트를 작성하며 접근제어자가 `private` 인 메소드는 테스트하기가 난감했다. 마땅한 해결책이 없어 해당 메소드를 그대로 테스트 클래스로 옮겨 테스트했다. 책에서는 `private` 메소드의 경우 따로 테스트하지 않고 그 메소드를 사용하는 `public` 메소드를 통해 테스트 하거나, 테스트시에만 접근제어자를 변경하거나, 자바의 `reflection`  클래스를 사용하라고 한다. 리플랙션은 생각도 못했는데 이 방법을 적용해볼 생각이다.



## Top-Down, Bottom Up

TDD 방식은 작은 단위의 기능부터 점진적으로 완성해 나가기 때문에 상향식 접근(Bottom-Up) 성향이 짙다. 소프트웨어 개발에는 설계가 굉장히 중요한 요소하기 때문에  설계적 접근(Top-Down)이 중요한데 이 때문에 TDD 실효성에 대해 논란이 발생한다고 한다. 책에서는 이에 대한 오해들을 풀어 설명하며 결국 두 가지는 병행해야 하며 디자인(설계 또는 시나리오 등)은 Top-Down, 기능은 Bottom-up 으로 접근해야 한다고 한다. 

중국음식식당 시스템을 개발하는 예를 들면서, 클라이언트의 요구 사항을 분석하고 이를 바탕으로 설계를 마치고 하향식접근 방식으로 테스트를 디자인한다.

```java
// 간략히 보기 위해 각 메소드 한 줄로 작성
@Test public void test_손님입장() {}
@Test public void test_자리찾기() {}
@Test public void test_세팅하기() {}
@Test public void test_메뉴받기() {}
@Test public void test_쿠폰받기() {}
@Test public void test_계산하기() {}
```

이 후에는 각 요구사항 마다 기능 구현은 TDD를 통해 상향식으로 접근한다.



## 테스트주도개발

> TDD를 하는 개발자 상당수가 TDD를 테스트에 대한 것으로만 생각할 뿐, 케이스라고는 생각하지 않는다는 점이다. (중략) 사실 TDD는 테스트를 위한 개발 방법론이 아니다. 코드를 작성하기에 앞서 어떤 코드를 작성할지 미리 명세화하고 기대되는 행동들을 실행 가능한 형태로 만들어 나가는 개발 방법론이다.
>
> -TDD에 관한 오해와 진실. 신정호 외 4명 저. 한빛미디어. 2014. 141페이지



이 부분은 소프트웨어 개발의 특징과 연관된 부분이라고 생각한다. 소프트웨어 개발에서 클라이언트는 본인이 원하는 것을 정확히 모른다고 말한다. 그리고 개발이 진행되면서 점점 본인이 원하는 것을 알아간다고 한다. 이는 개발자도 똑같다고 생각한다. 요구사항을 바탕으로 큼지막한 분류는 나눌 수 있지만 더 세부적인 분류로 어떤 기능들을 가져야할 지 고민하는 것은 쉽지 않다. 또한 코드로 구현해보기 전에 생각을 완벽히 정리하기도 힘들다. 따라서 TDD 과정은 단순 테스트 뿐만 아니라 인터페이스를 만들고 세부 기능을 구현해 나가는 과정이라 할 수 있겠다.