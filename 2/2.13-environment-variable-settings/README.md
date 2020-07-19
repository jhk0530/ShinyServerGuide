---
description: 'https://docs.rstudio.com/shiny-server/#environment-variable-settings'
---

# 2.13 Environment Variable Settings



We strive to expose most settings through the configuration file described previously. However, there are some settings that are not included in the configuration file that some users may still wish to change. Where possible, we allow users to configure these settings using environment variables. Some of these environment variables will later be promoted to configuration directives, but will be documented here until that time.

Typically, it is best to define these environment variables in the startup script used to run Shiny Server. This varies depending on which Linux distribution and version you are running.

**2.13.0.1 systemd \(RedHat 7, Ubuntu 15.04+, SLES 12+\)**

File to change:

```text
/etc/systemd/system/shiny-server.service
```

How to define the environment variable:

```text
[Service]
Environment="SHINY_LOG_LEVEL=TRACE"
```

Commands to run for the changes to take effect:

```text
$ sudo systemctl stop shiny-server
$ sudo systemctl daemon-reload 
$ sudo systemctl start shiny-server
```

**2.13.0.2 Upstart \(Ubuntu 12.04 through 14.10 and RedHat 6\)**

File to change:

```text
/etc/init/shiny-server.conf
```

How to define the environment variable:

```text
env SHINY_LOG_LEVEL=TRACE
```

Commands to run for the changes to take effect:

```text
$ sudo stop shiny-server
$ sudo start shiny-server
```

**2.13.0.3 init.d \(RedHat 5, SLES 11\)**

File to change:

```text
/etc/init.d/shiny-server
```

How to define the environment variable:

```text
export SHINY_LOG_LEVEL=TRACE
```

Commands to run for the changes to take effect:

```text
$ sudo /sbin/service shiny-server restart
```

