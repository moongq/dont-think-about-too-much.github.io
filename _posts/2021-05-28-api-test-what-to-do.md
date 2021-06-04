---
layout: post
title: API 테스트 때 뭘 해야할지 모르겠다면,
tags: [Node, Backend, API TEST]
---

## 기본적인 확인 목록
- 인풋들이 제대로 입력되는지,
- 필수 값이 아닌 인풋들이 들어가지 않았을 때 디폴트값, 혹은 의도된 값으로 자동으로 설정되는지.
- 응답 코드가 예상대로 반환되는지

---

## 메서드별 확인 목록
### GET 
- 반환 값이 있을 때: 페이지네이션이 있다면 페이지네이션이 정상 응답
- 반환 값이 없을 때: 값이 없을 시 의도한대로 응답하는지
- 필요한 데이터들이 모두 반환되는지

### POST
- 로직적으로 유니크해야하는 값을 넣었을때 Duplicate 에러가 안나는지,
- 정의된 에러코드가 제대로 작동하는지

### PATCH
- 존재하지 않는 데이터에 대한 시도에 대한 응답
- 유니크해야하는 값으로 수정하면 duplicate 에러 응답

### DELETE
- 존재하지 않는 데이터에 대한 삭제 시도시 에러 응답
- 연결되어있는 데이터가 받는 영향이 의도된데로인지 (onCascade, onDelete)

---

## 입력 파라미터별 확인 목록
- "", " "(공백) 인풋에 대한 반응
- 특수문자 입력시
- 압뒤로 공백문자 (" 단어 ")
- 숫자 타입에 대해서 (string인 숫자로 들어오면)
- 대소문자

---

## 유저 인증, 유저 권한 범위 확인 목록
- 로그인된 상태에 따른 응답
- 유저 권한에 따른 응답.

---
### + Postman Test
postman으로 api들을 확인해왔다면 postman에서도 테스트 기능을 제공해준다. <br>
굳이 api테스트까지는 jest, supertest를 이용하여 테스트하지 않아도 괜찮다고 본다.(물론 unit test는 스크립트를 작성해서 해야하지만.)<br>
### [Postman API Test 링크](https://learning.postman.com/docs/writing-scripts/test-scripts/)

<br><br>
# References
- [https://www.slideshare.net/genycho/rest-api-64569519](https://www.slideshare.net/genycho/rest-api-64569519)