# TIL
당일 배운 지식들을 정리하는 곳입니다
## 23.08.18
  - vue 수업
    - 뷰는 부모 템플릿과 자식템플릿은 단방향으로만 데이터를 보낼 수 있다.
    - 방향으로
## 23.08.17
  - 니꼴라스 백엔드 수업
    - aws s3 buket에 파일을 나눠서 업로드하려고 하였다. image, video.
      ```javascript
      const videoUpload = s3({
        bucket: "richdad6208/image" //이부분에서 오류가 발생했다.
      //갖가지 구글링 끝에 결국
        key: function (req, file, cb) { //cb 부분이 파일명으로 들어간다. 
      const fileName = Date.now() + file.originalname; //이부분은 랜덤한 숫자를 주기위함//
      const fullPath = `image/${fileName}`;
      cb(null, fullPath); 
      }
      }) //고생 끝에 해결한 오류라서 너무 기뻤다.
      ``` 
## 23.08.16 
  - 니꼴라스 백엔드 수업
    - aws s3 buket에 정상적으로 업데이트 완료하였다. heroku online 때 업로드는 aws s3 buket, 로컬 환경일때 업로드는 upload/파일로 분산시켰다.
    - 아직 comment 부분, 비디오 업로드 부분이 남았다. 비디오 업로드는 나중에 강의를 제작해서 홈페이지에 올릴 때 쓸만할 것 같다.
  + WORDFLEX
    - 환경변수 .env 파일의 변수가 참조가 안되었다. 알고보니 server.js 에서 import dotenv 선언의 위치가 참조하는 파일 import위치보다 낮아서그랬다.  dotenv 선언을 제일 위로 올려주면서 해결하였다.
    - 몽고DB 아틀라스에 연결을 완료하였다.
    - 회원가입 기능을 만들고, form method="POST"로 전송하려고 하는데, 자꾸 morgan 메세지에서 get이 떴다.
      app.use(express.urlencoded({extend:true}))의 위치를 조절하니까 정상작동 하였다.
  + 엘리스 수업
    - window.scrollTo()는 스크롤을 움직여줌
    - xxx.offsetTop => 선택된 영역에서 상단까지의 거리
    - 이미지 슬라이드를 노드 선택과 xxx.animation으로 하였다.
    - 고생했던 오류: xxx.style.transform = "scale(1);" <= 이부분 ; 위치 오류
    - node 선택시 firstChild가 아니라 firstElementChild이다. 
## 23.08.12
  - 니꼴라스 백엔드 수업
    - heroku 배포 db 몽고 atlas 연결완료 뿌듯하였다.
    - aws는 s3 buket을 만들고 iam을 만들고 id와 키를 받았어야 했는데 빼먹었다.
    - 서버가 돌아가면서 고치려고 하다보니 정신이 없었다. 고칠 때는 localhost로 고쳤다.
  - WORDFLEX (개인프로젝트)
    - kevin powell의 순서를 비슷하게 따라하고 있다. 먼저 html 짜고 css 변수설정 후, utility 만들고  
      general styling, 그 후 배치는 하지 않고 만들어 나간다. 구성요소들을 다 만들고 나서 .flow 유틸리티로
      간격 띄우고 그리고 나서 section마다 padding을 준다.
    - 넷플릭스가 디자인이 약간 심심하고 수월하다.
      
