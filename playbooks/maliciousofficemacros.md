# Malicious Word Documents

## Hypothesis
Initial or refined hypothesis.

## Description
Brief description of the TTP or behavior you are looking for.

## Analytic 1 - Look for office tools launching powershell
image_path:powershell.exe AND (parent_image_path:winword.exe OR parent_image_path:excel.exe)

## Reference
Reference to the trigger.


## Reference(s)
- https://attack.mitre.org/techniques/Txxxx/
