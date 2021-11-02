---
layout: post
title:  "API Gateway"
date:   2021-10-28 21:09:00 +000
categories: API Gateway System-design
---
API Gateway

---

### Index
# 들어가며
>  

# API Gateway란
## API Gateway의 개념
> API Gateway는 서비스로 전달되는 모든 API 요청의 관문 역할을 하는 서버 시스템의 아키텍처를 내부로 숨기고 외부의 요청에 대한 응답만을 적절한 형태로 응답합니다. 즉, 클라이언트는 내부 구조가 어떠한 아키텍쳐인지 알 필요 없이 서로 약속한 형태의 API 요청만을 서버로 보냅니다.

[<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmhnjM%2Fbtq27UikvEv%2FG8u25AhAIRUlD3o3eAB3JK%2Fimg.jpg">](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmhnjM%2Fbtq27UikvEv%2FG8u25AhAIRUlD3o3eAB3JK%2Fimg.jpg)

## API Gateway의 장점
> - 클라이언트의 요청을 일괄적으로 처리
> - 전체 시스템의 부하를 분산 시키는 로드 밸런서의 역할
> - 동일한 요청에 대한 불필요한 반복 작업을 줄일 수 있는 캐싱
> - 시스템 상을 오고가는 요청과 응답에 대한 모니터링
> - 시스템 내부에 아키텍처를 숨길 수 있음

# API Gateway의 주요 기능
## 인증 및 인가
> 마이크로 서비스 아키텍처에서 각각의 서비스에 API 호출에 대한 인증 및 인가를 하는 것은, 같은 소스 코드를 서비스 인스턴스들마다 심어주어야 한다는 것을 의미합니다. 이러한 경우, 소스의 중복이 심하여 유지 관리가 어려운 것은 물론, 로깅 및 모니터링을 관리하는 것도 매우 어려워집니다. 이러한 이유로 인증서 관리나, 인증, SSL 프로토콜 변환과 같은 기능들은 API Gateway에서 오프로드함으로, 각각 서비스의 부담을 줄이고 서비스의 관리 및 업그레이들르 보다 쉽게 할 수 있습니다.

## 요청 절차의 단순화
> 여러 마이크로 서비스를 대상으로 기능을 이용하려 할 때, 만약 API Gateway가 없다면 클라이언트에서 여러 서비스들에 대해 요청을 진행해야 했을 겁니다. 하지만, API Gateway는 여러 클라이언트의 요청을 단일 클라이언트의 요청으로 대체 가능하도록 합니다. 따라서 클라이언트와 백엔드 간의 API 통신량을 줄여주어 대기시간을 줄이고 효율성을 높여줄 수 있습니다.

## 라우팅 및 로드밸런싱
> API Gateway는 클라이언트로부터 접수된 메시지에 따라 API 호출을 적절한 서비스에 라우팅 할 수 있는 기능이 있습니다. 또한, 서비스 인스턴스들에 대한 부하 분산을 할 수 있습니다.


## 서비스 디스커버리
> API Gateway는 각 서비스를 호출하기 위해, 서비스마다 IP 주소와 포트 번호를 알고 있어야 합니다. legacy 환경에서는 고정적인 IP 주소를 가지고 있기 때문에 서비스의 위치를 찾는 것이 어렵습니다. API Gateway에서는 서버사이드나, 클라이언트 사이드를 기준으로 하여 서비스 디스커버리를 구현할 수 있습니다.

## API Gateway 적용 시 고려해야할 사항
> API Gateway의 Scale-out 적용이 유연하게 일어나지 않을 경우, API Gateway가 병목 지점이 되어 어플리케이션의 성능 저하가 일어날 수 있습니다.
API Gaeway라는 추가적인 계층이 만들어지는 것이기 때문에, 그만큼 네트워크 latency가 증가하게 됩니다.
 

### Reference 
> - [참고]

[참고]: https://kchanguk.tistory.com/156
