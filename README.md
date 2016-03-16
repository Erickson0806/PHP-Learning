# PHP-Learning
###1.变量
PHP是弱类型语言,在php中使用变量之前不需要声明变量,只需要为变量赋值即可

```
$tstr = 'string';
```
###2.类型
1.数组
php中的数组相当于oc中的数组和字典的结合体
定义数组的格式如下:

```
$array = ('value1','value2');
```
  
```
$arr = ('a',1,'abc');  
```

使用数组函数array(),

```
$array[key]='value';
```
例如: `$arr[0] ='a';`
  
key表示数组的键值,下标从0开始,这段代码的表示给数组变量$arr的第一个元素赋值字符串a;

```
$arr = array(key1=>value1,key2=>value2....)
```
```
$arr2 = array('name'=>'张三','age'=>'18');
```
###3.常量
定义常量使用define()函数,常量名前面不需要加$符号,按照惯例常量名全部使用大写

```
define ("NAME","张三")
```
define()函数有3个参数,第一个参数是常量名(NAME),第2个参数是常量的值(张三),第三个参数表示是否区分大小写,默认为true.

判断一个常量是否存在使用defined()函数,成功返回true,失败返回假.

```
<?php
define("NAME","张三")
if(defined("NAME")) {
	echo NAME;
} else {
	echo "没有此常量";
}
?>
```
常量的值只能是标量（boolean ，integer，float 和 string）
###4.运算符
#####1.字符串运算符中的`.`和swift中的`+`一样
#####2.在可以产生值的表达式前使用错误控制运算符，可以忽略因表达式运算错误而产生的错误信息。错误控制运算符是`@`
#####3.执行运算符，PHP将把运算符内的字符作为外壳命令来执行，其作用与shell_exec()函数相同

```
<?php
    $output = `ifconfig`;
    echo "<pre>$output</pre>";
?>
```
###5.break语句
break后面可以跟一个数字参数(如:break 1;  break 2; ) 来决定跳出几重循环。break不写参数系统默认是break 1

###6.函数
1.函数内部调用全局变量只需要在变量前面加上global关键字.

```
<?php
    $a = 1;
    $b = 2;
    function Sum()
    {
       global $a, $b;
       $b = $a + $b;
    }
    Sum();
    echo $b;
?>
运行结果:3 
```

###7.数组

```
<?php
        $arr =array ('name'=>'jim', 'age'=>18, 'sex'=>'男');
        echo $arr['name'];
?>
```
###8.foreach循环
语法格式：

```
foreach (array as $value){
       循环体语句;
}
```
第一个参数array是待遍历的数组, as是关键字, $value表示每次循环把当前元素的值赋给$value. 这个$value可以是自定义的任意变量,比如你把它定义为$a或他的变量都没有问题,不过我们通常使用默认$value,与swift语言中的forin类似


```
<?php
		$arr3 = array('name'=>'jim','age'=>23,'sex'=>'男');
		foreach($arr3 as $value) {
				echo $value;
		}
?>
运算结果: name:jim age:18 sex:男 
```
###9.字符串常用函数

