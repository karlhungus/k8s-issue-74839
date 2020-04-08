# Reproduction of k8s issue #74839

## Howto

1. Create a cluster with at least 2 nodes.
1. Deploy the app.
```console
kubectl create -f https://raw.githubusercontent.com/anfernee/k8s-issue-74839/master/deploy.yaml
```

1. Check if the server crashed
```console
$ kubectl get pods
NAME                           READY   STATUS             RESTARTS   AGE
boom-server-59945555cd-8rwqk   0/1     CrashLoopBackOff   4          2m
startup-script                 1/1     Running            0          2m
```

## Reference

https://github.com/kubernetes/kubernetes/issues/74839

## Fix

use the damon.yaml deamonset

## Links

https://kubernetes.io/blog/2019/03/29/kube-proxy-subtleties-debugging-an-intermittent-connection-reset/
https://github.com/kubernetes/kubernetes/issues/45976
https://github.com/tcarmet/k8s-connection-reset
