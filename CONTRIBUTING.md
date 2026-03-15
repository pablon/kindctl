# Contributing to kindctl

## Quick Start

1. Fork and clone the repo
2. Create a branch: `git checkout -b feature/my-change`
3. Make changes and test
4. Submit a PR

## Code Style

- Run `shellcheck kindctl` before committing (must pass with zero warnings)
- Use `"${VARIABLE}"` quoting consistently
- Follow existing patterns in the codebase
- Add comments for non-obvious logic

## Testing

```bash
# Syntax check
bash -n kindctl

# Lint
shellcheck kindctl

# Dry-run test
./kindctl new test-cluster -d
```

## Pull Requests

- Keep changes focused and atomic
- Update README.md if adding features
- Describe what and why in the PR description

## Adding Components

When adding new Helm chart installations:

1. Add `install_<component>()` function
2. Include dry-run support: `if [ "${MODE}" == "dryrun" ]; then ...`
3. Add `kubectl wait` for pod readiness
4. Call from `create_cluster()`

## Questions?

Open an issue for discussion before large changes.