## 23.08.11
  - 니꼴라스 백엔드 수업
    - 서버배포에 대해서 배웠다. 배포는 heroku, db는 몽고, 서버는 aws.  heroku는 깃과 같은 명령어를 써서 쉬웠다.
    - heroku setting에서 .env 환경변수를 입력하는 것이 있는데 db 클러스터의 계정과 비밀번호가 착오가 있어서 해맸다.
    - 개발 기술은 한 언어를 정확하게 암기했을 때 늘어나는 것이 아니고  , 다양한 기술들을 그때 그때, 공식문서 등을 참조하며 적용해가며 는다는 것을 느꼈다. 
  - WORDFLEX (개인프로젝트)
    - 복습 겸 webpack을 이 프로젝트에 적용해보았다.
    - src/client 파일을 외부에 assets 파일로 빼낼 때, 사이즈를 압축해주는 플러그인이 있는데,   백엔드 수업에서는 잘 되었지만, 내가 해보니까 안되었다. 현재 asset/js/main.js는 압축이 되있지 않은 상태다.
    - 질문영역의 아코디언 메뉴 구현하였다. 옛날에도 했던 실수인데, list.forEach(item=> item.classList.remove("showing")을 해놓고 다시 item.classList.add("showing")을 한 것이다.  toggle 기능이라서,
      한번 켜진 버튼을 다시 누르면 꺼져야 하는데, 꺼졌다가 순간적으로 다시 켜지니 적용이 안되는 것처럼 느껴지는 것이다.  list.forEach((item,i=> if(i===index) item.classList.remove("showing")으로 해결하였다.
  - 엘리스 수업  
    - 오늘은 깃에 대한 수업을 들었는데, 내가 처음 독학할 당시에 들었으면 어땠을까라는 생각이 들정도로 퀄리티가 좋았다.  
    - 깃에는 작업공간의 개념이 있는데, 크게 3가지다. 워킹트리, 스테이지, 레퍼지토리.  
    - merge 충돌이 발생했을 때 git diff 를 누르면 충돌의 영역을 볼 수 있다.  
    - 브런치 구성은 크게 마스터, develope, topic이 있는데, 우측으로 갈수록 중요도가 떨어진다  
    - 이해가 안 가는 점: branch에서 수정을 하고 master를 merge한다음 다시 master로 가서 branch를 merge하라는 문제가 나왔는데  이해가 가지 않는다.
    - git clone을 하면 원격 저장소를 통채로 local로 가져오는거라서 git init이 필요없다.
    - pull은 가져오면서 merge도 실행, fetch는 merge는 안함. 그러면 어디로 가는지 궁금하다.
    - git reset --hard <커밋해쉬> 해당 커밋으로 HEAD를 맞춤
    
      
## 23.08.10
  - 니꼴라스 백엔드 수업  
    -웹팩으로 src 폴더의 client 폴더 내 js파일, css파일 외부로 추출.  
    -babel cli로 백엔드 자바스크립트 언어 호환성 증가.  webpack developement mode에서 build 모드로 전환  
      -여기서 development mode는 개발할 때 모드로 최신언어를 쓰면서 작업할 수 있게 해주고,  build 모드는 호환성을 늘리기 위해 구식버전으로 낮추고, 최대한 압축해준다.  
      -build mode로 파일들을 변환하고 서버를 작동시켜 보니 속도가 엄청 빨라서 기분이 좋았다.  이래서 속도와 사용자경험이 큰 상관관계가 있다는 것이 다시금 느껴졌다.  
    -webpack build 모드에서 src/client 폴더 내 css 파일이 외부의 assets 파일 속으로 들어가기는 하지만, 압축이 되지 않는다. 이런 저런 시도를 해봐도 되지 않는다.  

  - WORDFLEX (개인프로젝트)  
    - 주말에 html, css 코드리뷰를 할 수도 있어서, 우선은 클론코딩을 하기로 했다. 디자인을 만들어 놓고,  회원가입 기능, 로그인 기능 차례로 만들 생각이다.  
    - 아코디언을 바닐라 자바스크립트로 구현을 하는데, 어이없는 실수를 했다. 내 인터넷 창과 클론코딩 인터넷 창의 개발자도구 창을 착각을 해서 한참동안 해맸다.  
  
  - 엘리스 수업  
    - --webkit-과 같은 prefix는 css의 속성을 브라우저의 하위 버전에서도 사용하게 해준다. 최신버전에만 사용하고자 하면 없어도 된다  
    - transition, animation은 duration, delay 순서 지키기  
    - animation alternate: from -> to -> from  
    - @keyframes 에 prefix 달았다고 해서 그 속성에도 prefix가 붙는 것은 아니다.  
    - 반응형은 브라우저 창에 따라 자연스럽고 부드럽게 레이아웃이 조절되는 것이고,  적응형은 뚝뚝 끊기면서 레이아웃이 변화하는 것을 말한다.  
      - 나는 그동안 단순히 적응형이 레이아웃이 고정되있고 변하지 않는 것인 줄 알았는데 아니였다.  
    
## 23.08.09
  - 니꼴라스 백엔드 수업
    - 웹팩에 대해서 배움. 웹팩이란 css, js, scss 등등 각종 파일들을 압축하고 호환성을 좋게 최적화해준다.  node.js의 자바스크립트 언어를 버전 다운해서 호환성을 높이는 기능은 없어서,  따로 babel을 추가해야한다.
    - 어려웠던 점: webpack 첫 세팅을 할 때, js 파일압축이 잘 되었지만, babel을 webpack.config.js 파일에 적용해보니  오류가 발생했다.
  - WORDFLEX (개인프로젝트)
    - 회원가입 기능을 만들었다. 계정을 DB에 저장하는 것까지 빠르게 만들어서 기분이 좋았다.
    - 어려웠던 점: 깃허브 로그인을 만들려고 했는데, 깃허브 authorization 중 scope 옵션을 객체에 담아서  url로 바꾸려고 하는데, 버벅댔다.
    - 클론코딩 스터디 모임에서 이번 주 일요일에 코드리뷰를 할 수도 있다.  그래서 나의 저질 디자인보다 넷플릭스 디자인을 써야될 것 같다. 고민이다.
    - 클론코딩 할 때 pug 템플릿엔진은 태그가 일반 html 태그와는 생김새가 달라서  가독성이 떨어진다. 그래서 ejs 템플릿으로 교체했다. ejs 템플릿은 html과 형태가 똑같고,  <%- errorMessage -%> 이런식으로 변수를 넣을 수 있다.  하지만 기호들이 난무해서 어려운 것 같다. 하지만 pug는 템플릿 내에서 emmet을 쓸 수 없는데 반해,  ejs는 템플릿에서 emmet을 쓸 수 있다. 너무 좋다.
  - 엘리스 수업
    - 웹표준을 지키면 SEO에 좋다.
    - <!DOCTYPE html>은 단순히 html을 선언하는 것이 아니라, html5를 선언하는 것
    - meta charset="UTF-8"은 모든 문자를 표현해줌
    - 구역을 설정하는 section, article 등은 내부에 h2~h6가 반드시 있어야함.  스크린리더가 h1~h6을 목차구조로 인식해서 사용자에게 알려줌
    - display: inline은 상하 padding, margin 안먹음.
    - css internal style과 css external style은 명시도를 공유한다.  똑같은 명시도일때 internal이 앞서지만, external이 명시도가 높을 때 external이 앞선다.
    - class는 별명 느낌. id는 이름 느낌
    - 협업 시 타인이 만든 코드를 수정해야 할 때, 그 코드를 지우고 내 것을 적는 대신,  내 코드를 타인의 코드보다 우선순위를 높게해서 덮어쓰기해야,  타인의 코드를 유지하며 커스터마이징 할 수 있다.
    - 박스모델을 사람이라고 치면 사람 외부로 풍겨져 나오는 오오라를 margin,   사람의 피부는 border, 피부 밑 지방은 padding, 지방 밑 장기들은 content이다.
    - 마진병합: 서로 형제의 관계가 있는 박스들의 마진이 서로 겹칠 때, 큰 마진이 작은 마진을 잡아 먹는다.  부모와 자식관계에도 영향이 있는데, 자식에게 margin-top이 있으면, 마치 부모에게 margin-top이 적용된다.
    - float는 적용시킨 box를 공중에 붕 띄워 새로운 레이어층을 만든다.  float를 적용시키면 box들을 inline-block화 시킨다.
    - git branch로 각각 작업을 하다가 어느 시점에 main branch로 merge 시킨다. 
  
## 23.08.08
  - 니꼴라스 백엔드 수업
    - 드디어 User.findById(id).populate("videos")에서 왜 빈객체만 나오는지 알게되었다.  video를 생성할 때 user에게 video의 _id를 주어야 하는데 user의 _id를 주었기 때문에  인식을 못했던 것이다.
  - wordFlex (개인프로젝트)
    - 선생님의 조언대로 일단 실습부터 하라해서, 자바스크립트 이론공부는 당분간은 멈출계획이다.
    - 일단 디자인이 실력이 없는 것 같다. 참조할 만한 웹디자인을 찾아야 할 것 같다.
    - 현재 디자인, 프론트, 백을 번갈아가면서 하고 있는 중이다.
  - 엘리스 수업시작
    - req.body는 html 문서의 body 태그를 뜻한다.
    - 협업을 해야하는 중요한 이유 중 하나는, 혼자서 작업할 때는 보이지 않던 오류들을 볼 수 있다.
    - grid, flex는 라이브러리로 신속히 처리하고 나머지는 핵심기능에 집중하자
    - main, section 등 시멘틱 태그를 쓰면 좋은 이유는 클래스명 중복을 피하기 위해서  main .first, section .first와 같이 쓸 수 있다.
    - header는 검색엔진 seo에 필수적으로 써야하지만  main, section은 케바케 사바사이다.
    - 돈을 주는 클라이언트가 이해할 수 있는 코드를 짜라
    - css 속성의 기본속성값을 알아야 불필요한 코드를 없앨 수 있다.
    - transition의 연산비용이 많이 든다. 대신 @keyframes를 이용하면 좋다.

    
## 23.08.07
  - 니꼴라스 백엔드 수업
    - User.findById(id).populate("videos")를 했을 때 console.log로 찍어보면  빈객체가 뜬다. 원래 비디오목록이 떠야하는데, 왜 이러는지 모르겠다.
  - 엘리스 수업시작
    - 마스터하려고 하지마라. 정말 와닿는 말. 이론부터 공부하려는 사람은 이런 마인드를 가지고 있다.
    - 주변의 실무자들은 처음부터 작게 시작하고 점점 발전시켜나간다.
    - 실습을 주로하고 이론공부는 나중에 바짝하자
    - css 적용 우선순위는 inline style > head style > outside file style
      - css 라이브러리나 오픈소스를 쓸 때에 외부 css파일로 커스터마이징 못함, 인라인이나, head style로 커스터마이징해야함
    - 회사에서 지시사항, 요청사항이 내려올 때 반드시 한번 더 상사에게 물어보아라.
      - 혼자만의 방식대로 일처리하면 큰일난다.
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

