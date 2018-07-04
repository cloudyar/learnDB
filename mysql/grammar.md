### 创建表
create table table_name(column_name column_type);

create table test(
	id int not null auto_increment,
	title varchar(100) not null,
	author varchar(40) not null,
	submission_date date,
	primary key(id)
);

### 删除表
drop table table_name;

### 插入数据
insert into table_name (field1, field2, fieldN)
						values
					   (value1, value2, valueN);

INSERT INTO test (title, author, submission_date) VALUES ("Learn PHP", "Paul", NOW());