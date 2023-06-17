# Intro

- 주식/코인 자동 매매 프로그램 개발 with A&A API Server
  - 배포 방식: 실행 파일
  - 요구사항:
    - 인가된 사용자만 프로그램을 실행할 수 있어야 한다
    - 사용자의 인가는 관리자만이 승인할 수 있다
    - 인증의 유효시간은 5분이며, 인증 이후 30분동안 유효하다

# Flow & Arch.

<img width="1434" alt="Screen Shot 2023-06-16 at 2 39 03 AM" src="https://github.com/S-hayeon/archive/assets/25574165/a009f0ee-04b7-4054-a4b8-553289a26bf2">

# Details

- Server-side:
  - springboot + redis  + SocketIO: 
    - API 서버 제외하고 MQ만 사용해도 기존 요구사항은 충족할 수 있으나, API서버는 추후를 위해 구축해서 나쁠것이 없다고 생각한다. 유효기간 관리에는 redis만한게 없는 것 같다. 제한된 사용자 수때문에 인가 여부를 확인하는 request를 무한정 보낸다 하더라도 네트워크/서버부하 등의 문제는 걱정 없지만 굳이 그렇게 하고 싶진 않았다. 
- Executable Program & telegram Controller
  - python : flet 라이브러리가 Flutter-like 실행파일을 만드는데 있어 굉장히 유효했다 (cross-platform인것은 덤) 
- Infra: EC2 + docker-compose



