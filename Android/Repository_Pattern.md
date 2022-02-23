bb## Repository Pattern

### Repository 패턴을 사용하는 이유

- Repository는 DataSource를 캡슐화 한다.
- 필요한 DataSource가 무엇인지 Presenter 계층에서는 알 필요가 없다.
- DataSource의 변경이 발생하더라도 다른 계층은 영향 받지 않는다.
- client는 repoistory 인터페이스에 의존하기 때문에 테스트 하기 용이하다.
  <br>
  --> repository는 Presenter 계층과 data 께층의 coupling을 느슨하게 만들어준다.

### 안드로이드에서의 Repository 패턴

View -> Presenter / Viewmodel -> Repository -> DataSource(API, LocalDB)

레포지토리는 뷰모델 또는 프레젠터가 요청하는 데이터를 local 또는 remote(서버)로부터 가져와 전달해준다. 이를 통해 뷰모델 또는 프레젠터는 누구한테서 온 데이터인지 신경쓸 필요가 없다. 레포지토리가 중간 다리 역할을 해준다고 보면 된다.
</br>
레포지토리 패턴을 사용한다는 것은 DataSource 즉, Data Layer를 캡슐화한다는 의미이다.
따라서 DataSource의 변경이 발생해도, 캡슐화를 통해 변경사항은 알 필요없이 interface로 전달이 가능하다.
</br>

#### 캡슐화

캡슐화는 객체 지향 프로그래밍에서 2가지 측면이 있다.

1. 객체의 속성과 행위를 하나로 묶고,
2. 실제 구현 내용 일부를 외부에 감추어 은닉한다.  
   외부에 감추는 방법으로는 언어적 측면에서 접근지정자를 두어 은닉의 정도를 기술하여 구현한다.  
   -> 정보은닉을 하게되면 객체의 내부로직을 알 수 없게 되고 접근할 수 있는 부분이 제한되기 때문에 다른 코드와의 *결합도*가 낮아진다.  
   정보은닉을 하는 이유는 변경에 유연하게 대처하기 위해서다!
