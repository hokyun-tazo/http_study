# HTTP 헤더
---

## 표현 헤더

- 표현 데이터를 해석할 수 있는 정보를 제공한다
- 데이터의 유형, 데이터 길이, 압축 정보 등등

|헤더|뜻|예시|
|:---:|:---|:---|
|Content-Type| **표현 데이터의 형식을 설명한다**|text/html, charset=utf-8, Application/json, image/png|
|Content-Encoding|**표현 데이터를 압축하기 위해 사용**, 서버에서 데이터를 압축후 인코딩 헤더를 추가하면 Client 쪽에서 인코딩 헤더의 정보를 보고 압축을 해제한다|Content-Encoding: gzip, deflate, identify|
|Content-Language|**표현 데이터의 자연 언어를 표현**|Content-Language: ko, en
|Content-Length|바이트 단위로 이루어진 **표현 데이터의 길이**를 의미한다|Content-Length: 3578

---

## 협상 헤더
 - 클라이언트가 원하거나 선호하는 표현 방식을 서버에 요청해서 알리는 헤더를 말한다
 - 요청시에만 사용하는 헤더이다

|헤더|뜻|
|:---:|:---|
|Accept|클라이언트가 선호하는 미디어 타입을 전달하는 헤더
|Accept-charset| 클라이언트가 선호하는 문자 인코딩 방식을 전달
|Accept-Encoding |클라이언트가 선호하는 압축 인코딩 방식을 전달
|Accept-Language |- 클라이언트가 선호하는 자연 언어를 전달
