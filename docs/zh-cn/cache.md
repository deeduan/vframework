# 缓存简介

缓存系统对于系统性能的提升有着非常重要的作用，现在流行的常用缓存有memcached,redis等。vframework默认使用`文件驱动`缓存并内置了3种缓存驱动支持,他们分别是:

* APC (需要php APC扩展支持)
* File (基于文件的缓存)
* Memcache

？vframework居然不支持redis?！！, 放心..这将会在之后的自定义缓存章节描述..如果你按捺不住想要一看究竟..`传送门`

## 缓存预定义接口

我们先来看一下缓存的上层抽象类接口..Cache_Abstract类，这个类定义了缓存实现类的必要行为:

* 构造函数
* **save** 保存缓存资料

```php
abstract public function save($id, $data, $expired = null);
```
* **load** 加载缓存资料

```php
abstract public function load($id);
```

* **remove** 移除指定key缓存资料

```php
abstract public function remove($id);
```

* **clean** 清空缓存资料

```php
abstract public function clean();
```

## APC缓存

APC可选php缓存,由APC扩展驱动,想查看更多细节,请访问: [PHP APC](https://www.php.net/manual/en/book.apc.php) 查看。不过APC缓存即将废弃并且不再被维护..
   
>Warning
    This extension is considered unmaintained and dead. However, the source code for this extension is still available within PECL GIT here: http://git.php.net/?p=pecl/caching/apc.git.

## 文件缓存

## memcache缓存

## 简单使用

由于vframework提供了组件化编程模式(面向接口编程),可以让你很方便的任意切换缓存实现,而不需要改动业务逻辑,这些..你只需要配置切换你的缓存驱动即可。下面是缓存系统的使用一些简单例子，示例使用Redis驱动缓存系统。

* 配置缓存驱动

* 加载缓存实例


## 其他参考

* psr缓存接口,推荐实现此接口

