# WinGuard-Windows-Hardening
A powershell script that checks a windows 11 machine against 15 security settings, giving a security score, and can optionally fix the failing settings.

# Requirements
- Windows 11 (Enterprise recommended; BitLocker and LSA protection need it)
- Windows PowerShell 5.1 or later
- Run as Administrator
- Use on a test VM only; Apply mode changes real security settings

# How to run
Open PowerShell as Administrator in the script's folder, then:

    .\Harden-Windows.ps1               # Audit only, changes nothing
    .\Harden-Windows.ps1 -Mode Apply   # Audit, fix, then audit again

If the script is blocked, run `Unblock-File .\Harden-Windows.ps1` first.

# Output
A report is saved to `C:\Users\<you>\WinGuard_reports`, showing PASS/FAIL for each control and a score rated STRONG, MODERATE, or NEEDS WORK.

# Notes
- BitLocker is audit only; enable it manually with `manage-bde -on C:`
- UAC and LSA protection changes need a reboot
- Turn off Defender Tamper Protection before Apply mode, or Defender fixes will fail

## AI assistance
Copilot was used to help me debug issues that came up.
