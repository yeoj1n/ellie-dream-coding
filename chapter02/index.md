## html 내 javascript를 넣는 방법
1) head 안에 script 를 넣는 방법
    - HTML 파싱 도중 JS 를 만나면 import 시작
    단점 : JS fetching 시간이 오래걸릴 수 있음.
2) body 안에 script 를 넣는 방법 
    - html 을 먼저 볼 수 있음
    - js 에 의존적인 경우 fetcing & execute 과정 기다려야함
3) head + async
async : boolean 값이므로 선언하는 것만으로도 true
<script async src="main.js"></script>
    - 장점 : JS import 가 병렬적으로 작동하기 때문에 fetching 시간이 줄어든다.
    - 단점 : DOM 요소 조작에 시점 문제가 있을 수 있다, 중간중간 html을 parsing 하기 때문에 화면을 한번에 보지 못할 수 있다.
4) head + defer
<script defer src="main.js"></script>
    - 모든 DOM 요소를 읽어온 후 JS 를 읽어온다.

### async vs defer
async : 다수의 js 파일을 import 하는 경우 async의 경우 먼저 읽은 순서대로 실행하기 때문에 순차적으로 이루어지지 않을 수 있다.
defer: DOM을 먼저 읽고 다음 순차적으로 선언된 js 파일도 읽어오기 때문에 순차적이고 안정적이다.

### use strict
- 파일 최상단에 `use strict` 를 선언하고 strict 모드로 사용하는 경우 문법 에러를 잡아준다. 또한 자바스크립트 엔진이 빠르게 동작하기 때문에 성능면에서도 효율적이다.