# HTTP message 구성
---

## HTTP message 구조
![image](https://user-images.githubusercontent.com/104821475/187861516-b61f5c31-d74e-403b-a1a9-acce6a3eea9e.png)

**시작라인**: 요청메시지의 시작줄은 **서버에 무엇을 요청하는지 말해주고**  응답 메시지의 시작줄은 **요청을 받아서 서버에 무슨일이 일어 났는지 말해준다**

**헤더**: 쌍점(:)으로 구분되어 있는 하나의 이름과 하나의 값으로 구성되며 **http 전송에 필요한 모든 부가정보**를 기입한다
헤더는 빈줄(CRIF)로 끝나게 된다

**본문**: 어떤 종류의 데이터든 들어갈 수 있는 곳이며 임의의 이진 데이터를 포함할 수 있다

---

## http message의 시작라인

**요청 메시지의 시작라인**

![image](https://user-images.githubusercontent.com/104821475/187862997-e0455f5c-ef24-40dc-909d-99683ddb9475.png)

 1. 맨앞에 HTTP 메소드(GET)가 오며 **서버가 수행해야할 동작을 지정한다**
 2. 메소드 다음에는 '/' 절대경로로 시작하며 **요청하는 대상을 의미하고 ?로 시작하는 query로 이루어져 있다**
 3. 마지막은 client가 어떤 http를 사용하는지 버전이 적혀있다

**응답 메시지의 시작라인**

![image](https://user-images.githubusercontent.com/104821475/187863792-90080815-d8f3-4b4b-b1e0-605df7b903aa.png)


 1. 요청을 받은 결과가 어떻게 됬는지 나타내는 **상태코드(200)과 사유구절이 적힌다**
 2. 엔터티 본문의 추가정보를 나타내는 헤더가 기입된다
 3. 요청한 데이터가 담겨져 있는 메시지 바디가 있다

----

## http 메서드

| 메서드 | 의미 |
 |:---:|:---:|
| GET | **리소스를 조회한다**, 클라이언트가 서버에게 데이터를 가져와달라고 부탁하는 것 | 
| POST | **client가 서버에게 메시지 바디를 통해 요청 데이터를 전달해서 서버에게 데이터를 처리해 달라고 명령하는 것**, 단순히 값 변경을 넘어서 프로세스의 상태가 변경이 된다 |
| PUT | **리소스가 존재한다면 기존의 리소스를 변경하고 리소스가 없다면 새로 생성한다** |
| HEAD | GET과 동일하게 행동하지만 서버는 응답으로 **헤더만 돌려준다**, 개발자들은 반환되는 헤더가 **GET으로 얻는 것과 정확히 일지함을 보장하도록 개발해야한다** |
| TRACE | 수정 가능성이 있는 **http 요청이 종단 서버에 도착했을떄 어떻게 종단 서버에게 보이게 됬는지 클라이언트에게 알려준다**, 주로 진단을 할때 사용한다 |
| OPTIONS | 서버에게 특정 리소스에 대해 **어떤 메서드가 지원되는지 물어보는 메소드이다**
| DELETE | 서버에 존재하는 리소스를 삭제하는 것 |
| PATCH | 서버에 존재하는 리소스의 값을 **부부적으로 바꿀수 있다**, PATCH를 지원하지 않는 서버가 있다면 POST를 사용하면 된다 |
 
 ----
 
 ## http 메서드의 속성
 
 ![image](https://user-images.githubusercontent.com/104821475/188272447-f6ef8740-4a2c-4108-9f0a-632a9335dfa4.png)

**safe**
 - 호출해도 리소스를 변경하지 않는 메서드를 말한다

**Idempotent**
 - 한번 호출하든 백번 호출하든 결과가 똑같은 메서드이다
 - 서버에 요청을 했는데 서버가 TIMEOUT으로 정상 응답을 못주었을때 client가 다시 같은 요청을 해도 괜찮은 메소드들을 의미한다
 - 몇번을 요청해도 결과가 같기 때문에 서버가 응답을 못주면 다시 서버에 재요청하는 **자동복구 메커니즘에 사용한다**
 - Idempotent는 외부 요인으로 중간에 리소스가 변경되는 것 까지는 고려하지 않는다

**Cacheable**
 - 응답결과 리소스를 캐시해서 사용해도 되는 것을 의미한다






