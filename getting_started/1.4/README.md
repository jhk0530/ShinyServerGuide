---
description: 'https://docs.rstudio.com/shiny-server/#stopping-and-starting'
---

# 1.4 서버 정지 및 시작

인스톨러는, `Shiny Server`가 PC의 부팅이후, 자동으로 실행 되는데 필요한 스크립트 들을 설치 합니다. 이는 `systemd` 혹은 `Upstart` 를 이용하여 이루어집니다. 만약 두 가지가 전부 불가능 한 경우, **init.d** 스크립트를 통해 서비스의 시작과 중지를 실행합니다.

