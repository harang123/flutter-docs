# flutter-docs
flutter docs

## 플러터의 중요 개념 잡기

Widget(위젯)

* 일반적인 widget의 의미 : 
1) 독립적으로 실행되는 작은 프로그램이다.
2) 주로 바탕화면 등에서 날씨나 뉴스, 생활정보 등을 보여준다.
3) 그래픽이나 데이터 요소를 처리하는 함수를 가지고 있다.

### Flutter 상에서의 위젯이란?
 - UI를 만들고 구성하는 모든 기본 단위 요소
<img src="C:\Users\USER\Desktop\이미지\148803486-7029328b-c029-4802-bce0-75651f7afa5d.png" width="30%" height="40%" title="px(픽셀) 크기 설정"></img>
 - 그림에서 보듯이 test, icon, image, Text field, button과 같은 앱 화면을 구성하고있는 모든 요소들을 플로터에서는 위젯이라고 말한다.

- 플로터에서는 눈에보이는 요소들 뿐만 아니라 눈에 보이지 않는 요소들까지 위젯이라고한다.
 
center, column, padding과 같이 눈에 보이지 않는 레이아웃을 정의하는 모든 요소들까지 위젯이라고 한다.

- 플로터에서는 모든것이 위젯이라 할 수 있다. 위젯들을 모아 만들어진 앱 또한 위젯이라고 할 수 있다.

플로터에서는 반드시 알아야 할 3종류의 위젯이 있다.
1) Stateless Widget
2. Stateful Widget
3. Inherited Widget

### Stateless와 Stateful의 일반적인 의미
1. Stateless => 이전 상호작용의 어떠한 값도 저장하지 않음(상대가 없는 정적인 위젯)
2. Stateful => 입력되는 Value값에 의한 상호작용의 상태를 지속적으로 추적 보존(계속 움직임이나 변화가 있는 위젯)

각 위젯에 대한 특징
1. Stateless Widgets
 - 스크린상에 존재만 할 뿐 아무것도 하지 않는다.
 - 어떠한 실시간 데이터도 저장하지 않는다.
 - 어떤 변화(모양, 상태)를 유발시키는 value값을 가지지 않는다.
(보여지는 텍스트나, 움직이지않는 이미지 파일 같은것을 예시로 들수있다)

2. Stateful Widgets
 - 사용자의 상호작용에 따라서 모양이 바뀐다.(체크박스나 라운드 같은 경우)
 - 데이터를 받게 되었을 때 모양이 바뀐다. ex) Text Field와 같이 입력받은 값이 화면에 나타나는 것

### Flutter Widget tree
1. Widget들은 tree 구조로 정리될 수 있음
2. 한 Widget내에 얼마든지 다른 widget들이 포함될 수 있다.
3. Widget은 부모 위젯과 자식 위젯으로 구성되어 있다.
4. Parent widget을 widget container라고 부르기도 한다.

widget tree의 구조를 간단히 살펴보자.
최상위 위치에는 MyApp이란 위젯이 존재한다. 앱의 루트위젯이자, 앱의 시작점이다.
참고로 이름이 꼭 MyApp일 필요는 없다.

2번째의 위치에는 MaterialApp이 위치한다.
실질적으로 이 MaterialApp위젯이 전체앱을 감싸고 있는 위젯이라고 할 수 있습니다.
그리고 이 MaterialApp위젯을 통해 우리가 설치했던 flutterSdk에서 제공하는 위젯이라고 이름붙여진 모든 것들을 사용할 수 있게 됩니다.

3번째로 MyHomePage위젯이 있습니다. 이거 또한 최상위 위치의 MyApp처럼 이름이 반드시 MyHomePage일 필요는 없습니다.
여기에서부터 본격적으로 앱의 디자인과 기능들이 만들어진다고 보면 됩니다.

4번째로는 Scaffold위젯이라는 것이 있습니다.
아주 중요한 위젯이고, 이 위젯은 앱 화면과 기능을 구성하기 위한 빈 페이지를 준비해주는 위젯이라고 이해하시면됩니다.
이 Scaffold위젯 밑으로 본격적으로 UI와 관련해서 보여지는 모든 앱의 구성요소들(이미지, 버튼, 텍스트 or 눈에보이지는 않는 center, column, padding과 같은 위젯들이 사용된다.)

5번째에는 AppBar위젯이 위치합니다.
Scaffold위젯이 생성되었기 때문에 이제부터는 방금 말씀드린대로 앱 화면의 가장 상단에 위치하는 AppBar부터 디자인이 가능하게 된 것이다.

6번째는 AppBar의 구성요소중에 하나인 Text위젯이 위치합니다.
AppBar 타이들인 Log in이 바로 이 Text 위젯에 속하는 것입니다.
이제부터는 AppBar 밑으로 페이지의 바디부분에 해당하는 요소들이 오게된다.

7번째는 center위젯이 오게 된다. center위젯은 눈에 보이는 위젯은 아니지만 모든 구성요소들을 화면의 중앙에 위치시키기 위한 위젯이다.

8번째는 column위젯이 온다. 이 위젯은 요소들을 세로로 위치시키게 하기 위한 위젯이다.

마지막으로 image위젯, TextField위젯, button위젯이 오게 됩니다.
-----widget tree 모형도-----
  ![image](https://user-images.githubusercontent.com/87854296/148803559-bd1537f0-5792-40de-ae3a-a50bb63d9bd6.png)

요약 
 - Flutter의 모든 것은 widget이다.
 - 위젯이 전혀 변화가 없으면 stateless widgets
 - 위젯의 모양이나 상태가 바뀐다면 stateful widgets
 - 위젯은 트리 구조로 구성되어 있다















