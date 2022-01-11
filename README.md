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
