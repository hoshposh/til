# Exec Shell Into A Pod's Container

Simple enough pattern or approach to take when you need to execute shell commands inside a Pod's containers.

## Invocation

Run the following exec command to get a steel inside a pod's container:

```bash
kubectl exec --stdin --tty pod-name -- /bin/bash
```

or

```bash
kubectl exec -i -t pod-name -c container-name -- /bin/bash
```

## Reference

- https://kubernetes.io/docs/tasks/debug-application-cluster/get-shell-running-container/