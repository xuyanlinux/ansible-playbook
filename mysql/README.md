## 一、 下载二进制安装包
官网下载即可，这里安装的是5.7.22，地址是：
https://downloads.mysql.com/archives/get/p/23/file/mysql-5.7.22-linux-glibc2.12-x86_64.tar.gz
下载后，把安装包放到files目录里
./mysql/roles/mysql/files/


## 二、一键安装
在mysql目录下直接执行
```
ansible-playbook mysql_role.yaml
```

## 三、根据需求更改配置
- hosts文件中可以修改目标节点
- roles/mysql/vars/main.yml中可以修改以下信息：
```
PORT: 3006 #端口号
USERNAME: mysql #用户名
GROUPNAME: mysql #用户组名
BASEDIR: /usr/local/mysql/ #mysql环境运行目录
DATADIR: /data/mysql/ #msyql数据目录
RESOURCEDIR: /opt/mysql/ # 存放安装包的目录
# 软连接路径
LINKPATH: /usr/local/mysql # 为运行环境创建软链接，方便后期升级、维护
# 安装包解压后的目录名，后面加上".tar.gz"就是安装包的名字
PACKAGENAME: mysql-5.7.22-linux-glibc2.12-x86_64 # mysql安装包名字，如果安装其他版本，这里的名字应该做相应更改
```
