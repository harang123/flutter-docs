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
 ![image](https://user-images.githubusercontent.com/87854296/148805153-affb6afb-7b89-4cbb-a67f-880cd2655090.png)
 - 그림에서 보듯이 test, icon, image, Text field, button과 같은 앱 화면을 구성하고있는 모든 요소들을 플로터에서는 위젯이라고 말한다.
 
- 플로터에서는 눈에보이는 요소들 뿐만 아니라 눈에 보이지 않는 요소들까지 위젯이라고한다.
 ![image](https://user-images.githubusercontent.com/87854296/148805172-1139141c-8e17-4bc8-ae55-835dba4d8e46.png)
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
 


******
flutter-docs

공부방법 계획 : flutter-docs를 읽어봤는데 영어로 되있어서 의미를 정확하게 이해하기 어렵고 집중해서 읽은만큼 많이 이해되는부분이 없었다. 
또한 chrome 한글번역을 사용하니 위젯들이나 주요 메서드들도 한글로 번역되어 나오는바람에 이해하는데 어려움이 있었다.
기본적인 개념을 알고 읽으면 좀 쉽게 이해할수 있을거 같아 부득이하게 유투브로 간단한 앱을 만들며 먼저 대략적인 흐름이나 자주사용하는 위젯들을 익히고 flutter-docs의
개념을 다시 읽어보려한다. 

아래는 오늘 강의를 들은 후 다시 만들어본 위젯이다.

 ![image](https://user-images.githubusercontent.com/87854296/148982510-7e85d67c-5227-40d8-b529-0a79207a61e5.png)



아래로는 위의 위젯을 만들며 공부한 위젯들과 설명을 작성하였다.
<pre>
<code>
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // 전체적인 뼈대를 형성하기 때문에 정적인 위젯이다.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false, // 우측상단의 debug띠 모양 삭제하는 위젯
      title: 'BBANTO',
      home: Grade(),
    );
  }
}

