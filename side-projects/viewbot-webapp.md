# Intro

- 스트리밍 플랫폼 뷰봇 유입 웹앱 개발
  - 요구사항:
    - 사용자는 스트리머 이름과 유입하고하는 시청자수를 입력할 수 있다

# Arch.

<img width="1384" alt="Screen Shot 2023-06-16 at 3 48 05 AM" src="https://github.com/S-hayeon/archive/assets/25574165/e36dcf60-f734-4135-b85b-22da183c0b4a">



# Details

1. 사용자는 스트리머 명과 할당하고자 하는 시청자 유입 수를 입력한다

2. Controller는 요구사항을 충족할 수 있는 `REGION`을 찾고, `REGION`, `name`, `num`을 input값으로 스크립트를 실행시킨다 
   - 하나의 IDC에서 생성할 수 있는 최대 EC2 인스턴스 수는 18이었다.
3. 스크립트 실행
   1. 유입수 / 3의 갯수만큼 stopped상태인 instance를 running으로 바꾼다
   2. 새로 동작하는 인스턴스에 대해, 3개의 컨테이너를 실행시킨다 (환경변수: name)
   3. 컨테이너는 `selenium`활용해 웹페이지에 접속하는 용도이다
4. 스트리머가 방송을 종료한 경우, 스트리머 명으로 떠있는 instance를 종료할 수 있다 



CSP가 사용할 수 있는 instance의 갯수에 제한을 두었다는 것에 한번 놀랬다

k8s operator패턴을 이용해 요청에 따라 pod를 할당하는 방식으로 작업하고 싶었으나, 스트리밍 플랫폼이 하나의 IP에 대해 최대 3의 시청자 수를 늘릴 수 있도록 되어있기 때문에 적용할 수 없었다.



