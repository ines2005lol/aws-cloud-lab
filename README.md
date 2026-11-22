# AWS Cloud Networking Labs

Hands-on labs where I learn AWS networking and cloud security by building things myself, one small step at a time.

I'm a computer science student interested in cybersecurity and cloud. Each lab documents what I actually configured, why each component exists, and the security decisions behind it. These are learning environments, not production architectures.

---

## Labs

| # | Lab | Topics | Status |
|---|---|---|---|
| 01 | [VPC, Public Subnet, and EC2 over SSH](lab-01-vpc-ec2-ssh/README.md) | VPC, Internet Gateway, subnets, route tables, Security Groups, EC2, SSH key pairs | ✅ Completed |
| 02 | *Network connectivity and routing* | Public vs private IPs, DNS resolution, routing checks | 🔜 Planned |
| 03 | *Security Groups vs Network ACLs* | Stateful vs stateless filtering | 🔜 Planned |
| 04 | *Private subnet and secure access* | Private subnets, accessing private instances | 🔜 Planned |
| 05 | *IAM roles and EC2 hardening* | IAM roles for EC2, instance hardening | 🔜 Planned |

> Planned labs are ideas for what I'll learn next. They aren't done yet, and the list may change.

---

## Repository structure

```
aws-cloud-networking-lab/
├── README.md                  ← you are here (intro + lab index)
├── .gitignore                 ← keeps private keys and credentials out of Git
└── lab-01-vpc-ec2-ssh/
    └── README.md              ← full write-up for Lab 01
```

Each lab folder has its own `README.md` with:

- the objective and what I built
- an architecture diagram (Mermaid)
- the resource configuration (names, IDs, CIDRs)
- an explanation of each component
- security and cost notes
- next steps

---

## Environment

| | |
|---|---|
| **Cloud provider** | Amazon Web Services (AWS) |
| **Region** | `eu-north-1` (Europe – Stockholm) |
| **Local machine** | Windows, using PowerShell and the built-in OpenSSH client |
| **Setup method** | AWS Management Console |

---

## General principles I follow

### Security

- **Least exposure:** only open the ports that are needed, and only to the sources that need them (for example, SSH limited to my own IP with `/32`).
- **Key-based authentication** instead of passwords for remote access.
- **No secrets in Git:** private keys (`.pem`), AWS access keys, and account IDs are never committed. Resource IDs and network settings are documented because they aren't secrets on their own.
- **Be honest about limitations:** each lab says what it does *not* cover.

### Cost

AWS resources can cost money, even in small labs. Things like running instances, public IPv4 addresses, and storage volumes can be billed. Free Plan eligibility and credits depend on the account, so I check the **Billing and Cost Management** console instead of assuming anything is free, and I stop or terminate resources when I'm done.

---

## Disclaimer

These labs are for learning. The configurations are intentionally simple and are not meant to be used as-is in production.
