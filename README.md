# TIL
당일 배운 지식들을 정리하는 곳입니다
## 23.08.07
  - 엘리스 수업시작
    1) 마스터하려고 하지마라. 정말 와닿는 말. 이론부터 공부하려는 사람은 이런 마인드를 가지고 있다.
    2) 주변의 실무자들은 처음부터 작게 시작하고 점점 발전시켜나간다.
    3) 실습을 주로하고 이론공부는 나중에 바짝하자
    4) css 적용 우선순위는 inline style > head style > outside file style
       ㄱ. 그래서
## 23.07.30
  - 자바스크립트 딥다이브 독서
    1) 2회독 째, 점점 읽는 속도가 빨라지고 이해가 잘 가지 않던 프로토타입 (객체의 부모 역할을 하는 객체)에 대해서도  조금씩 이해가 가고있다.
    2) 자바스크립트는 프로토타입의 기반의 객체지향형 프로그래밍
    3) 생성자 함수는 아직 눈에 익지 않는다. 프로젝트를 하면서 많이 만들어봐야겠다.
    4) 자바스크립트는 객체, 함수가 가장 중요한 것 같다. 아 부분을 중점적으로 공부하자.
## 23.07.29
  - 자바스크립트 딥다이브 독서
    1) 목표 자바스크립트 딥다이브 '빠르게' 4번 읽기 중 1번 읽기 완료
    2) 이해가 가지 않는 부분이 많았다. event, dom에서 배워야 할 것이 많구나라는 것을 느꼈다.
    3) array 고차함수와 정규식 등 알고리즘 할 때 막혔던 부분들을 알게 되었다.
    4) 엘리스 트랙이 시작하기 전까지는 자바스크립트 '빠르게' 4번 읽고 1번 제대로 정독을 끝내야 한다.

## 23.07.27
  - 자바스크립트 딥다이브 독서
    1) 1~13강(스코프)까지 1독, 기존에 20강까지 약 2독 정도 하다보니, 13강까지는 무난하게 이해함.
    2) 어려웠던 점: 렉시컬 환경에 대해서 아직 감이 안온다.
    3) 깨달았던 점
       (1) 자바스크립트 딥다이브 이론을 알고리즘 풀이와 병행하면 시너지가 있는 것 같다.
       (2) 알고리즘 풀다가, 배열을 복사해서 활용하는 문제가 있었다. 배열은 원시값이 아닌, 객체대이터로써 변경이 가능하다.
           그리고 배열은 값이 있는 메모리를 참조하는게 아니고, 배열이 있는 위치를 참조하는 것이다. 그러므로
           let array1 = [1,2,3,4];
           let array2 = array1; 이라고 할 때, array2를 [1,2]로 할당했을 때, array1도 [1,2]가 된다.  그래서 곤란에 빠졌다.
           딥다이브에서, 이럴 때 할 수 있는 방법은 깊은 복사라고 했다. npm i lodash로 var _ = require("lodash");
           let array2 = _.cloneDeep(array1) 하면 된다고 했는데 안되더라...
           알고리즘을 많이 풀면 풀수록, 이론공부와 연결이 되는 것 같아서 기분이 좋다.

## 23.07.26
  - backend
    1) video.owner 의 정보와 res.locals.user._id 의 정보 일치여부 확인 후 delete, edit 버튼 작업.
    2) 어려웠던 점: pug template에서 video를 mixin 하여 사용하고 있었는데,  여러 페이지에서 mixin video를 불러오다보니 점점 뒤죽박죽이 되고 있다.
                   단순한 작업은 mixin video를 불러오지 않고 그냥 그 페이지 내에서 작업을 해야겠다.
                   
   

## 23.07.25
  - backend
    1) user profile photo upload, video upload, Video model에 owner 속성 추가 
    2) 어려웠던 점: 갑자기 mongodb에 video가 upload 되지 않았다. 무엇이 문제일까.  pug의 upload 페이지의 form 속성들을 지우고 해보니 작동이 되었다.
                   이해할 수가 없다.

## 23.07.24 
  - 알고리즘
    1) 프로그래머스 lv.0 문제 약 2pages 품. 어렵지는 않았지만, 비효율적으로 풀고 있다는 느낌이 든다.

## 23.07.22
  - backend
    1) multer middleware로 user profile photo upload
    2) 어려웠던 점: req.file.path을 받아와서 avatarUrl에 담은 뒤, 어디다가 집어넣어야 할지 몰랐다. 답: User.findByIdUpdate({}) 안에 집어넣음
    3) 깨달은 점: 당일 진도를 git commit을 하여, 강의 도중 실습할 때 git reset --hard로 되돌려가며 연습하자

## 23.07.21
- backend
  1) multer middleware, form 데이터 받기
  2) bcrypt.compare를 통한 비밀번호 일치여부 확인 후 db, session에 new password 전송 <br>
  3) 어려웠던 점: multer middleware 작성할 때 오류발생
- 알고리즘
  1) 매게변수 등비수열, 등차수열 마지막 수 리턴함수 만들기
  2) 해결: if문은 표현식이 아니라 결과값을 뺄 수 없어, 삼항연산자를 써서 값을 도출했다
- 클론코딩
  1) flex을 활용한 레이아웃
  2) 개발자 도구 중 마우스커서를 활용한 오류탐색 (z-index)
  3) 어려웠던 점: fullpage.js를 사용할 때 section의 크기를 100vh를 주었음에도 불구하고 100vh가 넘어가는 현상이 발생함. 이유를 찾아봐야하겠음

