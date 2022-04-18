# FEInterview
Learn FE Concept and prepare Interview

## 🍖 JavaScript

## 🍔 React

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
3. [프로미스](https://velog.io/@dbstjrwnekd/Promise)에 대해 설명해주세요.
> Promise는 자바스크립트의 비동기 처리 상태와 처리 결과를 관리하는 객체입니다. 일반적으로 자바스크립트의 비동기 처리는 콜백 함수를 이용한 콜백 패턴을 활용하는데요. 이러한 방식은 중첩될 경우 콜백헬 이라는 현상이 발생해 가독성이 떨어지게 됩니다. 또 이런 패턴은 에러처리가 어렵기에 각각의 콜백함수에 전부 에러처리를 해줘야 하는 문제점이 발생합니다.

> 이러한 문제를 해결하기 위해 등장한 것이 프로미스 입니다. 프로미스는 pending, fulfilled, rejected의 3가지 상태를 가지고 있으며 .then, .catch 등의 후속 처리 함수를 제공합니다. 상태는 각각 비동기 처리 결과를 기다리는 상태(pending), 비동기 처리가 완료된 상태(fulfilled), 비동기 처리가 실패한 상태(rejected)입니다. 매개 변수로 받는 resolve, reject함수를 통해 pending -> settled(fulfilled | rejected)상태로 변화할 수 있으며 변화된 이후로는 상태를 변화할 수 없습니다. 프로미스의 .then, .catch, .finally 등의 후속 처리 메서드는 암묵적으로 프로미스를 반환하여 체이닝이 가능합니다. 프로미스 체이닝을 통해 콜백헬 문제를 해결할 수 있으며, 후속 처리 메서드 .catch를 통해 에러 처리가 유용해집니다.

> async, await키워드와 함께 사용하면 후속 처리 메서드를 사용하지 않고 동기적인 코드처럼 작성이 가능하다는 장점도 있습니다.

> 또한 프로미스는 Promise.prototype.all, Promise.prototype.allSettled, Promise.prototype.race 등의 함수를 제공하여 비동기 처리를 병렬적으로 수행할 수 있도록 도와줍니다.
> 위 함수들은 프로미스를 요소로 갖는 배열 등의 이터러블을 원소로 받습니다.
> Promise.all은 전달받은 모든 프로미스가 fulfilled 상태가 되면 결과를 배열에 저장해 새로운 프로미스를 반환합니다. 이때 중간에 rejected가 발생하면 다른 처리를 기다리지 않고 즉시 종료합니다.
> Promise.allSettled는 fulfilled, rejected와 상관 없이 모든 프로미스가 settled상태가 되면 결과를 배열에 저장해 새로운 프로미스를 반환합니다.
> Promise.race는 가장 먼저 fulfilled 상태가 된 프로미스의 처리 결과를 배열로 반환합니다. all과 마찬가지로 에러를 reject하는 새로운 프로미스를 즉시 반환합니다.
## 🍟 data structures & algorithms

## 🍤 CS
