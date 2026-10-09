# MySQL
##  DDL 
<font color="red">数据定义语言，用来定义数据库对象（数据库，表，字段）</font>
### 数据库操作
show databases; 查询所有数据库  
select database(); 查询当前数据库  
create databases [if not exists] 数据库名 [default charset 字符集] [collate 排序规则]; 创建  
drop database [if exists] 数据库名; 删除
use 数据库名; 使用
### 表操作
show tables; 查询当前数据库所有表  
desc 表名; 查询表结构  
show create table 表名; 查询指定表的建表语句  
alter table 表名 add 字段名 类型(长度) [comment 注释] [约束]; 添加字段  
alter table 表名 modify 字段名 新数据类型(长度); 修改数据类型  
alter table 表名 change 旧字段名 新字段名 类型(长度) [comment 注释] [约束]; 修改字段名和字段类型  
alter table 表名 drop 字段名; 删除字段  
alter table 表名 rename to 新表名; 修改表名  
drop table [if exits] 表名; 删除表  
truncate table 表名; 删除指定表，并重新创建该表  
##  DML 
<font color="red">数据操作语言，用来对数据库表中的数据进行增删改</font>  
insert into 表名 (字段名1,字段名2,...) values(值1,值2,...); 给指定字段添加数据  
insert into 表名 values(值1,值2,...); 给全部字段添加数据  
insert into 表名 (字段名1,字段名2,...) values(值1,值2,...),(值1,值2,...)(值1,值2,...); 批量添加数据  
insert into 表名 values(值1,值2,...),(值1,值2,...)(值1,值2,...); 批量添加数据  
update 表名 set 字段名1=值1,字段名2=值2,...[where 条件]; 修改数据  
delete from 表名 [where 条件]; 删除数据
##  DQL 
<font color="red">数据查询语言，用来查询数据库中表的记录</font>  
select 字段列表 from 表名 where 条件列表 group by 分组字段列表 having 分组后条件列表 order by 排序字段列表 limit 分页参数
##  DCL 
<font color="red">数据控制语言，用来创建数据库用户、控制数据库的访问权限</font>
### 管理用户
create user '用户名@主机名' identified by '密码'; 创建用户  
alter user '用户名@主机名' identified with mysql_native_password by '新密码'; 修改用户密码  
drop user '用户名@主机名'; 删除用户
### 权限控制
show grants for '用户名@主机名'; 查询权限   
grant 权限列表 on 数据库名.表名 to '用户名@主机名'; 授予权限    
revoke 权限列表 on 数据库名.表名 from '用户名@主机名'; 撤销权限 
##  函数
### 字符串函数
`concat(s1,s2,...sn)` 字符串拼接    
`lower(str)` 字符串小写     
`upper(str)` 字符串大写     
`lpad(str,n,pad)` 左填充    
`rpad(str,n,pad)`右填充     
`trim(str)` 去头尾空格  
`sustring(str,start,len)` 字符串截取    
### 数值函数
`ceil(x)` 向上取整  
`floor(x)` 向下取整     
`mod(x,y)` 返回x/y的模  
`rand()` 返回0~1内的随机数  
`round(x,y)` 求参数x的四舍五入的值，保留y位小数     
`select lpad(round(rand()*1000000,0),6,0);`  ||  `select substring(rand(),3,6);` 生成六位的随机数  
### 日期函数
`curdate()` 返回当前日期    
`curtime()` 返回当前时间    
`now()` 返回当前日期和时间  
`year(date)` 获取指定date的年份     
`month(date)` 获取指定date的月份    
`day(date)` 获取指定date的日期  
`date_add(date,interval expr type)` 返回一个日期或时间值加上一个时间间隔expr的时间值    
`datediff(date1,date2)` 返回日期差（天数）  
### 流程函数
`if(value,t,f)` 如果值为真，返回t，否则返回f    
`ifnull(value1,value2)` 如果值1不为空，返回值1，否则返回值2     
`case when [val1] then [res1] ... else [defalut] end` 如果值1为真，返回结果1，否则返回默认值    
`case [expr] when [val1] then [res1] ...else [defalut] end` 如果expr等于val1，返回结果1，否则返回默认值     
##  约束
not null 非空约束   
unique 唯一约束     
primary key 主键约束        
default 默认约束        
check 检查约束（8.0.16版本）        
foreign key 外键约束        
### 外键
alter table 表名 add constraint 外键名称 foreign key(外键字段名) reference 主表(主表列名); 添加外键     
alter table 表名 drop foreign key 外键名称; 删除外键
### 外键行为
cascade 级联        
set null 设为空
##  多表查询
### 多表关系
1.一对多：在多的一方设置外键，关联的一方的主键      
2.多对多：建议中间表，中间表包含两个外键，关联两张表的主键      
3.一对一：用于表结构拆分，在其中一方设置外键（UNIQUE），关联另一方的主键
## 内连接
select 字段列表 from 表1,表2 where 条件...; 隐式内连接      
select 字段列表 from 表1 [inner] join 表2 on 条件...; 显示内连接
## 外连接
select 字段列表 from 表1 left [outer] join 表2 on 条件...; 左外连接（查询表1的所有数据 包含 表1和表2交集部分的数据）        
select 字段列表 from 表1 right [outer] join 表2 on 条件...;  右外连接（查询表2的所有数据 包含 表1和表2交集部分的数据）
## 自连接
select 字段列表 form 表1 别名1 join 表1 别名2 on 条件...; 
## 联合查询
select 字段列表 from 表1 union [all] select 字段列表 from 表2; (列数和字段类型保持一致，union all将全部数据合并，union会去重)
## 子查询
<font color="red">标量子查询 列子查询 行子查询 表子查询</font>  
1.标量子查询：子查询返回的结果是单个值（数字、字符串、日期等）      
2.列子查询：子查询返回的结果是一列（可以是多行）        
3.行子查询：子查询返回的结果是一行（可以是多列）        
4.表子查询：子查询返回的结果是多行多列      
select * from t1 where column = (select column1 from t2);
##  事务
<font color="red">是一组操作的集合，它是一个不可分割的工作单位，事务会把所有的操作作为一个整体一起向系统提交或撤销操作请求，即这些操作要么同时成功，要么同时失败</font>
### 事务操作1
`select @@autocommit;` 查看事务提交方式     
`set @@autocommit = 0;` 设置事务提交方式        
`commit;` 提交事务      
`rollback;` 回滚事务
### 事务操作2
start transaction 或 begin; 开启事务        
commit; 提交事务        
rollback; 回滚事务
### 事务四大特性（ACID）
原子性（Atomicity）事务是不可分割的最小操作单元，要么全部成功，要么全部失败     
一致性（Consistency）事务完成时，必须使所有的数据都保持一致状态 
隔离性（Isolation）数据库系统提供的隔离机制，保证事务在不受外部并发操作影响的独立环境下运行     
持久性（Durability）事务一旦提交或回滚，它对数据库中的数据的改变就是永久的
### 并发事务问题
* 脏读 一个事务读到另外一个事务还没有提交的的数据
* 不可重复读 一个事务先后读取同一条记录，但两次读取的数据不同，称之为不可重复读
* 幻读 一个事务按照条件查询数据时，没有对应的数据行，但是在插入数据时，又发现这行数据已经存在，好像出现了“幻影”
### 事务隔离级别
<font color="red">事务隔离级别越高，数据越安全，但是性能越低</font>     
Read Uncommitted（读未提交）        
Read Uncommitted（读已提交）        
Repeatable Read（可重复读取）       
Serializable（可串行化）        
select @@transaction_isolation; 查看事务隔离级别        
set [session | global] transaction isolation level {Read Uncommitted | Read Uncommitted | Repeatable Read | Serializable} 设置事务隔离级别