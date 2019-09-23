### 1.Tomcat启动入口main函数的设计？
#### ①类的加载过程
#### ②Tomcat启动过程

### 一旦执行main函数是否就意味着启动了一个JVM进程

### 2.bootstrap.init()设计分析
#### ①设置环境变量：catalina.home、catalina.base
#### ②初始化类加载器：initClassLoader()
#### ③为当前线程设置类加载器
#### ④通过反射的方式加载启动类Catalina，并创建实例
#### ⑤设置共享扩展类加载器为父类加载器(此处不解???)
#### ⑥将启动类实例赋值给：catalinaDaemon

### 3.Tomcat类加载机制
#### ①基本概念：双亲委派原则、违背双亲委派原则
#### ②createClassLoader()之简单工厂设计模式

### 4.catalina.properties配置文件读取

### 5.线程上下文类加载器
#### ①默认为系统类加载器AppClassLoader
#### ②可据此抛弃双亲委派原则

### 6.通过反射加载类、创建实例、调用方法

### 1.①所做事情总结
#### ①启用Tomcat类加载机制
#### ②加载启动类Catalina
#### ③创建启动类实例：startupInstance

### 7.daemon.setAwait(true)意义分析

### 8.Digester解析xml配置文件

### 9.Tomcat启动流程分析

### 10.Tomcat架构图(server.xml)