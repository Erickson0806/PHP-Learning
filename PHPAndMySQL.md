#PHP操作Mysql

php操作Mysql需要4个步骤:
####第一,需要连接数据库的服务器
与MySQL数据库建立链接的是`mysql_connect()`函数

```
 mysql_connect('数据库地址', '用户名', '密码');
```
返回一个资源句柄. 这个资源句柄在操作数据库时使用.

```
<?php
$likn = mysql_connect('localhost','admin','123456');
if (!$link) {
	echo '连接失败';
}
echo '连接成功';
mysql_close($link);

?>
```
####第二,选择服务器上的一个数据库
建立数据库服务器链接后，需要使用`mysql_select_db()`函数，来指定一个数据库.

```
mysql_select_db("db_name",$link) //成功返回true，失败返回false
```
第一个参数“db_name”是要选择的数据库名称,第二个参数$link是连接数据库服务器返回的资源句柄.

```
$link = mysql_connect('localhost','admin','123456');
mysql_select_db('user',$link);
mysql_close($link);
```
####第三,对数据库里面的表进行操作(查询,修改,删除等)
PHP中使用`mysql_query()`函数，执行关于MySQL的数据库语句。`mysql_query()`函数有2个参数：
第1个参数是必选参数，值是用于指定要运行的SQL语句。
第2个参数是可选参数，其值是使用`mysql_connect()`打开的数据库句柄，当这个参数被设置后，将在指定的数据库链接中选择数据库。当这个参数为空时，使用上一个打开的数据库链接。
####第四,最后操作完毕后需要断开数据库连接.
使用`mysql_close()`函数断开连接,此函数只有一个参数,就是在第一步中连接数据库获取的资源句柄.


