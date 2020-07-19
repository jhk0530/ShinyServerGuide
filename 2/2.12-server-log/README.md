---
description: 'https://docs.rstudio.com/shiny-server/#server-log'
---

# 2.12 Server Log

All information related to Shiny Server itself, rather than a particular Shiny application, is logged in the global system log stored in `/var/log/shiny-server.log`. This log should be checked often to ensure Shiny Server is performing as expected. Any errors and warnings that Shiny Server needs to communicate will be written here.

If `logrotate` is available when Shiny Server is installed, a `logrotate` configuration will be installed. The default configuration is to rotate the logfile when it exceeds 1MB in size. The old log file will be compressed and stored alongside the original log file with a `.1.gz` extension \(then `.2.gz`, etc.\). Up to twelve archived log files will be maintained; upon the thirteenth log rotation, the oldest log file will be deleted.

For logs related to individual Shiny Applications, see the section on [Logging and Analytics](https://docs.rstudio.com/shiny-server/#logging-and-analytics).

