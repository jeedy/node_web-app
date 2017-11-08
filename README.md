# node_web-app

Chapter 7. 웹 애플리케이션 - Node.js 정석 
============

## 오류 정정
1. express4 부터 `app.use(express.logger('dev'));` 지원하지 낳는다. `morgan` 모듈로 사용하도록 바뀌었다.
````
const app = require('express') ();
const logger = require('morgan');
app.use(logger('dev'));
````
1. 

## 아키텍처와 코어
 지금까지 우리는 Node.js 코어의 많은 측면을 지나쳐 왔다. 하지만 Node는 지금까지 우리가 예제로 해 본 것들 보다 훨씬 더 많은 것을 가능하게 해 주는 기반 기술이다.

## 패턴
 이번 장에서 Express 미들웨어에 더 깊이 들어가서, 이것을 이용해 커스텀 인증 핸들러를 구현할 것이다.

## 자바스크립티즘
ECMAScript Harmony는 이터레이터(iterator)와 *제너레이터(generator)라는 새로운 개념을 도입했다. 어떻게 제너레이터를 만들고 사용하는지를 배우고 프라미스(promise)와 합해져 비동기 프로그래밍을 단순화 하는 것도 배울 것이다.

## 지원 코드
이장에서는 프로젝트의 시동을 거는 스크립트를 명시하는 것과 같은 npm의 더 많은 특성들을 사용할 것이다. 또한, nodemon을 활용해서 Node 프로그램을 모니터하고 소스코드가 바뀌면 자동적으로 재시작하도록 할 것이다.


## CouchDB 1.6.0
> - 참고 API : [http://docs.couchdb.org/en/1.6.1/intro/api.html]
> - HTTP API reference : [http://docs.couchdb.org/en/1.6.0/http-api.html]

설치
```
$ brew install couchdb
```

실행 
```
$ couchdb
```

쿼리
```
$ curl -X POST 'http://localhost:5984/books'    // 생성
$ curl -X PUT 'http://localhost:5984/books'     // 생성 및 갱신
$ curl -X GET 'http://localhost:5984/books'     // 조회
$ curl -X DELETE 'http://localhost:5984/books'  // 삭제
```

데이터 예제 (Project Gutenberg)
```
$ curl -O http://www.gutenberg.org/cache/epub/feeds/rdf-files.tar.bz2
$ tar -xvjf rdf-files.tar.bz2
```
