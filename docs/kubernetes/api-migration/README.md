# Check Kubernetes deprecated APIs

In order to do that, we'll be using `kube-no-trouble` tool.

[Github - kube-no-truble](https://github.com/doitintl/kube-no-trouble)

## Install
```
sh -c "$(curl -sSL https://git.io/install-kubent)"
```

## Usage
1. Check if you're in the right kubernetes cluster context
2. Run `kubent`
3. Check output and upgrade helm charts or yaml files.