class Grade extends StatelessWidget {
  // ststeless, steteful 중에 하나라도 동적인게 있으면 stateful로 작성한다.

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // 페이지의 도화지를 설정하는 위젯이다.
      backgroundColor: Colors.amber[800], // 페이지의 전체 생상을 선택해준다.
      appBar: AppBar(
        backgroundColor: Colors.amber[700],
        title: Text('BBANTO'), // 앱을 처음실행했을때 보이는 home의 appbar 제목설정
        centerTitle: true, // 타이틀을 center에 위치하게 하고 싶을때
        elevation: 0.0, // appbar의 입체감을 죽이고 싶을때
      ),
      body: Padding(
        // 이제 home부분에서 body에 해당하는데 body부분에서 padding으로 위치를 정해준다.
        padding:
            EdgeInsets.fromLTRB(30.0, 40.0, 0.0, 0.0), // LTRB를 이용해 세부 위치 지정
        child: Column(
          // Padding의 값을 받는 자식 위젯 생성
          crossAxisAlignment:
              CrossAxisAlignment.start, // 자식들에게 적용되는 값 가로에 대한 값인데 시작점이 같아진다.
          children: [
            // child인수에서 children 위젯(배열)을 생성해 값을 지정해준다. column의 값을 받으므로 세로로 작성된다.
            Center(
              // 세로로 정렬되는 값 중 해당 세로 위치에서 center로 지정하고 싶을때 사용하는 위젯
              child: CircleAvatar(
                // center의 값을 받는 child 인수에서 CircleAvatar 위젯 사용
                backgroundImage: AssetImage(
                    'asset/bear.jpeg'), // CircleAvatar를 사용하였기 때문에 이미지가 동그라미 모양으로 들어감.
                radius: 60.0, // Circle이기때문에 radius(반지름)의 크기를 키워 이미지의 크기를 조절한다.
              ),
            ),
            Divider(
              // Divider 위젯은 구분선을 지정해 줄때 사용하는 위젯이다.
              height: 60.0, // 여기서 height는 구분선을 기준으로 아래 30.0, 위 30.0의 길이를 지정해준다.
              color: Colors.grey[850], // 구분선의 색깔을 지정해준다.
              thickness: 0.5, // 이게 구분선의 굵기를 설정해 주는 인수이다.
              endIndent: 30.0, // 이건 구분선이 끝나는 지점에서 30.0만큼 잘라준다.
            ),
            Text(
              'NAME', // Text위젯의 값이 설정된다.
              style: TextStyle(
                // Text에 대한 스타일을 적용해주는 인수의 TextStyle위젯이다.
                color: Colors.white, // 글자의 색상을 지정해준다.
                letterSpacing: 2.0, // 글자사이의 간격을 정해준다.
              ),
            ),
            SizedBox(
              // 위의 Text위젯과 아래의 Text위젯 사이에 SizedBox를 넣어 거리를 조절해주는 위젯이다.
              height: 10.0,
            ),
            Text(
              'BBANTO', // Text위젯의 값 설정
              style: TextStyle(
                  // style인수의 TextStyle 위젯
                  color: Colors.white, // 글자 색 지정
                  letterSpacing: 2.0, // 글자 간격 설정
                  fontSize: 28.0, // 글자 크기 설정
                  fontWeight: FontWeight.bold // 글자 굵기 설정
                  ),
            ),
            SizedBox(
              height: 30.0,
            ),
            Text(
              'BBANTO POWER LEVEL',
              style: TextStyle(
                color: Colors.white,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(
              height: 10.0,
            ),
            Text(
              '14',
              style: TextStyle(
                color: Colors.white,
                letterSpacing: 2.0,
                fontSize: 28.0,
                fontWeight: FontWeight.bold,
              ),
            ),
            SizedBox(
              height: 30.0,
            ),
            Row(
              // Row 위젯은 column위젯과 반대의미이다. column위젯은 세로로 레이아웃을 설정해 주고 Row위젯은 가로로 해준다.
              children: [
                // Row 위젯에서 children 인수 배열을 사용하여 가로로 정렬하고 싶은 값들을 넣어준다.
                Icon(Icons
                    .check_circle_outline), // Icon 위젯을 사용하여 투명동그라미에 체크표시된 icon을 받아온다.
                SizedBox(
                  // 여기서도 sizedBox를 사용하여 icon과 밑의 Text위젯 사이의 간격을 조절해준다.
                  width: 10.0,
                ),
                Text(
                  'using lightsaber',
                  style: TextStyle(
                    fontSize: 16.0,
                    letterSpacing: 1.0,
                  ),
                )
              ],
            ),
            Row(
              children: [
                Icon(Icons.check_circle_outline),
                SizedBox(
                  width: 10.0,
                ),
                Text(
                  'face hero tattoo',
                  style: TextStyle(
                    fontSize: 16.0,
                    letterSpacing: 1.0,
                  ),
                )
              ],
            ),
            Row(
              children: [
                Icon(Icons.check_circle_outline),
                SizedBox(
                  width: 10.0,
                ),
                Text(
                  'fire flames',
                  style: TextStyle(
                    fontSize: 16.0,
                    letterSpacing: 1.0,
                  ),
                )
              ],
            ),
            Center(
              // 여기서부터는 따로 Row 위젯이 필요없기때문에 row를 사용하지 않고 가운데에 위치시키기 위한 center만 사용하였다.
              child: CircleAvatar(
                // 위에서와 마찬가지로 이미지를 넣는 방식인 CircleAvatar 위젯을 사용하였다.
                backgroundImage:
                    AssetImage('asset/rabbit.jpeg'), // 배경이미지에 해당 이미지를 지정해준다.
                radius: 40.0,
                backgroundColor: Colors.amber[800],
              ),
            )
          ],
        ),
      ),
    );
  }
}
</code>
</pre>

추가적으로 정리한 내용!

#### 좌측 각 폴더 및 파일에 대한 설명

pubspec.yaml 파일 : 
- 프로젝트의 메타데이터를 정의하고 관리하는 파일
- 프로젝트의 버전, 사용환경, dart의 버전이나 각종 디펜던시, 라이브러리 등을 이곳에서 정의함

-> 앱을 만들 때  여러가지 필요한 중요한 내용들을 이곳에 등록한다 정도로 알고 있자.

좌측 메뉴열에 android폴더와 ios폴더는 각 플랫폼에 맞게 앱을 배포하기 위한 정보들을 가지고 있다.

test폴더는 개발하기 원하는 각종 dart관련 코드들을 테스트해볼 수 있다.

가장 중요한 폴더는 lib폴더이다. lib폴더안에는 main.dart 파일이 들어있다. 앞으로 앱을 만들때 거의 99%를 여기서 작업해야 한다.

#### 앱을 만드는 순서 및 주요개념정리

