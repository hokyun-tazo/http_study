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

#### 협상과 우선순위

**Quality Values**
 
 - 다중 언어를 지원하는 서버가 있을 때 원하는 언어를 **클라이언트가 우선순위를 지정해줄수 있다**
 - **1과 가까울수록 우선순위가 높은 것이며** 값을 생략하면 1이 된다
 - ex)  ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7

**경로**
 - 경로가 구체적인 것을 우선시한다
 
 - ex) text/*, text/plain, text/plain;format=flowed, */*
 
1. text/plain;format=flowed 2. text/plain 3. text/* 4. */

---

## 일반 정보헤더
|헤더|뜻
|:---:|:---|
|From |유저의 이메일 정보로써 검색 엔진 같은 곳에서 주로 사용되지만 일반적으로 잘 사용되지 않는다
|Referer |현재 요청된 페이지의 이전 웹 페이지 주소를 말하며 **Referer를 사용해서 유입 경로를 분석할수 있다**
|User-Agent |클라이언트의 애플리케이션 정보(웹 브라우저 정보 등등)를 말하며 **서버 입장에서 어떤 종류의 브라우저에서 장애가 발생하는지 파악 가능하다**
| Server|요청을 처리하는 ORIGIN서버의 SW정보를 말한다
|DATA |메시지가 발생한 날짜와 시간

---

## 특별한 헤더

