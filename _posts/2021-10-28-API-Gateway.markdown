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


#### 클러스터 모드
> 클러스터 모드: Node.js 로드 밸런싱 및 다운타임 제로 재로드 클러스터 모드는 Node.js 애플리케이션을 시작할 때의 특수 모드로, 여러 프로세스를 시작하고 이들 사이에서 HTTP/TCP/UDP 쿼리를 로드 밸런싱합니다. 이렇게 하면 전체 성능(16코어 시스템에서 10배)과 안정성(처리되지 않은 오류의 경우 더 빠른 소켓 재조정)이 향상됩니다.

#### Cluster Mode: Node.js Load Balancing & Zero Downtime Reload
The Cluster mode is a special mode when starting a Node.js application, it starts multiple processes and load-balance HTTP/TCP/UDP queries between them. This increase overall performance (by a factor of x10 on 16 cores machines) and reliability (faster socket re-balancing in case of unhandled errors).


# 3. pm2 자주사용하는 command?
```
# app.js 등록
pm2 start app.js

# pm2가 실행하는 앱 모니터링
pm2 monit

# logs 확인
pm2 logs

# 클러스터모드 사용시 다운타임 없이 서버를 재가동 한다
pm2 reload all

# 모든 프로세스를 멈춘다
pm2 stop all

# pm2 관리 목록에서 인스턴스를 삭제한다. app.js가 변경된 경우엔 restart 해주면 되지만 pm2의 인자가 변경된 경우 delete 후 다시 start 해줘야한다.
pm2 delete app1

# 클러스터모드로 앱을 실행한다. -i 인스턴스 개수
pm2 start app.js -i 3

# 프로세스 수를 늘리거나 줄인다
pm2 sacle app 2

# 앱을 실행한다. 별도로 이름을 지정하지 않으면 파일 이름을 쓴다.
pm2 start app.js
pm2 start app.js --name 'app1'
pm2 start app.js --name 'app1' --watch //변동사항이 있을 때 재시작

# 실행된 프로세스 목록을 확인한다
pm2 list

# 프로세스의 내용을 상세하게 확인한다
pm2 show app1

# 어플리케이션 재시작
pm2 restart

# 로그 파일 확인
pm2 logs app1

#로그 파일 지우기
pm2 flush
```

# 4. windows 2019 -offline 에 설치하기
> 1. [git] code download 후 압축을 풀고
> 2. 인터넷이 되는 환경에서 아래의 명령어
```
npm i -g ./pm2-5.1.1
```
> 3. 설치된 폴더를 off-line 서버로 이동
> 4. Window path 설정
> 5. 사용하면 된다.
 

### Reference site 
> - [git]
> - [정리good]
> - [pm2offline]


[git]: https://github.com/Unitech/pm2
[정리good]: https://engineering.linecorp.com/ko/blog/pm2-nodejs
[pm2offline]: https://velog.io/@gingaminga/Offline-%ED%99%98%EA%B2%BD%EC%97%90-PM2-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0