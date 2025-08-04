# Istio
Repo for managing the configuration of istio across my homelab clusters.

## Notable Issues

If the cni-node daemonset fails to initialize with the error below, check the node's underlying VM configuration. In my case, I use Proxmox which will default to using the `kvm64` cpu type which has a reduced instruction set. Changing that to `host` should resolve the issue.

```bash
Error: failed to create ambient nodeagent service: error initializing mesh dataplane: error configuring iptables: failed to execute iptables-save: exit status 127 Fatal glibc error: CPU does not support x86-64-v2
```