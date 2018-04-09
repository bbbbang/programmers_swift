# let과 var
•	let : 상수 선언 (값 변경 불가)
•	var : 변수 선언 (값 변경 가능)
•	let 사용 권장

practice

“`
판교역 도착 방송을 위해 작성한 코드에서 문제가 생겼습니다. 어디가 문제인지 알아내, 방송이 무사히 전달될 수 있도록 코드를 수정해주세요.

var announcement:String = ""
let intro = "다음 역은 "
let outro = "입니다."

var station = "판교역"

announcement = intro + station + outro
print(announcement)

->다음 역은 판교역입니다.
