# Title: Host Discovery Commands
## Hypothesis
Adversaries are gaining knowledge about the environment by running "host discovery commands" hosts in my environment.

Example Host Discovery Commands
- hostname
- ipconfig
- net
- quser
- qwinsta
- sc with flags query, queryex, qc
- systeminfo
- tasklist
- dsquery
- whoami

## Analytic 1 - 
Look for multiple host discovery commands being ran on a host.

## Analytic 2 
Look for host discovery commands being ran from where cmd.exe has unusual parent process


## Reference
- https://car.mitre.org/analytics/CAR-2016-03-001/
- https://attack.mitre.org/techniques/T1087/
- https://attack.mitre.org/techniques/T1069/
- https://attack.mitre.org/techniques/T1016/
- https://attack.mitre.org/techniques/T1082/
- https://attack.mitre.org/techniques/T1033/
- https://attack.mitre.org/techniques/T1057/
- https://attack.mitre.org/techniques/T1007/