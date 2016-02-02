#dig命令详解
[2016年1月30日]  

##前言
**dig**是一个非常有用的DNS查询工具，最近在学习[consul](http://consul.io)的时候，文档中提到了使用 dig命令查询consul注册的service，因此决定仔细研究一下这个命令。

##命令描述
**dig**命令用于查询DNS server, 它比已经废弃的nslookup命令更加灵活。命令格式如下:  

```
dig [@server] [options] [name] [type] [class] [query-options] 
```  

如果使用不带任何参数的dig命令，它将搜索root server, 标准参数如下：

> server  
> > 要查询的服务器。如果不提供这个参数，dig将会检查/etc/resolv.conf文件中所列的服务器列表,地址可以是 IP v4或者IP v6, 如果是hostname，dig也可以通过/etc/resolv.conf文件hostname得到IP地址。  
> 
> name
> > 要查询的域名  
> 
> type  
> > 查询类型，例如 A，ANY, MX, SIG等。

