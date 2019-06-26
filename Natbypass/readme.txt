

实例：
	本地笔记本连接的热点，开启了web服务。
	python -m SimpleHTTPServer

	公网机器（centos7）监听2个端口，1997和2017。1997端口为隧道连接用，2017为服务连接端口。
	./nb -listen 1997 2017
	本地（win10）
	nb.exe -slave 127.0.0.1:8000    47.98.*.*:1997

	连接成功后，访问47.98.*.*:2017，看到本地机器开启的web服务。


https://github.com/foolboy365/NATBypass
