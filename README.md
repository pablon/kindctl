# kindctl

CLI wrapper for [kind](https://kind.sigs.k8s.io/) that creates fully-configured local Kubernetes clusters with one command.

**Version:** 0.1.0

## Features

- Interactive cluster creation with version selection via `fzf`
- Auto-installs: MetalLB, ingress-nginx, cert-manager, Caretta
- Separate kubeconfig per cluster (`~/.kube/configs/`)
- Optional port mappings (80/443) with conflict detection
- Multi-node cluster support (up to 3 nodes)
- Automation support with `--yes` flag
- Works great with [kubie](https://github.com/kubie-org/kubie)

## Requirements

`curl` `fzf` `jq` `docker` `helm` `kind` `kubectl`

## Usage

```bash
kindctl <command> [name] [options]

Commands:
  new [name]       create a cluster
  list             list all clusters with kubeconfig locations
  status [name]    show cluster status and health
  del [name]       delete an existing cluster

Options:
  -d, --dry-run    preview changes without executing
  -y, --yes        skip confirmation prompts
  -h, --help       show this help
  -v, --version    show version

Examples:
  kindctl new              # Interactive cluster creation
  kindctl new demo -d      # Dry-run for cluster 'demo'
  kindctl list             # List all clusters
  kindctl status demo      # Check cluster 'demo' status
  kindctl del demo -y      # Delete cluster 'demo' without confirmation
```

## Contributing

[Contributing Guide](CONTRIBUTING.md)

## License

[GPL v3.0](LICENSE) - feel free to use, modify, and share.
