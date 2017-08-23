## MySQL安装运行基础命令
|功能|命令行|
|---|---|
|启动|sudo support-files/mysql.server start|
|关闭|sudo support-files/mysql.server stop|
|重启|sudo support-files/mysql.server restart|
|检查运行状态|sudo support-files/mysql.server status|
|初始化密码|cd /usr/local/mysql/bin  ./mysqladmin -u root password <your-password>|
|连接数据库|./mysql -u root -p + password|


## MySQL便捷操作
* 设置 PATH="$PATH"+/usr/local/mysql/bin，之后可以快捷使用 mysql -u root -p 登录

## MySQL安装问题
* Mac版本过高，MySQLworkbench兼容问题
* 新版XAMPP使用问题
