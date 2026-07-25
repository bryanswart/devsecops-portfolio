# DevSecOps Portfolio — Bryan Swart

Security engineering in practice. This portfolio documents my transition from 20+ years of enterprise GRC and NIST framework work into hands-on DevSecOps engineering — building the pipelines, infrastructure, and container platforms where security controls actually live.

Each project is built to demonstrate a real skill, not a tutorial walkthrough. Security decisions are documented with NIST 800-53 control mappings because that's how I think about security — in terms of what the control requires and how the implementation satisfies it.

---

## Projects

### Project 1 — CDP Pipeline Security Demo
**Status:** 🔄 In Progress (Phase 1 — Week 22 target)  
**Repo:** *(link coming)*

A Python web application with a complete GitHub Actions security pipeline:

| Tool | Type | What It Catches |
|---|---|---|
| Bandit | SAST | Python code vulnerabilities (injection, weak crypto, hardcoded secrets) |
| Safety | SCA | Known CVEs in Python dependencies |
| TruffleHog | Secrets Scan | Accidentally committed credentials in Git history |
| OWASP ZAP | DAST | Runtime web vulnerabilities (OWASP Top 10) |
| InSpec | Compliance as Code | Linux hardening checks mapped to NIST 800-53 controls |

The pipeline blocks merges when critical findings are present. InSpec profiles test CIS benchmark requirements and NIST AC-2 (Account Management) controls directly.

---

### Project 2 — Three-Tier AWS Architecture (Terraform + Checkov)
**Status:** ⬜ Planned — Phase 3 (Week 38 target)  
**Repo:** *(link coming)*

A production-realistic AWS architecture deployed entirely via Terraform, with IaC security scanning in the CI pipeline:

- VPC with public, private, and database subnets — strict security group rules between tiers
- EC2 (web tier), RDS MySQL with encryption at rest (DB tier)
- Checkov scanning on every pull request — pipeline blocks on HIGH/CRITICAL findings
- CloudTrail + VPC Flow Logs deployed as Terraform resources
- Security controls table: each NIST 800-53 control the architecture implements, mapped to the specific Terraform resource that satisfies it

---

### Project 3 — Kubernetes GitOps App (ArgoCD + OPA Gatekeeper + Falco)
**Status:** ⬜ Planned — Phase 4 (Week 58 target)  
**Repo:** *(link coming)*

A containerized application deployed to Kubernetes using a GitOps workflow, secured with policy-as-code enforcement and runtime threat detection:

- ArgoCD manages all deployments from Git — every change is auditable (NIST AU-2, CM-3)
- OPA Gatekeeper enforces admission policies: no root containers, resource limits required, no privileged pods
- Falco provides runtime alerting with custom rules for this application
- RBAC: ServiceAccounts with minimum required permissions; Pod Security Standards at `restricted` level
- kube-bench cluster score documented in the README

---

## Certifications

| Credential | Status |
|---|---|
| ISC2 Certified in Cybersecurity (CC) | ✅ |
| OneTrust CPMP | ✅ |
| ServiceNow CAD / CSA | ✅ |
| CompTIA Security+ SY0-701 | 🔄 In Progress |
| Certified DevSecOps Professional (CDP) | 🔄 In Progress |
| CRISC — ISACA | 🔄 In Progress |
| AWS Cloud Practitioner | ⬜ Planned |
| AWS Solutions Architect Associate | ⬜ Planned |
| AWS Security Specialty | ⬜ Planned |

---

## The GRC-to-DevSecOps Bridge

Most DevSecOps engineers know the tools. Fewer know what the controls actually require and why. My background in NIST 800-53, risk management, and compliance program design means I approach every tool integration with the question: *what control does this satisfy, and what evidence does it produce?*

That framing shows up throughout this portfolio — in the NIST control mapping tables, in the InSpec profiles written against real requirements, and in the incident response runbooks structured around NIST 800-61.

---

## Contact

- LinkedIn: [linkedin.com/in/bryan-swart](https://www.linkedin.com/in/bryan-swart)
- GitHub: [github.com/bryanswart](https://github.com/bryanswart)
