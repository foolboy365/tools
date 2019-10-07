1、查看当前用户权限，是否符合要求
whoami /priv
如果开启SeImpersonate权限，juicypotato的参数可以使用-t t

如果开启SeAssignPrimaryToken权限，juicypotato的参数可以使用-t u

如果均开启，可以选择-t *

如果均未开启，那么无法提权


Juicy Potato的限制条件如下：

1、需要支持SeImpersonate或者SeAssignPrimaryToken权限
2、开启DCOM
3、本地支持RPC或者远程服务器支持PRC并能成功登录
4、能够找到可用的COM对象

参考：
https://3gstudent.github.io/3gstudent.github.io/Windows%E6%9C%AC%E5%9C%B0%E6%8F%90%E6%9D%83%E5%B7%A5%E5%85%B7Juicy-Potato%E6%B5%8B%E8%AF%95%E5%88%86%E6%9E%90/
https://www.chabug.org/tools/568.html