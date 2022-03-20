## AAC ViewModel VS MVVM ViewModel

### 1. MVVM ViewModel

- MVVM패턴은 비즈니스 로직과 프레젠테이션 로직을 UI로부터 분리하는 것이다. 이렇게 되면 유지보수와 테스트 측면에서 용이하다.

VIew <-> ViewModel <-> Model

1. ViewModel : View에 연결될 데이터와 메서드를 구현하고, 상태가 변화하게 되면 변경 알림이벤트(LiveData)를 통해 View에게 상태변화를 알린다. View는 ViewModel의 상태변화를 observe 한다. 옵저버패턴을 사용하여서 View는 ViewModel을 알고 있지만, 반대는 아니다.

### 2. AAC ViewModel

- AAC 에서의 ViewModel은 Android의 수명 주기를 고려하여 UI 관련 데이터를 저장하고 관리하도록 설계되었다. AAC ViewModel을 사용하면 기존의 Activity가 생명 주기 때문에 데이터 관리 측면에서 겪던 어려움들을 간단하게 처리할 수 있다.

Activity가 생성되고 파괴되기 전까지 ViewModel은 파괴되지 않고 유지되게 된다. 이 때문에 화면 회전과 같은 View가 파괴되고 새로 그려지는 과정에서도 데이터를 보존할 수 있다.
