# P0-P26  MYSQL

## MYSQL的启动和停止

1. 计算机-右击管理-服务
2. 通过管理员身份运行（1）net start  服务名（2）net stop 服务名

MYSQL  服务的登录和退出

1. 通过MySQL自带的客户端（只限于root用户）
2. 通过Windows客户端

登录MySQL-h主机名-p端口号-u用户名-p密码

退出 exit 或者CTRL+C

## MySQL 常见命令介绍

show  databases;

use    库名；打开库

show tables；打开表

show tables from MySQL；打开其他库中的表

select database（）；查看目前所在的库

create table  名字（

id  int,                   

name varchar(20)

）;创建表：列名     类型

​                    ID列       int

​              name列     varchart

desc 表名；查看表结构

select*from 表名；查看数据

insert into 表名（id，name）values（1，‘John’）；插入数据

update 表名 set   name=‘lilei’ where（ID=1；改数据

delete from 表名 where id =1；删除表内数据

select version（）；查看当前版本

#MySQL的语法规范

1. 不区分大小写，但建议关键字大写，表名，列名小写

2. 每条命令最好用分号结尾

3. 每条命令根据需要，可以缩进或换行

4. 注释  单行注释  

   （1）#注释文字

   （2）--空格+注释文字

   多行注释：/* 注释文字 */

DQL语言，数据查询语言

DML语言，数据操作语言

DDL语言，数据定义语言

TCL语言，事物控制语言

DQL：基础查询   select

select 查询列表

from 表名；

1. 查询列表中的单个字段 select Last_name From employees;
2. 查询表中的多个字段 select Last_name,salary,email from employees;
3. 查询表中的所有字段 select * from employees;此时顺序与列表的顺序一致。

*：use 库名；开头建议

``着重号，内部的内容为字段不是关键字。

### 查询常量

select 100;常量值

select '100'

### 查询表达式

select 100*98;    * %都可以用

### 查询函数

select version();得到该函数的返回值

### 为字段起别名

1.便于理解  2.若字段有重名，可以使用别名区分开来。

select 100%98 as 结果;或者select Last_name 姓from employees;

### #案例：

别名中若有out，#等关键字会报错数，应将该别名加双引号

### 去重

案例；查询员工表中涉及到的所有的部门编号

select distinct department_id from employees;

### +号的使用方法

案例：查询员工名和姓连成一个字段，并显示为姓名；

select concat (last_name,first_name) as 姓名

from

employees;

#mysql中的+号：仅仅只有一个功能：运算符

select 100+90;两个操作符都为数值型，加法运算符

select  '123'+90;其中一方为字符型，试图将字符型数值转换为数值型，若转换成功，运行加法运算

select 'john'+90;若转换失败，则将字符型数值转换为0，故此行命令的结果为90

select null +10;只要其中一方为null，则结果肯定为null

-----------------------------------------以上是P26的笔记------------------------------------------

