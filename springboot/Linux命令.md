[toc]



[Linux命令大全地址：https://blog.csdn.net/luansj/article/details/97272672](https://blog.csdn.net/luansj/article/details/97272672)



### `文件和目录`

#### 目录

- ```
   pwd 查看当前目录
   ll  查看当前目录下的所有文件或目录
   
   cd /	进入文件根目录
   cd ..	返回上一级目录
   cd ../..	返回上两级目录
cd /home	进入home目录
   cd -	返回上次所在的目录
   ```
   
- ```
   mkdir dir1		   创建dir1目录
   mkdir dir1 dir2    同时创建dir1、dir2两个目录
   mkdir -p/tmp/dir1/dir2		创建一个目录树
   
   rmdir dir1		删除名为dir1的空白目录
   rm -rf dir1		删除名为dir1的目录并同时删除其内容
   rm -rf dir1 dir2	同时删除两个目录及其
   rm -rf ./*		删除当前目录下的所有内容，但当前不包括当前目录
   ```
- ```
   touch file1		创建名为file1的空白文件
      
   rm -f file1		删除名为file1的文件
   ```

- ```
   mv old_dir new_dir		重命名/移动一个目录
   mv jdk1.8.0_231/ /usr/local/	将jdk1.8.0_231目录移动到/usr/local/目录下
mv apache-tomcat-9.0.29/ tomcat9.0		将apache-tomcat-9.0.29重命名为tomcat9.0
   ```
   
- ```
  ./startup.sh	在Linux中启动一个可执行命令使用'./命令'来启动，./表示当前目录，startup.sh是tomcat的启动命令，所以./startup.sh表示启动tomcat服务器
  ```

   

- ```
   ls		查看当前目录中的文件
   ls -a	查看当前目录中的所有文件（包括隐藏文件）
   ls -lh	查看文件大小
   
   pwd		显示当前工作目录的全路径
   ```

- ```
   :q		回退(不保存)
   :wq		保存并且退出
   ```

   

### 打包和压缩文件

- ```
   tar -zxvf jdk-8u201-linux-x64.tar.gz	解压一个gzip格式的压缩包
   ```

   



### 文件搜索



### Linux防火墙相关命令

- ```
   systemctl status firewalld		查看Linux防火墙状态 (开启/关闭)
   systemctl start firewalld		开启Linux防火墙
   systemctl stop firewalld		关闭Linux防火墙
   service firewalld restart		重启Linux防护墙
   
   firewall-cmd --zone=public --list-ports 	查看Linux防火墙开放的所有端口号
   
   firewall-cmd --zone=public --add-port=80/tcp --permanen		开放tcp的80端口
   firewall-cmd --zone=public --add-port=80/udp --pernanen		开放udp的80端口
   firewall-cmd --zone=publid --add-port=3306/tcp --pernanen		开放tcp的3306端口
   firewall-cmd --zone=public --add-port=80-8888/tcp --pernanen 	开放tcp端口范围在80至8888的端口
   
   firewall-cmd --zone=public --remove-port=80/tcp --pernanen		关闭tcp的80端口
   firewall-cmd --zone=public --remove-port=80 --pernanen		关闭80端口
   
   firewall-cmd --reload	刷新Linux防火墙 (比如我们开放了Linux的某个端口后,就刷新一下防火墙)
   
   Warning: ALREADY_ENABLED: 3306:tcp		注意这不是一个命令，这是一个提示，意思是tcp的3306端口已经开放了
   ```



### Linux操作端口相关命令

- ```
   ps -ef		查看Linux进程名称
   lsof -i:端口号		查看某端口的占用情况
   ps -ef|grep tomcat		查看tomcat进程
   ps -e|grep tomcat		查看tomcat进程
   netstat -anop|grep Tomcat进程号	根据Tomcat进程号查看端口详情（包括端口号和占用端口的进程）
   netstat -anp|grep Tomcat进程号	根据Tomcat进程号查看端口详情（包括端口号和占用端口的进程）
   kill -9 某某端口号		杀掉占用某某端口的进程
   ```




### 数据库相关命令

- ```
   service mysqld status	查看mysql状态(是否为运行状态)
   ps -e|grep mysqld		查看mysql运行的对应进程
   netstat -anp|grep 3306	查看3306端口占用情况
   
   mysql -u root -p		连接mysql数据库/进入mysql数据库
   use mysql		选择数据库
   update user set password=password("你的新密码") where user="root";	修改数据库密码
   service mysqld restart		重启mysql数据库
   
   create database 数据库名		 创建数据库
   use 数据库名					 选择数据库 
   cource /home/caidong/o2o.sql	执行/home/caidong/目录下的o2o.sql文件
   
   
   #本地navicat连接阿里云远程Linux服务器的MySQL
   
   grant all privileges on *.* to 'root'@'%' identified by '远程数据库的密码' with grant option;
   flush privileges	刷新权限
   
   ```


