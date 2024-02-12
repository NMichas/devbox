FROM ubuntu:24.04

ENV OPENJDK_VERSION=17
ENV KUBECTL_VERSION=1.29.1
ENV HELMFILE_VERSION=0.161.0
ENV HELM_VERSION=3.14.0

RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update && \
    apt-get install -y openjdk-${OPENJDK_VERSION}-jdk maven curl apt-transport-https git && \
    curl -L "https://dl.k8s.io/release/v${KUBECTL_VERSION}/bin/linux/amd64/kubectl" -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    curl -L https://github.com/helmfile/helmfile/releases/download/v${HELMFILE_VERSION}/helmfile_0.161.0_linux_amd64.tar.gz | tar -xz -C /usr/local/bin && \
    curl -L https://get.helm.sh/helm-v${HELM_VERSION}-linux-amd64.tar.gz | tar -xz -C /tmp && \
    mv /tmp/linux-amd64/helm /usr/local/bin/helm && \
    curl -L https://raw.githubusercontent.com/ahmetb/kubectx/master/kubens -o /usr/local/bin/kubens && \
    curl -L https://raw.githubusercontent.com/ahmetb/kubectx/master/kubectx -o /usr/local/bin/kubectx && \
    chmod +x /usr/local/bin/kubens /usr/local/bin/kubectx && \
    mkdir -p ~/.kube && \
    echo "export KUBECONFIG=\$(find ~/.kube -type f -name 'config-*' -exec echo -n {} \; -exec echo -n ':' \; | sed 's/:$//')" >> ~/.bashrc && \
    curl -L https://raw.githubusercontent.com/jonmosco/kube-ps1/master/kube-ps1.sh -o /usr/local/bin/kube-ps1.sh && \
    echo "source /usr/local/bin/kube-ps1.sh" >> ~/.bashrc && \
    echo "PS1='[\u@\h \W \$(kube_ps1)]\$ '" >> ~/.bashrc && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && rm -rf /tmp/linux-amd64
