## iOS 커리어 스타터 캠프

### 숫자야구 프로젝트 저장소

- 이 저장소를 자신의 저장소로 fork하여 프로젝트를 진행합니다

![image](https://user-images.githubusercontent.com/98506825/163377965-584a5274-c412-4956-b04f-b4aed86ee62e.png)

# [STEP1]
🔥 전역변수

initialComputerInput ← 컴퓨터 숫자들 위한 중복 방지용 세트

verifiedComputerArray ← 세트를 인덱스로 접근해 비교하기 위한 배열 (컴퓨터)

verifiedUserArray ← 세트를 인덱스로 접근해 비교하기 위한 배열 (사용자)

remainingChance ← 사용자의 총 기회

strikeFlag ← 3 스트라이크를 판단하기 위한 플레그

🔥 함수

generateRandomNumbersForComputer() → 1부터 9사이의 임의의 숫자들을 컴퓨터의 배열에 넣어주는 함수.

generateRandomNumbersForUser() → 1부터 9사이의 임의의 숫자들을 사용자의 배열에 넣어주는 함수.

decide() → 스트라이크와 볼 카운트 및 출력 함수.

gameStart() → 메인 함수로서 게임을 시작하기 위한 함수.

🔥 고민 및 해결한 점 - 코드

1️⃣ 컴퓨터의 숫자들과 사용자의 숫자들을 무작위로 받을때 어떻게 중복을 해결할 수 있을까 고민하다가 Set 컬렉션 타입을 사용하고 각각의 Set 변수의 총 요소의 수가 정해놓은 일정 수준에 도달하게 되면 반복문을 종료하고 다시 각각 컴퓨터와 사용자의 배열에 강제 형변환으로 넣어 주었습니다.

2️⃣ “컴퓨터는 한번 값들을 받으면 게임이 끝날때 까지 고정이지만, 사용자는 매번 바뀌기 때문에 어떻게 처리를 해주어야 할까” 고민하다, 각각의 함수를 따로 만들기로 결론이 났고 그에 따라 사용자를 위한 Set변수를 매번 선언하는 방식으로 사용과 초기화를 동시에 해결 했습니다.

3️⃣ 게임이 시작되고 만약 스트라이크가 나오는 상황에서 어떻게 while문을 나올지 고민한 결과 Bool 타입의 변수를 전역변수로 선언과 함께 false로 초기화 해주고 스트라이크인 경우, Bool 타입 변수를 true로 바꿔줬습니다. 이에따라 스트라이크 및 볼을 결정 및 출력하는 함수 decide()에서 나오자마자 Bool 타입 변수의 값에 따라 반복문을 빠져 나오도록 했습니다.

4️⃣ decide() → 스트라이크 및 볼 판단 함수에서 어떻게 하면 효율적으로 볼과 스트라이크를 판단할 수 있을까 고민하던중, 먼저 스트라이크를 세는 변수와 볼을 세는 변수를 각각 만들어 주었습니다. 반복문을 돌면서 각각의 배열의 동일한 인덱스에 접근하여, 만약 두 값이 같다면 스트라이크를 하나 추가하고, 그게 아니라면 컴퓨터의 배열 내 인덱스로 접근한 값이 사용자의 배열에 포함이 된다면 볼 카운트를 하나씩 올려주는 방식으로 해결 했습니다.

5️⃣ 3 스트라이크로 게임이 끝나는 경우를 decide()내에서 어떻게 처리할까 고민했습니다. 먼저 함수 내 반복문이 끝나면 스트라이크 카운트 값이 3과 같다면 지정 문자열과 사용자 승리 문구를 함께 출력하고, 만약 3과 같지 않다면 해당 스트라이크와 볼로 출력했습니다.

6️⃣ 게임을 시작하는 함수 startGame()에서 사용자의 숫자를 한칸씩 띄워 출력하는 부분을 고민했습니다. 고민한 결과, 먼저 String 타입의 변수를 하나 생성해주고 배열의 요소와 빈칸을 함께 변수에 추가해주는 형식으로 했습니다. 이 결과 마지막에 한칸의 공백이 생기는 부분은 String 타입의 내장함수 removeLast()로 해결 해주고 변수를 그대로 출력하는 방법으로 문제를 해결 했습니다.

🔥 코드 이외의 궁금한 점

1️⃣ 서로가 페어 프로그래밍이 처음이고 어떻게 해야 더 효율적으로 공부하고 도움을 줄 수있는지 궁금했습니다. 처음부터 이리저리 부딪히면서 배우는 것도 좋지만 저희 둘 다 좋은 습관을 가지고 시작하고 싶은 마음입니다. 이런 부분에 도움을 많이 주셨으면 좋겠습니다!

2️⃣ 상대방이 코드를 작성할 동안 다른 상대방이 해당 파일에 다른것을 작성한 상태로 pull을 했더니 정상적으로 pull을 받을 수 없던 경우가 2번정도 있었습니다. 이에 대해 저희끼리 먼저 찾아본 결과 정확히 어떤 이유에서 그런 상황이 발생하는지 알 수 없었고 이에 대해서 자세하게 알려주시면 감사하겠습니다.

# [STEP2]
🔥 특이사항
어제밤 회의실에서 말씀해 주신 함수명, 변수명, 매개변수명 수정 했습니다.

1️⃣ startMenu() -> void
Repeat- while문을 사용하여 게임종료가 나오기 전까지 계속 “게임시작, 게임종료” 문구가 나오도록 구현하였습니다.

2️⃣ menu함수 -> Int 반환
사용자의 입력 받은후 if let으로 받은후 그 값에 따라 지정된 숫자를 리턴하는 함수를 구현 했습니다.

3️⃣ checkUserInput 함수는 사용자로부터 입력받은 배열을 검사하는 함수입니다.

총 3가지의 검사 항목이 있는데, 숫자가 아닌 문자인지 검사하고, 숫자라면 1~9사이의 숫자인지 검사,
그리고 세트에 넣어 중복값이 있는지 검사했습니다. 그리고 이 모든 검사를 통과하면 true, 아니면 false를 출력해 사용자에게 알려주는 방식으로 구현했습니다.

4️⃣ checkUserInputRange 함수는 해당숫자가 1부터 9사이의 숫자인지 확인하는 함수입니다.

🔥 고민한점 & 해결한점
1️⃣ checkUserInputRange 호출 후 리턴값이 저희가 예상했던 결과가 아니였고 이에따라 프로그램이 정상적으로 동작하지 않아 반환 받은 직후 다시 검사하는 방법으로 해결했습니다.

2️⃣ makeUserRandomNumbers() 함수에서 많은 시간을 보냈는데, “if let과 guard let 중 어떤 바인딩 이 상수를 바인딩 밖에서 사용할 수 있게 해줄까”라는 문제로 많은 시간을 보내고 guard let을 사용해 문제를 원하는 대로 잘 해결했습니다.

3️⃣ makeUserRandomNumbers() 함수는 실제로 사용자로부터 입력을 받는 함수입니다.

사용자로 부터 입력값을 “ “로 나누어 받고 guard let을 사용해 옵셔널 바인딩을 해주었습니다.

만약 사용자로부터의 입력값이 유효하지 않은 경우 재귀함수를 이용해 다시 받도록 하였습니다.
