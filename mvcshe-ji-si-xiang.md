# MVC设计思想

MVC——M：mode（模型层） V：view（视图层） C：controller（控制层）

MVC实体对象是什么？其实答案都知道，只是不知道这个名词是什么意思，很简单答案就是JavaBean。

作用：业务逻辑更清晰，层次更分明

设计思想流程：view（视图层：jsp）——&gt;controller（控制层：Servlet）——&gt;DB（数据库）

创建页面（jsp）将页面的信息发送到后台（Servlet），在后台中控制处理，后台再将信息返回到数据库中。

暂时还没有用到模型层，模型层就是JavaBean。MVC实体对象就是JavaBean。

