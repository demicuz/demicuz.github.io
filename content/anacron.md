---
title: "anacron"
date: "2023-01-19"
---

Execute jobs regularly. Differences from [[cron]]:
1. If a task is missed, it's launched anyway on the next system start up.
2. The minimal interval for tasks is one day.

On my system, anacron was set to not run jobs if on battery power. Do disable this "feature", edit `/etc/cron.hourly/0anacron`.

### Links
- [Automating System Tasks :: Fedora Docs](https://docs.fedoraproject.org/en-US/fedora/latest/system-administrators-guide/monitoring-and-automation/Automating_System_Tasks/)