# Hunt for malicious PowerShell by identifying 

## Hypothesis
Threat Actors are avoiding detection and executing malicious scripts using encoded PowerShell scripts.

## Description
Multiple Threat Intelligence sources indicate PowerShell as one of the most common methods of executing malware and bypassing security controls.

## Analytic 1 - Encoded PowerShell
Look for PowerShell.exe as the Image with Commandlines that are encoded.

## Reference Information/Hunters Notes
MITRE Reference(s)
- https://attack.mitre.org/techniques/T1086/

