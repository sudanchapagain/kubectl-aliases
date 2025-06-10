# kubectl-aliases

[a script](generate_aliases.py) to generate hundreds of convenient shell
aliases for kubectl.

### examples

some of the 800 generated aliases are:

```sh
alias k='kubectl'
alias kg='kubectl get'
alias kgpo='kubectl get pod'

alias ksysgpo='kubectl --namespace=kube-system get pod'

alias krm='kubectl delete'
alias krmf='kubectl delete -f'
alias krming='kubectl delete ingress'
alias krmingl='kubectl delete ingress -l'
alias krmingall='kubectl delete ingress --all-namespaces'

alias kgsvcoyaml='kubectl get service -o=yaml'
alias kgsvcwn='kubectl get service --watch --namespace'
alias kgsvcslwn='kubectl get service --show-labels --watch --namespace'

alias kgwf='kubectl get --watch -f'
...
```

See [the full list](.kubectl_aliases).

### installation

you can directly download the [`.kubectl_aliases.nu` file](https://raw.githubusercontent.com/ahmetb/kubectl-aliases/master/.kubectl_aliases.nu)
for Nushell and save it to your `$HOME` directory.

add the following to your `~/.config/nushell/config.nu` file:

```nushell
source ~/.kubectl_aliases.nu
```

### syntax explanation

* **`k`**: `kubectl`
  * **`sys`**: `--namespace kube-system`
* commands:
  * **`g`**: `get`
  * **`d`**: `describe`
  * **`rm`**: `delete`
  * **`a`**: `apply -f`
  * **`ak`**: `apply -k`
  * **`k`**: `kustomize`
  * **`ex`**: `exec -i -t`
  * **`lo`**: `logs -f`
* resources: **:warning: Please do not suggest new resources here, instead fork the project.**
  * **`po`**: `pod`
  * **`dep`**: `deployment`
  * **`ing`**: `ingress`
  * **`svc`**: `service`
  * **`cm`**: `configmap`
  * **`sec`**: `secret`
  * **`ns`**: `namespace`
  * **`no`**: `node`
* flags:
  * output format: **`oyaml`**, **`ojson`**, **`owide`**
  * **`all`**: `--all` or `--all-namespaces` depending on the command
  * **`sl`**: `--show-labels`
  * **`w`**: `-w/--watch`
* value flags (should be at the end):
  * **`n`**: `-n/--namespace`
  * **`f`**: `-f/--filename`
  * **`l`**: `-l/--selector`

### running the script

The script has only one optional argument, the shell to which the aliases will be generated. If not given, it assumes `bash`. Ex:

```bash
# Generate aliases for bash/zsh
python generate_aliases.py > .kubectl_aliases

# Generate aliases for nushell
python generate_aliases.py nushell > .kubectl_aliases.nu
```

### authors

- [@ahmetb](https://twitter.com/ahmetb)

-----

This is not an official Google project.
