## CentOS中安装配置jdk的三种方式

### yum在线安装
​	a.输入命令：

```shell
yum -y list java*
```

​	b.执行命令：

```shell
yum -y install xxx(xxx为上一条命令显示出的内容中，选择需要安装的)
```

### rpm包离线安装
​	a.从oracle官网下载所需版本的jdk的rpm格式的安装包
​	b.执行命令：

```shell
rpm -ivh xxx(xxx为rpm包的[路径]包名)
```

### tar.gz包离线安装
​	a.从oracle官网下载所需版本的jdk的tar.gz格式的安装包
​	b.解压并拷贝解压后的文件夹到/usr/java下
​	c.配置环境变量
​		c.1. vim /etc/profile,追加如下这些内容：

```bash
#set java environment
JAVA_HOME=/usr/java/jdkxxx
JRE_HOME=$JAVA_HOME/jre
PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib
export JAVA_HOME JRE_HOME PATH CLASSPATH
```

​	d.使配置文件生效：

```shell
source /etc/profile
```
