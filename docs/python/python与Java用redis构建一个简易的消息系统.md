## 目的

使用一个轻量级类似mq的效果，py会产生一些计算结果，推送给Java那边，Java那边消费消息，然后执行一些具体操作







## python工作



```python
import redis

host = '127.0.0.1'
port = 6379
db = 1
password = ''
# 构建redis的一个实例
r = redis.Redis(host=host, port=port, db=db, password=password)

 
def pub_push(name, v):
    """
    发布消息到redis
    :param name:
    :param v:
    :return:
    """
    r.publish(name, v)
```





测试



```python
from util import  redisutil as ru
import json
obj = {}
obj['type'] = 'warn'
obj['content'] = 'good good eat'
ru.pub_push('test_mq',json.dumps(obj))
```







## Java工作



