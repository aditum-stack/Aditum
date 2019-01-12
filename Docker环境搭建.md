# Linux开发环境部署

## Centos7部署Docker

通过yum搜索安装即可。

## Docker

预计需要以下镜像和容器：

![镜像](docker/docker镜像.png)

![容器](docker/docker容器.png)

### Docker常用命令

docker images #展示镜像

docker ps #展示运行容器

docker ps -a #展示所有容器

docker build ...... #根据dockerfile创建镜像

docker run ........ #根据镜像创建容器并设定初始配置

docker exec -it name bash #进入相关容器的命令行交互，例如进行mysql容器

docker logs name #查看容器运行日志

docker rm 容器名 #删除容器

docker rmi 镜像名 #删除镜像

docker start 容器名 #启动未启动的容器

docker stop 容器名 #关闭启动的容器

......

### Docker部署Mysql

1. 拉取mysql镜像，当前默认版本为8.0.11

2. 启动容器，注意，为了方便操作，应该指定端口映射为 3306->3306；同时指定默认密码

3. 进行配置更改，允许远程访问，并设置默认密码格式（mysql8更改了默认格式，导致Navicat连接不上）

> 使用mysql8的相关命令进行授权和密码默认格式修改。注意，不要使用低版本的语言，会失败，从网上搜索mysql8的授权和默认密码格式修改方式即可。

5. 使用Navicat等工具访问主机ip:3306进行验证，若报错，根据错误信息搜索进行解决。

**注意：** 配置防火墙，放通相关端口，一是使用云服务器配置界面，二是进入iptables手动修改。

**思考：** 直接使用docker部署mysql服务，是可行的。但若是删除容器，那么数据也就损失了，解决方式是通过外挂数据卷，docker中仅保留外部数据的引用。
          对于mysql的docker化，同程旅游进行了大规模实践，可通过搜索引擎搜索他们的实践经验。（为了方便，我没有使用外挂数据卷，留待日后使用）

### Docker部署Apollo

> 前提，配置好mysql数据库中的apollo必需数据库，连接到mysql容器，然后执行官方提供的sql文件即可。

1. 下载官方Release包：共三个zip文件

2. 修改三个包中的配置信息，/config/目录下的配置文件，若三个服务都在本地，那么直接将ip设为本机的ip地址（不能是localhost）

    
    因为三个包分别部署为三个docker容器，而docker容器的localhost指向的是容器内部，所以必须将localhost修改为外部地址
    1. 使用主机地址代替localhost（方便）
    2. 使用容器地址代替localhost
    

3. 修改配置文件中的mysql地址，同理，若mysql容器在本地，那么将ip直接设为主机ip即可

4. 下载三个包的相关dockerfile，并修改其中的版本信息

**以上内容全部在[docker/apollo](docker/apollo)中**

5. 将三个包上传到服务器，每个包包含一个zip和一个dockerfile

6. 进入相应目录，执行dockerfile构建命令（在相应的dockerfile文件的注释部分有）

7. 三个容器构建完成，可以使用apollo服务

**注意**：同理，数据库中eureka注册链接默认为localhost，需要修改为主机ip地址


