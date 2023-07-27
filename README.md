# TIL
당일 배운 지식들을 정리하는 곳입니다
## 23.07.27
  - 자바스크립트 딥다이브 독서
    1) 1~13강(스코프)까지 1독, 기존에 20강까지 약 2독 정도 하다보니, 13강까지는 무난하게 이해함.
    2) 어려웠던 점: 렉시컬 환경에 대해서 아직 감이 안온다.
    3) 깨달았던 점
       (1) 자바스크립트 딥다이브 이론을 알고리즘 풀이와 병행하면 시너지가 있는 것 같다.
       (2) 알고리즘 풀다가, 배열을 복사해서 활용하는 문제가 있었다. 배열은 원시값이 아닌, 객체대이터로써 변경이 가능하다.
           그리고 배열은 값이 있는 메모리를 참조하는게 아니고, 배열이 있는 위치를 참조하는 것이다. 그러므로
           let array1 = [1,2,3,4];
           let array2 = array1; 이라고 할 때, array2를 [1,2]로 할당했을 때, array1도 [1,2]가 된다. 그래서 곤란에 빠졌다.
           딥다이브에서, 이럴 때 할 수 있는 방법은 깊은 복사라고 했다. npm i lodash로 var _ = require("lodash");
           let array2 = _.cloneDeep(array1) 하면 된다고 했는데 안되더라...
           알고리즘을 많이 풀면 풀수록, 이론공부와 연결이 되는 것 같아서 기분이 좋다.

## 23.07.26
  - backend
    1) video.owner 의 정보와 res.locals.user._id 의 정보 일치여부 확인 후 delete, edit 버튼 작업.
    2) 어려웠던 점: pug template에서 video를 mixin 하여 사용하고 있었는데, 여러 페이지에서 mixin video를 불러오다보니 점점 뒤죽박죽이 되고 있다.
                   단순한 작업은 mixin video를 불러오지 않고 그냥 그 페이지 내에서 작업을 해야겠다.
                   
   

## 23.07.25
  - backend
    1) user profile photo upload, video upload, Video model에 owner 속성 추가 
    2) 어려웠던 점: 갑자기 mongodb에 video가 upload 되지 않았다. 무엇이 문제일까. pug의 upload 페이지의 form 속성들을 지우고 해보니 작동이 되었다.
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

