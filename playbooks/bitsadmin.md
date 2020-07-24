# BitsAdmin Abuse

## Hypothesis
Adversaries are abusing BITS

## Description
BITSAdmin is a command line tool used to create and manage BITS Jobs. [1]

## Check existing saved searches, watchlists, etc

## Analytics
- Analytic: Powershell BITSAdmin Downloader

|Field|Condition|Term|
|---|---|---|
|image_path|Contains|powershell.exe|
|commandline|Contains|BitsTransfer|
|commandline|Does Not Contain|-retryinterval|
|commandline|Does Not Contain|Remove-BitsTransfer|
|commandline|Does Not Contain|Get-BitsTransfer|

- Analytic: Suspicious stop of Background Intelligent Transfer (BITS) service

|Field|Condition|Term|
|---|---|---|
|image_path|Contains|net.exe|
|commandline|Contains|BitsTransfer|
|commandline|Contains|bits|
|commandline|Contains|stop|
|commandline|Contains|/y|

- Analytic: BITSAdmin Uploader

|Field|Condition|Term|
|---|---|---|
|image_path|Contains|bitsadmin.exe|
|commandline|Contains|/upload|

- Analytic: BITSAdmin File Download

|Field|Condition|Term|
|---|---|---|
|image_path|Contains|bitsadmin.exe|
|commandline|Contains|/create|
|commandline|Contains|/addfile|

- Analytic: BITSadmin file transfer 2

|Field|Condition|Term|
|---|---|---|
|image_path|Contains|cmd.exe|
|commandline|Contains|bitsadmin|
|commandline|Contains|/transfer|
|commandline|Does Not Contain|"Known Good"|

## Leucene Queries
- `image_path:bitsadmin.exe AND -commandline:(list OR getieproxy OR reset OR setieproxy OR info)`
- `commandline:"bitstransfer" AND -commandline:"allusers"`
- `commandline:SetNotifyCmdLine`

## Reference(s)
- https://lolbas-project.github.io/lolbas/Binaries/Bitsadmin/
- https://www.dfrws.org/sites/default/files/session-files/pres-finding_your_naughty_bits.pdf
- https://isc.sans.edu/forums/diary/Investigating+Microsoft+BITS+Activity/23281/
