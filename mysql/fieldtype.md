## MySQL表字段类型
总体上分为三类：数字、日期、时间和字符串类型

### 数字数据类型
* int 正常大小的整数，可带符号。
* tinyint 一个非常小的整数，可带符号。有符号：-128到127；无符号：0-255
* smallint 一个小的整数，可带符号。有符号：-32768到32767；无符号：0-65535
* mediuint 一个中等大小的整数，可带符号。
* bigint 一个大的整数
* float(M, D) 浮点数字。定义显示长度M和小数位数D，M是数字（包括小数）的总数。
* double(M, D) 双精度浮点数。
* decimal(M, D) 

### 日期和时间类型
* date 以YYYY-MM-DD格式的日期
* datetime 以YYYY-MM-DD HH:MM:SS格式的日期
* timestamp 时间戳
* time 以HH:MM:SS格式的日期
* year(M) 

### 字符串类型
* char(M) 固定长度的字符串
* varchar(M) 可变长度的字符串
* blob or text 字段的最大长度是65535个字符
* tinyblob or tinytext
* mediublob or mediutext
* longblob or longtext
* enum 枚举 enum('A','B','C')
