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
