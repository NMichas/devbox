#  Heraclitus
- [x] Ubuntu 22.04
- [x] Java 17 (OpenJDK)
- [x] Maven
- [x] Git
- [x] kubectl
- [x] Helm
- [x] Helmfile
- [x] kubens & kubectx
- [x] kube-ps1

## Usage
### Docker
```shell
docker run -ti \
  --name devbox \
  nassos/devbox-heraclitus
```

### Kubernetes
```shell
kubectl run devbox -ti \
  --image nassos/devbox-heraclitus \
  --restart Never
```
