**目录**

[TOC]

# $cache
是当前本地缓存服务对象，可以用来读写缓存数据

## $cache.write()
$cache.write()方法用来写缓存数据和缓存文件

**代码演示**
```javascript
$cache.write (key,value)//key为设置缓存的名字，value为设置的缓存内容
```

## $cache.read()
$cache.read()方法用来读取缓存数据内容

**代码演示**
```javascript
$cache.read(key)//key为读取缓存的名字，返回结果为缓存内容
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qCache">用例github下载地</a>
