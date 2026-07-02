
Active Directory Offensive Security Lab (Active Build)
📌 Project Overview

This repository documents the ongoing architecture, deployment, and eventual exploitation methodologies of a custom-built Active Directory (AD) home lab. The environment is designed to simulate a realistic enterprise network to practice offensive security techniques, vulnerability research, and the mapping of complex attack paths.

Current Project Status: Phase 2 (Infrastructure Provisioning) - In Progress
🗺️ Project Roadmap & Status
Phase 1: Attacker Infrastructure & Boundary Configuration (✅ Complete)

    Provisioned primary offensive machine (Kali Linux) utilizing a QEMU hypervisor on a Windows host.

    Engineered and deployed a persistent network share bridge between the Windows host and the isolated Kali VM.

    Automated the SMB boundary traversal using custom batch scripts to manage Windows SMB permissions and QEMU syntax, facilitating secure, rapid payload transfer and exfiltration testing.

Phase 2: Enterprise Network Topology Provisioning (🔄 In Progress - Expected July 2026)

    Deploy DC01 (Windows Server 2022) as the primary Domain Controller (CORP.LOCAL).

    Deploy WS01 (Windows 10 Enterprise) as a domain-joined workstation (simulated HR user).

    Deploy WS02 (Windows 11 Enterprise) as a domain-joined workstation (simulated IT Admin).

    Configure isolated virtual networking to model multi-subnet routing.

Phase 3: Environment Population & Misconfiguration (📅 Planned)

    Integrate BadBlood to automatically populate the CORP.LOCAL domain.

    Generate thousands of simulated users, groups, and organizational units (OUs).

    Randomize and assign complex, vulnerable Access Control Lists (ACLs) across the domain to create realistic exploitation vectors and "messy" enterprise conditions.

Phase 4: Offensive Tooling Deployment & Mapping (📅 Planned)

    SharpHound / BloodHound: Map object relationships and visualize multi-step privilege escalation paths via misconfigured ACLs and Group Policy Objects (GPOs).

    NetExec: Execute network service enumeration, credential spraying, pass-the-hash (PtH) attacks, and identify lateral movement opportunities.

    Impacket Suite: Test SMB relay attacks, Kerberoasting, and AS-REP Roasting.

🎯 Modeled Attack Paths (Upcoming Execution)

Once provisioning is complete, this lab will facilitate the execution and documentation of the following AD-specific attack methodologies:

    Initial Access & Enumeration: Establishing a foothold and running SharpHound ingress to map the domain architecture.

    Identity & Credential Theft: Executing Kerberoasting against Service Principal Names (SPNs) and AS-REP Roasting.

    Lateral Movement: Utilizing NetExec and compromised local administrator hashes to pivot between WS01 and WS02.

    Domain Escalation: Exploiting BadBlood-generated ACL misconfigurations (e.g., GenericAll, WriteDacl) to force password resets or DCSync attacks, ultimately resulting in Domain Admin compromise.
