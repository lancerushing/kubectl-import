# Kubectl-import

`kubectl-import` is a tool for importing a `kubectl` configuration file.

The imported file can be raw configuration files or base64-encoded version. Base64 is helpful for sharing using tools that impose maximum line size.

## Using

```console
kubectl-import new-ctx-name ~/Downloads/cluster-kubectl-config
```

The specified file is merged back to your kubectl config file - `~/.kube/config` by default, unless `KUBECONFIG` environment variable is set.

In order to write output to a different file, simply set `KUBECONFIG` variable - such as:

```console
KUBECONFIG=/tmp/kubectl-merged kubectl-import new-ctx-name-1 ~/Downloads/cluster-kubectl-config-1
KUBECONFIG=/tmp/kubectl-merged kubectl-import new-ctx-name-2 ~/Downloads/cluster-kubectl-config-2
```

## Installing

Simply download the script to a directory in your path. For example:

```console
sudo curl -o /usr/local/bin/kubectl-import https://raw.githubusercontent.com/lancerushing/kubectl-import/master/kubectl-import && sudo chmod 0755 /usr/local/bin/kubectl-import
```