Flutter material 라이브러리를 import하는 것이 첫번째이다. 이 라이브러리 안에 플로터 프레임워크, 즉 SDK에 포함된 모든 기본 위젯과 
material 테마 디자인 요소들을 사용할 수 있기 떄문이다. 
material design(모바일, 데스크탑, 그 외의 다양한 device)를 아우르는 일관된 디자인을 위해서 구글이 제공한 가이드 라인이라는 것을 이해하면 된다.

그 이후 아래에 void main() 함수를 만들어 주는데 이게 앱의 시작점으로 보면된다.

- main(), runApp()은 함수이지만 MyApp은 함수가 아니다. 앞글자가 소문자로 시작하면 함수이고 대문자이면 클래스라고 생각하면된다.
- MyApp위젯은 앱을 만들때 전체적인 뼈대를 설정하는 위젯이기때문에 정적(stateless)인 요소들로 이루어질 것이다.
- 모든 custom 위젯은 또 다른 위젯을 리턴하는 build라는 함수를 가지고 있다. 그래서 MyApp위젯은 container라는 위젯을 리턴하고 있는것을 알 수있다.
- flutter/material 라이브러리를 사용할 수 있는 기능을 가진 materialApp이라는 위젯이 있는데 return값인 container 위젯을 지우고 그 자리에 mate를 입력하여 입력란의 
  materialApp이라는 함수를 선택하여 준다. 이렇게 바꿔 줌으로써 플로터 프레임워크가 제공하는 모든 기본 위젯과 이자인 테마를 본격적으로 사용할 수 있다.

- material 위젯이 위젯트리에서 2번째 자리에 위치하고 있고 실질적으로 모든 위젯을 감싸고 있다고 보면 된다. material 위젯은 runApp함수처럼 반드시 인수들을 가져야 한다. 
- 또한 플러터의 모든 위젯들이 이렇게 인수를 가진다고 생각하면 된다.

- materialApp은 title이라는 문자열을 인수로 가지고 있다.

- 위젯이 끝나는 부분에 //ThemeData라는 글이 보이는데 이것을 클로징 레이블이라고 한다.
  플로터는 여러 위젯들을 나열하면서 코딩을 하기 때문에 위젯들의 구분이 아주 중요하다. 그래서 알아보기쉽게 자동으로 위젯의 끝을 알려주는 시스템이 있다.

- home은 앱이 정상적으로 실행되었을때에 가장먼저 보여지는 경로이다. 따라서 이제 홈 뒤에 MyHomePage()라는 커스텀 위젯을 만들어 준다.
  이제 앱을 실행시키면 MyHomePage위젯 내의 내용들을 가장 먼저 보게된다.

- MyHomePage()또한 새로운 위젯이기때문에 MyApp 위젯에서 나와 생성한다.
  새로운 커스텀위젯을 만들때는 만들기전에 이 커스텀 위젯을 steteless위젯으로 만들지 stateful 위젯으로 만들지를 정하고 시작해야 한다.
  만약 MyHomePage 위젯내에 무언가 데이터를 받거나 체크박스나 라디오 버튼처럼 체크했을때 모양이 변하는 요소가 하나라도 있다면 stateful 위젯으로 지정해야 한다.

- scaffold위젯은 앱 화면에 다양한 요소들을 배치하고 그릴 수 있도록 도와주는 도화지 같은 위젯이다.
  scaffold라는 뜻은 무언가를 혼자 해낼 수 있도록 발판을 만들어 주다라는 의미가 있다.

- 기본적으로 앱을 실행하게 되면 쨸 상단에 AppBar가 있다. scaffold위젯도 이 appbar란 위젯을 가지고 있다.
  AppBar() 위젯내에서 AppBar만을 위한 모든 디자인과 기능들을 구성할 수 있다.


- Text()위젯은 text와 관련된 다양한 디자인적 인수를 가지는 요소이다.

- 여기서 중요한 차이점이 있는데 MyApp에서는 title인수를 받았을때 text 위젯을 거치지 않고 바로 'First App'이란 문자열로 타이틀을 나타냈다. 이 이유는 MyApp위젯의 materialApp의 인수인 
  title은 앱을 총칭하는 제목이다. 예를 들어 우리가 아이폰에서 어떠한 앱을 다운받으려 할때 snow처럼 보여지는 이름이 바로  title이다. 

- body에 해당하는부분들을 작성하기 위해서는 scaffold() 위젯에서 body인수를 받은 뒤  body인수의 값으로 작성해가기 시작하면된다.

