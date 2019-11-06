# 相关资料

[官方文档，array 数组](https://www.php.net/manual/zh/language.types.array.php)

[官方文档，数组函数库](https://www.php.net/manual/zh/book.array.php)

# 简介

相对于之前的几种类型，array 是稍微有点复杂的。

如果说变量是「**数据**」的容器，「**数组**」就是「**变量**」的容器，因为数组可以保存一组数据。

# 调试技巧

请记住 `var_dump($变量);` 可以帮助你调试所有数据类型，包括数组；我在文章开头写出来，就是告诉你它的重要性！

# 键值对（key=>value）

- 数组中可以保存多个数据（值、value）
- 每个数据有个唯一编号（键、key）
- 每个键值对用逗号"`,`"分割

每组数据，我们习惯称之为：键值对

```PHP

# 定义数组a,b,c 就是数据的key
$arr = ['a'=>1, 'b'=>2, 'c'=>3];
```

实际上，我们也可以不填写key，由PHP帮我们生成（从0开始自动编号）

```PHP
# 123是值，自动生成的编号为：012
$arr = [1,2,3];
```

# 增删改查

说起数组，就需要提到「增删改查」这个经典术语；面对一组数据，我们就要对其进行：添加、删除、修改、查询；

```PHP
# 定义数组，并使用自动编号（0123）
$arr = ['a'=>1, 'b'=>2, 'c'=>3];

# 增加一个键值对
$arr['d'] = 4;

# 修改指定key的值
$arr['a'] = 2;

# 输出一个key的值
echo $arr['a'];

# 删除一个键值对，和其他的语法不一样，需要用unset() 函数
unset($arr['a']);
```

`[key]` 是非常重要的操作符，所有需要用key的时候，都是这个操作符。

# 遍历（循环）

在实际开发中，有一个很实际的需求：逐一获取数组中所有的键值对，我们称之为遍历，也叫循环；这主要是通过 `foreach` [流程控制](../control.md)语法实现的。

```PHP
$arr = [1,2,3,4,5];
foreach( $arr as $value ){
    //逐一输出12345
    var_dump($value);
}
```