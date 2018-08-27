## FastDFS环境准备:
---
### 1.1 基础包安装:
<pre>
# wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
# yum -y install zlib zlib-devel pcre pcre-devel gcc gcc-c++ openssl openssl-devel libevent libevent-devel perl unzip net-tools lsof tree wget vim
</pre>

### 1.2 关闭防火墙:
<pre>
# systemctl stop firewalld 
</pre>
### 1.3 关闭Selinux
<pre>
# setenforce 0  #临时关闭
# vim /etc/selinux/config # 编辑配置文件
SELINUX=disabled
# sed -i.bak 's/SELINUX=enforcing/SELINUX=disabled/' /etc/selinux/config
</pre>

### 1.4 同步时间:
<pre>
# yum install ntpdate -y
# echo "*/5 * * * * /usr/sbin/ntpdate time1.aliyun.com > /dev/null 2>&1" >> /var/spool/cron/root
</pre>

### 1.4 操作系统说明:
<pre>
[root@localhost ~]# cat /etc/redhat-release 
CentOS Linux release 7.5.1804 (Core) 
[root@localhost ~]# uname  -r 
3.10.0-327.el7.x86_64
[root@localhost ~]# uname -m
x86_64
</pre>