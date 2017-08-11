## MySQL安装运行基础命令
|功能|命令行|
|---|---|
|启动|sudo support-files/mysql.server start|
|关闭|sudo support-files/mysql.server stop|
|重启|sudo support-files/mysql.server restart|
|检查运行状态|sudo support-files/mysql.server status|
|初始化密码|cd /usr/local/mysql/bin  ./mysqladmin -u root password <your-password>|
|连接数据库|./mysql -u root -p + password|
