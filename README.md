# Kubernetes How-To

## Pods

To list pods:

```
kubectl get pods
```

To view the descriptor of a pod in YAML:

```
kubectl get pods <pod-name> -o yaml
```

To view the descriptor of a pod in JSON:

```
kubectl get pods <pod-name> -o json
```

To create a pod from a YAML file:

```
kubectl create -f <yaml-file>
```

## Application Logs

To view a pod's logs:

```
kubectl logs <pod-name>
```

To veiw the logs of a container running in a pod:

```
kubectl logs <pod-name> -c <container-name>
```

## Port Forwarding

To forward a local port to a pod's port:

```
kubectl port-forward <pod-name> <local-port>:<pod's-port>
```

## Labels

To provide labels when creating a pod:

```
...
metadata:
  labels:
    <label-key-0>: <label-value-0>
    ...
    <label-key-n>: <label-value-n>
...
```

To create a label on an existing pod:

```
kubectl lobel pod <pod-name> <label-key>=<label-value>
```

To modify a label on an existing pod:

```
kubectl lobel pod <pod-name> <label-key>=<label-value> --overwrite
```

To list all labels attached to pods:

```
kubectl get pods --show-labels
```

To list specific labels attached to pods:

```
kubectl get pods -L <label-key>[,<label-key>[,...]]
```

## Label Selectors

To list pods with labels with particular values attached:

```
kubectl get pods -l <label-key>=<label-value>[,...]
```

To list pods with labels attached, regardless of values:

```
kubectl get pods -l <label-key>[,...]
```

To list pods that do **NOT** have the specified labels attached:

```
kubectl get pods -l '!<label-key>'[,...]
```

To list pods with labels **NOT** equal to particular values attached:

```
kubectl get pods -l <label-key>!=<label-value>[,...]
```

To list pods with labels values in a particular list of values:

```
kubectl get pods -l <label-key> in (<label-value>,<label-value>[,...])
```

To list pods with labels values **NOT** in a particular list of values:

```
kubectl get pods -l <label-key> notin (<label-value>,<label-value>[,...])
```

## Nodes

To create a label on an existing node:

```
kubectl lobel node <node-name> <label-key>=<label-value>
```

To list pods with labels with particular values attached:

```
kubectl get nodes -l <label-key>=<label-value>[,...]
```

## Annotations

To add an annotation to a pod:

```
kubectl annotate pod <pod-name>  -l <annotation-key>=<annotation-value>[,...]
```

To view the annotations on a pod:

```
kubectl describe pod <pod-name>
```

## Namespaces


