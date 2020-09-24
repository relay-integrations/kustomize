# kustomize-step-apply

The Kustomize step container applies Kubernetes kustomizations.

## Examples

Here is an example of the step in a Relay workflow:

```YAML
steps:

...

- name: kustomize
  image: relaysh/kustomize-step-apply
  spec:
    cluster:
      name: my-cluster
      connection: !Connection { type: kubernetes, name: my-cluster }
    path: /infra/app
    namespace: my-namespace
    git:
      ssh_key:
        $type: Secret
        name: ssh_key
      known_hosts:
        $type: Secret
        name: known_hosts
      name: my-git-repo
      branch: dev
      repository: path/to/your/repo
```
