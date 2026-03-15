# kindctl

CLI wrapper for [kind](https://kind.sigs.k8s.io/) that creates fully-configured local Kubernetes clusters with one command.

## Features

- Interactive cluster creation with version selection via `fzf`
- Auto-installs: MetalLB, ingress-nginx, cert-manager, Caretta
- Separate kubeconfig per cluster (`~/.kube/configs/`)
- Works great with [kubie](https://github.com/kubie-org/kubie)

## Requirements

`curl` `fzf` `jq` `docker` `helm` `kind` `kubectl`

## Usage

```bash
kindctl new [name] [-d]   # Create cluster (-d for dry-run)
kindctl get               # Get kubeconfig for existing cluster
kindctl del [name]        # Delete cluster
kindctl -h                # Help
```

## Example

```bash
# Create a new cluster (interactive prompts for name, version, nodes)
kindctl new

# Preview what would be created
kindctl new my-cluster -d

# Create cluster with specific name
kindctl new my-cluster
```

## Contributing

[Contributing Guide](CONTRIBUTING.md)

## License

[GPL v3.0](LICENSE.md) - feel free to use, modify, and share.
