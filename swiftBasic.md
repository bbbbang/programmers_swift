## 

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
- print("₩\₩(name)")
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

<pre><code>let distance = 69500
let description = "판교에서 파주는 " + String(Double(Double(distance)/Double(1000))) + "km 거리입니다."

print(description)
</code></pre>

>>판교에서 파주는 69.5km 거리입니다.


# Tuple
- 괄호 () 로 묶어 표현하며, 콤마 , 로 구분 한 값의 리스트

<pre><code> let time1 = (9,0,48)  
  let time2:(h:Int, m:Int, s:Int) = (11, 51, 5)
  time1.0 // 0번째 값 9 출력
  time2.h , time2.m // 숫자 index보다 사용 편리
  let duration = (time1, time2)  
  let (start, end) = duration  
  let endHour = end.h</code></pre>

# typealias
- 직접 type을 지정하여 사용하는 방법

  <pre><code>typealias Time = (h:Int, m:Int, s:Int)  
  typealias Duration = (start:Time, end:Time)  
  let today:Duration = ((910,23)(17,8,32)  
  print("We studied until ₩\₩(today.end.h) today")</code><pre>

#### practice
> 트라이애슬론은 수영, 사이클, 달리기가 합쳐진 운동으로, 우리에게 철인 3종 경기라는 이름으로 잘 알려져 있습니다. 트라이애슬론에는 단거리 경주인 sprint와 장거리 경기인 ironMan 경기가 있습니다.
ironMan경기의 사이클 거리가 sprint경기의 사이클 거리의 몇배인지를 times에 저장하고 싶습니다. 코드 5번째 줄의 _____를 수정해서 times에 값을 저장하세요.

<code><pre> typealias Triathlon = (swim:Int, cycle:Int, running:Int)
let sprint = Triathlon(750, 20000, 5000)
let ironMan = Triathlon(3800, 180000, 42200)

let times = ironMan.cycle/sprint.cycle

print(times)</pre></code>

>>9


# Array
- 순서를 가지고 있는 값의 배열
- 선언 및 값 추가
  - var meetingRooms:Array<String> = ["Kahlo","Picasso","Matisse"]  
  var groups:[Int] = [5,10,15]  
- 값 추가
  - var newRoom:String = "Renoir"  
    let newCapacity = 0.5
  - meetingRooms += [newRoom]
  speedHistory.append(Int(newCapacity))  ... 형을 변경시켜서 추가(append 해준다.
- 접근
  - speedHistory[0] = speedHistory.first

# Dictionary
- 값에 이름표를 붙여 저장하는 상자
- 두 개 이상의 변수를 한번에 저장하려 할 때 사용(Array 예제의 meetingRooms와 groups를 한번에 저장하고 싶을 때 사용.)  
- 정의  
  var roomCapacity:[String:int] = ["Kahlo":5, "Picasso":10, "Matisse":15]  
- 값 추가  
  roomCapacity["Renoir"]=0
- 특정 값들만 가져오고 싶을 때  
  let roomNames = roomCapacity.keys  
  let capacities = roomCapacity.values  

# Set
- 순서를 가지고 있지 않기 때문에 집합연산을 하기 쉽다. (intersect, subtract, union, exclusiveOR)

<code><pre>let num:Set = [1,2,3,4,5,6,7,8,9,10]
let even:Set = [2,4,6,8,10]

let same = num.intersect(even)
let dif = num.subtract(even)
let union = num.union(even)
let exOR = num.exclusiveOr(even) (합집합-교집합)
</pre></code>

#### practice
>영웅들로 구성된 파티를 만들어, 상대방의 파티와 싸우는 게임을 만드려고 합니다. 기존 파티 heroes에 새로운 영웅 newHero를 파티의 맨 앞에 영입하는 완성하세요.
heroes에 새로운 항목을 추가할 수 있도록 만든 뒤, newHero를 맨 앞에 추가하면 됩니다.
newHero를 맨 앞에 추가하려면, insert를 참고하세요.

<pre><code>
var heroes = ["프린스", "마녀", "해골 군대", "고블린 통"]
var newHero = "흑룡"

heroes.insert(newHero, atIndex: 0)

print(heroes)
</code></pre>

>>["흑룡", "프린스", "마녀", "해골 군대", "고블린 통"]

>상대방의 영웅 파티가 나타났습니다. 상대방과 겨룰 때에는 서로 겹치는 영웅들끼리만 대전을 할 수 있습니다.
내가 가진 영웅 heros과 상대의 영웅 oppHeros끼리 겹치는 영웅으로 이루어진 Set인 intersectHeros를 구하세요.
(Swift 최신 버전에서 intersect가 intersection으로 이름이 변경되었습니다.)

<pre><code>
let heros:Set = ["프린스", "마녀", "해골 군대", "고블린 통"]
let oppHeros:Set = ["자이언트 해골", "고블린 통", "대형석궁", "프린스"]

// 상대와 겹치는 영웅들로 이뤄진 set을 완성하세요
let intersectHeros = heros.intersect(oppHeros)

print(intersectHeros)
</code></pre>

>> ["프린스", "고블린 통"]

# Control Flow
- if문  
  if condition {}  
  else {}  
- for문  
  for i=0;i<count;i++ {}  
  for item in collection{}
- switch문  
switch value { case 1: case 2: default: }
  - case 5...10 //5에서 10 사이의 수

#### practice
> 그마트에서는 아이템 수량에 따라 계산 카운터를 안내하는 차세대 카트를 도입하려고 합니다. 카트에 담긴 맥주 수량에 따라
3병 이하는 소량 계산대로 보내고,
4병부터 50병까지는 일반 계산대로 보내고,
51병 부터 100병까지의 구매는 매니저에게 연락하고,
100병 이상은 경찰에 신고하는
switch문을 완성해 주세요.

<pre><code>typealias ShopingItem = (name:String, amount:Int)
let cart = ShopingItem("beer", 1)

switch cart {
case ("beer", 0...3) : //맥주 3병 이하
    print("Guide to small item counter")
case ("beer", 51...100) : //맥주 51병이상 100병 까지
    print("Call manager")
case ("beer", let amount) where amount>100 : //맥주 100병 초과
    print("Call police")
default: //나머지(맥주 4병 이상 50병 이하)
    print("Make wait in line")
}</code></pre>
>>Guide to small item counter

# Optional
- 실행 중에 nil이 될 수 있는 변수를 ? 로 관리하는 것
- nil : 값이 없는 상태
- 선언  
  var title : String = "Story"
  var ratings : [int]? = nil
  var subURL : String? = nil
  - nil인 값을 출력하려하면 에러가 난다.
- Optional변수 사용법
1. Force Unwrapping : !     -- 지양
  - 값의 존재를 확신할 때 사용
  - 출력시 optional() 이 없어진다.
2. Optional binding : if let, if var
  - optional이 아닌 새로운 상수와 변수 생성
  - if ratings != nill {}  
    if let theRatings = ratings {}
      - 값이 있는 경우에만 if만 작성
3. Implicitly Unwrapped Optional : 선언시 ! 사용
  - 구조적으로 초기화 이후 항상 값이 존재하는 경우를 위함
  - Optional이 아닌 척 함

#### practice
>아래는 애플와치와 쌍을 이룬 아이폰을 찾는 가상의 코드입니다.(실제 애플와치 앱에서 이런 코드를 사용하는 것은 아닙니다)
optional binding을 써서 빈 칸에 적당한 코드를 작성해주세요.

<pre><code>struct WatchDevice {
    var pairediPhone:String? //애플와치와 쌍을 이루는 아이폰의 이름.
    var appInstalled = false //어플리케이션의 설치 유무

    enum WatchSize {
        case m42, m38
    }
}

var appleWatch:WatchDevice? = nil
appleWatch = WatchDevice(pairediPhone: "링고스타의 아이폰", appInstalled: true)

// ①appleWatch에 대해 optional binding으로 watch라는 새로운 변수를 생성해주세요.
if var watch = appleWatch {
    // ②watch와 쌍을 이루는 아이폰의 이름에 대해
    // optional binding으로 phoneName이라는 새로운 변수를 생성해 주세요.
    if let phoneName = watch.pairediPhone {
        print ("AppleWatch가 \(phoneName)과 쌍을 이룹니다.")
    }
}
</code></pre>
>>AppleWatch가 링고스타의 아이폰과 쌍을 이룹니다.

>실습1에서 쓴 코드를 더 줄여 써 봅시다. 실습1과 동일한 결과가 나오도록 밑줄 친 구문을 완성해주세요.
실행 시 AppleWatch가 링고스타의 아이폰과 쌍을 이룹니다.라는 구문이 나오면 됩니다.

<pre><code>

???

</code></pre>
