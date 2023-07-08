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
  - springboot + redis  + SocketIO
  
- Executable Program & telegram Controller
  - python :flet (exe. app build-deploy)
  
  



