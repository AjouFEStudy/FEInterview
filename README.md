# FEInterview
Learn FE Concept and prepare Interview

## 🍖 JavaScript
1. [프로미스](https://velog.io/@dbstjrwnekd/Promise)에 대해 설명해주세요.
> Promise는 자바스크립트의 비동기 처리 상태와 처리 결과를 관리하는 객체입니다. 일반적으로 자바스크립트의 비동기 처리는 콜백 함수를 이용한 콜백 패턴을 활용하는데요. 이러한 방식은 중첩될 경우 콜백헬 이라는 현상이 발생해 가독성이 떨어지게 됩니다. 또 이런 패턴은 에러처리가 어렵기에 각각의 콜백함수에 전부 에러처리를 해줘야 하는 문제점이 발생합니다.

> 이러한 문제를 해결하기 위해 등장한 것이 프로미스 입니다. 프로미스는 pending, fulfilled, rejected의 3가지 상태를 가지고 있으며 .then, .catch 등의 후속 처리 함수를 제공합니다. 상태는 각각 비동기 처리 결과를 기다리는 상태(pending), 비동기 처리가 완료된 상태(fulfilled), 비동기 처리가 실패한 상태(rejected)입니다. 매개 변수로 받는 resolve, reject함수를 통해 pending -> settled(fulfilled | rejected)상태로 변화할 수 있으며 변화된 이후로는 상태를 변화할 수 없습니다. 프로미스의 .then, .catch, .finally 등의 후속 처리 메서드는 암묵적으로 프로미스를 반환하여 체이닝이 가능합니다. 프로미스 체이닝을 통해 콜백헬 문제를 해결할 수 있으며, 후속 처리 메서드 .catch를 통해 에러 처리가 유용해집니다.

> async, await키워드와 함께 사용하면 후속 처리 메서드를 사용하지 않고 동기적인 코드처럼 작성이 가능하다는 장점도 있습니다.

> 또한 프로미스는 Promise.prototype.all, Promise.prototype.allSettled, Promise.prototype.race 등의 함수를 제공하여 비동기 처리를 병렬적으로 수행할 수 있도록 도와줍니다.
> 위 함수들은 프로미스를 요소로 갖는 배열 등의 이터러블을 원소로 받습니다.
> Promise.all은 전달받은 모든 프로미스가 fulfilled 상태가 되면 결과를 배열에 저장해 새로운 프로미스를 반환합니다. 이때 중간에 rejected가 발생하면 다른 처리를 기다리지 않고 즉시 종료합니다.
> Promise.allSettled는 fulfilled, rejected와 상관 없이 모든 프로미스가 settled상태가 되면 결과를 배열에 저장해 새로운 프로미스를 반환합니다.
> Promise.race는 가장 먼저 fulfilled 상태가 된 프로미스의 처리 결과를 배열로 반환합니다. all과 마찬가지로 에러를 reject하는 새로운 프로미스를 즉시 반환합니다.

2. [Ajax와 JSON](https://velog.io/@dbstjrwnekd/Ajax%EC%99%80-JSON)이란?
> Ajax는 자바스크립트를 이용해 브라우저에서 필요한 데이터만을 비동기 방식으로 서버에 요청하는 기술을 말합니다. Ajax가 등장하기 이전에는 웹 페이지가 전환되기 위해 서버로부터 전체 HTML을 받아와 새로 렌더링해야 했습니다. 따라서 불필요한 데이터 통신이 발생하였고 화면 깜빡임 같은 현상이 존재했습니다.
> Ajax는 2005년 구글 맵스 이후로 주목받기 시작했습니다. Ajax의 기술을 이용해 필요한 데이터만 서버에 요청하고 전체가 아닌 변화가 있는 부분만 부분적으로 렌더링 하는 방식을 통해 높은 퍼포먼스와 부드러운 화면 전환이 가능해졌습니다. Ajax의 등장 이후 프론트엔드 진영에 큰 변화가 일어나기 시작했습니다.
> Ajax를 이용하면 불필요한 데이터 통신이 줄어들고, 변경이 필요한 부분만 렌더링하여 깜빡이 현상이 없어집니다. 또한 비동기 방식으로 동작하기에 서버에게 요청을 보낸 이후 블로킹 현상이 발생하지 않습니다.
> Ajax의 단점은 추적이 어렵다는 점과 사용자 이벤트 등으로 계속해서 요청을 보낼 경우 서버에 무리가 갈 수 있다는 점입니다.

> JSON은 언어 독립형 데이터 포멧으로 HTTP 통신을 위한 텍스트 데이터 포멧입니다. 자바스크립트 객체 리터럴과 유사하게 키와 값으로 구성된 순수한 텍스트며 대부분의 프로그래밍 언어에서 사용할 수 있습니다.
> 자바스크립트는 JSON.stringify, JSON.parse 메서드를 통해 직렬화와 역직렬화를 제공합니다.
## 🍔 React
1. [useEffect](https://velog.io/@dbstjrwnekd/Using-the-Effect-Hook)가 어떻게 동작하나요?
> useEffect는 부수효과와 clean-up phase를 담당하는 hook api입니다. 기본적으로 mount/update를 구별하지 않고 매 랜더링시 실행되는 구조를 갖고 있습니다. 이러한 구조는 update 로직의 구현에서 발생할 수 있는 에러를 방지할 수 있도록 도와줍니다. useEffect의 첫 번째 인자로 함수를 넘겨주면, 리액트는 DOM 업데이트 이후 해당 함수(부수효과)를 호출합니다. 또한 해당 함수에서 특정 함수를 return 하면 리액트는 다음 효과 적용 전 리턴되는 함수를 이용해 clean-up phase를 진행합니다. 이러한 구조로 리액트는 데이터 일관성을 보장하며 버그를 방지할 수 있습니다.
> 또한 useEffect의 두 번째 인자로 관련된 변수를 배열로 넣을 수 있습니다. 두 번째 인자로 들어오는 배열에 포함된 변수가 변할때만 부수효과/clean-up phase를 동작하도록 하여 최적화를 진행합니다. 만약 첫 마운트와 unmount시에만 필요한 효과와 clean-up이 있다면 빈 배열을 넘김으로써 구현할 수 있습니다.
> useEffect는 기존 lifecycle methods와 달리 중복된 코드를 방지하고, 연관된 효과들을 코드상 가까이 유지할 수 있도록 도와줍니다. 또한 여러 번의 사용을 통해 연관된 효과들끼리 코드를 나눌 수 있도록 도와줍니다.
> 코드 중복 방지, 일관성 유지, 버그 예방, 역할에 따른 코드 spliting 등의 장점을 갖고 있습니다.

## 🍷 Network
1. [REST API](https://velog.io/@dbstjrwnekd/Rest-API)는 무엇인가요?
> REST API는 2000년 로이 필딩의 논문에서 처음 등장한 개념입니다. HTTP를 기반으로 클라이언트가 서버에 접근하는 방식에 대해 규정하는 아키텍쳐입니다. REST에는 크게 2가지 핵심 원칙이 있습니다.
> * URI는 리소스를 표현해야 한다.
> * 행위는 HTTP 메서드를 사용해 표현해야한다.
> 
> REST API는 자체 표현 구조를 통해 API만으로 HTTP 요청의 의미를 이해할 수 있습니다. 또한 이러한 원칙을 지키기 위해 "URI는 동사가 아닌 명사로 표현한다", "행위는 HTTP 메서드로 표현한다." 등의 세부적인 규칙들을 갖고 있습니다.
>
> 즉 REST 란 HTTP기반의 클라이언트-서버 통신을 규정한 아키텍처이고, REST에 입각하여 설계된 API가 REST API입니다.

2. [WebSocket](https://velog.io/@dbstjrwnekd/Websocket%EA%B3%BC-socket.io)은 무엇인가요? ws프로토콜을 들어보았나요?
> WebSocket은 HTML5 표준 기술로 클라이언트와 서버간 connection을 유지하며 양방향 소통을 가능하게 해주는 기술입니다. ws프로토콜을 사용하며 HTTP를 이용한 handshake를 통해 연결이 이루어집니다.
> Handshaking과정은 다음과 같습니다.
> 먼저 http request 메시지를 작성합니다. 이때 Upgrade헤더는 websocket을, Connection 헤더에는 Upgrade를 명시하여 프로토콜을 웹소켓으로 변경할 것을 요청합니다. 또한 서로의 신원을 인증하기 위해 Sec-WebSocket-Key 헤더를 포함합니다. 이후 서버에서는 101 switching protocol 응답을 통해 웹소켓 연결을 허용합니다. 마찬가지로 Upgrade: websocket, Connection: Upgrade 헤더를 포함합니다. 또한 Sec-WebSocket-Accept헤더를 보내 신원을 확인합니다.

> Sec-WebSocket-Accept헤더는 Sec-WebSocket-key헤더에 특정 문자열을 연결한 뒤 SHA-1 해싱값을 base64로 인코딩한 결과물입니다. 브라우저에서 해당 값을 계산하여 일치하지 않으면 연결할 수 없습니다.
> 이후 ws프로토콜로 전환되어 이벤트 드리븐 형식의 양방향 통신이 가능해집니다. WebSocket으로 전송 가능한 데이터는 바이너리와 텍스트 뿐입니다. 따라서 해석이 전적으로 어플리케이션에 맡겨지게 됩니다. 이를 위해 STOMP같은 서브 프로토콜을 사용하거나 JSON형식을 정의하여 통신하는 경우가 많습니다.

> WebSocket은 ws(80번), wss(443번) 프로토콜(포트)를 이용해 양방향 통신을 하며, 통신이 종료되는 경우 Close Frame을 보내 연결을 종료합니다.
## 🍟 data structures & algorithms

## 🍤 CS
