# 1. 개요

```
웹 기술을 사실 굉장히 단순하다. 서버 또는 클라이언트에 hmtl, javascript, css를 브라우저가 해석 할 수 있도록 정의하고 사용자가 공개된 주소(도메인)을 통해 접근하면 의도한 페이지를 볼 수 있다. 이게 전부이다.

하지만 우리는 보다 나은 발전된 기술을 통해 사용자에게 서비스를 제공하기 위해 현대에서는 프로그래밍 환경, 기술들이 고도화 되면서 특정 목적에 의해 기술들이 정의되고 있고, 파생에 파생을 이어가고 있다.
특정 목적은 개발의 생산성, 타 플랫폼과의 연동, 임베디드 기기와의 통신, AI, 빅데이터, 그 외 특정 엔지니어링들이 있을 수 있다.

빠르게 발전하는 웹기술에서 우리는 적절한 기술들을 선택하고 학습하며 익술해지는 과정에서 원활히 소통하는 방법을 훈련 하도록 하자.

우리는 서로 무수한 관점에서 서로에게 질문을 던지고 답하며 서로 다르게 정의 될 수 있는 기술들을 준수히 공통화 될 수 있고 나아가 분업된 협업에서 원환한 소통을 통해 보다 나은 결과물을 낼 수 있을 것이라 기대한다.
```

# 순서

```
1장. 웹의 구성요소들에 대해 정의하고 개념을 확립하자.
2장. Node를 알아보자.
3장. ...
```

# 웹의 구성 요소

> 웹의 구성 요소를 키워드로 정리 해보자.

- Web Client(Web browser)

  - 웹 서버에 접속해 HTML/CSS/JS 를 해석하여 웹페이지를 렌더링해 주는 소프트웨어
  - 태일 : 사용자가 웹페이지를 조회하고 상호작용할 수 있게 함
  - 준영 : 원하는 서비스를 서버측에 요청하는 장소
  - 다연 : 사용자가 브라우저를 통해 서버에게 요청한 역할 수행
  - 종류
    - edge
    - safari
    - chrome
    - firefox
    - other browser...

---

- Web server

  - 클라이언트에서 요청을 받아 응답을 보내는 컴퓨터 시스템/소프트웨어
  - 클라이언트 요청에 따라 웹페이지, 이미지, 파일, 데이터베이스 제공
  - HTTP 프로토콜을 이용하여 클라이언트의 요청을 서버에 전달
  - 종류
    - apache
    - tomcat
    - node

---

- Http, Https

  - HyperText Transfer Protocol
  - 클라이언트와 서버 간 데이터 전송을 위한 표준 프로토콜
  - HTTPS - 보안 강화
  - port : 80, 443

---

- API
  - Application Programming Interface
  - 프로그램들이 서로 상호작용하는 것을 도와주는 매개체
  - 서버와 데이터베이스에 대한 출입구 역할
  - soap
    - xml
  - rest
    - json

---

- Web Application

  - 개발을 위한 라이브러리
  - html

    - responsive design (반응형)
    - | adaptive design (적응형) |                                                             | 반응형                                          | 적응형 |
      | ------------------------ | ----------------------------------------------------------- | ----------------------------------------------- | ------ |
      | 기기/화면 감지           | 미디어 쿼리로 기기 감지                                     | 서버 또는 브라우저에서 기기 감지                |        |
      | 템플릿                   | 하나의 템플릿                                               | 기기마다 다른 템플릿 필요                       |        |
      | 콘텐츠                   | 모든 콘텐츠 다운로드                                        | 기기별 콘텐츠만 다운로드                        |        |
      | 장점                     | 일관성있는 uiux 제공, 다양한 기기 대응                      | 적은 데이터 낭비, 빠른 로딩 속도                |        |
      | 단점                     | 디자인-개발-테스트 시 드는 많은 시간과 비용, 느린 로딩 속소 | 기기별 별도 유지보수 요구, 일관되지 않은 데이터 |        |

  - javascript

    - es6
    - framework
      - react
      - vue
      - angular
      - angularJS
    - typescript

  - css

    - sass
    - scss

  - SPA
  - Rendering

    - SSR
    - CSR

  - database - DBMS - O-DBMS -
    ** 추가 **

- 쿠키, 세션

  - 클라이언트와 서버 간 상태 유지
  - 사용자 정보 저장

- 웹 호스팅 및 클라우드 서비스

  - 종류
    - AWS, Google Cloud

- 웹 보안

  - 종류
    - SSL/TLS, CORS, CSP

- 웹 소켓

  - 실시간 양방향 통신 프로토콜
  - 채팅..

---

> Q. 웹서버의 역할을 서술 해보자.

```
A.
1. 웹 페이지 전송 (브라우저 요청을 받은 후 웹페이지를 클라이언트에게 전송함)
2. 파일 제공(이미지, 동영상, 음악 등의 파일 제공)
3. 웹 애플리케이션 실행
웹 서버가 없으면 웹 페이지와 웹 애플리케이션을 사용할 수 없다.
1. 프로토콜 처리
2. HTTP를 사용해 클라이언트와 통신
```

---

> Q. API는 무엇이고 왜 구성되게 되었을까 서술해보자.

```
A.
1. 응용 프로그램의 기능을 재사용함으로써 개발에 소요되는 시간, 비용 절감
2. 새로 개발할 필요없이 이미 만들어진 API를 사용함으로써 유연성, 확장성 향상
3. 보안 강화 목적
```

---

> Q. 웹서버의 역할과 웹클라이언트의 역할을 구분하고, 각 위치에는 어떤 것들이 구성 될 수 있는지 알아보자.

