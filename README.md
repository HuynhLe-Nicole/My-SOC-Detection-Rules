# My SOC Detection Rules
A practical collection of custom Sigma dectection rules for common cyber threats built, tested, and mapped to MITRE ATT&CK.

## Why It Matters
These rules show I can:
- Detect real attack patterns (ransomware, credential theft, phishing)
- Write clean, valid Sigma rules
- Align detections with MITRE ATT&CK

## Rules
Rule file                            Threat Detected                  MITRE ATT&CK
`powershell_encoded_command.yml`    Malicious encoded PowerShekk      T1059.001
`mimikatz_lsass_access.yml`         Credential dumping via LSASS      T1003.001
`ransomware_mass_file_rename.yml`   Ransomware file encryption        T1486
`office_macro_enabled.yml`          Phishing with malicious macros    T1566.001
`certutil_decode_suspicious.yml`    Living-off-the-land decoding      T1218
`psexec_remote_execution.yml`       Lateral movement with PsExec      T1021.002
`wmi_event_subscription.yml`        Persistence via WMI               T1047 
`dll_side_loading_rundll32.yml`     DLL side-loading abuse            T1574.002 
`scheduled_task_malicious.yml`      Abusive scheduled tasks           T1053.005 
`rdp_tunneling_unusual.yml`         Suspicious Remote Desktop use     T1021.001

## Testing
- Validated using **sigma-cli** (`v0.25+`)
- Tested against synthetic Window event logs (see `/test_logs/`)
- All rules pass `sigma rule-check`

## How to use 
1. Clone this repo
2. Covert rules to your SIEM format using [Sigma CLI]
   EX:
   ```bash
   sigma convert  --target splunk rules/powershell_encoded_command.yml
   

`
