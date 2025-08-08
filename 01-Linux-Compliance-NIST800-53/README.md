# Linux Compliance Scan & Remediation - NIST 800-53

## Executive Summary
_A brief overview of what the project is and why it matters._
> Example:  
> This project demonstrates how to assess and remediate compliance gaps on a Linux system using OpenSCAP and the NIST 800-53 security controls framework. The goal is to show practical experience in continuous monitoring, risk reduction, and audit readiness.

## Tools & Environment
- OS: Red Hat Enterprise Linux 9.6 (VM)
- Tools: OpenSCAP, SCAP Security Guide,
- Terminal (for command line operations)

## Steps Taken
1. Installed OpenSCAP and SCAP Security Guide using dnf (to enable NIST scanning): sudo dnf install openscap-scanner scap-security-guide
2. Ran a compliance scan with the NIST 800-53 moderate profile
3. Reviewed the HTML report and identified top 3-5 failing controls
4. Remediated issues (e.g., hardened SSH, set password policy, enabled firewall)
5. Re-ran scan to verify remediation
6. Documented results and lessons learned

## Key Findings & Remediation
_Detail the security gaps you found, why they matter, and what you did to fix them._
| Control | Issue Found        | Risk Level | Remediation Step                   |
|---------|--------------------|------------|------------------------------------|
| AC-6    | SSH root enabled   | High       | Disabled root login in sshd_config |
| IA-5    | Weak password policy | Medium   | Enforced password length/min complexity |
| CM-7    | Unnecessary services | Medium   | Disabled unused services           |

## Results
_Share before/after screenshots, report snippets, or summary stats._

## Compliance Mapping
_Which NIST 800-53 controls did your actions align with?_
- AC-6: Least Privilege
- IA-5: Authenticator Management
- CM-7: Least Functionality

## Lessons Learned
_Reflect on what you gained, challenges you hit, and how this is used in GRC work._
> Example:  
> This lab taught me the value of automated compliance scans, the importance of closing the remediation loop, and how even simple configuration oversights can cause real risk in federal systems.

## Appendix
_Add any raw scan reports, configs, or resources you used. Optional, but shows depth!_

