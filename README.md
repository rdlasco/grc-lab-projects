# Projects-1-Compliance-Scan

## Executive Summary

This lab demonstrates a real-world compliance scan using the OpenSCAP security tool on a Red Hat-based system. The objective was to identify, analyze, and remediate key vulnerabilities based on the NIST 800-53 compliance framework.

The scan revealed three findings across high, medium, and low severity levels. The project prioritized remediation of those vulnerabilities based on potential business impact, ease of exploitation, and compliance alignment. Key actions included updating the system's cryptographic policy, ensuring critical audit packages were installed, and verifying log partition integrity.

This project highlights my ability to assess system hardening against federal standards, make informed decisions on remediation priorities, and document work clearly for both technical and non-technical stakeholders.


## Tools Used

- **OpenSCAP** – Used to conduct the initial system compliance scan against the NIST 800-53 baseline.
- **SCAP Workbench** – For reviewing rule results and visualizing compliance data.
- **Nano** – Text editor for writing and editing system files and this documentation.
- **Git & GitHub** – For professional documentation and portfolio hosting.
- **RHEL Terminal** – All commands and configurations were performed in a Red Hat Enterprise Linux 9 environment.


## Lab Overview

This lab focused on assessing and remediating system compliance using OpenSCAP on a Red Hat virtual machine. The evaluation was based on the NIST 800-53 security baseline, which is widely used in federal information systems. The primary objectives were to:

- Identify compliance gaps across high, medium, and low severity rules.
- Prioritize remediation efforts according to risk level and impact.
- Apply system hardening techniques and verify improvements by rescanning.
- Document all changes and findings in a clear, repeatable format.

The lab workflow followed a structured approach to scanning, analysis, remediation, and validation, simulating a real-world system hardening scenario in a controlled environment.


## Methodology

1. Preparation:

- Set up a Red Hat Enterprise Linux 9 (RHEL 9) virtual machine for testing.

- Updated the system to ensure all software was current.

- Installed required packages: OpenSCAP scanner and SCAP Security Guide.

2. Initial Compliance Scan:

- Conducted a baseline scan using OpenSCAP with the NIST 800-53 profile.

- Reviewed results to identify failed rules and noncompliant configurations.

3. Remediation:

Prioritized findings based on severity (high, medium, low).

- Applied fixes for selected high-priority issues, including enabling FIPS mode and installing missing tools.

- Rebooted the system as necessary to apply changes.

4. Verification:

- Reran the OpenSCAP scan to confirm remediation efforts.

- Compared initial and final results to demonstrate improved compliance.


## Findings and Remediation

The OpenSCAP scan reported several compliance issues of varying severity. Below is a summary of key findings and the remediation steps performed:

### High Severity Findings
- **Enable FIPS Mode:** 
  - *Finding:* The system was not running in FIPS mode initially. 
  - *Remediation:* Enabled FIPS mode using `fips-mode-setup --enable` and updated the system's cryptographic policies accordingly. Rebooted the system to apply changes.

### Medium Severity Findings
- **Install and configure gnutls-utils:**
  - *Finding:* gnutls-utils was not installed, limiting cryptographic verification capabilities. 
  - *Remediation:* Installed with `sudo dnf install gnutls-utils`.
- **dnf-automatic not installed/configured:** 
  - *Finding:* Automated updates were not enabled for package management. 
  - *Remediation:* Installed and partially configured, but further automation setup is recommended.

### Low Severity Findings
- **/var/log/audit not on a separate partition:**
  - *Finding:* Audit logs were stored on the root filesystem rather than a dedicated partition. 
  - *Remediation:* Partitioning changes were not made in this lab environment but should be considered for production systems.

### Remaining Issues
Some medium and low severity findings were not fully remediated in this lab due to environment constraints or non-production context. These are documented in the full scan report for future action.


## Lessons Learned

This project reinforced the importance of automated security compliance scans in maintaining a secure system baseline. Key takeaways include:

- **Thorough Documentation:** Careful note-taking and documentation were crucial for tracking changes and understanding scan results.
- **Remediation Complexity:** Some findings, especially those involving partitioning and system cryptography, require planning and may involve service disruptions.
- **Iterative Hardening:** Security is an ongoing process. Automated scans provide direction, but continuous monitoring and periodic reviews are essential to ensure lasting compliance.
- **Tool Familiarity:** Gaining hands-on experience with OpenSCAP, SCAP Workbench, and RHEL command-line tools improved my ability to troubleshoot and remediate findings efficiently.

Moving forward, I plan to automate portions of the remediation process and to experiment with integrating OpenSCAP scans into CI/CD pipelines for proactive security management.


## Screenshots / Evidence

Below are selected screenshots representing key steps and evidence from the compliance project workflow. Additional images are available in the /screenshots/ folder.

- openscap-scanner_install.png — OpenSCAP scanner installed successfully.

- openscap-scanner-results_compliance-and-scoring.png — Initial compliance scan scoring and summary.

- openscap-scanner-results_pass-fail.png — Pass/fail breakdown of scan results.

- audit-partition-lsblk-output.png — Disk layout verification using lsblk.

- crypto-policies-config.png — System cryptography policy set to FIPS.

- fips-enabled-status.png — Confirming FIPS mode is enabled.

- kernel-boot-fips-check.png — Verifying FIPS parameter in kernel boot config.

- dracut-fips-regenerate-output.png — Output from regenerating initramfs for FIPS.

- openscap-scan-2-summary.png — Post-remediation scan summary and scoring.

- openscap-scan-2-rule-overview.png — Rule-by-rule overview of final scan.

For a full chronological set of screenshots, please see the /screenshots/ folder in this repository.



## References & Further Reading
- [OpenSCAP Project Documentation](https://www.open-scap.org/resources/documentation/)
- [NIST 800-53 Security Controls](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
- [Red Hat Security Compliance Tools](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9/html/security_hardening/index)
- [SCAP Security Guide](https://www.open-scap.org/security-policies/scap-security-guide/)
- [GitHub Docs: Managing your README file](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-readmes)


## Contact / About the Author

**Robert Lasco** 
Aspiring GRC Analyst & Cybersecurity Enthusiast 
[LinkedIn](https://www.linkedin.com/in/robertdlasco/) 
[GitHub](https://github.com/rdlasco) 
Email: rdlasco@gmail.com

*Feel free to connect with me on LinkedIn or GitHub for questions, collaboration, or professional opportunities.*

