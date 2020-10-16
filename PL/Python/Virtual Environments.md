Virtual Environments
=====================

가상환경(Virtual Environments)이란 자신이 원하는 Python 환경을 구축하기 위해 필요한 모듈만 담아 놓은 바구니라고 생각하면 됩니다.   

<img src="https://user-images.githubusercontent.com/26195706/92327317-b540c100-f093-11ea-90f0-6854c99b9e66.png"></img> 

즉 위 사진 상단의 Python Virtual Envs처럼 각 가상환경 (virtualenv1, 2, 3...)은 독립적으로 관리됩니다. 각 모듈은 다른 모듈에 대한
의존성(dependency)이 다르기 때문에 마구잡이로 설치하다보면 이유 모를 충돌이 날 수도 있습니다. 따라서 각 프로젝트 별로 별개의 가상환경을
만들어놓고 사용하는것이 좋습니다.

가상환경을 사용하는 이유는, 같은 모듈을 사용한다고 하더라도 다른 버전을 필요로 한다거나, Python프로그램을 실행하기 위해 최소한의 환경을
마련하고자 할 때나, GitHub 등의 저장소나 네트워크와 연계하고자 할 때 등으로 매우 다양합니다.

Python에서 가상환경을 만드는 방법은 크가지 2가지로 vituralenv와 conda를 사용합니다.

* PowerShell
가상환경을 구축 후 activate.bat이 아니라 activate.ps1를 실행해야 한다.
이 때 권한 문제로 오류가 뜰 수 있다. 권한 문제는 Powershell은 문제로 스크립트를 허용하지 않는다. 해결책은 Powershell 관리자 모드로 실행 후, 
```Set-ExecutionPolicy Unrestricted``` 커맨드를 실행하면 virtualenv가 잘 실행된다. 보안 오류의 문제는 해결되지만, Powershell 보안정책
을 꺼둔 것이므로, 주의해야한다.
또 다른 방법은 cmd로 변경 후 activate.bat을 실행하는 방법도 있다.
