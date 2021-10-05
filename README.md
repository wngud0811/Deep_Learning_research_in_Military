# Machine_Learning_research_in_Military
- Describing the methods and useful tips to develop Machine Learning Codes and run experiment inside the Military base of Repulic of Korea Army.<br>대한민국 군부대(육군) 내에서 머신러닝 코드를 개발하고 실험을 수행할 수 있는 방법과 노하우를 기록합니다.

## Summary
- Referring the security regulations in the military, functions and softwares like NAS(ssh, ftp), VNC and Proxy bypassing is prohibited. Also, the web access logs are recorded for each personnel and strictly inspected. Special treatments are required for setting up computational equipments and experimental environment.<br>군내 보안규정에 따라, NAS(ssh, ftp), VNC와 Proxy 우회 기능 사용이 제한되고 인터넷 접속 로그가 사용자별로 기록 및 검열되는 상황에서 딥러닝 연구를 위한 별도의 연산장비와 특수한 실험환경 세팅 필요
- We test several frameworks like Jupyter Notebook(For single user server), JupyterHub(For multiple user server) and Docker(Virtualization, Development Environment Management) to fit the security requirements and enable Machine Learning project environments. <br>Jupyter Notebook(단일 사용자 서버), JupyterHub(다중 사용자 서버), Docker(가상화, 개발 환경 관리) 등의 툴을 활용해 쉽게 Machine Learning 프로젝트 환경 설정
- Usage of computational resources compying with the security regulations with appropriate server settings and port distribution.<br>적절한 서버 설정과 네트워크 포트 분배을 통해 보안이 허용하는 범위 내에서 연산 서버 사용

## Preparation
- Private Server or Desktop linked to WAN.<br>인터넷에 연결된 개인 서버/데스크탑.
- Internet PC in military base.<br>군내(영내) 인터넷망 PC.
  - Commercial Web Browser.(Google Chrome, etc)<br>상용 웹 브라우저(크롬 등).
 
## Prerequisites
- Linux series OS usage.
- Basic Network knowledge.
- Understanding of port forwarding functions of "ssh" command in Linux shell.(-R, -L, -D arguments)
 
## Examples
- Example Setting 1
  - Access to <em>Personal</em> Server with public IP(A) with machine inside military base(B).<br> 공인 IP가 있는 개인 서버(A)에 군대 영내 데스크탑으로(B) 접속
- Example Setting 2
  - Access to compute server with no public IP(A) connected to <em>Personal</em> (Gateway Server|NAT|Router) with Public IP(B) by machine inside military base(C).<br> 공인 IP가 없는 연산 서버(A)에 공인 IP가 있는 <em>개인</em> (게이트웨이 서버|NAT|공유기) (B)를 통해 군대 영내에서 접속
- Example Setting 3
  -  Access to compute server with no public IP(A) connected to (Gateway Server|NAT|Router) with Public IP(B) by machine inside military base(C).<br> 공인 IP가 없는 연산 서버(A)에 공인 IP가 있는 (게이트웨이 서버|NAT|공유기) (B)를 통해 군대 영내에서 접속

<br>*<em>'Personal'</em> implies you have root privilege on the machine and can modify file permissions, port options, services, etc. The point is that ssh outbounds from military base is prohibited and we need significant cares to handle this issue when we cannot change the service port of ssh at machine.<br>'개인'은 머신에 루트 권한을 가지고 있어 파일 권한 조정, 포트 분배, 서비스 관리 등을 수행할 수 있는 경우를 의미합니다.

## Reference
- Machine Learning Engineering for Production (MLOps) Specialization, Coursera and Deeplearning.AI
- [국가정보원법 보안업무규정(국가정보원)][link1]
- [국가정보원법 보안업무규정 시행규칙(국가정보원)][link2]
  - [[별표 2] 정보통신 보안 규정 위반 사항(제66조1항 관련)][link3]
- [국방부 군사기밀 보호법 시행령(국방정보본부 보안정책과)][link4]


[link1]: https://www.law.go.kr/%EB%B2%95%EB%A0%B9/%EB%B3%B4%EC%95%88%EC%97%85%EB%AC%B4%EA%B7%9C%EC%A0%95
[link2]: https://www.law.go.kr/LSW/admRulLsInfoP.do?admRulSeq=2200000061152
[link3]: https://github.com/wngud0811/Machine_Learning_research_in_Military/blob/main/%5B%EB%B3%84%ED%91%9C%202%5D%20%EC%A0%95%EB%B3%B4%ED%86%B5%EC%8B%A0%EB%B3%B4%EC%95%88%20%EA%B7%9C%EC%A0%95%20%EC%9C%84%EB%B0%98%20%EC%82%AC%ED%95%AD(%EC%A0%9C66%EC%A1%B0%EC%A0%9C1%ED%95%AD%20%EA%B4%80%EB%A0%A8)(%EB%B3%B4%EC%95%88%EC%97%85%EB%AC%B4%EA%B7%9C%EC%A0%95%20%EC%8B%9C%ED%96%89%EA%B7%9C%EC%B9%99).pdf
[link4]: https://www.law.go.kr/%EB%B2%95%EB%A0%B9/%EA%B5%B0%EC%82%AC%EA%B8%B0%EB%B0%80%EB%B3%B4%ED%98%B8%EB%B2%95%EC%8B%9C%ED%96%89%EB%A0%B9
