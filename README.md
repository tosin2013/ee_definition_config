# Ansible Automation Platform on OpenShift Configuration

This repository contains configuration and deployment files for setting up Ansible Automation Platform (AAP) 2.5 on OpenShift using OpenShift Data Foundation (ODF) storage.

## Documentation

### User Documentation
- [Getting Started Guide](docs/user/getting-started.md)
- [Troubleshooting Guide](docs/user/troubleshooting.md)

### Technical Documentation
- [Technical Implementation](docs/technical/implementation.md)
- [Security Guidelines](docs/technical/security.md)

### Architecture Decision Records (ADR)
- [ADR-0001: Use ODF for Storage](docs/adr/0001-use-odf-for-storage.md)
- [ADR-0002: Execution Environment Builder Architecture](docs/adr/0002-execution-environment-builder-architecture.md)
- [ADR-0003: Security Implementation Strategy](docs/adr/0003-security-implementation.md)
- [ADR-0004: Deployment Strategy](docs/adr/0004-deployment-strategy.md)
- [ADR-0005: Architectural Patterns and Component Organization](docs/adr/0005-architectural-patterns.md)
- [ADR-0006: Implementation and Documentation Alignment](docs/adr/0006-implementation-alignment.md)
- [ADR-0007: Gap Analysis and Implementation Status](docs/adr/0007-gap-analysis.md)
- [ADR-0008: GitOps-based Post-Deployment Configuration](docs/adr/0008-post-deployment-configuration.md)

### Additional Documentation
- [System Architecture](system_architecture.txt)
- [Technical Debt Tracking](technical_debt.txt)
- [Dependency Analysis](dependency_analysis.txt)

## Quick Start

1. Configure OpenShift access:
   ```bash
   export KUBECONFIG=/home/student/cluster/auth/kubeconfig
   ```

2. Follow the [Getting Started Guide](docs/user/getting-started.md) for detailed setup instructions.

## Repository Structure

```
.
├── docs/
│   ├── adr/               # Architecture Decision Records
│   │   └── 0001-use-odf-for-storage.md
│   ├── technical/         # Technical documentation
│   │   ├── implementation.md
│   │   └── security.md
│   └── user/             # User documentation
│       ├── getting-started.md
│       └── troubleshooting.md
├── gitops/              # GitOps configuration
│   ├── base/            # Base infrastructure configuration
│   ├── overlays/        # Environment-specific overlays
│   └── configuration/   # AAP configuration resources
├── manifests/           # Kubernetes/OpenShift manifests
│   └── 02-aap.yaml
└── system/             # System analysis and documentation
    ├── dependency_analysis.txt
    ├── system_architecture.txt
    └── technical_debt.txt
```

## Security Note

⚠️ This repository contains template files with placeholder values. Never commit actual credentials or sensitive information to version control.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.