# Toast editor 적용 이슈

## 1. 번들링 문제
Npm으로 연결된 번들링이 많고 editor의 위치 확인의 어려움이 있다. webpack으로 모듈화에 추가로 필요한 모듈 및 동작이 npm으로 구동되어 yarn으로 구성된 작업중인 환경과 맞지 않다. 또한 번들링을 할 때에 규모가 큰 모듈을 번들링 하기가 어렵다.

## 2. Export와 template연결
Editor는 모듈을 받아온 후 template에 코드를 통해 동작하고 있는데 template는 기본적으로 html로 작성되는 방식이다. webpack을 통해 한 포트의 컴포넌트를 다른 포트로 보내주는 내용은 export default와 import를 통해 보내주고 있는데 export 부분은 자바스크립트로 되어있는 부분이기 때문에 기본적인 데이터와 동작 등은 보낼 수가 있지만 template에서 작성되는 요소는 포함되지 않는다. 현재 다른 페이지에서 가져와 페이지 내에 동작할 수 있게 하는 부분은 스크립트로 구현되고 있기 때문에 html으로 작성된 toast editor를 불러내기 어렵다.
