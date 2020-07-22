# Abuse of Certutil

## Hypothesis
Initial or refined hypothesis.

## Description
The goal of this playbook is to review suspicious `certutil` usage.

## Review existing watchlists
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/b139ec92-224b-4f50-b1d8-f5ff380ea454
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/d00204cc-eb0a-4cbf-bb28-723d69015ae9
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/17f805a5-2691-4c25-b172-a8d2fa7e161a
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/e2cb5824-677e-4c0c-ada3-08112f02da5b
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/3edd36c4-4d95-4c40-813e-25e10662fd5e
  - https://redcloak.secureworks.com/portal/countermeasures/watchlists/11411a9e-9eef-4cf1-a482-c429464db68a

## Analytic 1
`image_path:certutil.exe AND (commandline:urlcache OR commandline:url OR commandline:ping)`

`image_path:certutil.exe AND (commandline:http OR commandline:ftp)`

## Reference(s)
- https://lolbas-project.github.io/lolbas/Binaries/Certutil/
- https://attack.mitre.org/techniques/T1105/
- https://attack.mitre.org/techniques/T1140/
- https://attack.mitre.org/techniques/T1553/004/
- https://isc.sans.edu/forums/diary/Analyzis+of+a+Malicious+lnk+File+with+an+Embedded+Payload/20763/
- https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1105/T1105.md#atomic-test-8---certutil-download-verifyctl
- https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1105/T1105.md#atomic-test-7---certutil-download-urlcache