```
A. 웹 서버는 웹 페이지를 제공하는 역할을 하며, 웹 클라이언트는 웹 페이지를 웹 서버로부터 받아 볼 수 있게 해주는 역할을 한다.

#### A. 구성 요소
#### server : server-side programing language(php, java, c# ...), html, css, javascript

#### client : html, css, javascript
```

![1701259660522](image/abucus-tutoring/1701259660522.png)

#### ※ html, css, javascript는 서버에도 있을 수 있고 클라이언트에도 있을 수 있다. 이유는 무엇이고 차이점은 무엇인가?

```
서버에 있는 HTML, CSS, JS 는 이를 통해 웹 페이지를 생성하며, 클라이언트에 있는 HTML, CSS, JS 는 생성된 웹 페이지를 화면에 표시한다.
```

---

> Q. 자바스크립트 규격은 ECMA Script는 es6 버전부터 페러다임적 변화가 있었다. es6 전과 후의 버전은 무엇이 달라졌는지 서술해보자.

```
A.
1. 직관적인 문법으로 개선 (화살표 함수 등)
2. 컴파일러 및 배열 처리의 최적화
3. 템플릿 리터럴 (문자열과 변수 결합 표현)
4. const, let
https://velog.io/@kim_unknown_/JavaScript-ES6
```

---

> Q. 웹의 랜더링 방식은 크게 SSR과 CSR로 구분된다. 각 랜더링 방식에 대해 특징을 이해하고 서술해보자.

```
A.
SSR = 서버 사이드 렌더링. 서버에서 웹 페이지 생성 후 클라이언트에 전송. MPA에서 사용되는 방식. 완성된 HTML을 서버가 사용자 요청 시마다 즉시 만들어 보여줌.
초기 로딩 속도가 빠르고, 페이지 이동 속도가 느림. SEO에 유리하지만, 동적인 웹 페이지를 구현하기 어렵고, 리소스 사용량이 많음.
ttv와 ttl의 간극이 있음

CSR = 클라이언트 사이드 렌더링. 클라이언트에서 웹 페이지 생성. SPA에서 사용되는 방식. 자바스크립트를 이용해 사용자의 화면에서 HTML을 렌더링하여 보여줌.
동적인 웹 페이지를 구현하기 쉽고, 리소스 사용량이 적지만, 초기 로딩 속도가 느리고, SEO에 불리. 페이지 이동 속도는 빠름.
ttv와 tti의 간극이 없음

* ttv : time to view 사용자가 보는 시점
* tti : time to interact 사용자가 인터랙션 하는 시점

```

---

> Q. SPA란 무엇이고 어떤 특징을 가지고 있고 어떤 역할을 하는지 서술해보자.

```
A.
Single Page Application
단일 페이지로 구성된 웹 어플리케이션.
즉 하나의 HTML에서 페이지가 그려지는 것. 사용자의 요청에 따라 특정 부분만 갈아끼워 보여주는 형태

역할 : UX 향상 및 성능 개선, 효율적인 개발 및 유지보수(새로고침이 필요없어 페이지 상태 추적, 유지 관련 코드도 줄어듬)
```

---

> Q. 오랜 해 동안 데이타 베이스는 R-DBMS만이 사용 되어 왔다. 현재에 이르러서는 객체지향 개발론, 데이터 구조론의 고도화됨에 따라 R-DBMS는 프로그래밍 언어와의 구조적 이질감에 효율적 사용에 많이 논의 되어 왔다. R-DBMS가 프로그래밍 언어들과 어떤 구조적 차이가 있는지 서술 해보자.

```
A.
```

---

> Q. 현대에 R-DBMS를 대체할 O-DBMS는 무엇이고 어떤 구조를 가지고 있는지 서술 해보자.

```
A.
```

---

# NodeJS의 이해

- Reference

1. [NodeJS 소개](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs "NodeJS 소개")
2. [Node.js를 설치하는 방법](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs "Node.js를 설치하는 방법")
3. [Node.js를 사용하려면 얼마나 많은 JavaScript를 알아야 합니까?](https://nodejs.org/en/learn/getting-started/how-much-javascript-do-you-need-to-know-to-use-nodejs "Node.js를 사용하려면 얼마나 많은 JavaScript를 알아야 합니까?")
4. [ECMAScript 2015(ES6)](https://nodejs.org/en/learn/getting-started/ecmascript-2015-es6-and-beyond "ECMAScript 2015(ES6)")
5. [NPM 패키지 관리자 소개](https://nodejs.org/en/learn/getting-started/an-introduction-to-the-npm-package-manager "NPM 패키지 관리자 소개")
6. [Node.js, 개발과 프로덕션의 차이점](https://nodejs.org/en/learn/getting-started/nodejs-the-difference-between-development-and-production "Node.js, 개발과 프로덕션의 차이점")
7. [TypeScript를 사용한 Node.js](https://nodejs.org/en/learn/getting-started/nodejs-with-typescript "TypeScript를 사용한 Node.js")
8. [Node.js에서 환경 변수를 읽는 방법](https://nodejs.org/en/learn/command-line/how-to-read-environment-variables-from-nodejs "Node.js에서 환경 변수를 읽는 방법")

- NODE 환경에서 NPM(Node package manager) 저장소에 있는 모듈이 개발환경(local)에 저장되는 과정
  `<img src="./img/node_npm_registry_flow.PNG" width="100%" title="node_npm_registry_flow" alt="node_npm_registry_flow"/>`
- Javascript framework rank - 2023
  `<img src="./img/javascript_framework_rank_2023.png" width="100%" title="javascript_framework_rank_2023" alt="javascript_framework_rank_2023"/>`
