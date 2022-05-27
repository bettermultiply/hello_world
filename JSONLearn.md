# Python & JSON

Mapping relationship
python 		JSON
dict		object
list,tuple	array
float,int,long	number
True		true
False		false
str,unicode	string
None		null

object is wrote in '{}' and more than one key-value couple can be contained
array can contain many objects

##using JSON in python
improt json

json.dumps(): encode python object into JSON string
json.loads(): decode JSON string into python object
json.dump(object, filename): 将python内置类型序列化为JSON对象后写入文件  # waiting more complaination
json.loads(object, filename): 读取文件中JSON形式的字符串元素转化为Python类型  # waiting more complaination

## 参数详解

dumps(	obj,
	skipkeys=False, 
	ensure_ascii=True, 
	check_circular=True,
        allow_nan=True, 
	cls=None, 
	indent=None, 
	separators=None,
        default=None, 
	sort_keys=False, 
	**kw)
skipkeys: 为True时，若非字典对象，则TypeError，默认False
ensure_ascii：确定是否为ASCII编码
check_circular：为true，则循环类型检查  # 即，对容器类型的循环引用检查，循环引用将导致溢出等糟糕结果
allow_nan：确定是否为允许的值  # # waiting more complaination
ident：num，根据数据格式缩减显示
separators：对象分隔符，默认为','
encoding： 编码方式，默认为utf-8
sort_keys：True时，对于字典对象按照key的ASCII码进行排序
  # it's the same as dump except fp<filename> 


### 读取多行JSON文件时不可一次读取（会抛出JSONDecodeError异常，表示数据错误），而应手写代码循环单行读取
读取空行时也会异常，所以应对空行进行处理再转换为Python对象
控制台乱码时可考虑是否是编码格式错误，尝试使用ensure_ascii=False






