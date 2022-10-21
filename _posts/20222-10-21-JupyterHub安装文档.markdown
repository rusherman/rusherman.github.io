1. 下载chart

wget https://jupyterhub.github.io/helm-chart/jupyterhub-2.0.0.tgz

tar -zxvf jupyterhub-2.0.0.tgz

2. 变更values和Chart文件

将k8s.gcr.io 替换成

registry.cn-hangzhou.aliyuncs.com/google_containers

3. 安装jupyterhub

```SQL
helm upgrade --cleanup-on-fail \
  --install jupyterhub ./jupyterhub \
  --namespace jupyterhub \
  --create-namespace \
  --version=2.0.0 \
  --values config.yaml
```
