# Stalwart Mail Helm Chart

```bash
$ helm install stalwart-mail . -f your-values.yaml
```

## Values:

```yaml
replicaCount: 1

image:
  repository: stalwartlabs/mail-server
  pullPolicy: IfNotPresent
  # Overrides the image tag whose default is the chart appVersion.
  tag: ""

persistence:
  enabled: true
  storageClass: ""
  accessMode: ReadWriteOnce
  size: 10Gi
  mountPath: /opt/stalwart-mail
```

## Resources

```
pod         stalwart-mail-0
service     stalwart-mail          LoadBalancer 8080/TCP,443/TCP,25/TCP,587/TCP,465/TCP,143/TCP,993/TCP,4190/TCP
service     stalwart-mail-headless ClusterIP    8080/TCP,443/TCP,25/TCP,587/TCP,465/TCP,143/TCP,993/TCP,4190/TCP
statefulset stalwart-mail
```
