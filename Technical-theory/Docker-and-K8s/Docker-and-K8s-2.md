# Docker and Kubernetes 
Docker와 Kubernetes에 대해 간략하게 정리한 내용입니다.
# Kubernetes 
Kubernetes는 도커의 컨테이너 오케스트레이션 중 하나입니다.<br/>
컨테이너 오케스트레이션이란 복잡한 컨테이너 환경을 효과적으로 관리하기 위한 도구입니다. Kubernetes의 장점은 여러가지가 있지만 아래와 같이 크게 세가지를 꼽을 수 있을 것 같습니다. <br/> 
### 1. 컨테이너의 관리
도커를 이용한 서비스에서는 개발 환경뿐만 아니라 서비스 자체를 컨테이너로 분리하여 배포하기도 합니다. 예를 들어 어떤 컨테이너는 유저 정보만 다루고, 어떤 컨테이너는 결제를 다루는 등, 컨테이너 마다 모두 다른 기능을 담당하고 있을 것입니다. 하지만 이러한 컨테이너들을 조합하여 하나의 서비스를 작동시키기 위해서는 수많은 컨테이너들이 동시에 배포가 되고 업데이트 되어야합니다. <br/>  <br/> 
컨테이너의 수가 점점 많아진다면 동시에 배포하거나 업데이트하는 것 뿐만 아니라 컨테이너들을 각각 모니터링하는 것도 어려워 질 것입니다. 서비스 중인 컨테이너 중 일부가 죽어버리면 그것들을 수동으로 재시작해 주어야하는데, Kubernetes는 모든 컨테이너들을 모니터링하여 문제가 생겨 죽은 컨테이너를 자동으로 재시작 시킵니다.<br/> 
### 2. 로드밸런싱
로드밸런싱이란 간단하게 말해서, 서버에게 가해지는 부하를 분산시켜주는 장치나 기술을 말합니다.<br/> 
서비스를 돌리는 도중 갑자기 트래픽 량이 많아져 컨테이너 수를 늘려야 하는 경우 Kubernetes는 자동으로 컨테이너들을 추가로 생성해 주고, 다시 트래픽이 줄어들면 지정해둔 컨테이너 수로 다시 조정해주기도 합니다.<br/> 
### 3. 롤링업데이트
서비스를 진행하는 중에는 일부 혹은 전체 요소를 업데이트하거나 코드를 수정해야하는 경우가 빈번하게 발생합니다. 현재 동작하는 서비스를 업데이트하기 위해서는 우선 작동중인 컨테이너들을 정지시킵니다. 그리고 한꺼번에 새로운 버전으로 수정 및 교체 후 재시작 하는 것이 일반적인 방법입니다. 그렇게 되면 웹사이트가 일시적으로 다운이 되겠지요.<br/> 
하지만 Kubernetes를 활용하면 컨테이너를 순차적으로 업데이트 시키기 때문에 웹사이트가 다운되는 일 없이 수정사항을 적용시킬 수 있습니다.<br/> <br/> 
이뿐만 아니라, 여러 부분에서 컨테이너를 이용한 웹사이트를 자동화시킬 수 있기 때문에, 점점 Kubernetes와 도커를 채택하는 기업들이 늘어나는 추세입니다.<br/> 
하지만 모든 상황에서 도커와 Kubernetes가 필요한 것은 아니기 때문에 상황과 서비스에 맞게 사용하는 것이 좋습니다. 