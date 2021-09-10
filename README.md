# Machine_Learning_research_in_Military
Describing the methods and useful tips to develop Machine Learning Codes and run experiment in the Repulic of Korea Army.
한국 군대 내에서 머신러닝 코드를 개발하고 실험을 수행할 수 있는 방법과 노하우를 기록합니다.

Preparation. 준비물.
- Private Server or Desktop linked to WAN.<br>인터넷에 연결된 개인 서버/데스크탑.
- Internet PC in military base.<br>군내(영내) 인터넷망 PC.
  - Commercial Web Browser.(Google Chrome, etc)<br>상용 웹 브라우저(크롬 등).

Motivation. 필요성.
- Referring the security regulations in the military, functions like VNC and Proxy bypassing is prohibited. Also, the web access logs are recorded for each personnel and strictly inspected. Special treatments are required for setting up computational equipments and experimental environment.<br>군내 보안규정에 따라, VNC와 Proxy 우회 기능 사용이 제한되고 인터넷 접속 로그가 사용자별로 기록 및 검열되는 상황에서 딥러닝 연구를 위한 별도의 연산장비와 특수한 실험환경 세팅 필요
- We test several frameworks like Jupyter Notebook(For single user), JupyterHub(For multiple user) and Docker to fit the security requirements and enable Machine Learning project environments. <br>Jupyter Notebook(For single user), JupyterHub(For multiple user), Docker 등의 툴을 활용해 쉽게 Machine Learning 프로젝트 환경 설정
- Usage of computational resources compying with the security regulations with appropriate server settings and port distribution.<br>적절한 서버 설정과 네트워크 포트 분배을 통해 보안이 허용하는 범위 내에서 연산 서버 사용
