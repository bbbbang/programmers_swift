# let과 var
- let : 상수 선언 (값 변경 불가)
- var : 변수 선언 (값 변경 가능)
- let 사용 권장

#### practice
> 판교역 도착 방송을 위해 작성한 코드에서 문제가 생겼습니다. 어디가 문제인지 알아내, 방송이 무사히 전달될 수 있도록 코드를 수정해주세요.

<pre><code> var announcement:String = ""
  let intro = "다음 역은 "
  let outro = "입니다."

  var station = "판교역"

  announcement = intro + station + outro
  print(announcement)
</code></pre>


>>다음 역은 판교역입니다.


# String
- 문자열 정의 시, "let name:String = "Jiwon"
- let characters = name.characters
  - 문자열 하나하나에 독립적으로 접근 가능한 array와 비슷한 'String.CharacterView' object가 나온다.
- let count = characters.count
  - characters의 길이 5 가 출력된다.
- let url = "programmers.co.kr/learn/courses/4/lessons/75#"
let hasProtocol = url.hasPrefix("http://")
  - http:// 라는 프로토콜을 가지고 있는지에 대해 출력 (T/F)
- print("\(name)")
  - 괄호 안 변수/상수 출력

# Number
- var currentSpeed:Int = 110
  var currentSpeed += Int(20.5)
  - int type에 float/double 형 변수 연산을 하고 싶을 때
- UInt : 부호를 갖고있지 않은 정수
  - min : 0
  - max : Int.max 의 두배
- let pi = 3.14 (기본적으로 double값으로 저장 된다.)
  let divider = 2 (당연히 정수형으로 저장)
  let halfPi-pi/Double(divider)
    - divider를 double형으로 변환하여 연산하지 않으면, 오류가 발생한다.

#### practice
> 판교와 파주 사이에 거리는 69500m입니다.
2번째 줄의 distance를 적당한 타입으로 변경해서 description을 다음과 같이 출력되게 완성해보세요.
판교에서 파주는 69.5km 거리입니다.

<pre><code>
let distance = 69500
let description = "판교에서 파주는 " + String(Double(Double(distance)/Double(1000))) + "km 거리입니다."

print(description)
</code></pre>

>>판교에서 파주는 69.5km 거리입니다.
