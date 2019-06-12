# Tools
Tools

#redis 安装
一、Linux在线安装redis
1、因为redis是c语言开发的，所以需要安装gcc（在根目录下执行）：

yum install gcc-c++
2、因为是在线安装，需要使用wget命令，如果linux中没有，就用如下命令安装（在根目录下执行）：

yum -y install wget
3、下载redis最新的稳定版本，也可以下载其他版本压缩包：

wget http://download.redis.io/redis-stable.tar.gz
4、解压redis压缩包：

tar xzf redis-stable.tar.gz
5、进入到redis的解压文件中，编译redis：
make
6、安装redis：

make install PREFIX=/usr/local/redis
PREFIX参数指定文件的安装目录，一般安装在/usr目录下
/usr/local/目录下已经生成redis目录

7、启动redis，进入redis到安装目录中，即/usr/local/redis/bin：

./redis-server

二、redis的启动
redis分两种启动：

1、前端启动：
在usr/local/redis/bin/  中执行命令：

./redis-server
前端启动以后，我们不能再继续操作redis,所以一般不用。启动成功后如上图所示。
2、后台启动：
1、把redis解压文件中的redis.conf文件复制到redis的安装目录下，即/usr/local/redis/bin。

进入到redis的解压文件中，执行命令：

cp redis.conf /usr/local/redis/bin/
复制成功以后，redis安装目录中会多出一个redis.conf文件。

2、修改一下这个配置文件的内容：将daemonize的值由原来的no修改为yes,保存退出。

3、在redis的安装文件的bin目录下输入命令，则redis便会后台启动：

./redis-server redis.conf
4、通过进程查看命令，查看redis有没有启动：

ps aux | grep redis
5、停止redis：

./redis-cli shutdown

https://blog.csdn.net/java_xuetu/article/details/80299509

