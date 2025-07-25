# Ubuntu 24.04 LTS CIS Benchmarks for Fleet

[![CIS Benchmarks](https://img.shields.io/badge/CIS-Ubuntu%2024.04%20LTS-blue)](https://www.cisecurity.org/cis-benchmarks)
[![Fleet Compatible](https://img.shields.io/badge/Fleet-4.0%2B-green)](https://fleetdm.com/)
[![osquery Compatible](https://img.shields.io/badge/osquery-5.17.0%2B-orange)](https://osquery.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A complete, production-ready implementation of **CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0** security policies for Fleet device management platform.

## 🚀 Quick Start

1. **Download** the `cis-policy-queries.yml` file from this repository
2. **Upload** to Fleet using fleetctl
3. **Deploy** policies to your Ubuntu 24.04 LTS hosts
4. **Monitor** compliance in Fleet dashboard

## 📋 What's Included

### 🛡️ **172 Security Controls**
- **Level 1 (Basic)**: Essential security configurations
- **Level 2 (Advanced)**: Comprehensive security hardening
- **All major sections**: Filesystem, services, network, logging, access control, maintenance

### 🎯 **Coverage Areas**
- **Initial Setup**: Filesystem configuration, package management, mandatory access control
- **Services**: Disable unnecessary services, configure essential services
- **Network**: IP forwarding, packet routing, firewall configuration  
- **Logging & Auditing**: System event monitoring, log management
- **Access Control**: SSH hardening, user management, authentication
- **System Maintenance**: File permissions, user accounts, system updates

## 🔧 Requirements

| Component | Version | Notes |
|-----------|---------|-------|
| **Fleet** | 4.0+ | Device management platform |
| **osquery** | 5.17.0+ | Query engine |
| **Ubuntu** | 24.04 LTS | Target operating system |
| **Permissions** | Admin/Root | Required for system queries |

## 📦 Installation

### Fleet CLI (fleetctl)
```bash
# Install fleetctl
https://fleetdm.com/guides/fleetctl#installing-fleetctl

# Configure Fleet connection
fleetctl config set --address https://your-fleet-instance.com

# Upload policies
fleetctl apply -f cis-policy-queries.yml
```

## ✅ Validation & Testing

### Policy Verification
Each policy returns:
- **1** = **PASSING/COMPLIANT** (secure configuration detected)
- **0** = **FAILING/NON-COMPLIANT** (security issue found)

## 📊 Policy Categories

| Section | Policies | Level | Description |
|---------|----------|-------|-------------|
| **1. Initial Setup** | 48 | 1 & 2 | Filesystem configuration, software updates, mandatory access control, boot settings, process hardening |
| **2. Services** | 26 | 1 & 2 | Time sync, special purpose services, client services |
| **3. Network** | 22 | 1 & 2 | Network parameters, firewall configuration |
| **4. Logging & Auditing** | 28 | 1 & 2 | rsyslog, journald, auditd configurations |
| **5. Access Control** | 28 | 1 & 2 | SSH server hardening, PAM, user environment |
| **7. System File Permissions** | 20 | 1 & 2 | File permissions and user/group settings |

**Total: 172 comprehensive security policies**

## 🛠️ Customization

### Modifying Policies
1. **Edit queries** in the YAML file to match your environment
2. **Adjust tags** for custom categorization
3. **Update descriptions** for organization-specific guidance

### Example Customization
```yaml
# Custom remediation for your environment
resolution: |
  Run the following command on your systems:
  ansible-playbook -i inventory site.yml --tags=cis-1.1.2.1.1
```

### Environment-Specific Adjustments
- **Development**: Disable certain strict policies
- **Production**: Enable all Level 1 + critical Level 2 policies
- **Compliance**: Enable all policies for audit requirements

### Getting Help
- **Fleet Documentation**: [https://fleetdm.com/docs](https://fleetdm.com/docs)
- **osquery Documentation**: [https://osquery.readthedocs.io](https://osquery.readthedocs.io)
- **CIS Benchmarks**: [https://www.cisecurity.org/cis-benchmarks](https://www.cisecurity.org/cis-benchmarks)

## 🤝 Contributing

### Reporting Issues
1. **Check existing issues** before creating new ones
2. **Provide details**: osquery version, Fleet version, error messages
3. **Include examples**: failing queries, expected vs actual results

### Contributing Improvements
1. **Fork** this repository
2. **Create feature branch**: `git checkout -b feature/improvement-name`
3. **Test thoroughly** with osquery and Fleet
4. **Submit pull request** with detailed description

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚖️ Legal & Compliance

- **CIS Benchmarks**: Policies based on CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0
- **Usage Rights**: Free for commercial and non-commercial use
- **Warranty**: Provided "as-is" without warranty
- **Liability**: Users responsible for testing and validation in their environments

## 🙏 Acknowledgments

- **Center for Internet Security (CIS)** for the Ubuntu 24.04 LTS Benchmark
- **Fleet Team** for the device management platform
- **osquery Community** for the query engine
- **Contributors** who helped test and improve these policies

## 📈 Stats

- **🎯 172 policies** covering comprehensive security controls
- **✅ 100% schema validated** against osquery 5.17.0
- **🔧 Production tested** on Ubuntu 24.04 LTS systems
- **📊 Fleet compatible** with proper pass/fail logic

---

**Ready to secure your Ubuntu fleet?** Download the YAML file and start monitoring CIS compliance today! 🚀
