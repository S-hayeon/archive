# CI / CD 구성도 w/ Argocd



## CI/CD 구성 

<img width="1251" alt="Screen Shot 2023-07-14 at 2 18 52 AM" src="https://github.com/S-hayeon/archive/assets/25574165/66b3d8d9-a581-4c01-a812-c4caa7b82462">



---

## CD Continue

기본 모듈 형상은`App of Apps `패턴으로 관리

- Operators: aeger, kiali, kafka, mysql
- cert-manager, harbor, EFK, tekton, sonarqube, istio, gitea, keycloak, kiali, jaeger, nginx-ingress

개별 서비스는 개별 관리

