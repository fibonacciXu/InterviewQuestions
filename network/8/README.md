# 从输入URL到页面加载的全过程

1. 浏览器获取用户输入，等待 url 输入完毕，触发 enter 事件；
2. 解析 URL，分析协议头，再分析主机名是域名还是 IP 地址；
3. 如果主机名是域名的话，则发送一个 DNS 查询请求到 DNS 服务器，获得主机 IP 地址；
4. 使用 DNS 获取到主机 IP 地址后，向目的地址发送一个（http/https/protocol）请求，并且在网络套接字上自动添加端口信息（http 80 https 443）；
5. 等待服务器响应结果；
6. 将响应结果（html）经浏览器引擎解析后得到 `Render tree`，浏览器将 `Render tree` 进行渲染后显示在显示器中，用户此时可以看到页面被渲染。