- MyApp 커스텀 위젯에서 MaterialApp 위젯에 home부분에 MyHomePage()라는 커스텀 위젯을 만들 필요 없이 바로 scaffold 위젯을 넣어 작성할 수 있지만 굳이 MyHomePage라는 커스텀 위젯을 만들어 
  분리한 이유는 한페이지에 꼭 많은 양을 넣을 필요가 없고 그렇게 작성하게 된다면 가독성이 떨어질 수 있기 떄문입니다. 그래야 추후에 유지보수나 구별하는것이 쉬워지게 된다.
  
 - 위젯 삭제하는법  : 맨 뒷부분에 있는 클로징 레이블 부터 지워주는 것이다. 괄호를 지워준 후 앞부분을 지우면 아무 오류없이  삭제되는것을  알 수 있다.

- center 위젯으로 column위젯 감싸는방법 : body: column( 이렇게 시작부분에 커서를 놓으면 좌측에 노란색 전구모양이 뜨는데 그 전구모양을 클릭하고 Wrap with center를 클릭하여 
  Wrap center를 선택하여 column위젯을 감쌀 수 있다.

- column위젯과 center위젯의 주요 특징(mainAxisAlignment의 사용예) : 
  일반적으로 center위젯은 child위젯을 단순히 중앙에 배치하는 구나 생각하는데 center위젯이 있다고 해서 항상 위젯들이 정중앙에 배치되는것은 아니다.
  그 예가 center위젯과 column위젯이 만날때이다. 
  column위젯은 특별한 제약을 가지고있다 . 자식들에 대해 세로축에대한 제약이 전혀 없기 때문에 내 마음대로확장해도 돼 라고 전달을 해준다. 
  가로축에대해서는 넓이에 대한 확실한 제약을 두고 표현되지만 세로축상으로는 아무런 제약이 없다.
  column위젯과 cneter위젯이 만나면 center위젯은 column위젯의 자식들에 대해 세로축 위치에대해서는 관여하지않고 현재 column위젯의 자식위젯 세로축 높이에 자동으로 픽스 된다. 
  가로축으로만 중앙에 위치하게된다. 세로축은 픽스되어있는 상태이다.
  center위젯과 column위젯이 결합되었을때 세로축상으로 정 중앙에 위치하고 싶다면 mainAxisAlignment가 필요하다.
  정리하자면 column위젯에서 정 중앙에 위치시키고싶으면 center 위젯으로 column을 감싸주면되고, 세로축으로 정중앙에 위치시키고 싶으면 컬럼 위젯내에서 mainAxisAlignment을 설정하면 된다.

- crossAxisAlignment를 설정하여 두 텍스트의 시작점을 맞춰 줄 수 있다. ex) crossAxisAlignment: CrossAxisAlignment.start, 와 같이 사용하면 된다.

- 이미지 파일 넣어주는 방법 : 우선 프로젝트의 좌측 파일목록에 새로운 폴더를 만들고(이미지를 넣을 장소) 사용할 이미지를 넣어준 후 pubspec.yaml 파일을 클릭한다.
  pubspec.yaml 파일의 내용에 assets라는 멘션된 부분이 있는데 그 부분을 드래그하여 멘션을 풀어준다. pubspec파일은 들여쓰기에 굉장히 민감하니 가급적이면 이 형태 그대로 사용하도록 해야한다.
  그런다음 dart.main파일에서 이미지 파일을 넣어주고 싶은 부분에 CircleAvatar 위젯을 사용하고
  위젯 안에서 backgroundImage 인수를 실행한 후 값으로 AssetImage('pubspec.yaml에 입력했던 경로를 그대로 가져다 붙이면된다.)
  그런 후 이미지를 Circle형식으로 넣었기 떄문에 크기 조절은 radius: 60.0 이런식으로 하면 된다.
 
  ex)
  Center(  // 가져온 이미지를 center에 위치시켜야해서 사용!
              child: CircleAvatar(  // Circle 모양으로 가져오려함
                backgroundImage: AssetImage('asset/rabbit.jpeg'),  // 이미지를 넣어줌
                radius: 40.0,  // 원의 크기를 설정해줌
                backgroundColor: Colors.amber[800],  // 이미지의 뒷 배경색과 전체 배경색을 맞춰 배경이 투명인것처럼 설정해줌
              ),
            )
그리고 이 이미지를 중앙에 위치시키고 싶으면 center위젯으로 wrap해주면 되는데 
cildren 위젯안에 있는 child 위젯안에서 CircleAvatar를 사용하니까 그걸 center로 덮어주면 된다.
