# cf-workers-proxy-docker

https://cloud.tencent.com/developer/article/2436892

1. 前提准备
一个Cloudflare账号，并且有一个域名托管到了Cloudflare上面，可以注册一些免费或者便宜的域名托管过去。注意 Worker 每天每免费账号有次数限制，为10万次。每分钟为1000次。

2. 编辑脚本
将 [worker.js](worker.js) 中的第六行的 `https://docker.xxxxxx.com` 替换为自定义的 域名地址。

3. 为 worker 配置域名
`设置 > 触发器 > 路由 > 添加路由`

4. docker配置使用自己的镜像
```bash
sudo tee /etc/docker/daemon.json <<EOF
{
    "registry-mirrors": ["自定义域名"]
}
EOF
```