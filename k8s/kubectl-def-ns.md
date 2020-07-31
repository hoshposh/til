# Kubectl Default Namespace

A way to set the namespace to be used on subsequent `kubectl` invocations.

## Invocation

Establish the default namespace with the following, where `xxxx` should be replaced with the namespace value:

```console
kubectl config set-context --current --namespace=xxxx
```

## References

* https://stackoverflow.com/a/56342073/43638
* https://kubernetes.io/docs/reference/kubectl/cheatsheet/