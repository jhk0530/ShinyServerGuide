---
description: 'https://docs.rstudio.com/shiny-server/#run_as'
---

# 2.3 run\_as

어느 사용자가 R Shiny 프로세스들을 실행하는지 이해 하는 것은 다양한 이유에서 중요합니다. 한가지 예를 들자면, R이 패키지들을 위해 확인할 경로들과 \(.libPaths\(\)\) 는 주로 사용자와 연관이 있습니다. Shiny application이 실행 되기 위해 필요한 라이브러리들이 설치 되어있는 것을 확실히 하기 위해서, 우선 어떤 사용자가 application을 실행할지 반드시 알아야 합니다.추가로, 특정 사용자에게 쓰거나 읽는게 허용된 부분에 대해서만 디렉토리 접근을 허가 해야 합니다. 즉, 서버는 사용자가 shiny application을 실행하기 위한 최소한의 권한만을 허용하게 설정 되어야 합니다. 

user\_apps를 통해 설정되는 location들은 각 사용자의 application이 발견된 홈 디렉토리로 실행 될 것입니다. site\_dir, user\_dirs, 그리고 app\_dir를 통해 구성된 location의 경우, run\_as 설정이 어느 사용자가 R Shiny process를 실행할지를 결정하게 됩니다. 이러한 설정은 전역에 대하여 혹은 특정 server나 location에 대해서만 구성 하게끔 설정 할 수 있습니다. 예를 들어, 아래의 설정은 : 

```text
location / {
  run_as tim;
}
```

이 범위 \(/\) 에 포함되는 모든 application을 사용자 teim 과 tim의 .libpath를 사용하여 실행 할 것입니다. 

추가로, R process들은 Bash login shell을 통해 실행됩니다. 이는 R session의 실행에 앞서, Bash shell이 이 명령어 file이 존재 하는 경우 우선적으로 읽고 실행 할 것입니다:

```
/etc/profile
```

해당 파일을 읽은 후에, 다음과 같은 파일 순서대로 가능하면 읽고 실행 할 것입니다. \(이들 중 단 1개만 읽고 실행되는 것을 주의하십시오.\)

```text
~/.bash_profile
~/.bash_login
~/.profile
```

위 예시와 같은 설정에서, /etc/profile 혹은 /home/tim/.bash\_profile에 정의된 환경 변수 \(tim의 홈 디렉토리가 정상적인 위치에 있다고 가정\)는 Shiny server가 application을 사용자 tim으로 실행 하게 했기 때문에 R process에서 사용 가능 할 것입니다. 

