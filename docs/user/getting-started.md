# Getting Started Guide

This guide will help you set up Ansible Automation Platform (AAP) 2.5 on OpenShift using the provided manifests.

## Prerequisites

1. OpenShift Cluster Access
   ```bash
   export KUBECONFIG=/home/student/cluster/auth/kubeconfig
   ```

2. Verify ODF Storage Class Availability
   ```bash
   oc get sc
   ```
   The deployment requires the ODF storage class (ocs-storagecluster-ceph-rbd) for PostgreSQL persistence.

## Deployment Steps

### 1. Create Namespace
```bash
# Create the AAP namespace with monitoring enabled
oc apply -f manifests/01-namespace.yaml
```

### 2. Deploy AAP
```bash
# Deploy the Automation Controller
oc apply -f manifests/02-aap.yaml
```

### 3. Verify Deployment

1. Check namespace creation:
   ```bash
   oc get ns ansible-automation-platform
   ```

2. Monitor deployment progress:
   ```bash
   oc get pods -n ansible-automation-platform
   ```

3. Verify storage provisioning:
   ```bash
   oc get pvc -n ansible-automation-platform
   ```

4. Check route availability:
   ```bash
   oc get route -n ansible-automation-platform
   ```

## Next Steps

- Review the [Controller Configuration Guide](../configure-controller.md)
- Check the [Troubleshooting Guide](troubleshooting.md) if you encounter issues 