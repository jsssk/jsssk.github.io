---
title: 虚拟机搭建 Kubenetes
tags: Coding DevOps 
# article_header:
#   type: cover
#   image:
#     src: /image/java/java-streams.jpg

comments: false

show_author_profile: true

footer: false

mathjax: true
mathjax_autoNumber: false
mermaid: true
chart: true

modify_date: 2021-06-10

key: 20210106_1

---

<!--more-->
<!-- more --> 

准备三台虚拟机，


```shell
# Setup daemon.
cat > /etc/docker/daemon.json <<EOF
{
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m"
  },
  "storage-driver": "overlay2"
}
EOF
```

```shell
kubeadm reset -f
kubeadm init

```

[Flannel](https://github.com/flannel-io/flannel)

