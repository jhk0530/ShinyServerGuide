---
description: 'https://docs.rstudio.com/shiny-server/#stopping-and-starting'
---

# 1.4 서버 정지 및 시작

 The installer will automatically deploy the necessary scripts to ensure that Shiny Server is started automatically on boot. When possible, we use systemd or Upstart to manage the `shiny-server` service. If neither is available, we will deploy an `init.d` script to start and stop the service automatically.

