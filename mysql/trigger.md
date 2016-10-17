### 触发器
---
#### 语法
>   CREATE TRIGGER `trigger_name`   
>   `trigger_time`   
>   `trigger_event` ON tbl_name   
>   FOR EACH ROW   
>   `trigger_stmt`   
>   
>       不能同时在一个表上建立2个相同类型的触发器。
> 
> > * trigger_name：触发器名称
> > * trigger_time：出发时机（BEFORE | AFTER）
> > * trigger_event：触发事件（INSERT | UPDATE | DELETE）
> > * tbl_name：标识建立触发器的表名
> > * tigger_stmt：触发器程序体。可以是一个SQL，或用BEGIN...END包含的多条语句 
#### trigger_evert详解
> `LOAD DATE` 将一个文件载入到数据表中，相当于一系列的INSERT   
> `REPLACE` 相当于 INSERT 或 DELETE > INSERT   
> 因此：
> > * INSERT 类型触发器：插入某条数据激活触发器。可能通过INSERT，LOAD DATE, REPLACE触发。
> > * UPDATE 类型触发器：通过UPDATE触发。
> > * DELETE 类型触发器：可能通过DELETE，REPLACE处罚。
#### BEGIN...END
> `BEGIN [statement_list] END`   
> 其中`statement_list `代表一个或多个语句的列表，列表内每条语句必须用分号(;)结尾。分号(;)是MySQL默认的定界符，这时就会用到`DELIMITER`语句修改定界符。
> 
#### NEW 和 OLD 详解
> MySQL定义了NEW和OLD，用来表示触发器说所在的表中，触发了触发器的哪一行数据。
> > * INSERT类型触发器中，NEW用来表示将要（BEFORE）或已经（AFTER）插入的新数据。
> > * UPDATE类型触发器中，OLD用来表示将要或已被修改的原数据，NEW用来表示将要或已经修改为的新数据。
> > * DELETE类型触发器中，OLD用来表示将要或已被删除的原始数据。
> 
> <trong>使用方法：NEW.columnName （columnName 为相应数据表某一列名）<br>另外：OLD是只读的，而NEW可以在触发器中使用SET赋值，这样不会再次触发触发器。</trong>
#### 查看触发器
> `**SHOW TRIGGERS [FROM schema_name]**`   
> schema_name即Schema的名称，在MySQL中Schema和DATABASE是一样的。
#### 删除触发器
> `**DROP TRIGGER [IF EXISTS] [schema_name.]trigger_name**`
#### 触发器执行顺序
> 我们建立的数据库一般的InnoDB类型，在其上建的表是事物性表。这时，若SQL语句或触发器执行失败，MySQL会回滚事物。
> > 1. 如果BEFORE触发器执行失败，SQL无法正确执行。
> > 2. SQL执行失败时，AFTER触发器不会触发。
> > 3. AFTER类型触发器执行失败，SQL会回滚。
#### 其他相关
> * **`DECLARE`**：复合语句中声明局部变量。只能用在`BEGIN...END`语句内；并且应该定义在复合语句的开头。   
> > 语法：``DECLARE var_name[,...] type [DEFAULT value]`` 变量初始值为 NULL。   
> > 变量赋值：使用SET语法 `SET var_name = expr [,var_name = expr] ...`


摘自:<http://www.cnblogs.com/CraryPrimitiveMan/p/4206942.html>