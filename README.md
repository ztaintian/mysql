  mysql 学习（版本8.0.18）

    mysql可视化工具

      推荐mysql workbench 
    
    1、安装（参考https://www.runoob.com/mysql/mysql-install.html）
      
      （1、下载 https://www.mysql.com/

      （2）、接下来我们需要配置下 MySQL 的配置文件

          打开刚刚解压的文件夹 C:\web\mysql-8.0.11 ，在该文件夹下创建 my.ini 配置文件，编辑 my.ini 配置以下基本信息：

          [client]
          # 设置mysql客户端默认字符集
          default-character-set=utf8
          
          [mysqld]
          # 设置3306端口
          port = 3306
          # 设置mysql的安装目录
          basedir=C:\\web\\mysql-8.0.11
          # 设置 mysql数据库的数据的存放目录，MySQL 8+ 不需要以下配置，系统自己生成即可，否则有可能报错
          # datadir=C:\\web\\sqldata
          # 允许最大连接数
          max_connections=20
          # 服务端使用的字符集默认为8比特编码的latin1字符集
          character-set-server=utf8
          # 创建新表时将使用的默认存储引擎
          default-storage-engine=INNODB
      
        （3）、初始化数据库：

            mysqld --initialize --console

        （4）、输入以下安装命令：

          mysqld install

    2、登录 MySQL

      mysql -u root -p
    
    3、mysql重置密码（参考http://baijiahao.baidu.com/s?id=1603874060680405968&wfr=spider&for=pc）

      （1）net stop mysql  停止mysql
      （2）mysqld --console --skip-grant-tables --shared-memory
      （3）重开cmd  mysql.exe -u root
      （4）然后执行sql命令将root用户密码设置为空
        UPDATE mysql.user SET authentication_string='' WHERE user='root' and host='localhost';

    4、mysql设置密码

      提示You must reset your password using ALTER USER statement before executing this statement.后，直接输入

      alter user user() identified by "你要设置的新密码";  就ok了

    
    5、node 连接 mysql（8以上）报错（https://blog.csdn.net/weixin_36094484/article/details/83479992）

      //yourpassword 是你的数据库账户密码，root和host也是
      ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'yourpassword';



