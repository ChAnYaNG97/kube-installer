# KubeEdge安装
#### 准备
保证云节点和边节点可以访问外网 （github.com）
#### 1 切换为root用户
```shell
sudo su
```

#### 2 git clone
```shell
git clone https://github.com/ChAnYaNG97/kube-installer.git
cd kube-installer
```

#### 3 修改 kubeinst 文件
```shell
vi kubeinst
```
找到如下部分（第40行附近），将`cloud_ip`修改为云主机的IP
```shell
#### KubeEdge ####
version="1.9.0" 
cloud_arch="amd64"
edge_arch="arm64"
cloud_ip="133.133.135.12" # 修改为云主机的IP
```

#### 4 安装云
```shell
./kubeinst init-cloud
```
该命令会输出token，复制下来，在5中需要使用到，若未输出token，则使用
```shell
./bin/keadm_amd64 gettoken
```
获取token

#### 5 安装边
```shell
./kubeinst init-edge <token>
```

