# rke 安装步骤

1. 利用rke文件夹下面的rke_init.sh脚本初始化每个节点
2. 免密登录，使得172.18.16.34的主节点上的root和rkeuser可以在任何工作节点上面免密登录，参照rke文件夹下的ssh_login.sh文件
3. 参照rke_install.sh文件下，开始安装rke集群。(注意集群配置文件，cluster.yml) [配置具体详情参考](https://docs.rancher.cn/docs/rke/config-options/_index#%E6%A6%82%E8%BF%B0)

# rancher 安装步骤

1. 下载helm3 [地址](https://github.com/helm/helm/releases)
2. 执行安装: helm repo add rancher-stable https://releases.rancher.com/server-charts/stable
3. 创建明明空间： kubectl create namespace cattle-system
4. 根据rancher文件夹的cert-manager-install.sh 来安装自签名证书服务
5. 执行rancher-install.sh 安装

# istio 安装
1. 应用市场选择istio，勾选安所有的组件，安装
2. istio文件夹下有istio日志参考

# nfs-provisioner
1. nfs文件夹执行install-nfs-client.sh

# mysql 单机
1. root/root 管理员密码
2. cowain/cowain 用户密码
3. 建立nodeport 暴露mysql服务

# mysql 集群
1. root/root 管理员密码
2. cowain/cowain 用户密码
3. 建立nodeport 暴露mysql 主从服务

# redis 单机
1. 应用商店 bitnami redis
2. 模式 standalone
3. 认证 false
4. 存储 nfs-provisioner

# fastdfs
1. trakcer 追踪器 用于暴露上传接口 22122
2. storage 存储模块 用于存储具体文件
3. tracker nodeport 暴露
4. ingress

# 有用的网站

- [k8s各种组件](https://github.com/foxiswho/k8s-nacos-sentinel-rocketmq-zipkin-elasticsearch-redis-mysql)
- [markdown编辑器](http://www.txttool.com/wenben_markdowneditor.asp)
