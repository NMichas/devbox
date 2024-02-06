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
Run the container:
```bash
docker run -ti nassos/devbox-heraclitus
```

Mounting local resources:
```bash
docker run -ti \
  -v $HOME/.kube:/root/.kube \
  -v $HOME/Projects:/root/Projects \
  nassos/devbox-heraclitus
```
