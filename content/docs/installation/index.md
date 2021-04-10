---
title: 'Installation'
date: 2019-02-11T19:27:37+10:00
weight: 5
---

Basically, Heytaco Anywhere is self-managed service. So it is necesary to install in your infrastructure.

## Contents

* [Docker](#docker)
* [Kubernetes](#kubernetes)

## Docker

To install with Docker, follow the [Get started](/docs/get-started) document.

## Kubernetes

To install with Kubernete, it is required to apply the following YAML file. 

And we're also support the Helm chart, please this [document](https://github.com/heytaco-anywhere/helm-chart).

```yaml
kind: ConfigMap
apiVersion: v1
metadata:
  name: heytaco-anywhere
  labels:
    app.kubernetes.io/name: heytaco-anywhere
data:
  HEYTACO_ANYWHERE_SERVER_HOST: ""
  HEYTACO_ANYWHERE_SERVER_PROTO: "https"
  HEYTACO_ANYWHERE_HEYTACO_APP_SECRET: ""
  HEYTACO_ANYWHERE_SLACK_CHANNEL: ""
  HEYTACO_ANYWHERE_SLACK_CLIENT_ID: ""
  HEYTACO_ANYWHERE_SLACK_CLIENT_SECRET: ""
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: heytaco-anywhere
  labels:
    app.kubernetes.io/name: heytaco-anywhere
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: "8Gi"
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: heytaco-anywhere
  labels:
    app.kubernetes.io/name: heytaco-anywhere
spec:
  replicas: 1
  selector:
    matchLabels:
      app.kubernetes.io/name: heytaco-anywhere
  template:
    metadata:
      labels:
        app.kubernetes.io/name: heytaco-anywhere
    spec:
      containers:
        - name: heytaco-anywhere
          securityContext:
            null
          image: "heytacoanywhere/heytaco-anywhere:0.1"
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 8080
              protocol: TCP
          livenessProbe:
            httpGet:
              path: /healthz
              port: http
          resources:
            {}
          envFrom:
            - configMapRef:
                name: heytaco-anywhere
          volumeMounts:
            - name: storage-volume
              mountPath: /data
              subPath: ""
      volumes:
        - name: storage-volume
          persistentVolumeClaim:
            claimName: heytaco-anywhere
---
apiVersion: v1
kind: Service
metadata:
  name: heytaco-anywhere
  labels:
    app.kubernetes.io/name: heytaco-anywhere
spec:
  type: ClusterIP
  ports:
    - port: 80
      targetPort: http
      protocol: TCP
      name: http
  selector:
    app.kubernetes.io/name: heytaco-anywhere
---
apiVersion: networking.k8s.io/v1beta1
kind: Ingress
metadata:
  name: heytaco-anywhere
  labels:
    app.kubernetes.io/name: heytaco-anywhere
spec:
  rules:
    - host: "HEYTACO_ANYWHERE_SERVER_HOST"
      http:
        paths:
          - /
```
