# Abuse of Certutil

## Hypothesis
Initial or refined hypothesis.

## Description
The goal of this playbook is to review suspicious `certutil` usage.

## Analytics 

#### Powershell Using certutil to Add Certificate
Description: A process event activity associated with Powershell using certutil to add a certificate to a certificate store was identified. The presence of this activity may indicate that malware is running on the system.

|Field|Condition|Term|
|---|---|---|
|parent_image_path|Contains|powershell.exe|
|image_path|Contains|certutil.exe|
|commandline|Contains|addstore|
|commandline|Contains|TrustedPublisher|
|commandline|Contains|root|
|commandline|Does Not Contain|ccmcache|

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
