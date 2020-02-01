# Django 管理后台

Django 提供的管理后台位于 `django.contrib.admin` 包中，它也是一个应用，由 Django 内置。

## 将 Model 注册到后台

要使用管理后台，需要做一些准备。

***settings.py***

在创建 Django 项目时，这些配置已经自动完成了。

Django 在启动时会根据 *settings.py* 中定义的 *INSTALLED_APPS* 加载应用，在创建项目时默认已经将 *django.contrib.admin* 加入了。除此，还自动加入了四个 Admin 依赖的应用：

* *django.contrib.auth*，用户与权限认证
* *django.contrib.contenttypes*，对 Model 提供更高层次抽象接口的应用，也是 auth 的依赖
* *django.contrib.session*，会话，用来保存用户状态
* *django.contrib.messages*，消息

除此，有些应用还要使用中间件，所以还自动在 *MIDDLEWARE* 中加入了需要的中间件：

* *django.contrib.sessions.middleware.SessionMiddleware*，支持会话的中间件
* *django.middleware.common.CommonMiddleware*，对 URL 执行重写的中间件
* *django.contrib.auth.middle.AuthenticationMiddleware*，验证用户身份的中间件
* *django.contrib.messages.middleware.MessageMiddleware*，支持消息的中间件

*TEMPLATES* 是关于模板的配置，为了使用 Admin，在 context_processors 中加入了

* *django.contrib.auth.context_processors.auth*，用来在模板中访问用户和权限的上下文处理器
* *django.contrib.messages.context_processors.messages*，用来支持消息的上下文处理器





 