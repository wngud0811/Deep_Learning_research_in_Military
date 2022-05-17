# Machine_Learning_research_in_Military
- Describing the methods and useful tips to develop Machine Learning Codes and run experiment inside the Military base of Repulic of Korea Army.

## Problem 1: Compute Server Access
- Referring the security regulations in the military, some of the commercial function and software usage for communications is prohibited. Also, the web access logs are recorded for each personnel and strictly inspected. Special treatments are required for setting up computational equipments and experimental environment.
- We test several frameworks like Jupyter Notebook(For single user server), JupyterHub(For multiple user server) and Docker(Virtualization, Development Environment Management) to fit the security requirements and enable Machine Learning project environments.

### Preparation
- Personal/Public Server or Desktop linked to WAN.
- Internet PC in military base.
  - Commercial Web Browser.(Google Chrome, etc).
 
### Prerequisites
- Linux series OS usage.
- Basic Network knowledge.
- Understanding of port forwarding functions of secure shell command(ssh) in Linux shell.(-R, -L, -D arguments)
 
### Examples
- Example Setting 1
  - Access to <em>Personal</em> Server with public IP(A) with machine inside military base(B).
- Example Setting 2
  - Access to compute server with no public IP(A) connected to <em>Personal</em> (Gateway Server|NAT|Router) with Public IP(B) by machine inside military base(C).
  - Access to compute server with no public IP(A) connected to (Gateway Server|NAT|Router) with Public IP(B) by machine inside military base(C).

<br>\*<em>'Personal'</em> implies you have root privilege on the machine and can modify file permissions, port options, services, etc. ~~The point is that ssh outbounds with default port(22) from military base is prohibited and we need significant cares to handle this issue when we cannot change the service port of ssh at destination machine.~~ I noticed that this is not true.

### Solutions
- Cloud-based access/Cloud Computing(Google Cloud Platform, Amazon Web Service, Azure, IBM Cloud, Alibaba cloud, Web-based IDEs, etc)
- HTTP/HTTPS based access

## Securing data transfer
- I recognized that my communication and my data are being proctored even in my private cell phone communication. (Without the notification to me :angry:)
- I guess at least web logs and app synchronization data in my phone are being monitored.

### Solutions
- VPN
- SSH tunneling & Packet encryption
- Tor

### Steps (without Tor)
- Prepare a Vitual Machine with a network (from Cloud or On-Prem)
- Make a secured connection to the server with secured authorization. (It is recommended to use the method at least strong as ed25519)
- Make a proxy to the server (ex. dynamic forwarding with SOCKS5)

### Steps (with Tor)
- Prepare a Vitual Machine with a network (from Cloud or On-Prem)
- Make a secured connection to the server with secured authorization. (It is recommended to use the method at least strong as ed25519)
- Torify the outbound traffic of the server
- Make a port forwarding connection to the port of Tor service at the server
** Important: Do not sign in any account ind Tor network. Do not reveal your identity.

## (Optional) Preventing Spyapps
### Solutions
- Run vaccin apps
- Fatory reset your device occasionally
- Try not to root your phone

## (Optional) Preventing BlueBorne Attack (especially weak for Android devices)
### Solutions
- I can't find a better way than turning off Bluetooth.

## (Optional) Wireless device security
### Solutions
- I can't find a better way than using wired devices. (better with C-type to fit the security regulations)

## (Optional) Bypassing forced Mobile security application installation. (Testing)
### Solutions
- Install mobile OS emulator app to the phone.
- Install Military Mobile Security app (국방모바일보안) inside the virtual environment.

## Reference
- Machine Learning Engineering for Production (MLOps) Specialization, Coursera and Deeplearning.AI
- [사이버지식정보방 운영 및 관리에 관한 훈령(국방부 인적자원개발과)][link1]
- [국가정보원법 보안업무규정(국가정보원)][link2]
- [국가정보원법 보안업무규정 시행규칙(국가정보원)][link3]
  - [[별표 2] 정보통신 보안 규정 위반 사항(제66조1항 관련)][link4]
- [국방부 군사기밀 보호법 시행령(국방정보본부 보안정책과)][link5]

[link1]: https://www.law.go.kr/LSW/admRulInfoP.do?admRulSeq=2000000016242
[link2]: https://www.law.go.kr/%EB%B2%95%EB%A0%B9/%EB%B3%B4%EC%95%88%EC%97%85%EB%AC%B4%EA%B7%9C%EC%A0%95
[link3]: https://www.law.go.kr/LSW/admRulLsInfoP.do?admRulSeq=2200000061152
[link4]: https://github.com/wngud0811/Machine_Learning_research_in_Military/blob/main/%5B%EB%B3%84%ED%91%9C%202%5D%20%EC%A0%95%EB%B3%B4%ED%86%B5%EC%8B%A0%EB%B3%B4%EC%95%88%20%EA%B7%9C%EC%A0%95%20%EC%9C%84%EB%B0%98%20%EC%82%AC%ED%95%AD(%EC%A0%9C66%EC%A1%B0%EC%A0%9C1%ED%95%AD%20%EA%B4%80%EB%A0%A8)(%EB%B3%B4%EC%95%88%EC%97%85%EB%AC%B4%EA%B7%9C%EC%A0%95%20%EC%8B%9C%ED%96%89%EA%B7%9C%EC%B9%99).pdf
[link5]: https://www.law.go.kr/%EB%B2%95%EB%A0%B9/%EA%B5%B0%EC%82%AC%EA%B8%B0%EB%B0%80%EB%B3%B4%ED%98%B8%EB%B2%95%EC%8B%9C%ED%96%89%EB%A0%B9
