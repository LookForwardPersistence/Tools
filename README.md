# Tools
Tools
# idea
配置live Template
- **
* @decription $description$ 
* $param$
* @return $returns$
* @author fanqianghua
* @date $date$
*/
- param默认值： groovyScript("def result=''; def params=\"${_1}\".replaceAll('[\\\\[|\\\\]|\\\\s]', '').split(',').toList(); for(i = 0; i < params.size(); i++) {if(params[i] == '') return result; result+='* @param ' + params[i] + ((i < params.size() - 1) ? '\\n' : '')}; return result", methodParameters()) 

# idea 查看方法注释快捷键
- Ctrl+q
# redis 安装
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


#nvm Node version manager
nvm常用命令

输入nvm list -- 查看有哪些 node 版本

输入nvm use --- 使用某一个版本 例如 ： nvm use 8.6.0


## linux node 升级 

1.清楚node缓存；

$  sudo npm cache clean -f  

2.安装node版本管理工具'n';

$  sudo npm install n -g

3.使用版本管理工具安装指定node或者升级到最新node版本；

$  sudo n stable  （安装node最新版本）

$  sudo n 8.9.4 （安装node指定版本8.9.4）

4.使用node -v查看node版本，如果版本号改变为你想要的则升级成功。

若版本号未改变则还需配置node环境变量

1.查看通过n安装的node的位置；

$  which node  (如：/usr/local/n/versions/node/6.12.3）

2.cd进入/usr/local/n/versions/node/ 你应该能看到你刚通过n安装的node版本这里如：8.9.4；编辑/etc/profile;

$  vim /etc/profile

3.将node安装的路径（这里为：/usr/local/n/versions/node/8.9.4）添加到文件末尾；

#set node path

export NODE_HOME=/usr/local/n/versions/node/8.9.4

export PATH=$NODE_HOME/bin:$PATH

4.wq退出保存文件，编译/etc/profile;

$  source /etc/profile

5.再次使用node -v查看node版本，不出意外版本号应该变为你想要的。


#如果采用nvm安装node 则升级采用
##nvm install stable
