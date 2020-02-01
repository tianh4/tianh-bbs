## 2.2 Model 的相关概念

### 2.2.1 Model 的组成部分

每个 Model 都是 Python 类，由四部分组成：

* 继承自 `django.db.model.Model`
* `Model` 元数据声明
* 若干个 `Field` 类型的字段
* `__str__` 方法

### 2.2.2 Model Meta

**abstract**

如果为 True，表示当前类是一个抽象基类。

**proxy**

如果为 True，表示为基类的代理模型。

**db_table**

指定数据表的名称。

**ordering**

获取对象列表时的排序规则，如 `ordering = ['created_time', '-last_modified']` 。

**managed**

默认为 True，表示由 Django 管理数据表的生命周期，如果设置为 False，

### 2.2.3 Model Field

### 2.2.4 Model 继承模型

Model 有 3 种继承模型，即抽象基类、多表继承和代理模型。

**抽象基类**

定义 Meta 内部类，将 abstract 设置为 True，就把当前 Model 定义为抽象基类了。

抽象基类不能被实例化，也没有数据表，没有 model manager。

可以在 Meta 中定义元数据，元数据的继承遵循：

* 子类没有定义，子类继承基类的元数据
* 子类也定义了，子类定义的优先级更高
* 子类可以增加新的元数据

