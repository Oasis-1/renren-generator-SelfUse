版权属于[人人官方](https://www.renren.io/)，只是二次开发，自己留作备份

# 对于人人代码生成器的自定义【二次开发】

> 出处
>
> - Git仓库：https://gitee.com/renrenio/renren-generator
> - [人人开源](https://www.renren.io)：https://www.renren.io   
> - [人人开源社区](https://www.renren.io/community)：https://www.renren.io/community   

原版有些不好用的，自己看了些源码给他改了一部分（比如dao--->mapper，entity--->PO，删除了些官方的分页，crud）

其实最主要的是[这个](https://www.yuque.com/u29117801/idh7gu/wg7zwe)以后习惯中想全部都用`localDateTime`代替`date`然后改了一点，发现导包的路径也得改，导包的路径改了，其他的类名也顺便一起改了，后来就改完了

其实主要是为了表中几十个字段的时候，建实体类太体力劳动了

```java
package.moduleName
├── controller
├── ├── 表名Controller 
├── service
├── ├── I表名Service 
├── ├── impl
├── ├── ├── 表名ServiceImpl 
├── mapper
├── ├── 表名Mapper 
├── ├── xml
├── ├── ├── 表名Mapper.xml
├── entity
├── ├── 表名PO
```

后续有个点PO是否直接放到entity-->PO包-->PO类，现在碰到的项目一般在`entity-->PO包`之间都会有对应的模块名字，看情况要不要

## 使用方法

跟官方的差不多

1. `resources`-->`generator.properties`中改下包名，模块名

2. `resources`-->`application.yml`里面改下数据库

3. 启动。进入：http://localhost/即可

   tips：压缩包中复制这四个文件夹`controller`，`service`，`mapper`，`entity`。在java中这四个文件夹的上一级`Ctrl+V`可以直接把所有的文件都粘贴到对应的位置

   1. 还有一点默认是mysql的，其他数据库需要修改`DbConfig`具体参考[官方的教程](https://www.renren.io/guide#coder)

# 原文档内容

**项目说明** 

- renren-generator是人人开源项目的代码生成器，可在线生成entity、xml、dao、service、html、js、sql代码，减少70%以上的开发任务
<br>


**如何交流、反馈、参与贡献？** 
- Git仓库：https://gitee.com/renrenio/renren-generator
- [人人开源](https://www.renren.io)：https://www.renren.io   
- [人人开源社区](https://www.renren.io/community)：https://www.renren.io/community   
- 官方QQ群：324780204、145799952
- 技术讨论、二次开发等咨询、问题和建议，请移步到人人开源社区，我会在第一时间进行解答和回复
- 如需关注项目最新动态，请Watch、Star项目，同时也是对项目最好的支持
- 微信扫码并关注【人人开源】，获得项目最新动态及更新提醒<br>
![输入图片说明](http://cdn.renren.io/47c26201804031918312618.jpg "在这里输入图片标题")
<br>
<br>

 **本地部署**
- 通过git下载源码
- 修改application.yml，更新MySQL账号和密码、数据库名称
- Eclipse、IDEA运行RenrenApplication.java，则可启动项目
- 项目访问路径：http://localhost

**演示效果图：**
![输入图片说明](https://images.gitee.com/uploads/images/2018/0731/150920_761d8835_63154.jpeg "aa.jpg")