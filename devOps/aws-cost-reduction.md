# k8s 전환기 및 AWS 비용 절감



k8s를 도입하게 된 이유는 다음과 같다.

1. 개발 완료 / 운영중인 서비스가 4개가 있으며, 지속적인 프로토타입 형태의 서비스 개발이 이뤄지고 운영할 수 있어야 한다.
1. 작업자인 내 기준으로, 기존 배포환경으로 사용하고 있는 ECS보다 k8s가 더 사용하기 편하고, 유용하다
1. k8s 생태계를 활용할 수 있다
1. 현재 기준에서, 절대적인 비용 절감을 이뤄낼 수 있기 때문이다.



![Screen Shot 2023-07-09 at 3 12 16 PM](https://github.com/S-hayeon/archive/assets/25574165/9ee4dda1-a9e5-4081-95d6-62deea66a7e3)



기존 평균 월 $ 2000 ~ 2300불 내외의 요금이 발생하고 있었다.

기존 개발자가 경험해보고 싶은대로, 사용하고 싶은대로 클라우드 서비스를 사용한 것으로 보이고

이렇게 비용이 발생할 필요가 없었던 와중, aws 비용 절감에 대한 요청이 있었다.

k8s를 사용하지 않아도 절감은 가능하다. 하지만, 내가 원할한 운영을 하기 위해서는 이 방법이 나을 것이라 생각한다.



기본 구성은 다음과 같다.

1. `cert-manager` : certificate <-> AWS certificate-manager
2. `harbor` : image registry  <-> AWS ECR
3. `mysql / mariaDB cluster` : RDB  <-> AWS RDS
4. `ELK` : logging <-> AWS cloud watch
5. `tekton`: CI
6. `Argocd`: CD
7. `istio`: traffic-management
8. `jaeger / kiali` : tracing / monitoring
9. Nginx-ingress
10. gitea : private git



우선은 single cluster w/ 5 nodes로 구성하고, 추후에 hybrid로 전환하고자 한다.

이랬을 때, 비용은 $2000불에서 $400불 대로 줄일 수 있을 것으로 계산했다.

가장 걱정되는 것은, RDS를 버리고 DB cluster구축하여 사용하는 부분 + 우선적으로 public cluster에서 진행된다는 점인데,

진행함에 따라 추후 업데이트 하고자 한다.




