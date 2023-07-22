# TIL
당일 배운 지식들을 정리하는 곳입니다.
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
## 23.07.22
  - backend
    1) multer middleware로 user profile photo upload
    2) 어려웠던 점: req.file.path을 받아와서 avatarUrl에 담은 뒤, 어디다가 집어넣어야 할지 몰랐다. 답: User.findByIdUpdate({}) 안에 집어넣음
    3) 깨달은 점: 당일 진도를 git commit을 하여, 강의 도중 실습할 때 git reset --hard로 되돌려가며 연습하자
