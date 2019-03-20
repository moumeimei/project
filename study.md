# composer安装：
**1. composer中文网下载composer.exe**

**2. 查看php版本确定其路径，打开cmd 直接输出php报错,则php不是全局变量，可到电脑-->属性-->高级配置-->环境变量-->系统变量中找到path-->将php路径放入并以英文 ';'分割,保存，在cmd中直接输php，回车，不报错，则证明设置成功。**

**3. 安装composer;选择路径：例如“E:\phpStudy\PHPTutorial\php\php-7.0.12-nts\php.exe”；继续安装**

**4. 在cmd中输入composer回车，出现composer则安装成功。**

#composer安装thinkphp框架:
**1.第一次安装的话，在命令行执行：**
```
composer config -g repo.packagist composer https://packagist.laravel-china.org
```

**2.然后切换到www目录下，执行:**
```
composer create-project topthink/think tp5
```

**3.如果你之前已经安装过，那么切换到你的应用根目录下面，然后执行下面的命令进行更新：**
```
composer update topthink/framework
```

##路由：
**1.如果没有定义路由，则可以直接使用“模块/控制器/操作”的方式访问;如果强制开启路由，则必须通过定义的路由进行访问：**

```
//是否强制使用路由'url_route_must'         => false,
```
##操作：
1. 一个控制器包含多个操作（方法），操作方法是一个URL访问的最小单元。

##依赖注入
1. 依赖注入其实本质上是指对类的依赖通过构造器完成自动注入

####绑定类的实例:
1.直接绑定一个类的实例
```$xslt
    $cache = new think\Cache;
    // 绑定类实例
    bind('cache',$cache);
    // 快速调用类的实例
    $cache = app('cache');
```

####绑定至接口实现:
对于依赖注入使用接口类的情况，我们需要告诉系统使用哪个具体的接口实现类来进行注入，这个使用可以把某个类绑定到接口
```$xslt
    // 绑定think\LoggerInterface接口实现到think\Log
    bind('think\LoggerInterface','think\Log');
```


