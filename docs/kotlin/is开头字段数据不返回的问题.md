

## 问题

类



```kotlin
class IsLikeView:Serializable {

    var isLike:Int?=null
}
```



这个对象是有数据的，在配合spring boot使用的时候，这个返回使用的空的，原因是字段is开头导致的



## 解决办法



增加一个函数

```kotlin
fun getIsLike():Int?{
    return isLike
}
```

