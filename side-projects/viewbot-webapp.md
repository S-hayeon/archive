# Intro

- 스트리밍 플랫폼 뷰봇 유입 웹앱 개발
  - 요구사항:
    - 사용자는 스트리머 이름과 유입하고하는 시청자수를 입력할 수 있다

# Arch.

<img width="1384" alt="Screen Shot 2023-06-16 at 3 48 05 AM" src="https://github.com/S-hayeon/archive/assets/25574165/e36dcf60-f734-4135-b85b-22da183c0b4a">



# Details

- Server-side:
  - springboot + redis  + SocketIO: 
    - API 서버 제외하고 MQ만 사용해도 기존 요구사항은 충족할 수 있으나, API서버는 추후를 위해 구축해서 나쁠것이 없다고 생각한다. 유효기간 관리에는 redis만한게 없는 것 같다. 제한된 사용자 수때문에 인가 여부를 확인하는 request를 무한정 보낸다 하더라도 네트워크/서버부하 등의 문제는 걱정 없지만 굳이 그렇게 하고 싶진 않았다. 
- Executable Program & telegram Controller
  - python : flet 라이브러리가 Flutter-like 실행파일을 만드는데 있어 굉장히 유효했다 (cross-platform인것은 덤) 
- Infra: EC2 + docker-compose



